---
title: "Esquema de la configuración de red"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- elements [.NET Framework], network configuration elements
- sending data, network configuration elements
- receiving data, network configuration elements
- configuration settings [.NET Framework], networks
- Internet, network configuration elements
- network configuration elements
- network settings
- connections [.NET Framework], network configuration elements
- network resources, network configuration elements
ms.assetid: f1de5a0f-76c5-4833-819f-5222b8146340
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d8f13b75d0558c002fd29938ce98d85f358acc9a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="network-settings-schema"></a>Esquema de la configuración de red
La configuración de red especifica cómo se conecta .NET Framework a Internet. En la tabla siguiente se describe la función de cada elemento de configuración secundario bajo el [elemento \<system.Net> (configuración de red)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md).  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[Elemento \<authenticationModules> (configuración de red)](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|Especifica los módulos usados para autenticar solicitudes de Internet.|  
|[Elemento \<connectionManagement> (configuración de red)](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Especifica el número máximo de conexiones a hosts de Internet.|  
|[Elemento \<defaultProxy> (configuración de red)](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Especifica el servidor proxy usado para las solicitudes HTTP a Internet.|  
|[Elemento \<mailSettings> (configuración de red)](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|Contiene la configuración de opciones de envío de correo.|  
|[Elemento \<requestCaching> (configuración de red)](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Especifica los módulos usados para solicitar información de hosts de Internet.|  
|[Elemento \<requestCaching> (configuración de red)](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Configura opciones de red básicas para el espacio de nombres <xref:System.Net?displayProperty=nameWithType>.|  
|[Elemento \<webRequestModules> (configuración de red)](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Especifica los módulos usados para solicitar información de hosts de Internet.|  
  
 La configuración de URI especifica la manera en que .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI). En la tabla siguiente se describe la función de cada elemento de configuración secundario bajo el [elemento \<Uri> (configuración de URI)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md).  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[Elemento \<idn> (Configuración de URI)](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|Especifica si se aplica el análisis de nombres de dominio internacionalizados (IDN) a los nombres de dominio.|  
|[Elemento \<iriParsing> (Configuración de URI)](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|Especifica si se aplica el análisis de identificadores de recursos internacionales (IRI) a un <xref:System.Uri> y si se deben aplicar reglas de análisis de IRI.|  
|[Elemento \<schemeSettings> (configuración de URI)](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.|  
  
## <a name="see-also"></a>Vea también  
 [Configuración de aplicaciones de Internet](../../../../../docs/framework/network-programming/configuring-internet-applications.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
