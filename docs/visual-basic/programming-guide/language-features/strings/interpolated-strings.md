---
title: Cadenas interpoladas (Visual Basic)
ms.date: 10/31/2017
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f865d5a7167847bf869d70a39570413dac271a2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="interpolated-strings-visual-basic-reference"></a><span data-ttu-id="ced56-102">Cadenas interpoladas (referencia de Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ced56-102">Interpolated Strings (Visual Basic Reference)</span></span>

<span data-ttu-id="ced56-103">Se utiliza para construir cadenas.</span><span class="sxs-lookup"><span data-stu-id="ced56-103">Used to construct strings.</span></span>  <span data-ttu-id="ced56-104">Una cadena interpolada es similar a una cadena de plantilla que contiene *expresiones interpoladas*.</span><span class="sxs-lookup"><span data-stu-id="ced56-104">An interpolated string looks like a template string that contains *interpolated expressions*.</span></span>  <span data-ttu-id="ced56-105">Una cadena interpolada devuelve una cadena que reemplaza a las expresiones interpoladas que contiene por sus representaciones de cadena.</span><span class="sxs-lookup"><span data-stu-id="ced56-105">An interpolated string returns a string that replaces the interpolated expressions that it contains with their string representations.</span></span> <span data-ttu-id="ced56-106">Esta característica está disponible en Visual Basic 14 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="ced56-106">This feature is available in Visual Basic 14 and later versions.</span></span>

<span data-ttu-id="ced56-107">Los argumentos de una cadena interpolada son más fáciles de entender que una [cadena de formato compuesto](../../../../standard/base-types/composite-formatting.md#composite-format-string).</span><span class="sxs-lookup"><span data-stu-id="ced56-107">The arguments of an interpolated string are easier to understand than a [composite format string](../../../../standard/base-types/composite-formatting.md#composite-format-string).</span></span>  <span data-ttu-id="ced56-108">Por ejemplo, la cadena interpolada</span><span class="sxs-lookup"><span data-stu-id="ced56-108">For example, the interpolated string</span></span>  
  
```vb  
Console.WriteLine($"Name = {name}, hours = {hours:hh}")
```  
<span data-ttu-id="ced56-109">contiene dos expresiones interpoladas, "{name}" y "{hours:hh}".</span><span class="sxs-lookup"><span data-stu-id="ced56-109">contains two interpolated expressions, '{name}' and '{hours:hh}'.</span></span> <span data-ttu-id="ced56-110">La cadena de formato compuesto equivalente es esta:</span><span class="sxs-lookup"><span data-stu-id="ced56-110">The equivalent composite format string is:</span></span>

```vb
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours); 
```  

<span data-ttu-id="ced56-111">La estructura de una cadena interpolada es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="ced56-111">The structure of an interpolated string is:</span></span>  
  
```vb  
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."  
```  

<span data-ttu-id="ced56-112">donde:</span><span class="sxs-lookup"><span data-stu-id="ced56-112">where:</span></span> 

- <span data-ttu-id="ced56-113">*field-width* es un entero con signo que indica el número de caracteres del campo.</span><span class="sxs-lookup"><span data-stu-id="ced56-113">*field-width* is a signed integer that indicates the number of characters in the field.</span></span> <span data-ttu-id="ced56-114">Si es positivo, el campo está alineado a la derecha. Si es negativo, está alineado a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="ced56-114">If it is positive, the field is right-aligned; if negative, left-aligned.</span></span> 

- <span data-ttu-id="ced56-115">*format-string* es una cadena de formato adecuada para el tipo de objeto al que se da formato.</span><span class="sxs-lookup"><span data-stu-id="ced56-115">*format-string* is a format string appropriate for the type of object being formatted.</span></span> <span data-ttu-id="ced56-116">Por ejemplo, para un <xref:System.DateTime> valor, podría ser un [cadena de formato de fecha y hora estándar](~/docs/standard/base-types/standard-date-and-time-format-strings.md) como "D" o "d".</span><span class="sxs-lookup"><span data-stu-id="ced56-116">For example, for a <xref:System.DateTime> value, it could be a [standard date and time format string](~/docs/standard/base-types/standard-date-and-time-format-strings.md) such as "D" or "d".</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ced56-117">No puede haber ningún espacio en blanco entre la `$` y `"` que comienza la cadena.</span><span class="sxs-lookup"><span data-stu-id="ced56-117">You cannot have any whitespace between the `$` and the `"` that starts the string.</span></span> <span data-ttu-id="ced56-118">Si lo hace, produce un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="ced56-118">Doing so causes a compiler error.</span></span>

 <span data-ttu-id="ced56-119">Puede utilizar una cadena interpolada en cualquier lugar que pueda utilizar un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="ced56-119">You can use an interpolated string anywhere you can use a string literal.</span></span>  <span data-ttu-id="ced56-120">La cadena interpolada se evalúa cada vez que se ejecuta el código con la cadena interpolada.</span><span class="sxs-lookup"><span data-stu-id="ced56-120">The interpolated string is evaluated each time the code with the interpolated string executes.</span></span> <span data-ttu-id="ced56-121">Esto le permite separar la definición y la evaluación de una cadena interpolada.</span><span class="sxs-lookup"><span data-stu-id="ced56-121">This allows you to separate the definition and evaluation of an interpolated string.</span></span>  
  
 <span data-ttu-id="ced56-122">Para incluir una llave ("{" o "}") en una cadena interpolada, use dos llaves, "{{" o "}}".</span><span class="sxs-lookup"><span data-stu-id="ced56-122">To include a curly brace ("{" or "}") in an interpolated string, use two curly braces, "{{" or "}}".</span></span>  <span data-ttu-id="ced56-123">Consulte la sección Conversiones implícitas para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="ced56-123">See the Implicit Conversions section for more details.</span></span>  

<span data-ttu-id="ced56-124">Si la cadena interpolada contiene otros caracteres con un significado especial en una cadena interpolada, como comillas dobles ("), dos puntos (:) o coma (,), deben incluirse entre caracteres de escape si aparecen en texto literal, o bien deben incluirse en una expresión delimitada por paréntesis si son elementos del lenguaje incluidos en una expresión interpolada.</span><span class="sxs-lookup"><span data-stu-id="ced56-124">If the interpolated string contains other characters with special meaning in an interpolated string, such as the quotation mark ("), colon (:), or comma (,), they should be escaped if they occur in literal text, or they should be included in an expression delimited by parentheses if they are language elements included in an interpolated expression.</span></span> <span data-ttu-id="ced56-125">En el ejemplo siguiente las comillas se escriben entre caracteres de escape para incluirlas en la cadena de resultado y se usan paréntesis para delimitar la expresión `(age == 1 ? "" : "s")` de modo que el carácter de dos puntos no se interprete como el principio de una cadena de formato.</span><span class="sxs-lookup"><span data-stu-id="ced56-125">The following example escapes quotation marks to include them in the result string, and it uses parentheses to delimit the expression `(age == 1 ? "" : "s")` so that the colon is not interpreted as beginning a format string.</span></span>

[!code-vb[interpolated-strings](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings4.vb)]  

## <a name="implicit-conversions"></a><span data-ttu-id="ced56-126">Conversiones implícitas</span><span class="sxs-lookup"><span data-stu-id="ced56-126">Implicit Conversions</span></span>  

<span data-ttu-id="ced56-127">Hay tres conversiones de tipo implícito de una cadena interpolada:</span><span class="sxs-lookup"><span data-stu-id="ced56-127">There are three implicit type conversions from an interpolated string:</span></span>  

1. <span data-ttu-id="ced56-128">Conversión de una cadena interpolada a <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ced56-128">Conversion of an interpolated string to a <xref:System.String>.</span></span> <span data-ttu-id="ced56-129">En el ejemplo siguiente se devuelve una cadena cuyas expresiones de cadena interpolada se han reemplazado por las representaciones de cadena.</span><span class="sxs-lookup"><span data-stu-id="ced56-129">The following example returns a string whose interpolated string expressions have been replaced with their string representations.</span></span> <span data-ttu-id="ced56-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ced56-130">For example:</span></span>

   [!code-vb[interpolated-strings1](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings1.vb)]  

   <span data-ttu-id="ced56-131">Este es el resultado final de una interpretación de cadena.</span><span class="sxs-lookup"><span data-stu-id="ced56-131">This is the final result of a string interpretation.</span></span> <span data-ttu-id="ced56-132">Todas las apariciones de llaves dobles ("{{" y "}}") se convierten en una única llave.</span><span class="sxs-lookup"><span data-stu-id="ced56-132">All occurrences of double curly braces ("{{" and "}}") are converted to a single curly brace.</span></span> 

2. <span data-ttu-id="ced56-133">Conversión de una cadena interpolada a una variable <xref:System.IFormattable> que permite crear varias cadenas de resultado con contenido específico de la referencia cultural de una sola instancia <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="ced56-133">Conversion of an interpolated string to an <xref:System.IFormattable> variable that allows you create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span> <span data-ttu-id="ced56-134">Esto resulta útil para incluir elementos como los formatos numéricos y de fecha correctos para cada referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="ced56-134">This is useful for including such things as the correct numeric and date formats for individual cultures.</span></span>  <span data-ttu-id="ced56-135">Todas las apariciones de llaves dobles ("{{" y "}}") permanecen como llaves dobles hasta que dé formato a la cadena mediante una llamada implícita o explícita al método <xref:System.Object.ToString>.</span><span class="sxs-lookup"><span data-stu-id="ced56-135">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces until you format the string by explicitly or implicitly calling the <xref:System.Object.ToString> method.</span></span>  <span data-ttu-id="ced56-136">Todas las expresiones de interpolación incluidas se convierten en {0}, \{1\} y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="ced56-136">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   <span data-ttu-id="ced56-137">En el ejemplo siguiente se usa la reflexión para mostrar los miembros y los valores de propiedad y campo de una variable <xref:System.IFormattable> que se crea a partir de una cadena interpolada.</span><span class="sxs-lookup"><span data-stu-id="ced56-137">The following example uses reflection to display the members as well as the field and property values of an <xref:System.IFormattable> variable that is created from an interpolated string.</span></span> <span data-ttu-id="ced56-138">También pasa el <xref:System.IFormattable> variable a la <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="ced56-138">It also passes the <xref:System.IFormattable> variable to the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method.</span></span>

   [!code-vb[interpolated-strings2](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings2.vb)]  

   <span data-ttu-id="ced56-139">Tenga en cuenta que la cadena interpolada solo se puede inspeccionar mediante reflexión.</span><span class="sxs-lookup"><span data-stu-id="ced56-139">Note that the interpolated string can be inspected only by using reflection.</span></span> <span data-ttu-id="ced56-140">Si se pasa a una cadena de método de formato como <xref:System.Console.WriteLine(System.String)>, sus elementos de formato se resuelven y devuelve la cadena de resultado.</span><span class="sxs-lookup"><span data-stu-id="ced56-140">If it is passed to a string formatting method, such as <xref:System.Console.WriteLine(System.String)>, its format items are resolved and the result string returned.</span></span> 

3. <span data-ttu-id="ced56-141">Conversión de una cadena interpolada a un <xref:System.FormattableString> variable que representa una cadena de formato compuesto.</span><span class="sxs-lookup"><span data-stu-id="ced56-141">Conversion of an interpolated string to a <xref:System.FormattableString> variable that represents a composite format string.</span></span> <span data-ttu-id="ced56-142">El hecho de inspeccionar la cadena de formato compuesto y la manera en que se presenta como cadena de resultado podría ayudarle a protegerse frente a un ataque por inyección si estuviese compilando una consulta.</span><span class="sxs-lookup"><span data-stu-id="ced56-142">Inspecting the composite format string and how it renders as a result string might, for example, help you protect against an injection attack if you were building a query.</span></span> <span data-ttu-id="ced56-143">Un <xref:System.FormattableString> también incluye:</span><span class="sxs-lookup"><span data-stu-id="ced56-143">A <xref:System.FormattableString> also includes:</span></span>

      - <span data-ttu-id="ced56-144">A <xref:System.FormattableString.ToString> sobrecarga que genera una cadena para el <xref:System.Globalization.CultureInfo.CurrentCulture>.</span><span class="sxs-lookup"><span data-stu-id="ced56-144">A <xref:System.FormattableString.ToString> overload that produces a result string for the <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>
      
      - <span data-ttu-id="ced56-145">A <xref:System.FormattableString.Invariant%2A> método que genere una cadena para el <xref:System.Globalization.CultureInfo.InvariantCulture>.</span><span class="sxs-lookup"><span data-stu-id="ced56-145">A <xref:System.FormattableString.Invariant%2A> method that produces a string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span>
      
      - <span data-ttu-id="ced56-146">Un <xref:System.FormattableString.ToString(System.IFormatProvider)> método que genera una cadena de resultado de una referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="ced56-146">A <xref:System.FormattableString.ToString(System.IFormatProvider)> method that produces a result string for a specified culture.</span></span> 
  
    <span data-ttu-id="ced56-147">Todas las apariciones de llaves dobles ("{{" y "}}") permanecen como llaves dobles hasta que dé formato.</span><span class="sxs-lookup"><span data-stu-id="ced56-147">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces until you format.</span></span>  <span data-ttu-id="ced56-148">Todas las expresiones de interpolación incluidas se convierten en {0}, \{1\} y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="ced56-148">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   [!code-vb[interpolated-strings3](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings3.vb)]  

## <a name="see-also"></a><span data-ttu-id="ced56-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="ced56-149">See Also</span></span>  
<span data-ttu-id="ced56-150">f<xref:System.IFormattable?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ced56-150">f <xref:System.IFormattable?displayProperty=nameWithType></span></span>   
 <xref:System.FormattableString?displayProperty=nameWithType>  
 [<span data-ttu-id="ced56-151">Referencia del lenguaje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ced56-151">Visual Basic Language Reference</span></span>](index.md)  
 