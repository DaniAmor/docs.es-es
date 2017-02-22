---
title: "Arquitectura de las herramientas de la línea de comandos de .NET Core Tools RC4 | Microsoft Docs"
description: RC4 plantea ciertos cambios en la forma en que las herramientas generales de .NET Core se superponen.
keywords: CLI, extensibilidad, comandos personalizados, .NET Core
author: blackdwarf
ms.date: 11/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 7fff0f61-ac23-42f0-9661-72a7240a4456
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 305d046c698ca9f7ebb5ac56387cfef00145393e

---

# <a name="high-level-overview-of-changes-in-cli-rc4"></a>Introducción de alto nivel de cambios en la CLI RC4

[!INCLUDE[preview-warning](../../../includes/warning.md)]

En este documento se describen los cambios de alto nivel que supone el paso de `project.json` a MSBuild y el sistema de proyecto `csproj`. Se analiza la nueva manera en que se superponen todas las herramientas y qué nuevas partes están disponibles y cuál es su lugar en el panorama general. Después de leer este artículo, debería tener una mejor comprensión de todas las partes que constituyen las herramientas de .NET Core tras el paso a MSBuild y `csproj`. 

## <a name="moving-away-from-projectjson"></a>Abandono de project.json
El cambio más importante en las herramientas RC4 para .NET Core es ciertamente el [abandono de project.json en favor de csproj](https://blogs.msdn.microsoft.com/dotnet/2016/05/23/changes-to-project-json/) como sistema de proyectos. La versión RC4 de las herramientas de línea de comandos es la primera versión de las herramientas de línea de comandos de .NET Core que no contiene ninguna compatibilidad con project.json. Esto significa que no puede utilizarse para compilar, ejecutar o publicar bibliotecas y aplicaciones basadas en project.json. Para poder utilizar esta versión de las herramientas, debe migrar los proyectos existentes o iniciar otros nuevos. 

Como parte de este proceso, el motor de compilación personalizado que se desarrolló para compilar proyectos de project.json se ha reemplazado por un motor de compilación maduro y totalmente compatible llamado [MSBuild](https://github.com/Microsoft/msbuild). MSBuild es un motor conocido en la comunidad. NET, ya que ha sido una tecnología clave desde el primer lanzamiento de la plataforma. Por supuesto, como debe compilar aplicaciones .NET Core, MSBuild se ha trasladado a .NET Core y puede utilizarse en cualquier plataforma donde se ejecute .NET Core. Una de las promesas principales de .NET Core es una pila de desarrollo multiplataforma, y nos hemos asegurado de que esta transición no rompa esa promesa.

> [!NOTE]
> Si no está familiarizado con MSBuild y quiere aprender más al respecto, puede empezar por leer el artículo [Conceptos de MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-concepts). 

## <a name="the-tooling-layers"></a>Las capas de herramientas
Cuando nos alejamos del sistema de proyecto existente y pensamos en la compilación de modificadores del motor, la pregunta que surge de manera natural es: ¿cambiarán algunos de estos cambios la "disposición en capas" general del ecosistema completo de herramientas de .NET Core? ¿Hay nuevos bits y componentes?

Comencemos con un repaso rápido de la disposición en capas de Preview 2, como se muestra en la siguiente imagen:

![Arquitectura de alto nivel de herramientas de Preview 2](media/p2-arch.png)

La disposición en capas de las herramientas es bastante sencilla. En la parte inferior, tenemos como base las herramientas de línea de comandos de .NET Core. Todas las demás herramientas de nivel más alto, como Visual Studio o VS Code, dependen de la CLI para compilar proyectos, restaurar dependencias, etc. Esto significa que si, por ejemplo, se quisiera realizar una operación de restauración con Visual Studio, se llamaría al comando `dotnet restore` de la CLI. 

Con el paso al nuevo sistema de proyecto, el diagrama anterior cambia: 

![Arquitectura de alto nivel de herramientas RC4](media/p3-arch.png)

La principal diferencia es que la CLI ya no es la base; este papel es ocupado ahora por el "componente de SDK compartido". Este componente de SDK compartido es un conjunto de destinos y tareas asociadas que son responsables de compilar el código y publicarlo, de empaquetar paquetes de NuGet, etc. El propio SDK es código abierto y está disponible en GitHub en el [repositorio de SDK](https://github.com/dotnet/sdk). 

> [!NOTE]
> Un "destino" es un término de MSBuild que indica una operación con nombre que puede invocar MSBuild. Normalmente está unido a una o varias tareas que ejecutan alguna lógica que se supone que debe hacer el destino. MSBuild admite michos destinos predefinidos, como `Copy` o `Execute`; también permite a los usuarios escribir sus propias tareas mediante código administrado y definir destinos para ejecutar esas tareas. Para obtener más información, consulte [Tareas de MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-tasks). 

Todos los conjuntos de herramientas consumen ahora el componente de SDK compartido y sus destinos, incluida la CLI. Por ejemplo, la siguiente versión de Visual Studio no llamará al comando `dotnet restore` para restaurar las dependencias para proyectos de .NET Core, sino que usará directamente el destino "Restore". Como son destinos de MSBuild, también puede usar MSBuild sin procesar para ejecutarlos mediante el comando [dotnet msbuild](dotnet-msbuild.md). 

### <a name="rc4-cli-commands"></a>Comando de la CLI RC4
El componente de SDK compartido implica que la mayoría de los comandos de la CLI existentes se han vuelto a implementar como tareas y destinos de MSBuild. ¿Qué significa esto para los comandos de la CLI y el uso del conjunto de herramientas? 

Desde una perspectiva del uso, no cambia la forma de usar la CLI. La CLI sigue teniendo los comandos principales que existen en la versión Preview 2:

* `new`
* `restore`
* `run` 
* `build`
* `publish`
* `test`
* `pack` 

Estos comandos todavía hacen lo que se espera que hagan (crear un nuevo proyecto, compilarlo, publicarlo, empaquetarlo, etc.). La mayoría de las opciones no varían y siguen ahí. Puede consultar las pantallas de ayuda de los comandos (mediante `dotent <command> --help`) o la documentación de RC4 de este sitio para familiarizarse con los cambios. 

Desde una perspectiva de la ejecución, los comandos de la CLI tomarán sus parámetros y construirán una llamada a MSBuild "sin procesar" que establecerá las propiedades necesarias y ejecutará el destino deseado. Para ilustrar mejor esto, considere el siguiente comando: 

    `dotnet publish -o pub -c Release`
    
Este comando está publicando una aplicación en una carpeta `pub` mediante la configuración de "Release". Internamente, este comando se traduce en la siguiente invocación de MSBuild: 

    `dotnet msbuild /t:Publish /p:OutputPath=pub /p:Configuration=Release`

La excepción importante a esta regla son los comandos `new` y `run`, dado que no se han implementado como destinos de MSBuild. 

## <a name="conclusion"></a>Conclusión 
Este documento es una descripción de alto nivel de los cambios que se están produciendo en la arquitectura y el funcionamiento de las herramientas de la CLI a nivel global que se incluyen con RC4. Se ha presentado la noción de componente de SDK compartido; también se ha explicado cómo funcionan los comandos de la CLI, desde una perspectiva técnica, en RC4.


<!--HONumber=Feb17_HO2-->

