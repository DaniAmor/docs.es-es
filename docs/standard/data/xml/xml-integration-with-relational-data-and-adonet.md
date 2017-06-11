---
title: "Integraci&#243;n de XML con datos relacionales y ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: f6ebb1a1-f2ca-49b9-92c9-0150940cf6e6
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 4
---
# Integraci&#243;n de XML con datos relacionales y ADO.NET
La clase **XmlDataDocument** se deriva de **XmlDocument**, y contiene datos XML.  La ventaja que aporta la clase **XmlDataDocument** es que proporciona un puente entre los datos relacionales y jerárquicos.  Se trata de una clase **XmlDocument** que puede enlazarse con otra **DataSet** para sincronizar cambios realizados en los datos incluidos en las dos clases.  Una clase **XmlDocument** que está enlazada con otra **DataSet** permite a XML integrarse con datos relacionales, sin necesidad de que los datos estén representados ni en formato XML ni relacional.  Se pueden hacer ambas cosas sin necesidad de restringirse a una única representación de los datos.  
  
 Las ventajas de tener los datos disponibles en dos vistas son las siguientes:  
  
-   La parte estructurada de un documento XML puede asignarse a un conjunto de datos y ser almacenada, indizada y buscada de forma eficaz.  
  
-   Las transformaciones, validación y navegación en los datos XML que están almacenados de forma relacional se pueden realizar eficazmente mediante un modelo de cursor.  En ocasiones, se puede realizar de forma más eficaz en estructuras relacionales que si el código XML está almacenado en un modelo **XmlDocument**.  
  
-   La clase **DataSet** puede almacenar una parte del código XML.  Es decir, se puede usar **XPath** o **XslTransform** para almacenar en un **DataSet** sólo aquellos elementos y atributos que resulten de interés.  A partir de aquí, se pueden realizar cambios en un subconjunto más pequeño y filtrado de datos y hacer que los cambios se propaguen a un conjunto mayor de datos en la clase **XmlDataDocument**.  
  
 Asimismo, se puede ejecutar una transformación sobre los datos que se cargaron en **DataSet** a partir del servidor SQL Server.  Otra opción es enlazar controles de WinForms y WebForms del estilo de las clases administradas de .NET Framework con un **DataSet** que se haya llenado a partir de un flujo de entrada.  
  
 Además de ser compatible con **XslTransform**, **XmlDataDocument** expone los datos relacionales a consultas y validación **XPath**.  Básicamente, todos los servicios XML están disponibles en los datos relacionales; las funciones relacionales, como el enlace de controles, codegen, etc., están disponibles en una proyección estructurada de XML sin comprometer la fidelidad con el lenguaje XML.  
  
 Como **XmlDataDocument** se hereda de **XmlDocument**, proporciona una implementación de DOM del consorcio W3C.  El hecho de que **XmlDataDocument** se asocie con un **DataSet** y almacene en su interior un subconjunto de sus datos, no restringe o altera en absoluto su uso como **XmlDocument**.  El código escrito para consumir un **XmlDocument** funciona sin alteraciones en **XmlDataDocument**.  **DataSet** proporciona la vista relacional de los mismos datos definiendo tablas, columnas, relaciones y restricciones, y constituye un almacén independiente y en memoria de datos de usuario.  
  
 En la siguiente ilustración se muestran las distintas asociaciones que los datos XML tienen con **DataSet** y **XmlDataDocument**.  
  
 ![Clase DataSet de XML](../../../../docs/standard/data/xml/media/xmlintegrationwithrelationaldataandadodotnet.gif "xmlIntegrationWithRelationalDataAndADOdotNet")  
  
 En la ilustración se muestra que los datos XML pueden cargarse directamente en un **DataSet**, lo que permite la manipulación directa con XML en la forma relacional.  O bien, el código XML se puede cargar en una clase derivada de DOM, que es **XmlDataDocument**, y posteriormente cargarlo y sincronizarlo con el **DataSet**.  Como **DataSet** y **XmlDataDocument** están sincronizados sobre un solo conjunto de datos, los cambios realizados en los datos en un almacén se reflejan automáticamente en el otro almacén.  
  
 **XmlDataDocument** hereda todas las características de edición y navegación de **XmlDocument**.  Existen ocasiones en las que utilizar **XmlDataDocument** y sus características heredadas, sincronizadas con un **DataSet**, constituye una opción más apropiada que cargar código XML directamente en el **DataSet**.  En la tabla siguiente se muestran los elementos que se deben tener en consideración al elegir qué método utilizar para cargar el **DataSet**.  
  
|Cuándo cargar XML directamente en un DataSet|Cuándo sincronizar un XmlDataDocument con un DataSet|  
|--------------------------------------------------|----------------------------------------------------------|  
|Las consultas de datos en el **DataSet** son más fáciles usando SQL que XPath.|Se necesitan consultas XPath sobre datos del **DataSet**.|  
|Preservar el orden de los elementos en el código fuente XML no es vital.|Preservar el orden de los elementos en el código fuente XML resulta vital.|  
|No es necesario preservar el espacio en blanco entre los elementos ni el formato del código fuente XML.|Preservar el espacio y formato del código fuente XML resulta vital.|  
  
 Si cargar y escribir código XML directamente en un **DataSet** o extraerlo de él, cubre sus necesidades, vea [Cargar DataSet desde XML](../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) y [Escribir un objeto DataSet como datos XML](../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Si cargar el **DataSet** a partir de un **XmlDataDocument** cubre sus necesidades, vea [Sincronizar un Dataset con un documento XML](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md).  
  
## Vea también  
 [Utilizar XML en un DataSet](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)