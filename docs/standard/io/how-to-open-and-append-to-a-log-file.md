---
title: "Cómo: Abrir y anexar a un archivo de registro"
ms.custom: 
ms.date: 03/30/2017
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
- log files, opening
- streams, opening and appending to log file
- log files, appending to
- I/O [.NET Framework], log files
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 60c31339231405a1cbbb98dae37d36ad3c3709c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-open-and-append-to-a-log-file"></a>Cómo: Abrir y anexar a un archivo de registro
<xref:System.IO.StreamWriter>y <xref:System.IO.StreamReader> escriben y leen caracteres de secuencias. El siguiente código en el ejemplo se abre la `log.txt` para la entrada de archivo, o crea el archivo si aún no existe y anexa información al final del archivo. El contenido del archivo, a continuación, se escribe en la salida estándar para su presentación. Como alternativa a este ejemplo, la información se puede almacenar como una sola cadena o una matriz de cadenas y el <xref:System.IO.File.WriteAllText%2A> o <xref:System.IO.File.WriteAllLines%2A> método podría utilizarse para lograr la misma funcionalidad.  
  
> [!NOTE]
>  Usuarios de Visual Basic pueden optar por usar los métodos y propiedades proporcionadas por el <xref:Microsoft.VisualBasic.Logging.Log> clase o <xref:Microsoft.VisualBasic.FileIO.FileSystem> clase para crear o escribir en archivos de registro.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO.StreamWriter>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType>  
 <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 [Enumerar directorios y archivos](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [Cómo: Leer y escribir en un archivo de datos recién creado](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [Cómo: Leer texto de un archivo](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [Cómo: Escribir texto en un archivo](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [Cómo: Leer caracteres de una cadena](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [Cómo: Escribir caracteres en una cadena](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [E/S de archivos y secuencias](../../../docs/standard/io/index.md)
