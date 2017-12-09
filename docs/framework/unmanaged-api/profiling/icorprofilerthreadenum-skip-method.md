---
title: "ICorProfilerThreadEnum::Skip (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerThreadEnum.Skip
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerThreadEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Skip method [.NET Framework profiling]
ms.assetid: acb8b029-4a96-4ed7-ae3c-310204e5ceea
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f492a455165f3b49994beb3220334e2932bf214c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="a7694-102">ICorProfilerThreadEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="a7694-102">ICorProfilerThreadEnum::Skip Method</span></span>
<span data-ttu-id="a7694-103">Desplaza el cursor del enumerador desde su posición actual para omitir el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="a7694-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7694-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7694-104">Syntax</span></span>  
  
```  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7694-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a7694-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a7694-106">[in] El número de elementos que se van a omitir.</span><span class="sxs-lookup"><span data-stu-id="a7694-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7694-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a7694-107">Return Value</span></span>  
 <span data-ttu-id="a7694-108">Este método devuelve los siguientes HRESULT específicos así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="a7694-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a7694-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a7694-109">HRESULT</span></span>|<span data-ttu-id="a7694-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7694-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a7694-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a7694-111">S_OK</span></span>|<span data-ttu-id="a7694-112">`celt`elementos omitidos.</span><span class="sxs-lookup"><span data-stu-id="a7694-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="a7694-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a7694-113">S_FALSE</span></span>|<span data-ttu-id="a7694-114">Menos de `celt` elementos omitidos, lo que indica que no hay ningún elemento más.</span><span class="sxs-lookup"><span data-stu-id="a7694-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7694-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a7694-115">Remarks</span></span>  
 <span data-ttu-id="a7694-116">La nueva posición del cursor de este enumerador es (posición actual) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="a7694-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7694-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a7694-117">Requirements</span></span>  
 <span data-ttu-id="a7694-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7694-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7694-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7694-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7694-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7694-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7694-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7694-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7694-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7694-122">See Also</span></span>  
 [<span data-ttu-id="a7694-123">ICorProfilerThreadEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7694-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="a7694-124">Interfaces de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a7694-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)