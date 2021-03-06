---
title: "Cómo: guardar zonas horarias en un recurso incrustado"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], saving
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 93dfc62df1c1d68e09a3734402924bbac1a074cb
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a>Cómo: guardar zonas horarias en un recurso incrustado

Una aplicación compatible con la zona horaria a menudo requiere la presencia de una zona horaria determinada. Sin embargo, dado que la disponibilidad de persona <xref:System.TimeZoneInfo> objetos depende de la información almacenada en el registro del sistema local, las zonas horarias disponibles habitualmente incluso puede que falte. Además, crea una instancia información sobre zonas horarias personalizadas mediante el uso de la <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método no se almacena con otra información de zona horaria en el registro. Para asegurarse de que estas zonas horarias están disponibles cuando se necesitan, puede guardarlos serializando ellos y restaurarlas más adelante mediante la deserialización de ellos.

Por lo general, serializar un <xref:System.TimeZoneInfo> objeto aparece además de la aplicación tenga en cuenta la zona horaria. Según el almacén de datos que se usa para contener serializado <xref:System.TimeZoneInfo> objetos, se pueden serializar los datos de zona horaria como parte de una rutina de instalación o el programa de instalación (por ejemplo, cuando los datos se almacenan en una clave del registro de aplicación), o como parte de una rutina de la utilidad que se ejecuta antes de que se compila la aplicación final (por ejemplo, cuando los datos serializados se almacenan en un archivo de recursos (.resx) XML. NET).

Además de un archivo de recursos que se compila con la aplicación, otros almacenes de datos pueden utilizarse para obtener información de zona horaria. Entre ellas se incluyen las siguientes:

* El registro. Tenga en cuenta que una aplicación debe utilizar las subclaves de su propia clave de aplicación para almacenar datos de zona horaria personalizada en lugar de utilizar las subclaves de HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.

* Archivos de configuración.

* Otros archivos del sistema.

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a>Para guardar una zona horaria al serializar en un archivo .resx

1. Recuperar una zona horaria existente o cree una nueva zona horaria.

   Para recuperar una zona horaria existente, vea [Cómo: obtener acceso a los objetos de zona hora local y UTC predefinidos](../../../docs/standard/datetime/access-utc-and-local.md) y [Cómo: crear una instancia de un objeto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md).

   Para crear una nueva zona horaria, llame a una de las sobrecargas de los <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método. Para obtener más información, consulte [Cómo: crear zonas horarias sin reglas de ajuste](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) y [Cómo: crear zonas horarias con reglas de ajuste](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).

2. Llame a la <xref:System.TimeZoneInfo.ToSerializedString%2A> método para crear una cadena que contiene los datos de la zona horaria.

3. Crear una instancia de un <xref:System.IO.StreamWriter> objeto proporcionando el nombre y, opcionalmente, la ruta de acceso del archivo .resx en el <xref:System.IO.StreamWriter> constructor de clase.

4. Crear una instancia de un <xref:System.Resources.ResXResourceWriter> objeto pasando el <xref:System.IO.StreamWriter> el objeto a la <xref:System.Resources.ResXResourceWriter> constructor de clase.

5. Pase la zona horaria serializa la cadena a la <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> método.

6. Llame al método <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>.

7. Llame al método <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>.

8. Cerrar la <xref:System.IO.StreamWriter> objeto mediante una llamada a su <xref:System.IO.StreamWriter.Close%2A> método.

9. Agregue el archivo .resx generado al proyecto de Visual Studio de la aplicación.

10. Mediante el **propiedades** ventana de Visual Studio, asegúrese de que el archivo .resx **acción de compilación** propiedad está establecida en **recurso incrustado**.

## <a name="example"></a>Ejemplo

El ejemplo siguiente se serializa un <xref:System.TimeZoneInfo> objeto que representa la hora estándar Central y un <xref:System.TimeZoneInfo> objeto que representa el Palmer, en vez de Antártida, a un archivo de recursos XML de .NET denominado SerializedTimeZones.resx. Hora estándar central suele estar definido en el registro; Palmer, Antártida en, es una zona horaria personalizada.

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

Este ejemplo, se serializa <xref:System.TimeZoneInfo> objetos para que estén disponibles en un archivo de recursos en tiempo de compilación.

Dado que el <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> método agrega información de encabezado completa a un archivo de recursos XML de .NET, no se puede utilizar para agregar recursos a un archivo existente. En el ejemplo se encarga de ello buscando el archivo SerializedTimeZones.resx y, si existe, almacenar todos sus recursos distinto de las dos zonas horarias serializan en un tipo genérico <xref:System.Collections.Generic.Dictionary%602> objeto. A continuación, se elimina el archivo existente y los recursos existentes se agregan a un nuevo archivo SerializedTimeZones.resx. Los datos de zona horaria serializada también se agregan a este archivo.

La clave (o **nombre**) campos de recursos no deben contener espacios incrustados. El <xref:System.String.Replace%28System.String%2CSystem.String%29> método se invoca para quitar todos los espacios en los identificadores de zona horaria antes de que se asignan al archivo de recursos.

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

* Que se agregará al proyecto una referencia a System.Windows.Forms.dll y System.Core.dll.

* Que se importarán los espacios de nombres siguientes:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Vea también

[Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
[información general de la zona horaria](../../../docs/standard/datetime/time-zone-overview.md)
[Cómo: restaurar zonas horarias de un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
