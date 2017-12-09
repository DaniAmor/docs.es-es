---
title: 'Tutorial: obtener acceso a un servicio Web mediante proveedores de tipo (F #)'
description: "Obtenga información acerca de cómo usar el proveedor de tipo de lenguaje de descripción de servicios Web (WSDL) disponible en F # 3.0 para tener acceso a un servicio de WSDL."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 63374fa9-8fb8-43ac-bcb9-ef2290d9f851
ms.openlocfilehash: 06d955033d465cf58af05f483d21175f90d1777a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-accessing-a-web-service-by-using-type-providers"></a><span data-ttu-id="ea230-104">Tutorial: Obtener acceso a un servicio Web mediante proveedores de tipos</span><span class="sxs-lookup"><span data-stu-id="ea230-104">Walkthrough: Accessing a Web Service by Using Type Providers</span></span>

> [!NOTE]
<span data-ttu-id="ea230-105">Esta guía se escribió para F # 3.0 y se actualizará.</span><span class="sxs-lookup"><span data-stu-id="ea230-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="ea230-106">Vea [FSharp.Data](http://fsharp.github.io/FSharp.Data/) para obtener información sobre los proveedores de tipos multiplataforma actualizados.</span><span class="sxs-lookup"><span data-stu-id="ea230-106">See [FSharp.Data](http://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="ea230-107">Los vínculos de referencia de API le llevará a MSDN.</span><span class="sxs-lookup"><span data-stu-id="ea230-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="ea230-108">La referencia de API de docs.microsoft.com no está completa.</span><span class="sxs-lookup"><span data-stu-id="ea230-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="ea230-109">En este tutorial se muestra cómo usar el proveedor de tipo de lenguaje de descripción de servicios Web (WSDL) que está disponible en F # 3.0 para tener acceso a un servicio de WSDL.</span><span class="sxs-lookup"><span data-stu-id="ea230-109">This walkthrough shows you how to use the Web Services Description Language (WSDL) type provider that is available in F# 3.0 to access a WSDL service.</span></span> <span data-ttu-id="ea230-110">En otros lenguajes. NET, generar el código para acceder al servicio web que realiza la llamada svcutil.exe o al agregar una referencia web en, por ejemplo, un proyecto de C# para obtener Visual Studio para llamar a svcutil.exe para usted.</span><span class="sxs-lookup"><span data-stu-id="ea230-110">In other .NET languages, you generate the code to access the web service by calling svcutil.exe, or by adding a web reference in, for example, a C# project to get Visual Studio to call svcutil.exe for you.</span></span> <span data-ttu-id="ea230-111">En F #, tiene la opción adicional de usar el proveedor de tipos WSDL, por lo que tan pronto como se escribe el código que crea el tipo WsdlService, los tipos se generan y estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="ea230-111">In F#, you have the additional option of using the WSDL type provider, so as soon as you write the code that creates the WsdlService type, the types are generated and become available.</span></span> <span data-ttu-id="ea230-112">Este proceso se basa en el servicio que está disponible cuando se escribe el código.</span><span class="sxs-lookup"><span data-stu-id="ea230-112">This process relies on the service being available when you are writing the code.</span></span>

<span data-ttu-id="ea230-113">En este tutorial se muestran las tareas siguientes.</span><span class="sxs-lookup"><span data-stu-id="ea230-113">This walkthrough illustrates the following tasks.</span></span> <span data-ttu-id="ea230-114">Debe completarlos en el orden para el tutorial sea correcta:</span><span class="sxs-lookup"><span data-stu-id="ea230-114">You must complete them in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="ea230-115">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="ea230-115">Creating the project</span></span>
<br />

- <span data-ttu-id="ea230-116">Configurar el proveedor de tipos</span><span class="sxs-lookup"><span data-stu-id="ea230-116">Configuring the type provider</span></span>
<br />

- <span data-ttu-id="ea230-117">Llamar al servicio web y procesar los resultados</span><span class="sxs-lookup"><span data-stu-id="ea230-117">Calling the web service, and processing the results</span></span>
<br />


## <a name="creating-the-project"></a><span data-ttu-id="ea230-118">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="ea230-118">Creating the project</span></span>
<span data-ttu-id="ea230-119">En el paso, cree un proyecto y agregar las referencias adecuadas para usar un proveedor de tipo WSDL.</span><span class="sxs-lookup"><span data-stu-id="ea230-119">In the step, you create a project and add the appropriate references to use a WSDL type provider.</span></span>


#### <a name="to-create-and-set-up-an-f-project"></a><span data-ttu-id="ea230-120">Para crear y configurar un proyecto de F#</span><span class="sxs-lookup"><span data-stu-id="ea230-120">To create and set up an F# project</span></span>

