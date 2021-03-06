---
title: "&lt;configuración&gt; elemento"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
caps.latest.revision: "15"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 3874a613879d099ede4968b5bce349aefa015a38
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="configuration-element"></a>\<Configuración > elemento

Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.

**\<configuration>**

## <a name="syntax"></a>Sintaxis

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a>Atributos

Ninguna

## <a name="parent-element"></a>Elemento primario

Ninguna

## <a name="child-elements"></a>Elementos secundarios

|     | Descripción |
| --- | ----------- |
| [**\<assemblyBinding >**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | Especifica la directiva de enlace del ensamblado en el nivel de configuración.|
| [**\<Inicio >** esquema de configuración](~/docs/framework/configure-apps/file-schema/startup/index.md) | Todos los elementos en el esquema de configuración de inicio. |
| [**\<en tiempo de ejecución >** esquema de configuración](~/docs/framework/configure-apps/file-schema/runtime/index.md) | Todos los elementos en el esquema de configuración en tiempo de ejecución. |
| [**\<System.Runtime.Remoting >** esquema de configuración](http://msdn.microsoft.com/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e) | Todos los elementos en el esquema de configuración de comunicación remota. |
| [**\<system.Net >** esquema de configuración](~/docs/framework/configure-apps/file-schema/network/index.md) | Todos los elementos en el esquema de configuración de red. |
| [**\<cryptographySettings >** esquema de configuración](~/docs/framework/configure-apps/file-schema/cryptography/index.md) | Todos los elementos en el esquema de configuración de criptografía. |
| [**\<Configuración >** esquema de secciones](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) | Todos los elementos en el esquema de configuración de la sección de configuración. |
| [Esquema de la configuración de seguimiento y depuración](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) | Todos los elementos en el esquema de configuración de seguimiento y depuración. |
| [Esquema de configuración de configuración de ASP.NET](https://msdn.microsoft.com/library/b5ysx397(v=vs.100).aspx) | Todos los elementos en el esquema de configuración de ASP.NET, que incluye elementos para configurar aplicaciones y sitios Web de ASP.NET. Usar en *Web.config* archivos. |
| [**\<webServices >** esquema de configuración](http://msdn.microsoft.com/f84d6d55-1add-4eb7-ae46-33df5833ea2e) | Todos los elementos en el esquema de configuración de servicios Web. |
| [Esquema de configuración web](~/docs/framework/configure-apps/file-schema/web/index.md) | Describe todos los elementos del esquema de configuración web, que incluye elementos para configurar cómo funciona ASP.NET con una aplicación host como IIS. Usar en *aspnet.config* archivos. |

## <a name="remarks"></a>Comentarios

Cada archivo de configuración debe contener exactamente un  **\<configuración >** elemento.

## <a name="see-also"></a>Vea también

[Esquema de archivos de configuración de .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
