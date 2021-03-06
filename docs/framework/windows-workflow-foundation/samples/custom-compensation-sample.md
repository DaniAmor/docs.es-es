---
title: "Ejemplo de compensación personalizada"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 385920da-9284-44bf-9fe9-0d87c7478ec5
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2bc76267cf4b3fe5f4e792ee185733e51185872f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="custom-compensation-sample"></a>Ejemplo de compensación personalizada
En este ejemplo se muestra cómo utilizar <xref:System.Activities.Statements.CompensableActivity> y su controlador de compensación para definir lógica de compensación personalizada. El escenario modelado en este ejemplo es una agencia de alquiler de camiones.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 Los pasos simulados son:  
  
1.  El usuario solicita ofertas de alquiler de camiones para una fecha determinada.  
  
2.  Se establece contacto con tres empresas de camiones y se proporcionan tres ofertas.  
  
3.  El usuario selecciona una oferta de camión y realiza el pedido con tarjeta de crédito.  
  
4.  La aplicación cancela las otras dos ofertas de camión.  
  
5.  La aplicación carga una cuota de servicio que no se puede reembolsar en las cuentas no bonificadas si se produce una cancelación en un periodo inferior a 10 días antes de la fecha de reserva.  
  
6.  La aplicación carga la cuota de alquiler del camión.  
  
7.  La aplicación espera hasta la fecha de la reserva o hasta que el cliente decida cancelar la reserva, lo que suceda primero.  
  
8.  Si el cliente cancela la reserva, se ejecuta la lógica de compensación personalizada de <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> según la siguiente lógica:  
  
    1.  Si el cliente tiene una cuenta no bonificada y faltan menos de 10 días para la fecha de reserva, se sigue cobrando la cuota de servicio; en caso contrario, la aplicación reembolsa la cuota de servicio.  
  
    2.  El resto de las actividades compensables (el pedido de camión + la cuota de pedido de camión) se ejecutan según la lógica de compensación predeterminada, que compensa en orden inverso a la ejecución.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Abra el archivo de solución CustomCompensation.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]. Se encuentra en el directorio \WF\Basic\Compensation\CustomCompensation.  
  
2.  Presione Ctrl+MAYÚS+B para compilar la solución.  
  
3.  Presione CTRL+F5 para ejecutar la aplicación.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CustomCompensation`