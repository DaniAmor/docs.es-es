---
title: Configurar la traza de flujo de mensajes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 15571ca2-bee2-47fb-ba10-fcbc09152ad0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8df32a64c07db8a45dfb41a46e7a65a92fbef434
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="configuring-message-flow-tracing"></a>Configurar la traza de flujo de mensajes
Cuando la traza de actividad de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] está habilitada, los identificadores de actividad de un extremo a otro se asignan a las actividades lógicas a lo largo de la pila de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]. En [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)], hay ahora una versión con un rendimiento más alto de esta característica que funciona con Seguimiento de eventos para Windows (ETW) denominada traza de flujo de mensajes. Cuando se habilita, los identificadores de actividad de un extremo a otro se toman (o se asignan si están vacíos) de los mensajes entrantes y se propagan a todos los eventos de traza que se emiten una vez que el canal ha descodificado el mensaje. Los clientes pueden utilizar esta característica para reconstruir flujos de mensajes con registros de seguimiento de distintos servicios tras la descodificación.  
  
 Se puede habilitar la traza al detectar un problema con la aplicación y, a continuación, deshabilitarla una vez resuelto el problema.  
  
## <a name="enabling-tracing"></a>Habilitar el seguimiento  
 Puede habilitar la traza del flujo de mensajes estableciendo el elemento de configuración `messageFlowTracing` de .NET Framework 4 como `true`, tal y como se muestra en el siguiente ejemplo.  
  
```xml  
<system.servicemodel>  
  <diagnostics>  
    <endToEndTracing propagateActivity="true" messageFlowTracing="true" />  
  </diagnostics>  
</system.servicemodel>  
```  
  
> [!NOTE]
>  Dado que el elemento de configuración `endToEndTracing` reside en un archivo Web.config, no se puede configurar dinámicamente de la misma manera que ETW. Para que el elemento de configuración `endToEndTracing` surta efecto, hay que reciclar la aplicación.  
  
 Las actividades se correlacionan mediante el intercambio de un identificador denominado de actividad. Este identificador es un GUID y lo genera la clase System.Diagnostics.CorrelationManager. Si manipula el System.Diagnostics.Trace.CorrelationManager.ActivityID, asegúrese de que el valor se establece en el valor original cuando el control de la ejecución se vuelve a transferir al código WCF.  Además, si usa un modelo de programación WCF asincrónico, se asegura de que el System.Diagnostics.Trace.CorrelationManager.ActivityID se transfiere entre los subprocesos.  
  
## <a name="message-flow-tracing-and-rest-services"></a>Seguimiento de flujo de mensajes y servicios REST  
 El seguimiento de flujo de mensajes permite realizar un seguimiento a una solicitud extremo a extremo.  Con servicios basados en SOAP- se envía un Id. de actividad en un encabezado de mensaje SOAP. Las solicitudes REST no contienen este encabezado, por ello se usa un encabezado especial de eventos HTTP en su lugar. El fragmento de código siguiente muestra cómo se puede recuperar mediante programación el valor de Id. de actividad:  
  
```csharp
Object output = null;
if (OperationContext.Current.IncomingMessageProperties.TryGetValue(HttpRequestMessageProperty.Name, out output))
{
   HttpRequestMessageProperty httpHeaders = output as HttpRequestMessageProperty;
   // Retrieve the Activity Id from the HTTP header    string e2eId = httpHeaders.Headers["E2EActivity"];
   // ...
}
```

 Puede agregar el encabezado mediante programación usando el código siguiente:  
  
```csharp  
HttpContent content = new StreamContent(contentStream);  
Guid correlation = Guid.NewGuid();  
content.Headers.Add("E2EActivity", Convert.ToBase64String(correlation.ToByteArray()));  
```
