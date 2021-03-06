---
title: "Cómo: Crear y utilizar un objeto GridLengthConverter"
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
helpviewer_keywords: Grid control [WPF], creating [WPF], GridLengthConverter objects
ms.assetid: 5ab75911-e36a-4825-80e4-081c57e8e182
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 300916ec102682e1d886d43fbe70eeaf088d6454
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-and-use-a-gridlengthconverter-object"></a>Cómo: Crear y utilizar un objeto GridLengthConverter
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo crear y usar una instancia de <xref:System.Windows.GridLengthConverter>. En el ejemplo se define un método personalizado denominado `changeCol`, que pasa la <xref:System.Windows.Controls.ListBoxItem> a una <xref:System.Windows.GridLengthConverter> que convierte el <xref:System.Windows.Controls.ContentControl.Content%2A> de un <xref:System.Windows.Controls.ListBoxItem> a una instancia de <xref:System.Windows.GridLength>. El valor convertido, a continuación, se pasa como el valor de la <xref:System.Windows.Controls.ColumnDefinition.Width%2A> propiedad de la <xref:System.Windows.Controls.ColumnDefinition> elemento.  
  
 El ejemplo también define un segundo método personalizado, denominado `changeColVal`. Este método personalizado convierte la <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> de un <xref:System.Windows.Controls.Slider> a una <xref:System.String> y, a continuación, pasa ese valor para la <xref:System.Windows.Controls.ColumnDefinition> como el <xref:System.Windows.Controls.ColumnDefinition.Width%2A> del elemento.  
  
 Tenga en cuenta que otro [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo define el contenido de un <xref:System.Windows.Controls.ListBoxItem>.  
  
 [!code-csharp[gridlengthConverterGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridlengthConverterGrid/CSharp/Window1.xaml.cs#1)]
 [!code-vb[gridlengthConverterGrid#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridlengthConverterGrid/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.GridLengthConverter>  
 <xref:System.Windows.GridLength>
