---
title: "Implementación de IEnumerable en Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 45b4008f0bf3ae0f303aa029e7bff5b82ab6f259
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>Tutorial: Implementar IEnumerable(Of T) en Visual Basic
El <xref:System.Collections.Generic.IEnumerable%601> interfaz está implementada por clases que pueden devolver una secuencia de valores uno a la vez. La ventaja de devolver datos de un elemento a la vez es que no tiene que cargar el conjunto completo de datos en la memoria para trabajar con ella. Solamente debe usar la memoria suficiente para cargar un elemento único de los datos. Las clases que implementan la `IEnumerable(T)` interfaz se puede usar con `For Each` bucles o las consultas LINQ.  
  
 Por ejemplo, considere una aplicación que debe leer un archivo de texto grande y devolver cada línea del archivo que coincide con los criterios de búsqueda determinada. La aplicación usa una consulta LINQ para devolver las líneas del archivo que coinciden con los criterios especificados. Para consultar el contenido del archivo mediante una consulta LINQ, la aplicación podría cargar el contenido del archivo en una matriz o una colección. Sin embargo, cargar el archivo completo en una matriz o colección consumiría mucho más memoria que es necesario. La consulta LINQ en su lugar, pudo consultar el contenido del archivo mediante el uso de una clase enumerable, devolver solo los valores que coincidan con los criterios de búsqueda. Las consultas que solamente devuelven algunos valores coincidentes consumirían mucha menos memoria.  
  
 Puede crear una clase que implementa el <xref:System.Collections.Generic.IEnumerable%601> interfaz para exponer los datos de origen como datos enumerables. La clase que implementa el `IEnumerable(T)` interfaz requerirá otra clase que implementa el <xref:System.Collections.Generic.IEnumerator%601> interfaz para recorrer en iteración los datos de origen. Estas dos clases permiten devolver elementos de datos secuencialmente como un tipo específico.  
  
 En este tutorial, creará una clase que implementa el `IEnumerable(Of String)` interfaz y una clase que implementa el `IEnumerator(Of String)` interfaz para leer un archivo una línea de texto a la vez.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a>Creación de la clase Enumerable  
  
|Para crear el proyecto de clase enumerable|  
|---|  
|1.  En [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], en el menú **Archivo**, seleccione **Nuevo** y haga clic en **Proyecto**.<br />2.  En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto**, asegúrese de que esté seleccionado **Windows**. Seleccione **Biblioteca de clases** en el panel **Plantillas**. En el cuadro **Nombre**, escriba `StreamReaderEnumerable` y haga clic en **Aceptar**. Se muestra el nuevo proyecto.<br />3.  En **el Explorador de soluciones**, haga clic en el archivo Class1.vb y haga clic en **cambiar el nombre de**. Cambie el nombre del archivo a `StreamReaderEnumerable.vb` y pulse ENTRAR. Al cambiar el nombre del archivo también se cambiará el nombre de la clase a `StreamReaderEnumerable`. Esta clase implementará la interfaz `IEnumerable(Of String)`.<br />4.  Haga clic en el proyecto StreamReaderEnumerable, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. Seleccione el **clase** plantilla. En el **nombre** , escriba `StreamReaderEnumerator.vb` y haga clic en **Aceptar**.|  
  
 La primera clase de este proyecto es la clase enumerable e implementará la `IEnumerable(Of String)` interfaz. Esta interfaz genérica implementa la <xref:System.Collections.IEnumerable> interfaz y garantiza que los consumidores de esta clase pueden tener acceso a valores de tipo `String`.  
  
