---
title: /resource (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 858a216873ad9999722388e45d5de28398b27fbe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="resource-visual-basic"></a>/resource (Visual Basic)
Inserta un recurso administrado en un ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/resource:filename[,identifier[,public|private]]  
' -or-  
/res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`filename`|Obligatorio. El nombre del archivo de recursos para incrustar en el archivo de salida. De forma predeterminada, `filename` es público en el ensamblado. Ponga el nombre de archivo entre comillas ("") si contiene un espacio.|  
|`identifier`|Opcional. El nombre lógico del recurso; el nombre utilizado para cargar el recurso. El valor predeterminado es el nombre del archivo. Si lo desea, puede especificar si el recurso es público o privado en el manifiesto del ensamblado, al igual que con los siguientes: `/res:``filename.res`,`myname.res`,`public`|  
  
## <a name="remarks"></a>Comentarios  
 Use `/linkresource` para vincular un recurso a un ensamblado sin incluir el archivo de recursos en el archivo de salida.  
  
 Si `filename` es un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] archivo de recursos creado, por ejemplo, con el [Resgen.exe (generador de archivos de recursos)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) o en el entorno de desarrollo, puede tener acceso a los miembros de la <xref:System.Resources> (consulte delespaciodenombres<xref:System.Resources.ResourceManager> para obtener más información). Para obtener acceso a todos los demás recursos en tiempo de ejecución, utilice uno de los métodos siguientes: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, o <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.  
  
 La forma abreviada de `/resource` es `/res`.  
  
 Para obtener información sobre cómo establecer `/resource` en el IDE de Visual Studio, vea [administrar aplicación de recursos (. NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `In.vb` y el archivo de recursos de adjunta `Rf.resource`.  
  
```  
vbc /res:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)  
 [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)  
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
