---
title: "ICorProfilerInfo::GetAssemblyInfo (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetAssemblyInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: GetAssemblyInfo Method
helpviewer_keywords:
- GetAssemblyInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetAssemblyInfo method [.NET Framework profiling]
ms.assetid: 7a3c97c3-1e31-47b1-bf23-386785c509c4
topic_type: apiref
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f3ac5bd35d12bb4c9d9308dcdff3e1fb8385f6f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetassemblyinfo-method"></a>ICorProfilerInfo::GetAssemblyInfo (Método)
Acepta un identificador de ensamblado y devuelve el nombre del ensamblado y el identificador de su módulo de manifiesto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetAssemblyInfo(  
    [in]  AssemblyID  assemblyId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] AppDomainID *pAppDomainId,  
    [out] ModuleID    *pModuleId);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `assemblyId`  
 [in] Identificador del ensamblado.  
  
 `cchName`  
 [in] Longitud, en caracteres, de `szName`.  
  
 `pcchName`  
 [out] Puntero a la longitud total de caracteres del nombre del ensamblado.  
  
 `szName`  
 [out] Búfer de caracteres anchos proporcionado por el llamador. Cuando se devuelve la función, contiene el nombre del ensamblado.  
  
 `pAppDomainId`  
 [out] Puntero al identificador del dominio de aplicación que contiene el ensamblado.  
  
 `pModuleId`  
 [out] Puntero al identificador del módulo del manifiesto del ensamblado.  
  
## <a name="remarks"></a>Comentarios  
 Tras la devolución de este método, debe comprobar que el búfer `szName` era lo suficientemente grande como para contener el nombre completo del ensamblado. Para ello, compare el valor que señala `pcchName` con el valor del parámetro `cchName`. Si `pcchName` apunta un valor mayor que `cchName`, asigne un búfer `szName` mayor, actualice `cchName` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetAssemblyInfo`.  
  
 También tiene la opción de llamar primero a `GetAssemblyInfo` con un búfer `szName` de longitud de cero para obtener el tamaño de búfer correcto. A continuación, puede ajustar el tamaño del búfer en función del valor devuelto en `pcchName` y volver a llamar a `GetAssemblyInfo`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)
