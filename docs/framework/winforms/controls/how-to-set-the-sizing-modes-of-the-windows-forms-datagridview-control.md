---
title: "Cómo: Establecer modos de cambio de tamaño para el control DataGridView de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], setting sizing modes
- DataGridView control [Windows Forms], sizing modes
ms.assetid: e9ad15e6-b4bb-44aa-a767-3738e9db1651
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3ae9cfe338e4e9c9ecc4a1fba67164ffc4af5307
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control"></a>Cómo: Establecer modos de cambio de tamaño para el control DataGridView de formularios Windows Forms
Los procedimientos siguientes muestran algunos escenarios comunes que personalizan o combinan las opciones de ajuste de tamaño disponibles para el control <xref:System.Windows.Forms.DataGridView> control y para las columnas específicas de un control.  
  
### <a name="to-create-a-fixed-width-column"></a>Para crear una columna de ancho fijo  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> en <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None>, la propiedad <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> en <xref:System.Windows.Forms.DataGridViewTriState.False>, la propiedad <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> en `true` y la propiedad <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> en un valor adecuado.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#10)]  
  
### <a name="to-create-a-column-that-adjusts-its-size-to-fit-its-content"></a>Para crear una columna que ajuste su tamaño al contenido  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> en un modo de ajuste de tamaño basado en el contenido.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#20)]  
  
### <a name="to-create-fill-mode-columns-for-values-of-varying-size-and-importance"></a>Para crear columnas en modo de relleno para valores de tamaño e importancia variable  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType> en <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill> para establecer el modo de ajuste de tamaño de todas las columnas que no invaliden este valor. Establezca las propiedades <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> de las columnas en valores que sean proporcionales al ancho promedio de su contenido. Establezca las propiedades <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> de las columnas importantes para garantizar la visualización parcial del contenido.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#30)]  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código completo proporciona una aplicación de demostración que puede ayudarle a entender las opciones de ajuste de tamaño descritas en este tema.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#00)]  
  
 Para usar esta aplicación de demostración:  
  
-   Cambie el tamaño del formulario. Observe cómo las columnas en modo de relleno cambian el ancho conservando las proporciones indicadas por los valores de la propiedad <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>. Observe cómo el <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> de una columna evita que cambie cuando el formulario es demasiado pequeño.  
  
-   Cambie el tamaño de las columnas arrastrando los divisores de columna con el mouse. Observe cómo algunas columnas no pueden cambiar de tamaño y cómo las columnas que pueden cambiar de tamaño no se pueden hacer más estrechas que el ancho mínimo.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System y System.Windows.Forms.  
  
 Para información sobre cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilación desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Compilar desde la línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>  
 <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A?displayProperty=nameWithType>