|Para agregar el código para implementar IEnumerable|  
|---|  
|1.  Abra el archivo StreamReaderEnumerable.vb.<br />2.  En la línea después de `Public Class StreamReaderEnumerable`, escriba lo siguiente y presione ENTRAR.<br />     [!code-vb[VbVbalrIteratorWalkthrough#1](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_1.vb)]<br />     [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]rellena automáticamente la clase con los miembros que son requeridos por la `IEnumerable(Of String)` interfaz.<br />3.  Esta clase enumerable leerá las líneas de un archivo una línea de texto a la vez. Agregue el código siguiente a la clase para exponer un constructor público que toma una ruta de acceso de archivo como parámetro de entrada.<br />     [!code-vb[VbVbalrIteratorWalkthrough#2](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_2.vb)]<br />4.  La implementación de la <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> método de la `IEnumerable(Of String)` interfaz devolverá una nueva instancia de la `StreamReaderEnumerator` clase. La implementación de la `GetEnumerator` método de la `IEnumerable` interfaz puede realizarse `Private`, porque se deben exponer solo los miembros de la `IEnumerable(Of String)` interfaz. Reemplace el código que [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] generado para el `GetEnumerator` métodos con el código siguiente.<br />     [!code-vb[VbVbalrIteratorWalkthrough#3](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_3.vb)]|  
  
|Para agregar el código para implementar IEnumerator|  
|---|  
|1.  Abra el archivo StreamReaderEnumerator.vb.<br />2.  En la línea después de `Public Class StreamReaderEnumerator`, escriba lo siguiente y presione ENTRAR.<br />     [!code-vb[VbVbalrIteratorWalkthrough#4](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_4.vb)]<br />     [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]rellena automáticamente la clase con los miembros que son requeridos por la `IEnumerator(Of String)` interfaz.<br />3.  La clase de enumerador abre el archivo de texto y realiza la E/S para leer las líneas del archivo de archivo. Agregue el código siguiente a la clase para exponer un constructor público que toma una ruta de acceso de archivo como parámetro de entrada y abra el archivo de texto para su lectura.<br />     [!code-vb[VbVbalrIteratorWalkthrough#5](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_5.vb)]<br />4.  El `Current` propiedades tanto para el `IEnumerator(Of String)` y `IEnumerator` interfaces devuelven el elemento actual del archivo de texto como un `String`. La implementación de la `Current` propiedad de la `IEnumerator` interfaz puede realizarse `Private`, porque se deben exponer solo los miembros de la `IEnumerator(Of String)` interfaz. Reemplace el código que [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] generado para el `Current` propiedades con el código siguiente.<br />     [!code-vb[VbVbalrIteratorWalkthrough#6](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_6.vb)]<br />5.  El `MoveNext` método de la `IEnumerator` interfaz se desplaza al elemento siguiente en el archivo de texto y actualiza el valor devuelto por la `Current` propiedad. Si no hay más elementos para leer, el `MoveNext` método `False`; de lo contrario el `MoveNext` método devuelve `True`. Agregue el código siguiente al método `MoveNext` .<br />     [!code-vb[VbVbalrIteratorWalkthrough#7](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_7.vb)]<br />6.  El `Reset` método de la `IEnumerator` interfaz dirige el iterador para que apunte al principio del archivo de texto y borra el valor del elemento actual. Agregue el código siguiente al método `Reset` .<br />     [!code-vb[VbVbalrIteratorWalkthrough#8](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_8.vb)]<br />7.  El `Dispose` método de la `IEnumerator` interfaz garantiza que se liberan todos los recursos no administrados antes de que se destruya el iterador. El identificador de archivo que se usa por la `StreamReader` objeto es un recurso no administrado y debe cerrarse antes de que se destruya la instancia del iterador. Reemplace el código que [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] generado para el `Dispose` método por el código siguiente.<br />     [!code-vb[VbVbalrIteratorWalkthrough#9](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_9.vb)]|  
  
## <a name="using-the-sample-iterator"></a>Mediante el iterador de ejemplo  
 Puede usar una clase enumerable en el código junto con estructuras de control que requieren un objeto que implementa `IEnumerable`, como un `For Next` bucle o una consulta LINQ. El siguiente ejemplo se muestra el `StreamReaderEnumerable` en una consulta LINQ.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_10.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [Estructuras de bucle](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [For Each...Next (instrucción)](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
