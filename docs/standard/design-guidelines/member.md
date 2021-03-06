---
title: "Instrucciones de diseño de miembros"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ae69b77098c7f2e1de83eedd40cf0f0da9473326
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="member-design-guidelines"></a>Instrucciones de diseño de miembros
Métodos, propiedades, eventos, constructores y campos se conocen colectivamente como miembros. Los miembros en última instancia son el medio por el que la funcionalidad de framework se expone a los usuarios finales de un marco de trabajo.  
  
 Los miembros pueden ser virtual o no virtual, concreta o abstracto, estático o instancia y pueden tener varios ámbitos diferentes de accesibilidad. Todos los esta variedad proporciona expresividad increíble pero al mismo tiempo requiere atención por parte del Diseñador de framework.  
  
 Este capítulo proporciona instrucciones básicas que se deben seguir al diseñar a los miembros de cualquier tipo.  
  
## <a name="in-this-section"></a>En esta sección  
 [Sobrecarga de miembro](../../../docs/standard/design-guidelines/member-overloading.md)  
 [Diseño de propiedades](../../../docs/standard/design-guidelines/property.md)  
 [Diseño de constructores](../../../docs/standard/design-guidelines/constructor.md)  
 [Diseño de eventos](../../../docs/standard/design-guidelines/event.md)  
 [Diseño de campos](../../../docs/standard/design-guidelines/field.md)  
 [Métodos de extensión](../../../docs/standard/design-guidelines/extension-methods.md)  
 [Sobrecargas de operador](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [Diseño de parámetros](../../../docs/standard/design-guidelines/parameter-design.md)  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
