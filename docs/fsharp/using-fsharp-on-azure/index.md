---
title: 'Uso de F # en Azure'
description: "Guía para usar los servicios de Azure con F #"
keywords: "Azure, nube, visual f#, f#, programación funcional, .NET, .NET Core"
author: sylvanc
ms.author: phcart
ms.date: 09/22/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: FAD4D11E-703A-42D4-9F72-893D9E0F569B
ms.openlocfilehash: 636604b1a0b645f13ac20d7ed85bde9abae3f9f6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="using-f-on-azure"></a>Uso de F # en Azure

F# es un lenguaje excelente para la programación en la nube y se suele usar para escribir aplicaciones web, servicios en la nube, microservicios hospedados en la nube y para el procesamiento de datos escalables.

En las secciones siguientes encontrará recursos sobre cómo usar varios servicios de Azure con F#.

> [!NOTE]
> Si un servicio de Azure determinado no aparece en este conjunto de documentos, consulte la documentación de Azure Functions o .NET para ese servicio. Algunos servicios de Azure son independientes del lenguaje y no requieren ninguna documentación específica del lenguaje y no se muestran aquí.

## <a name="using-azure-virtual-machines-with-f"></a>Uso de máquinas virtuales de Azure con F # #

Azure admite una amplia gama de configuraciones de máquina virtual (VM), vea [Linux and Azure Virtual Machines](https://azure.microsoft.com/services/virtual-machines/) (Linux y Azure Virtual Machines).

Para instalar F# en una máquina virtual para ejecución, compilación o scripting, vea [Using F# on Linux](http://fsharp.org/use/linux) (Uso de F# en Linux) y [Using F# on Windows](http://fsharp.org/use/windows) (Uso de F# en Windows).


## <a name="using-azure-functions-with-f"></a>Usar funciones de Azure con F # #

[Azure Functions](https://azure.microsoft.com/services/functions/) es una solución para ejecutar fácilmente pequeños fragmentos de código, o "funciones", en la nube. Se puede escribir simplemente el código necesario para el problema en cuestión, sin preocuparse por toda la aplicación o la infraestructura para ejecutarlo. Las funciones se conectan a los eventos en el almacenamiento de Azure y otros recursos hospedados en la nube. Los datos fluyen a las funciones de F# a través de argumentos de función. Puede usar el lenguaje que prefiera y confiar en Azure para escalar según las necesidades.

Azure Functions admite F# como lenguaje de primera clase con ejecución reactiva, eficaz y escalable de código de F#. Vea la [Referencia para desarrolladores de F# de Azure Functions](/azure/azure-functions/functions-reference-fsharp) para obtener documentación de referencia sobre cómo usar F# con Azure Functions.

Otros recursos para usar Azure Functions y F#:

* [Scale Up Azure Functions in F# Using Suave](http://blog.tamizhvendan.in/blog/2016/09/19/scale-up-azure-functions-in-f-number-using-suave/) (Escalar Azure Functions en F# con Suave)
* [How to create Azure function in F#](https://mnie.github.io/2016-09-08-AzureFunctions/) (Cómo crear Azure Functions en F#)
* [Usar el proveedor de tipo de Azure con las funciones de Azure](https://compositional-it.com/blog/2017/08-30-using-the-azure-type-provider-with-azure-functions/index.html)

## <a name="using-azure-storage-with-f"></a>Uso de almacenamiento de Azure con F # #

Azure Storage es una capa base de servicios de almacenamiento para aquellas aplicaciones modernas que necesitan durabilidad, disponibilidad y escalabilidad para satisfacer las necesidades de los clientes. Los programas de F# pueden interactuar directamente con los servicios de almacenamiento de Azure usando las técnicas que se describen en los siguientes artículos.

* [Introducción a Azure Blob Storage mediante F#](blob-storage.md)
* [Introducción a Azure File Storage mediante F#](file-storage.md)
* [Introducción a Azure Queue Storage mediante F#](queue-storage.md)
* [Introducción a Azure Table Storage mediante F#](table-storage.md)

Azure Storage también puede usarse junto con Azure Functions a través de configuración declarativa en lugar de llamadas de API explícitas. Vea [Desencadenadores y enlaces de Azure Functions para Azure Storage](/azure/azure-functions/functions-bindings-storage) que incluye ejemplos de F#.

## <a name="using-azure-app-service-with-f"></a>Usar servicio de aplicaciones de Azure con F # #

[Azure App Service](https://azure.microsoft.com/services/app-service/) es una plataforma en la nube para crear aplicaciones web y móviles eficaces que se conectan a los datos en cualquier lugar, en la nube o de forma local.

* [Ejemplo de API web de Azure de F#](https://github.com/fsprojects/azure-webapi-example)
* [Hospedaje de F# en una aplicación web en Azure](https://github.com/isaacabraham/fsharp-demonstrator)

## <a name="using-apache-spark-with-f-with-azure-hdinsight"></a>Uso de Apache Spark con F# con Azure HDInsight

[Apache Spark para Azure HDInsight](https://azure.microsoft.com/services/hdinsight/apache-spark/) es una plataforma de procesamiento de código abierto que ejecuta aplicaciones de análisis de datos a gran escala. Azure hace que Apache Spark sea fácil y rentable de implementar. Desarrolle su aplicación de Spark en F# con [Mobius](https://github.com/Microsoft/Mobius), una API de .NET para Spark.

* [Implementing Spark Apps in F# using Mobius](https://github.com/Microsoft/Mobius/blob/master/notes/spark-fsharp-mobius.md) (Implementar aplicaciones de Spark en F# con Mobius)
* [Aplicaciones de Spark de F# de ejemplo con Mobius](https://github.com/Microsoft/Mobius/tree/master/examples/fsharp)

## <a name="using-azure-documentdb-with-f"></a>Uso de documentos de Azure con F # #

[Azure DocumentDB](https://azure.microsoft.com/services/documentdb/) es un servicio NoSQL para aplicaciones altamente disponibles y distribuidas de forma global.

Azure DocumentDB se puede usar con F# de dos maneras:

1. Mediante la creación de Azure Functions de F# que reaccionen ante los cambios o los provoquen en colecciones de DocumentDB. Vea [Desencadenadores de Azure Functions para DocumentDB](/azure/azure-functions/functions-bindings-documentdb), o bien
2. Mediante el uso del [SDK de .NET para Azure](/azure/documentdb/documentdb-get-started-quickstart). Tenga en cuenta que estos ejemplos son de C#.

## <a name="using-azure-event-hubs-with-f"></a>Uso de los centros de eventos de Azure con F # #

[Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/) proporciona la ingesta de telemetría de escala de nube de sitios web, aplicaciones y dispositivos.

Azure Event Hubs se puede usar con F# de dos maneras:

1. Mediante la creación de Azure Functions de F# desencadenadas por eventos. Vea [Desencadenadores de Azure Functions para Event Hubs](/azure/azure-functions/functions-bindings-event-hubs), o bien
2. Mediante el uso del [SDK de .NET para Azure](/azure/event-hubs/event-hubs-csharp-ephcs-getstarted). Tenga en cuenta que estos ejemplos son de C#.

## <a name="using-azure-notification-hubs-with-f"></a>Usar centros de notificaciones de Azure con F # #

[Azure Notification Hubs](/azure/notification-hubs/) es una infraestructura de inserción multiplataforma y escalada que permite enviar notificaciones de inserción móviles desde cualquier back-end (en la nube o local) para cualquier plataforma móvil.

Azure Notification Hubs se puede usar con F# de dos maneras:

1. Mediante la creación de Azure Functions de F# que envían resultados a un centro de notificaciones. Vea [Desencadenadores de salida de Azure Functions para Notification Hubs](/azure/azure-functions/functions-bindings-notification-hubs), o bien
2. Mediante el uso del [SDK de .NET para Azure](https://blogs.msdn.microsoft.com/azuremobile/2014/04/08/push-notifications-using-notification-hub-and-net-backend/). Tenga en cuenta que estos ejemplos son de C#.


## <a name="implementing-webhooks-on-azure-with-f"></a>Implementación de WebHooks en Azure con F # #

Un [Webhook](https://en.wikipedia.org/wiki/Webhook) es una devolución de llamada que se desencadena a través de una solicitud web. Los Webhooks se usan en sitios como GitHub para señalizar eventos. 

Los Webhooks pueden implementarse en F# y hospedarse en Azure a través de [Azure Functions en F# con un enlace de Webhook](/azure/azure-functions/functions-bindings-http-webhook).

## <a name="using-webjobs-with-f"></a>Uso de Webjobs con F # #

[Webjobs](/azure/app-service-web/web-sites-create-web-jobs) son programas que se pueden ejecutar en la aplicación web de servicio de aplicaciones de tres maneras: bajo demanda, de forma continua o según una programación.

[Ejemplo de Webjob de F#](https://github.com/andredublin/fsharp-azure-webjob)

## <a name="implementing-timers-on-azure-with-f"></a>Implementación de temporizadores en Azure con F # #

Los desencadenadores de temporizador llaman a las funciones de acuerdo a una programación, una vez o de manera periódica.

Los temporizadores pueden implementarse en F# y hospedarse en Azure a través de un [Desencadenador de temporizador de Azure Functions en F#](/azure/azure-functions/functions-bindings-timer).

## <a name="deploying-and-managing-azure-resources-with-f-scripts"></a>Implementación y administración de recursos de Azure con scripts de F# #

Las máquinas virtuales de Azure se pueden implementar y administrar mediante programación desde scripts de F# con los paquetes y API de Microsoft.Azure.Management. Por ejemplo, vea [Introducción a las bibliotecas de administración para .NET](https://msdn.microsoft.com/library/dn722415.aspx) y [Uso de Azure Resource Manager](/azure/azure-resource-manager/resource-manager-deployment-model).

Del mismo modo, también se pueden implementar y administrar otros recursos de Azure desde scripts de F# mediante el uso de los mismos componentes. Por ejemplo, se pueden crear cuentas de almacenamiento, implementar Azure Cloud Services, crear instancias de Azure DocumentDB y administrar Azure Notifcation Hubs mediante programación desde scripts de F#.

Normalmente no es necesario usar scripts de F# para implementar y administrar recursos. Por ejemplo, los recursos de Azure también se pueden implementar directamente desde descripciones de plantillas de JSON, que pueden tener parámetros. Vea [Plantillas de Azure Resource Manager](/azure/azure-resource-manager/resource-manager-template-best-practices) con ejemplos como las [Plantillas de inicio rápido de Azure](https://azure.microsoft.com/documentation/templates/).

## <a name="other-resources"></a>Otros recursos

* [Documentación completa de todos los servicios de Azure](/azure/)
