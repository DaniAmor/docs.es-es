---
title: "Cómo: Realizar una prueba de posicionamiento usando Geometry como parámetro"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b5c5bb47e3f435419bcf3c472f052260adec7c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a>Cómo: Realizar una prueba de posicionamiento usando Geometry como parámetro
Este ejemplo muestra cómo realizar una prueba de posicionamiento en un objeto visual mediante un <xref:System.Windows.Media.Geometry> como un impacto en el parámetro de la prueba.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo configurar una prueba de posicionamiento usando <xref:System.Windows.Media.GeometryHitTestParameters> para el <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> método. El <xref:System.Windows.Point> valor que se pasa a la `OnMouseDown` método se utiliza para crear un <xref:System.Windows.Media.Geometry> objeto con el fin de ampliar el intervalo de la prueba de posicionamiento.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 El <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> propiedad de <xref:System.Windows.Media.GeometryHitTestResult> proporciona información acerca de los resultados de una prueba de posicionamiento que utiliza un <xref:System.Windows.Media.Geometry> como un impacto en el parámetro de la prueba. La siguiente ilustración muestra la relación entre la geometría de la prueba de posicionamiento (círculo azul) y el contenido representado del objeto visual de destino (cuadrado rojo).  
  
 ![Diagrama de IntersectionDetail usado en la prueba de posicionamiento](../../../../docs/framework/wpf/graphics-multimedia/media/intersectiondetail01.png "IntersectionDetail01")  
Intersección entre la geometría de la prueba de posicionamiento y el objeto visual de destino  
  
 En el ejemplo siguiente se muestra cómo implementar una devolución de llamada de la prueba de posicionamiento cuando un <xref:System.Windows.Media.Geometry> se utiliza como un parámetro de la prueba de posicionamiento. El `result` parámetro se convierte en una <xref:System.Windows.Media.GeometryHitTestResult> con el fin de recuperar el valor de la <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> propiedad. El valor de propiedad le permite determinar si el <xref:System.Windows.Media.Geometry> parámetro de prueba de posicionamiento está total o parcialmente dentro del contenido representado de la prueba de posicionamiento de destino. En este caso, el código de ejemplo solo está agregando los resultados de la prueba de posicionamiento a la lista para elementos visuales que estén totalmente entro del límite de destino.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
>  El <xref:System.Windows.Media.HitTestResult> devolución de llamada no debe llamarse una vez el detalle de la intersección <xref:System.Windows.Media.IntersectionDetail.Empty>.  
  
## <a name="see-also"></a>Vea también  
 [Realizar pruebas de posicionamiento en la capa visual](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [Geometría de una prueba de posicionamiento en un objeto Visual](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-geometry-in-a-visual.md)
