---
title: "Información general de la clase XAttribute (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 5a630f24-f9ad-400e-831e-c14ebfc9e142
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e9cfedb476f44ef8c3eaeb45bac571d17802d525
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="xattribute-class-overview-c"></a>Información general de la clase XAttribute (C#)
Los atributos son pares de nombre y valor asociados a un elemento. La clase <xref:System.Xml.Linq.XAttribute> representa los atributos XML.  
  
## <a name="overview"></a>Información general  
 Trabajar con atributos en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es similar a trabajar con elementos. Sus constructores son similares. Los métodos que usa para recuperar colecciones de ellos también son similares. Una expresión de consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] de una colección de atributos se parece mucho a una expresión de consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] de una colección de elementos.  
  
 Se conserva el orden en el que se agregaron los atributos a un elemento. Es decir, cuando procese una iteración en los atributos, los verá en el mismo orden en el que se agregaron.  
  
## <a name="the-xattribute-constructor"></a>El constructor XAttribute  
 El siguiente constructor de la clase <xref:System.Xml.Linq.XAttribute> es el que usará normalmente:  
  
|Constructor|Descripción|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|Crea un objeto <xref:System.Xml.Linq.XAttribute>. El argumento `name` especifica el nombre del atributo; `content` especifica el contenido del atributo.|  
  
### <a name="creating-an-element-with-an-attribute"></a>Crear un elemento con un atributo  
 El siguiente código muestra la tarea habitual de crear un elemento que contiene un atributo:  
  
```csharp  
XElement phone = new XElement("Phone",  
    new XAttribute("Type", "Home"),  
    "555-555-5555");  
Console.WriteLine(phone);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a>Construcción funcional de los atributos  
 Puede construir objetos <xref:System.Xml.Linq.XAttribute> de modo similar a la construcción de los objetos <xref:System.Xml.Linq.XElement>, tal como se indica a continuación:  
  
```csharp  
XElement c = new XElement("Customers",  
    new XElement("Customer",  
        new XElement("Name", "John Doe"),  
        new XElement("PhoneNumbers",  
            new XElement("Phone",  
                new XAttribute("type", "home"),  
                "555-555-5555"),  
            new XElement("Phone",  
                new XAttribute("type", "work"),  
                "666-666-6666")  
        )  
    )  
);  
Console.WriteLine(c);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Customers>  
  <Customer>  
    <Name>John Doe</Name>  
    <PhoneNumbers>  
      <Phone type="home">555-555-5555</Phone>  
      <Phone type="work">666-666-6666</Phone>  
    </PhoneNumbers>  
  </Customer>  
</Customers>  
```  
  
### <a name="attributes-are-not-nodes"></a>Los atributos no son nodos  
 Existen algunas diferencias entre los atributos y los elementos. Los objetos <xref:System.Xml.Linq.XAttribute> no son nodos en el árbol XML. Son pares de nombre y valor asociados a un elemento XML. A diferencia de Document Object Model (DOM), esto refleja de manera más precisa la estructura del código XML. Aunque los objetos <xref:System.Xml.Linq.XAttribute> no son realmente nodos en el árbol XML, trabajar con objetos <xref:System.Xml.Linq.XAttribute> es muy similar a trabajar con objetos <xref:System.Xml.Linq.XElement>.  
  
 Esta distinción solo resulta de importancia para los desarrolladores que escriban código que trabaje con árboles XML en el nivel de nodo. A muchos desarrolladores no les afecta esta distinción.  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre la programación de LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
