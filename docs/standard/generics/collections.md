---
title: "Colecciones gen&#233;ricas en .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "colecciones genéricas [.NET Framework]"
  - "genéricos [.NET Framework], colecciones"
ms.assetid: 5b646751-6ab7-465c-916c-b1a76aefa9f5
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Colecciones gen&#233;ricas en .NET Framework
Este tema proporciona una introducción a las clases de colección genéricas y otros tipos genéricos de .NET Framework.  
  
## Colecciones genéricas en .NET Framework  
 La biblioteca de clases de .NET Framework proporciona varias clases de colección genéricas en los espacios de nombres <xref:System.Collections.Generic> y <xref:System.Collections.ObjectModel>.  Para obtener más información sobre estas clases, consulte [Tipos de colección utilizados normalmente](../../../docs/standard/collections/commonly-used-collection-types.md).  
  
### System.Collections.Generic  
 Muchos de los tipos de colección genéricos son análogos directos de tipos no genéricos.  <xref:System.Collections.Generic.Dictionary%602> es una versión genérica de <xref:System.Collections.Hashtable>; usa la estructura genérica <xref:System.Collections.Generic.KeyValuePair%602> para la enumeración en lugar de <xref:System.Collections.DictionaryEntry>.  
  
 <xref:System.Collections.Generic.List%601> es una versión genérica de <xref:System.Collections.ArrayList>.  Hay clases <xref:System.Collections.Generic.Queue%601> y <xref:System.Collections.Generic.Stack%601> genéricas que se corresponden con las versiones no genéricas.  
  
 Hay versiones genéricas y no genéricas de <xref:System.Collections.Generic.SortedList%602>.  Ambas versiones son híbridos de un diccionario y una lista.  La clase genérica <xref:System.Collections.Generic.SortedDictionary%602> es un diccionario puro y no tiene ninguna homóloga no genérica.  
  
 La clase genérica <xref:System.Collections.Generic.LinkedList%601> es una lista vinculada genuina.  No tiene ninguna homóloga no genérica.  
  
### System.Collections.ObjectModel  
 La clase genérica <xref:System.Collections.ObjectModel.Collection%601> proporciona una clase base para derivar sus propios tipos de colección genéricos.  La clase <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> proporciona una manera sencilla de generar una colección de solo lectura de cualquier tipo que implementa la interfaz genérica <xref:System.Collections.Generic.IList%601>.  La clase genérica <xref:System.Collections.ObjectModel.KeyedCollection%602> proporciona una manera de almacenar objetos que contienen sus propias claves.  
  
## Otros tipos genéricos  
 La estructura genérica <xref:System.Nullable%601> permite usar tipos de valor como si se les pudiera asignar el valor `null`.  Esto puede ser útil para trabajar con consultas de base de datos en las que pueden faltar campos que contienen tipos de valor.  El parámetro de tipo genérico puede ser cualquier tipo de valor.  
  
> [!NOTE]
>  En C\# no es necesario usar <xref:System.Nullable%601> explícitamente porque el lenguaje tiene sintaxis para tipos que aceptan valores NULL.  
  
 La estructura genérica <xref:System.ArraySegment%601> proporciona una manera de delimitar un intervalo de elementos en una matriz unidimensional basada en cero de cualquier tipo.  El parámetro de tipo genérico es el tipo de los elementos de la matriz.  
  
 El delegado genérico <xref:System.EventHandler%601> elimina la necesidad de declarar un tipo de delegado para controlar los eventos, si su evento sigue el patrón de control de eventos que usa [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].  Por ejemplo, supongamos que ha creado una clase `MyEventArgs`, derivada de <xref:System.EventArgs>, para contener los datos del evento.  Puede declarar el evento de la siguiente manera:  
  
 [!code-cpp[Conceptual.Generics.Overview#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Generics.Overview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source2.cs#7)]
 [!code-vb[Conceptual.Generics.Overview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source2.vb#7)]  
  
## Vea también  
 <xref:System.Collections.Generic?displayProperty=fullName>   
 <xref:System.Collections.ObjectModel?displayProperty=fullName>   
 [Genéricos](../../../docs/standard/generics/index.md)   
 [Delegados genéricos para manipular matrices y listas](../../../docs/standard/generics/delegates-for-manipulating-arrays-and-lists.md)   
 [Interfaces genéricas](../../../docs/standard/generics/interfaces.md)