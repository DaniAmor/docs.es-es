---
title: "Operaciones de actualización, inserción y eliminación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 26a43a4f-83c9-4732-806d-bb23aad0ff6b
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 51af1dad545f6ac948b17d1bdbd39bfc688c7f11
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="insert-update-and-delete-operations"></a>Operaciones de actualización, inserción y eliminación
En `Insert`, las operaciones `Update`, `Delete` y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] se realizan agregando, cambiando y quitando objetos en el modelo de objetos. De forma predeterminada, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte estas acciones a SQL y envía los cambios a la base de datos.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]proporciona la máxima flexibilidad para manipular y conservar los cambios realizados en los objetos. En cuanto están disponibles los objetos entidad (ya sea recuperándolos a través de una consulta o construyéndolos nuevamente), puede cambiarlos como los objetos normales de la aplicación. Es decir, puede cambiar sus valores, puede agregarlos a las colecciones, y puede quitarlos de las colecciones. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] realiza un seguimiento de los cambios y está listo para volver a transmitirlos a la base de datos cuando llame al método <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite ni reconoce las operaciones de eliminación en cascada. Si desea eliminar una fila de una tabla que tiene restricciones, deberá establecer el `ON DELETE CASCADE` de regla en la restricción de clave externa de la base de datos o utilizar su propio código para eliminar primero los objetos secundarios que impiden que el objeto primario que se va a eliminar. De lo contrario, se inicia una excepción. Para obtener más información, consulte [Cómo: eliminar filas de la base de datos](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).  
  
 En los siguientes extractos se utilizan las clases `Customer` y `Order` de la base de datos de ejemplo Northwind. Para no extendernos demasiado, no incluimos las definiciones de clase.  
  
 [!code-csharp[DLinqCRUDOps#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCRUDOps/cs/Program.cs#1)]
 [!code-vb[DLinqCRUDOps#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCRUDOps/vb/Module1.vb#1)]  
  
 Al llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera y ejecuta automáticamente los comandos SQL necesarios para volver a transmitir los cambios a la base de datos.  
  
> [!NOTE]
>  Puede invalidar este comportamiento utilizando su propia lógica personalizada, normalmente mediante un procedimiento almacenado. Para obtener más información, consulte [las responsabilidades de los desarrolladores invalidar un comportamiento predeterminado](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md).  
>   
>  Los desarrolladores de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] pueden usar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para desarrollar procedimientos almacenados con este propósito.  
  
## <a name="see-also"></a>Vea también  
 [Descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [Personalización de operaciones de actualización, inserción y eliminación](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
