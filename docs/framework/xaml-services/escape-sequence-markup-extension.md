---
title: "Secuencia de escape {}: extensión de marcado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
caps.latest.revision: "21"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8419a1e89d5e94b9868b0fd1fb81540253efca5d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="-escape-sequence--markup-extension"></a>Secuencia de escape / extensión de marcado {}
Proporciona la secuencia de escape XAML para los valores de atributo. La secuencia de escape permite los valores siguientes en el atributo debe interpretarse como un literal.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xml  
<object property="{} literalValue" .../>  
```  
  
## <a name="xaml-property-element-usage"></a>Uso de elementos de propiedad XAML  
  
```  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|*literalValue*|La cadena literal que sigue la secuencia de escape. Normalmente, esta cadena contiene una llave de abrir o cerrar ({o}).|  
  
## <a name="remarks"></a>Comentarios  
 La secuencia de escape ({}) se utiliza para que pueda usarse una llave de apertura ({}) como un carácter literal en XAML.  
  
 Los lectores XAML normalmente use la llave de apertura ({}) para indicar el punto de entrada de una extensión de marcado; sin embargo, primero compruebe el siguiente carácter para determinar si se trata de una llave de cierre (}). Solo si las dos llaves ({}) son adyacentes, se consideran que una secuencia de escape.  
  
 Si se encuentra la secuencia de escape, el lector XAML debería procesar el resto de la cadena como una cadena. Sin embargo, si la secuencia de escape se aplica a un miembro que tenga un convertidor de tipos, la cadena podría someterse a una conversión de tipos cuando se interpreta mediante un escritor de XAML.  
  
 La secuencia de escape no es una extensión de marcado y no está respaldada por una clase. Sin embargo, es una convención que deben respetar los lectores XAML (incluidos los lectores XAML personalizados).  
  
 No se puede usar un signo de comillas (") como una secuencia de escape de esta manera. Si tiene que establecer un signo de comillas como un valor de propiedad para una propiedad sin contenido, usar la sintaxis de elemento de propiedad y coloque las comillas como una cadena dentro del elemento de propiedad o usar una entidad de caracteres XML. Para una propiedad de contenido, las comillas pueden ser todo el contenido.  
  
 La secuencia de escape ({}) se suele ser necesaria cuando se especifica un tipo XML que debe incluir un calificador de espacio de nombres en una ubicación donde puede aparecer una extensión de marcado XAML. Esto incluye el inicio de un valor de atributo XAML y en una extensión de marcado, inmediatamente después de un signo igual (=). El ejemplo siguiente muestra las secuencias de escape para un espacio de nombres XML que aparece al principio de un valor de atributo XAML.  
  
 [!code-xaml[XLINQExample#StackPanelResources](../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a>Vea también  
 [Convertidores de tipos y extensiones de marcado para XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)  
 [Entidades de caracteres XML y XAML](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)
