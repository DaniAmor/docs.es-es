---
title: throw (Referencia de C#)
ms.date: 03/02/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- throw
- throw_CSharpKeyword
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e56bd8f8b6bfcc7c8f1eb2df6ac157e28adac331
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="throw-c-reference"></a>throw (Referencia de C#)
Indica la aparición de una excepción durante la ejecución del programa.  
  
## <a name="remarks"></a>Comentarios

La sintaxis de `throw` es la siguiente:

```csharp
throw [e]
```
donde `e` es una instancia de una clase derivada de <xref:System.Exception?displayProperty=nameWithType>. En el ejemplo siguiente se usa la instrucción `throw` para producir una excepción <xref:System.IndexOutOfRangeException> si el argumento pasado a un método denominado `GetNumber` no se corresponde con un índice válido de una matriz interna.

[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]  

Después, los autores de llamadas a método usan un bloque `try-catch` o `try-catch-finally` para controlar la excepción generada. En el ejemplo siguiente se controla la excepción producida por el método `GetNumber`.

[!code-csharp[csrefKeyword#2](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]  

## <a name="re-throwing-an-exception"></a>Volver a iniciar una excepción

`throw` también se puede usar en un bloque `catch` para volver a iniciar una excepción controlada en un bloque `catch`.  En este caso, `throw` no toma un operando de excepción. Resulta más útil cuando un método pasa un argumento de un autor de llamada a otro método de biblioteca y el método de biblioteca produce una excepción que se debe pasar al autor de llamada. Por ejemplo, en el ejemplo siguiente se vuelve a iniciar una excepción <xref:System.NullReferenceException> que se produce al intentar recuperar el primer carácter de una cadena sin inicializar. 

[!code-csharp[csrefKeyword#3](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]  

> [!IMPORTANT]
> También puede usar la sintaxis `throw e` en un bloque `catch` para crear instancias de una nueva excepción que se pase al autor de llamada. En este caso, no se conserva el seguimiento de la pila de la excepción original, que está disponible en la propiedad <xref:System.Exception.StackTrace>.
 
## <a name="the-throw-expression"></a>La expresión `throw`

A partir de C# 7, se puede usar `throw` como una expresión y como una instrucción. Esto permite iniciar una excepción en contextos que antes no se admitían. Se incluyen los siguientes:

- [El operador condicional](../operators/conditional-operator.md). En el ejemplo siguiente se usa una expresión `throw` para iniciar una excepción <xref:System.ArgumentException> si se pasa a un método una matriz de cadena vacía. Antes de C# 7, esta lógica tendría que aparecer en una instrucción `if`/`else`.

   [!code-csharp[csrefKeyword#4](../../../../samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]  
  
- [El operador de uso combinado de NULL](../operators/null-conditional-operator.md). En el ejemplo siguiente, se usa una expresión `throw` con un operador de uso combinado de NULL para producir una excepción si la cadena asignada a una propiedad `Name` es `null`.
 
   [!code-csharp[csrefKeyword#5](../../../../samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]  
 
- Un método o [lambda](../../lambda-expressions.md) con forma de expresión. En el ejemplo siguiente se muestra un método con forma de expresión que produce una excepción <xref:System.InvalidCastException> porque no se admite una conversión a un valor <xref:System.DateTime>.
 
   [!code-csharp[csrefKeyword#6](../../../../samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]  
 
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [try-catch](../../../csharp/language-reference/keywords/try-catch.md)  
 [Try, catch y throw (instrucciones) en C++](../../../csharp/language-reference/keywords/try-catch.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [Instrucciones para el control de excepciones](../../../csharp/language-reference/keywords/exception-handling-statements.md)  
 [Cómo: Iniciar excepciones explícitamente](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
