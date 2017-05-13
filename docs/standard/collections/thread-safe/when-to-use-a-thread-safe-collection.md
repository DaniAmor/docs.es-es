---
title: "Cuándo usar una colección segura para subprocesos | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, when to upgrade
ms.assetid: a9babe97-e457-4ff3-b528-a1bc940d5320
caps.latest.revision: 9
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 87898a4a6ba3d3ef4c53fd1c6b8f94ff353f10e4
ms.lasthandoff: 04/18/2017

---
# <a name="when-to-use-a-thread-safe-collection"></a>Cuándo usar una colección segura para subprocesos
[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] presenta cinco nuevos tipos de colección que están especialmente diseñadas para admitir operaciones multiproceso de agregar y quitar. Para obtener seguridad para los subprocesos, estos nuevos tipos usan diversas clases de mecanismos de sincronización eficientes con bloqueo y sin bloqueo. La sincronización agrega sobrecarga a las operaciones. La cantidad de sobrecarga depende del tipo de sincronización que se use, el tipo de operaciones que se realicen y otros factores, como el número de subprocesos que intentan obtener acceso simultáneamente a la colección.  
  
 En algunos escenarios, la sobrecarga de la sincronización es insignificante y permite que el tipo multiproceso funcione mucho más rápido y aumente de tamaño mucho mejor que su equivalente no seguro para subprocesos cuando está protegido por un bloqueo externo. En otros escenarios, la sobrecarga puede hacer que el tipo seguro para subprocesos funcione y aumente de tamaño más o menos igual o incluso más lentamente que la versión del tipo no segura para subprocesos bloqueada externamente.  
  
 Las secciones siguientes proporcionan instrucciones generales acerca de cuándo usar una colección segura para subprocesos frente a su equivalente no seguro para subprocesos que tiene un bloqueo para la lectura y escritura proporcionado por el usuario. Dado que el rendimiento puede variar según muchos factores, las instrucciones no son específicas y tampoco son necesariamente válidas en todas las circunstancias. Si el rendimiento es muy importante, la mejor manera de determinar qué tipo de colección debe usar es medir el rendimiento en función de cargas y configuraciones de equipo representativas. Este documento usa los términos siguientes:  
  
 *Escenario puro de consumidor-productor*  
 Cualquier subproceso dado agrega o quita elementos, pero no realiza ambas operaciones.  
  
 *Escenario puro de consumidor-productor mixto*  
 Cualquier subproceso dado agrega y quita elementos.  
  
 *Aceleración*  
 Rendimiento algorítmico más rápido con respecto a otro tipo en el mismo escenario.  
  
 *Escalabilidad*  
 Aumento del rendimiento que es proporcional al número de núcleos del equipo. Un algoritmo que escala funciona más rápido con ocho núcleos que con dos núcleos.  
  
## <a name="concurrentqueuet-vs-queuet"></a>ConcurrentQueue(T) frente a Queue(T)  
 En escenarios productor-consumidor puros, cuando el tiempo de procesamiento de cada elemento es muy pequeño (pocas instrucciones), <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName> puede ofrecer modestas ventajas de rendimiento sobre <xref:System.Collections.Generic.Queue%601?displayProperty=fullName> con un bloqueo externo. En este escenario, <xref:System.Collections.Concurrent.ConcurrentQueue%601> funciona mejor cuando un subproceso dedicado se está poniendo en cola y un subproceso dedicado se está quitando de la cola. Si no se aplica esta regla, <xref:System.Collections.Generic.Queue%601> puede incluso realizarse un poco más rápido que <xref:System.Collections.Concurrent.ConcurrentQueue%601> en equipos con varios núcleos.  
  
 Cuando el tiempo de procesamiento es de unos 500 FLOPS (operaciones de punto flotante) o más, la regla de dos subprocesos no se aplica a <xref:System.Collections.Concurrent.ConcurrentQueue%601>, que en ese caso tiene muy buena escalabilidad. <xref:System.Collections.Generic.Queue%601> no escala bien en este escenario.  
  
 En escenarios mixtos de consumidor-productor, cuando el tiempo de procesamiento es muy pequeño, un <xref:System.Collections.Generic.Queue%601> que tiene un bloqueo externo escala mejor que <xref:System.Collections.Concurrent.ConcurrentQueue%601>. Sin embargo, cuando el tiempo de procesamiento es de unos 500 FLOPS o más, el elemento <xref:System.Collections.Concurrent.ConcurrentQueue%601> escala mejor.  
  
