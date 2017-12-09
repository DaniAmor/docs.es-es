---
title: "ICorDebugEval2::CallParameterizedFunction (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.CallParameterizedFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 720d9c4fb9b997538ee2bb18ac7987350f6bfb57
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2callparameterizedfunction-method"></a><span data-ttu-id="f6396-102">ICorDebugEval2::CallParameterizedFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="f6396-102">ICorDebugEval2::CallParameterizedFunction Method</span></span>
<span data-ttu-id="f6396-103">Configura una llamada a la instancia de ICorDebugFunction especificado, que se puede anidar dentro de una clase cuyo constructor toma <xref:System.Type> parámetros usados, ni puede propio <xref:System.Type> parámetros.</span><span class="sxs-lookup"><span data-stu-id="f6396-103">Sets up a call to the specified ICorDebugFunction, which can be nested inside a class whose constructor takes <xref:System.Type> parameters, or can itself take <xref:System.Type> parameters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6396-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6396-104">Syntax</span></span>  
  
```  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6396-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f6396-105">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="f6396-106">[in] Un puntero a un `ICorDebugFunction` objeto que representa la función que se llamará.</span><span class="sxs-lookup"><span data-stu-id="f6396-106">[in] A pointer to an `ICorDebugFunction` object that represents the function to be called.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="f6396-107">[in] El número de argumentos que la función toma.</span><span class="sxs-lookup"><span data-stu-id="f6396-107">[in] The number of arguments that the function takes.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="f6396-108">[in] Una matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugType que representa un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="f6396-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a function argument.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="f6396-109">[in] El número de valores pasados en la función.</span><span class="sxs-lookup"><span data-stu-id="f6396-109">[in] The number of values passed in the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="f6396-110">[in] Una matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugValue que representa un valor pasado en un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="f6396-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents a value passed in a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6396-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f6396-111">Remarks</span></span>  
 <span data-ttu-id="f6396-112">`CallParameterizedFunction`es similar a [ICorDebugEval:: CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) salvo que la función puede estar dentro de una clase con parámetros de tipo, puede tomar por sí misma parámetros de tipo, o ambos.</span><span class="sxs-lookup"><span data-stu-id="f6396-112">`CallParameterizedFunction` is like [ICorDebugEval::CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) except that the function may be inside a class with type parameters, may itself take type parameters, or both.</span></span> <span data-ttu-id="f6396-113">Los argumentos de tipo se deberían proporcionar primero para la clase y, a continuación, para la función.</span><span class="sxs-lookup"><span data-stu-id="f6396-113">The type arguments should be given first for the class, and then for the function.</span></span>  
  
 <span data-ttu-id="f6396-114">Si la función está en un dominio de aplicación diferente, se producirá una transición.</span><span class="sxs-lookup"><span data-stu-id="f6396-114">If the function is in a different application domain, a transition will occur.</span></span> <span data-ttu-id="f6396-115">Sin embargo, todos los argumentos de tipo y el valor deben estar en el dominio de aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="f6396-115">However, all type and value arguments must be in the target application domain.</span></span>  
  
 <span data-ttu-id="f6396-116">Evaluación de la función puede realizarse solo en escenarios limitados.</span><span class="sxs-lookup"><span data-stu-id="f6396-116">Function evaluation can be performed only in limited scenarios.</span></span> <span data-ttu-id="f6396-117">Si `CallParameterizedFunction` o `ICorDebugEval::CallFunction` se produce un error, el HRESULT devuelto indicará el motivo más general posible error.</span><span class="sxs-lookup"><span data-stu-id="f6396-117">If `CallParameterizedFunction` or `ICorDebugEval::CallFunction` fails, the returned HRESULT will indicate the most general possible reason for failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6396-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f6396-118">Requirements</span></span>  
 <span data-ttu-id="f6396-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6396-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6396-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6396-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6396-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6396-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6396-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6396-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>