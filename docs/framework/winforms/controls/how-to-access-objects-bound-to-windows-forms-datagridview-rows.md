---
title: "Cómo: Obtener acceso a objetos enlazados a filas DataGridView de formularios Windows Forms"
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
- object binding [Windows Forms], accessing bound objects
- data grids [Windows Forms], accessing bound objects
- DataGridView control [Windows Forms], accessing objects bound to rows
ms.assetid: 0e05748f-4403-4eb8-8b2f-b098108181b5
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 66db5f6ff7b964162f77317f17a9e3a8d3ed22b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-access-objects-bound-to-windows-forms-datagridview-rows"></a>Cómo: Obtener acceso a objetos enlazados a filas DataGridView de formularios Windows Forms
A veces resulta útil mostrar una tabla de información almacenada en una colección de objetos comerciales. Al enlazar un control <xref:System.Windows.Forms.DataGridView> a este tipo de colección, cada propiedad pública se muestra en su propia columna a menos que la propiedad se haya marcado como no examinable con un <xref:System.ComponentModel.BrowsableAttribute>. Por ejemplo, una colección de objetos `Customer` tendría columnas como **Nombre** y **Dirección**.  
  
 Si estos objetos contienen información adicional y código al que quiere acceder, puede llegar a él a través de los objetos de fila. En el siguiente ejemplo de código, los usuarios pueden seleccionar varias filas y hacer clic en un botón para enviar una factura a cada uno de los clientes correspondientes.  
  
### <a name="to-access-row-bound-objects"></a>Para acceder a objetos enlazados a fila  
  
-   Utilice la propiedad <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#10)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código completo incluye una implementación sencilla `Customer` y enlaza la <xref:System.Windows.Forms.DataGridView> a una <xref:System.Collections.ArrayList> que contiene algunos objetos `Customer`. El controlador de eventos <xref:System.Windows.Forms.Control.Click> del <xref:System.Windows.Forms.Button?displayProperty=nameWithType> debe acceder a los objetos `Customer` a través de las filas porque la colección del cliente no es accesible fuera del controlador de eventos <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType>.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System y System.Windows.Forms.  
  
 Para información sobre cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilación desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Compilar desde la línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType>  
 [Mostrar datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Cómo: Enlazar objetos a controles DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-objects-to-windows-forms-datagridview-controls.md)
