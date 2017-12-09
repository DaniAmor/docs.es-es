---
title: "ICorProfilerCallback::ExceptionUnwindFinallyEnter (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionUnwindFinallyEnter
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionUnwindFinallyEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter method [.NET Framework profiling]
- ExceptionUnwindFinallyEnter method [.NET Framework profiling]
ms.assetid: c7fab986-b69f-4ec8-b7b7-91dcfc239cd0
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ec1b05e67a10f5e7b22a950d1dec24528b5c4914
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="53a45-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="53a45-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="53a45-103">Notifica al generador de perfiles que la fase de desenredo de la excepción está accediendo al control un `finally` cláusula incluida en la función especificada.</span><span class="sxs-lookup"><span data-stu-id="53a45-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53a45-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53a45-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53a45-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="53a45-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="53a45-106">[in] El identificador de la función que contiene el `finally` cláusula.</span><span class="sxs-lookup"><span data-stu-id="53a45-106">[in] The ID of the function that contains the `finally` clause.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53a45-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="53a45-107">Remarks</span></span>  
 <span data-ttu-id="53a45-108">El generador de perfiles no debe bloquearse en su implementación de este método porque la pila no puede estar en un estado que permita la recopilación de elementos no utilizados y, por lo tanto, no se puede habilitar la colección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="53a45-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="53a45-109">Si el generador de perfiles se bloquea aquí y se intenta realizar la recolección de elementos, el tiempo de ejecución se bloqueará hasta que devuelve esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="53a45-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="53a45-110">Implementación del generador de perfiles de este método no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="53a45-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53a45-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53a45-111">Requirements</span></span>  
 <span data-ttu-id="53a45-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53a45-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53a45-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="53a45-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="53a45-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53a45-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53a45-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53a45-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53a45-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="53a45-116">See Also</span></span>  
 [<span data-ttu-id="53a45-117">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="53a45-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="53a45-118">GetNotifiedExceptionClauseInfo (método)</span><span class="sxs-lookup"><span data-stu-id="53a45-118">GetNotifiedExceptionClauseInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)  
 [<span data-ttu-id="53a45-119">ExceptionUnwindFinallyLeave (método)</span><span class="sxs-lookup"><span data-stu-id="53a45-119">ExceptionUnwindFinallyLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)