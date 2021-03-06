---
title: Extender metadatos mediante atributos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- metadata, extending
- attributes [.NET Framework], metadata
- elements [.NET Framework], attributes
- common language runtime, attributes
- annotating programming elements
- keyword-like descriptive declarations
- runtime, attributes
- extending metadata
ms.assetid: 30386922-1e00-4602-9ebf-526b271a8b87
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ae399e5213c95b29736c54fcc48ac45a778ba25b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="extending-metadata-using-attributes"></a>Extender metadatos mediante atributos
Common Language Runtime permite agregar declaraciones descriptivas a modo de palabras clave, conocidas como atributos, para anotar elementos de programación como tipos, campos, métodos y propiedades. Cuando compila el código para runtime, este se convierte al Lenguaje Intermedio de Microsoft (MSIL) y se coloca dentro de un archivo portable ejecutable (PE) junto con los metadatos generados por el compilador. Los atributos permiten colocar información descriptiva adicional en los metadatos que se puede extraer usando servicios de reflexión en tiempo de ejecución. El compilador crea atributos cuando se declaran instancias de clases especiales que derivan de <xref:System.Attribute?displayProperty=nameWithType>.  
  
 .NET Framework usa atributos por distintos motivos y para tratar diversos problemas. Los atributos describen cómo serializar los datos, especifican las características que se usan para aplicar la seguridad y limita las optimizaciones del compilador Just-In-Time (JIT) para que el código siga siendo fácil de depurar. Los atributos también pueden registrar el nombre de un archivo o el autor del código, o controlar la visibilidad de controles y los miembros durante el desarrollo de formularios.  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Title|Description|  
|-----------|-----------------|  
|[Aplicar atributos](../../../docs/standard/attributes/applying-attributes.md)|Describe cómo aplicar un atributo a un elemento del código.|  
|[Escribir atributos personalizados](../../../docs/standard/attributes/writing-custom-attributes.md)|Describe cómo diseñar clases de atributos personalizados.|  
|[Retrieving Information Stored in Attributes](../../../docs/standard/attributes/retrieving-information-stored-in-attributes.md) (Recuperar la información almacenada en atributos)|Describe cómo recuperar los atributos personalizados del código que se carga en el contexto de ejecución.|  
|[Metadatos y componentes autodescriptivos](../../../docs/standard/metadata-and-self-describing-components.md)|Proporciona información general de los metadatos y describe cómo se implementan en un archivo portable ejecutable (PE) de .NET Framework.|  
|[Cargar ensamblados en el contexto de solo reflexión](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)|Explica cómo recuperar la información de los atributos personalizados en el contexto de solo reflexión.|  
  
## <a name="reference"></a>Referencia  
 <xref:System.Attribute?displayProperty=nameWithType>