1. <span data-ttu-id="ea230-121">Abra un nuevo proyecto de aplicación de consola de F #.</span><span class="sxs-lookup"><span data-stu-id="ea230-121">Open a new F# Console Application project.</span></span>
<br />

2. <span data-ttu-id="ea230-122">En **el Explorador de soluciones**, abra el menú contextual para el proyecto **referencia** nodo y, a continuación, elija **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="ea230-122">In **Solution Explorer**, open the shortcut menu for the project's **Reference** node, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="ea230-123">En el **ensamblados** área, elija **Framework**y, a continuación, en la lista de ensamblados disponibles, elija **System.Runtime.Serialization** y  **System.ServiceModel**.</span><span class="sxs-lookup"><span data-stu-id="ea230-123">In the **Assemblies** area, choose **Framework**, and then, in the list of available assemblies, choose **System.Runtime.Serialization** and **System.ServiceModel**.</span></span>
<br />

4. <span data-ttu-id="ea230-124">En el **ensamblados** área, elija **extensiones**.</span><span class="sxs-lookup"><span data-stu-id="ea230-124">In the **Assemblies** area, choose **Extensions**.</span></span>
<br />

5. <span data-ttu-id="ea230-125">En la lista de ensamblados disponibles, elija **FSharp.Data.TypeProviders**y, a continuación, elija la **Aceptar** botón para agregar referencias a estos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ea230-125">In the list of available assemblies, choose **FSharp.Data.TypeProviders**, and then choose the **OK** button to add references to these assemblies.</span></span>
<br />

## <a name="configuring-the-type-provider"></a><span data-ttu-id="ea230-126">Configurar el proveedor de tipos</span><span class="sxs-lookup"><span data-stu-id="ea230-126">Configuring the type provider</span></span>
<span data-ttu-id="ea230-127">En este paso, usa el proveedor de tipos WSDL para generar tipos para el servicio web TerraServer.</span><span class="sxs-lookup"><span data-stu-id="ea230-127">In this step, you use the WSDL type provider to generate types for the TerraServer web service.</span></span>


#### <a name="to-configure-the-type-provider-and-generate-types"></a><span data-ttu-id="ea230-128">Para configurar el proveedor de tipo y generar tipos</span><span class="sxs-lookup"><span data-stu-id="ea230-128">To configure the type provider and generate types</span></span>

1. <span data-ttu-id="ea230-129">Agregue la siguiente línea de código para abrir el espacio de nombres del proveedor de tipo.</span><span class="sxs-lookup"><span data-stu-id="ea230-129">Add the following line of code to open the type provider namespace.</span></span>
<br />

```fsharp
open System
open System.ServiceModel
open Microsoft.FSharp.Linq
open Microsoft.FSharp.Data.TypeProviders
```

2. <span data-ttu-id="ea230-130">Agregue la siguiente línea de código para invocar el proveedor de tipos con un servicio web.</span><span class="sxs-lookup"><span data-stu-id="ea230-130">Add the following line of code to invoke the type provider with a web service.</span></span> <span data-ttu-id="ea230-131">En este ejemplo, utilice el servicio web TerraServer.</span><span class="sxs-lookup"><span data-stu-id="ea230-131">In this example, use the TerraServer web service.</span></span>
<br />

```fsharp
type TerraService = WsdlService<" HYPERLINK "http://terraserver-usa.com/TerraService2.asmx?WSDL" http://msrmaps.com/TerraService2.asmx?WSDL">
```

  <span data-ttu-id="ea230-132">Si el URI del servicio está mal escrito o si el propio servicio está inactivo o no está funcionando, aparece un subrayado ondulado de color rojo debajo de esta línea de código.</span><span class="sxs-lookup"><span data-stu-id="ea230-132">A red squiggle appears under this line of code if the service URI is misspelled or if the service itself is down or isn’t performing.</span></span> <span data-ttu-id="ea230-133">Si eliges el código, un mensaje de error describe el problema.</span><span class="sxs-lookup"><span data-stu-id="ea230-133">If you point to the code, an error message describes the problem.</span></span> <span data-ttu-id="ea230-134">Puede obtener la misma información en el **lista de errores** ventana o en la **ventana de salida** después de la compilación.</span><span class="sxs-lookup"><span data-stu-id="ea230-134">You can find the same information in the **Error List** window or in the **Output Window** after you build.</span></span>
