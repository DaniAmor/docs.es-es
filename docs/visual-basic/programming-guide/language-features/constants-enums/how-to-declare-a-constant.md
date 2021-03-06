---
title: "Cómo: Declarar una constante (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.constant
helpviewer_keywords:
- Integer data type [Visual Basic], declaring constants
- Single data type [Visual Basic], declaring constants
- Const statement [Visual Basic], declaring constants
- procedures [Visual Basic], declaration
- data types [Visual Basic], constants
- Long data type [Visual Basic], declaring constants
- Visual Basic code, declaring variables and constants
- Double data type [Visual Basic], declaring constants
- Boolean data type [Visual Basic], declaring constants
- modules, declaring constants
- Byte data type [Visual Basic], declaring constants
- constants [Visual Basic], declaring
- Date data type [Visual Basic], declaring constants
- String data type [Visual Basic], declaring constants
- declaring constants [Visual Basic], const keyword
- Currency data type [Visual Basic], declaring constants and variants
- module-level constants and variables
- Object data type [Visual Basic], declaring constants
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 554f659e060087228fb43efd8b9d06103e21e980
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-a-constant-visual-basic"></a>Cómo: Declarar una constante (Visual Basic)
Usa el `Const` instrucción para declarar una constante y establecer su valor. Al declarar una constante, se asigna un nombre significativo a un valor. Una vez que se declara una constante, no se pueden modificar ni asigna un nuevo valor.  
  
 Declarar una constante dentro de un procedimiento o en la sección de declaraciones de un módulo, clase o estructura. Constantes de nivel de la estructura o clase son `Private` de forma predeterminada, pero también se puede declarar como `Public`, `Friend`, `Protected`, o `Protected Friend` para el nivel adecuado de acceso al código.  
  
 La constante debe tener un nombre simbólico válido (las reglas son las mismas que para crear nombres de variable) y una expresión que se componga de numérico o cadena de constantes y operadores (pero no hay llamadas de función).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a>Para declarar una constante  
  
-   Escriba una declaración que incluya un especificador de acceso, el `Const` (palabra clave) y una expresión, como en los ejemplos siguientes:  
  
     [!code-vb[VbEnumsTask#8](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]  
  
     Cuando [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) es `Off` y [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) es `On`, debe declarar una constante explícitamente especificando un tipo de datos (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, o `String`).  
  
     Cuando `Option Infer` es `On` o `Option Strict` es `Off`, puede declarar una constante sin especificar un tipo de datos con un `As` cláusula. El compilador determina el tipo de la constante del tipo de la expresión. Para obtener más información, consulte [constante y tipos de datos literales](constant-and-literal-data-types.md).  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a>Para declarar una constante que tiene un tipo de datos establecidos explícitamente  
  
-   Escriba una declaración que incluya la `As` palabra clave y un explícitas tipo de datos, como en los ejemplos siguientes:  
  
     [!code-vb[VbEnumsTask#9](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]  
  
     Puede declarar varias constantes en una sola línea, aunque el código sea más legible si declara solamente una constante por línea. Si declara varias constantes en una sola línea, debe tener el mismo nivel de acceso (`Public`, `Private`, `Friend`, `Protected`, o `Protected Friend`).  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a>Para declarar varias constantes en una sola línea  
  
-   Separe las declaraciones con una coma y un espacio, como en el ejemplo siguiente:  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Const (instrucción)](../../../../visual-basic/language-reference/statements/const-statement.md)  
 [Tipos de datos constantes y literales](constant-and-literal-data-types.md)  
 [Información general de constantes](constants-overview.md) [Cómo: declarar una constante](how-to-declare-a-constant.md) [constantes definidas por el usuario](user-defined-constants.md) [tipos de datos constantes y literales](constant-and-literal-data-types.md) [Cómo: grupo Valores de constantes relacionadas](how-to-group-related-constant-values-together.md) [información general de las enumeraciones](enumerations-overview.md) [Cómo: declarar enumeraciones](how-to-declare-enumerations.md) [Cómo: hacer referencia a un miembro de enumeración](how-to-refer-to-an-enumeration-member.md) [Enumeraciones y calificación de nombres](enumerations-and-name-qualification.md) [Cómo: recorrer en iteración una enumeración](how-to-iterate-through-an-enumeration.md) [Cómo: determinar la cadena asociada con un valor de enumeración](how-to-determine-the-string-associated-with-an-enumeration-value.md) [Cuándo se debe utilizar una enumeración](when-to-use-an-enumeration.md)

 [Información general sobre las enumeraciones](enumerations-overview.md)  
 [Información general sobre las constantes](constants-overview.md)  
 [Cómo: declarar una enumeración](how-to-declare-enumerations.md)  
 [Enumeraciones y calificación de nombres](enumerations-and-name-qualification.md)  
 [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)
