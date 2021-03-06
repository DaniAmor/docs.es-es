---
title: "Buscar elementos secundarios en función de la posición (XPath-LINQ to XML) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: e35bb269-ec86-4c96-8321-12491a0eb2c3
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: df586c74d46513122029b3f5fdb5bec4f7b6003b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-child-elements-based-on-position-xpath-linq-to-xml-c"></a>Buscar elementos secundarios en función de la posición (XPath-LINQ to XML) (C#)
En ocasiones, deseará buscar elementos en función de su posición. Quizá desee buscar el segundo elemento o buscar el tercero en el quinto elemento.  
  
 La expresión XPath es:  
  
 `Test[position() >= 2 and position() <= 4]`  
  
 Existen dos aproximaciones posibles para escribir esta consulta de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] de forma diferida. Puede utilizar los operadores <xref:System.Linq.Enumerable.Skip%2A> y <xref:System.Linq.Enumerable.Take%2A>, o bien utilizar la sobrecarga <xref:System.Linq.Enumerable.Where%2A> que recibe un índice. Si utiliza la sobrecarga <xref:System.Linq.Enumerable.Where%2A>, estará utilizando una expresión lambda que recibe dos argumentos. El siguiente ejemplo muestra ambos métodos para seleccionar elementos en base a la posición.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo encontrará el segundo en el cuarto elemento de `Test`. El resultado es una colección de elementos.  
  
 En este ejemplo se usa el siguiente documento XML: [Sample XML File: Test Configuration (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md) (Archivo XML de muestra: Configuración de prueba [LINQ to XML]).  
  
```csharp  
XElement testCfg = XElement.Load("TestConfig.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    testCfg  
    .Elements("Test")  
    .Skip(1)  
    .Take(3);  
  
// LINQ to XML query  
IEnumerable<XElement> list2 =  
    testCfg  
    .Elements("Test")  
    .Where((el, idx) => idx >= 1 && idx <= 3);  
  
// XPath expression  
IEnumerable<XElement> list3 =  
  testCfg.XPathSelectElements("Test[position() >= 2 and position() <= 4]");  
  
if (list1.Count() == list2.Count() &&  
    list1.Count() == list3.Count() &&  
    list1.Intersect(list2).Count() == list1.Count() &&  
    list1.Intersect(list3).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
Results are identical  
<Test TestId="0002" TestType="CMD">  
  <Name>Find succeeding characters</Name>  
  <CommandLine>Examp2.EXE</CommandLine>  
  <Input>abc</Input>  
  <Output>def</Output>  
</Test>  
<Test TestId="0003" TestType="GUI">  
  <Name>Convert multiple numbers to strings</Name>  
  <CommandLine>Examp2.EXE /Verbose</CommandLine>  
  <Input>123</Input>  
  <Output>One Two Three</Output>  
</Test>  
<Test TestId="0004" TestType="GUI">  
  <Name>Find correlated key</Name>  
  <CommandLine>Examp3.EXE</CommandLine>  
  <Input>a1</Input>  
  <Output>b1</Output>  
</Test>  
```  
  
## <a name="see-also"></a>Vea también  
 [LINQ to XML para usuarios de XPath (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
