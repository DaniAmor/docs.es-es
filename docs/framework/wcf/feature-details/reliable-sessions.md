---
title: Sesiones de confianza
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 16480996b96145873b1d1f84d56af6d1aa863710
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="reliable-sessions"></a>Sesiones de confianza

Esta sección describe un [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] sesión confiable es, lo que se usa, cómo y cuándo usar uno, qué configuraciones de enlace admiten e indicaciones sobre procedimientos recomendados. La siguiente tabla resume los detalles sobre los puntos esenciales y temas relacionados de esta sección.

La sesión confiable [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona funciones de asegurarse de que los mensajes enviados entre extremos se transfieren a través de intermediarios de transporte o SOAP y se entregan una sola vez y, opcionalmente, en el mismo orden en que se enviaron.

Para utilizar una sesión confiable con una aplicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], utilice uno de los enlaces proporcionados por el sistema en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que admiten una sesión confiable de forma predeterminada u opcional, o cree su propio enlace personalizado que admita la sesión.

## <a name="in-this-section"></a>En esta sección

[Información general de las sesiones confiables](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)   
Describe las sesiones confiables, cuándo utilizarlas, los diferentes enlaces que admiten las sesiones confiables y cómo funcionan.

[Cómo: intercambiar mensajes dentro de una sesión confiable](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)   
Describe cómo crear una sesión confiable sobre HTTP utilizando un enlace personalizado especificado en la configuración.

[Cómo: proteger los mensajes dentro de las sesiones confiables](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md)   
Describe cómo proteger una sesión confiable.

[Cómo: crear un enlace personalizado de sesión confiable con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)   
Describe cómo crear una sesión confiable sobre HTTPS.

[Prácticas recomendadas para las sesiones confiables](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md)   
Describe algunos de los procedimientos recomendados asociados al uso de una sesión confiable.

## <a name="reference"></a>Referencia

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a>Vea también

[Las colas y sesiones confiables](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)   
[Sesiones, creación de instancias y simultaneidad](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