<br />  <span data-ttu-id="ea230-135">Hay dos maneras de especificar valores de configuración para una conexión de WSDL, mediante el archivo app.config para el proyecto, o mediante los parámetros de tipo estático en la declaración del proveedor de tipo.</span><span class="sxs-lookup"><span data-stu-id="ea230-135">There are two ways to specify configuration settings for a WSDL connection, by using the app.config file for the project, or by using the static type parameters in the type provider declaration.</span></span> <span data-ttu-id="ea230-136">Puede utilizar svcutil.exe para generar elementos del archivo de configuración adecuado.</span><span class="sxs-lookup"><span data-stu-id="ea230-136">You can use svcutil.exe to generate appropriate configuration file elements.</span></span> <span data-ttu-id="ea230-137">Para obtener más información acerca de cómo utilizar svcutil.exe para generar información de configuración para un servicio web, consulte [ServiceModel Metadata Utility Tool &#40; Svcutil.exe &#41; ](https://msdn.microsoft.com/library/aa347733.aspx).</span><span class="sxs-lookup"><span data-stu-id="ea230-137">For more information about using svcutil.exe to generate configuration information for a web service, see [ServiceModel Metadata Utility Tool &#40;Svcutil.exe&#41;](https://msdn.microsoft.com/library/aa347733.aspx).</span></span> <span data-ttu-id="ea230-138">Para obtener una descripción completa de los parámetros de tipo estático para el proveedor de tipos WSDL, vea [proveedor de tipos WsdlService](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="ea230-138">For a full description of the static type parameters for the WSDL type provider, see [WsdlService Type Provider](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d).</span></span>
<br />

## <a name="calling-the-web-service-and-processing-the-results"></a><span data-ttu-id="ea230-139">Llamar al servicio web y procesar los resultados</span><span class="sxs-lookup"><span data-stu-id="ea230-139">Calling the web service, and processing the results</span></span>
<span data-ttu-id="ea230-140">Cada servicio web tiene su propio conjunto de tipos que se utilizan como parámetros para sus llamadas de método.</span><span class="sxs-lookup"><span data-stu-id="ea230-140">Each web service has its own set of types that are used as parameters for its method calls.</span></span> <span data-ttu-id="ea230-141">En este paso, preparar estos parámetros, llamar a un método web y procesar la información que devuelve.</span><span class="sxs-lookup"><span data-stu-id="ea230-141">In this step, you prepare these parameters, call a web method, and process the information that it returns.</span></span>


#### <a name="to-call-the-web-service-and-process-the-results"></a><span data-ttu-id="ea230-142">Para llamar al servicio web y procesar los resultados</span><span class="sxs-lookup"><span data-stu-id="ea230-142">To call the web service, and process the results</span></span>

1. <span data-ttu-id="ea230-143">El servicio web podría agotar tiempo de espera o deje de funcionar, por lo que debe incluir la llamada del servicio web en un bloque de control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="ea230-143">The web service might time out or stop functioning, so you should include the web service call in an exception handling block.</span></span> <span data-ttu-id="ea230-144">Escribir el código siguiente para intentar obtener datos desde el servicio web.</span><span class="sxs-lookup"><span data-stu-id="ea230-144">Write the following code to try to get data from the web service.</span></span>
<br />

```fsharp
try
  let terraClient = TerraService.GetTerraServiceSoap ()
  let myPlace = new TerraService.ServiceTypes.msrmaps.com.Place(City = "Redmond", State = "Washington", Country = "United States")
  let myLocation = terraClient.ConvertPlaceToLonLatPt(myPlace)
  printfn "Redmond Latitude: %f Longitude: %f" (myLocation.Lat) (myLocation.Lon)
with
| :? ServerTooBusyException as exn ->
  let innerMessage =
    match (exn.InnerException) with
    | null -> ""
    | innerExn -> innerExn.Message
  printfn "An exception occurred:\n %s\n %s" exn.Message innerMessage
| exn -> printfn "An exception occurred: %s" exn.Message
```

<span data-ttu-id="ea230-145">Tenga en cuenta que crear los tipos de datos que son necesarios para el servicio web, como **lugar** y **ubicación**, como un tipo de los tipos anidados en el WsdlService **TerraService**.</span><span class="sxs-lookup"><span data-stu-id="ea230-145">Notice that you create the data types that are needed for the web service, such as **Place** and **Location**, as nested types under the WsdlService type **TerraService**.</span></span>
<br />


## <a name="see-also"></a><span data-ttu-id="ea230-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea230-146">See Also</span></span>
[<span data-ttu-id="ea230-147">Proveedor de tipos WsdlService</span><span class="sxs-lookup"><span data-stu-id="ea230-147">WsdlService Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d)

[<span data-ttu-id="ea230-148">Proveedores de tipos</span><span class="sxs-lookup"><span data-stu-id="ea230-148">Type Providers</span></span>](index.md)