---
title: "Envío y control de errores"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98e8e04d-2ac9-4a33-ae08-462f757a7a14
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc91b431123ff8776910550151a7783b2690d383
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="sending-and-handling-faults"></a>Envío y control de errores
En este ejemplo se muestra cómo utilizar las actividades de mensajería <xref:System.ServiceModel.Activities.SendReply> y <xref:System.ServiceModel.Activities.ReceiveReply> para enviar y recibir errores esperados e inesperados. En este escenario, la primera solicitud de cliente genera un error esperado que se ha incluido en su colección <xref:System.ServiceModel.Activities.Send.KnownTypes%2A>. Las siguientes solicitudes de cliente producen la recepción de errores inesperados, antes de que la solicitud final se realice correctamente.  
  
## <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con permisos elevados, haciendo clic en el [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icono y seleccione **ejecutar como administrador**.  
  
2.  Abra el archivo de solución Faults.sln.  
  
3.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
4.  Ejecute el proyecto de servicio.  
  
    1.  En **el Explorador de soluciones**, haga clic en el `FaultService` de proyecto y seleccione **establecer como proyecto de inicio**.  
  
    2.  Presione CTRL+F5.  
  
5.  Abra otra copia de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con permisos elevados, haciendo clic en el [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icono y seleccione **ejecutar como administrador**.  
  
6.  Abra el archivo de solución Faults.sln.  
  
7.  Ejecute el proyecto de cliente.  
  
    1.  En **el Explorador de soluciones**, haga clic en el `FaultClient` de proyecto y seleccione **establecer como proyecto de inicio**.  
  
    2.  Presione CTRL+F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Faults`