## <a name="concurrentstack-vs-stack"></a>ConcurrentStack frente a Pila  
 En escenarios productor-consumidor puros, cuando el tiempo de procesamiento es muy pequeño, <xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=fullName> y <xref:System.Collections.Generic.Stack%601?displayProperty=fullName> con un bloqueo externo probablemente funcionarán más o menos igual con un subproceso dedicado que se inserta y un subproceso dedicado que se extrae. Sin embargo, a medida que aumenta el número de subprocesos, ambos tipos se ralentizan debido a una mayor contención y <xref:System.Collections.Generic.Stack%601> puede funcionar mejor que <xref:System.Collections.Concurrent.ConcurrentStack%601>. Cuando el tiempo de procesamiento es de unos 500 FLOPS o más, ambos tipos escalan con una velocidad similar.  
  
 En escenarios de productor-consumidor mixtos, <xref:System.Collections.Concurrent.ConcurrentStack%601> es más rápido para cargas de trabajo grandes y pequeñas.  
  
 El uso de <xref:System.Collections.Concurrent.ConcurrentStack%601.PushRange%2A> y <xref:System.Collections.Concurrent.ConcurrentStack%601.TryPopRange%2A> puede acelerar considerablemente los tiempos de acceso.  
  
## <a name="concurrentdictionary-vs-dictionary"></a>ConcurrentDictionary frente a Dictionary  
 En general, use <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> en cualquier escenario en el que agregue y actualice claves o valores simultáneamente desde varios subprocesos. En escenarios que implican actualizaciones frecuentes y relativamente pocas lecturas, <xref:System.Collections.Concurrent.ConcurrentDictionary%602> suele ofrecer ventajas modestas. En escenarios que implican numerosas lecturas y actualizaciones, <xref:System.Collections.Concurrent.ConcurrentDictionary%602> suele ser considerablemente más rápido en equipos con cualquier número de núcleos.  
  
 En escenarios que implican actualizaciones frecuentes, puede aumentar el grado de simultaneidad en <xref:System.Collections.Concurrent.ConcurrentDictionary%602> y medir el rendimiento para ver si aumenta en equipos que tienen más núcleos. Si cambia el nivel de simultaneidad, evite las operaciones globales tanto como pueda.  
  
 Si solo va a leer claves o valores, <xref:System.Collections.Generic.Dictionary%602> es más rápido porque no se necesita ninguna sincronización cuando no hay ningún subproceso que modifique el diccionario.  
  
## <a name="concurrentbag"></a>ConcurrentBag  
 En escenarios productor-consumidor puros, <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName> probablemente será más lento que los otros tipos de colección simultánea.  
  
 En escenarios productor-consumidor mixtos, <xref:System.Collections.Concurrent.ConcurrentBag%601> es generalmente mucho más rápido y más escalable que cualquier otro tipo de colección simultánea para cargas de trabajo grandes y pequeñas.  
  
## <a name="blockingcollection"></a>BlockingCollection  
 Cuando se necesita una semántica de límite y bloqueo, <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> probablemente funcionará más rápido que cualquier implementación personalizada. Además, admite tareas avanzadas de cancelación, enumeración y control de excepciones.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Colecciones seguras para subprocesos](../../../../docs/standard/collections/thread-safe/index.md)   
 [Programación en paralelo](../../../../docs/standard/parallel-programming/index.md)