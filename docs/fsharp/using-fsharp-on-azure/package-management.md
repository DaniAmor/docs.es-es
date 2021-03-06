---
title: "Uso de administración de paquetes con F # para Azure"
description: 'Usar Paket o Nuget para administrar las dependencias de Azure de F #'
keywords: "Visual f #, f #, funcional de programación,. NET, .NET Core, Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: dd32ef9c-5416-467e-9fa3-c9ee3bb08456
ms.openlocfilehash: 22dc94ea69e0dfb95e22da4bc64ce915398190d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="package-management-for-f-azure-dependencies"></a>Administración de paquetes para las dependencias de Azure de F #

Obtención de paquetes para el desarrollo de Azure es fácil cuando se usa un administrador de paquetes. Las dos opciones son [Paket](https://fsprojects.github.io/Paket/) y [NuGet](https://www.nuget.org/).

## <a name="using-paket"></a>Usar Paket

Si usas [Paket](https://fsprojects.github.io/Paket/) como el Administrador de la dependencia, puede utilizar el `paket.exe` herramienta para agregar dependencias de Azure. Por ejemplo:

    > paket add nuget WindowsAzure.Storage

O bien, si usa [Mono](http://www.mono-project.com/) para el desarrollo de .NET de multiplataforma:

    > mono paket.exe add nuget WindowsAzure.Storage

Esto agregará `WindowsAzure.Storage` para el conjunto de dependencias de paquete para el proyecto en el directorio actual, modifique la `paket.dependencies` de archivos y descargar el paquete. Si se ha establecido previamente las dependencias o está trabajando con un proyecto que se han configurado las dependencias con otros desarrolladores, puede resolver e instalar las dependencias de forma local como el siguiente:

    > paket install

O bien, para el desarrollo de Mono:

    > mono paket.exe install

Puede actualizar todas las dependencias de paquete a la versión más reciente similar al siguiente:

    > paket update

O bien, para el desarrollo de Mono:

    > mono paket.exe update

## <a name="using-nuget"></a>Uso de Nuget

Si usas [NuGet](https://www.nuget.org/) como el Administrador de la dependencia, puede utilizar el `nuget.exe` herramienta para agregar dependencias de Azure. Por ejemplo:

    > nuget install WindowsAzure.Storage -ExcludeVersion

O bien, para el desarrollo de Mono:

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

Esto agregará `WindowsAzure.Storage` al conjunto de dependencias del paquete para el proyecto en el directorio actual y descargue el paquete. Si se ha establecido previamente las dependencias o está trabajando con un proyecto que se han configurado las dependencias con otros desarrolladores, puede resolver e instalar las dependencias de forma local como el siguiente:

    > nuget restore 

O bien, para el desarrollo de Mono:

    > mono nuget.exe restore

Puede actualizar todas las dependencias de paquete a la versión más reciente similar al siguiente:

    > nuget update

O bien, para el desarrollo de Mono:

    > mono nuget.exe update

## <a name="referencing-assemblies"></a>Referencia a ensamblados

Para utilizar los paquetes en el script de F #, tiene que hacer referencia a los ensamblados incluidos en los paquetes mediante un `#r` directiva. Por ejemplo:

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

Como puede ver, debe especificar la ruta de acceso relativa del archivo DLL y el nombre completo de DLL, que puede no ser exactamente el mismo que el nombre del paquete. La ruta de acceso incluye una versión de framework y, posiblemente, un número de versión del paquete. Para buscar todos los ensamblados instalados, puede usar algo parecido a esto en una línea de comandos de Windows:

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

O bien, en un shell de Unix, algo similar a éste:

    > find packages/WindowsAzure.Storage -name "*.dll"

Esto le proporcionará las rutas de acceso a los ensamblados instalados. Desde allí, puede seleccionar la ruta de acceso correcta para su versión de framework.
