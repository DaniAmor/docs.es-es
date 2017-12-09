---
title: ICorDebugModule2 Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2
helpviewer_keywords: ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 97259783d34babe3f0f229f5d62b3e945c0ac624
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodule2-interface1"></a><span data-ttu-id="16499-102">ICorDebugModule2 Interfaz1</span><span class="sxs-lookup"><span data-stu-id="16499-102">ICorDebugModule2 Interface1</span></span>
<span data-ttu-id="16499-103">Actúa como una extensión lógica ICorDebugModule (interfaz).</span><span class="sxs-lookup"><span data-stu-id="16499-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="16499-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="16499-104">Methods</span></span>  
  
|<span data-ttu-id="16499-105">Método</span><span class="sxs-lookup"><span data-stu-id="16499-105">Method</span></span>|<span data-ttu-id="16499-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="16499-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="16499-107">ApplyChanges (método)</span><span class="sxs-lookup"><span data-stu-id="16499-107">ApplyChanges Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|<span data-ttu-id="16499-108">Aplica los cambios en los metadatos y los cambios en el código de lenguaje intermedio (MSIL) de Microsoft a los procesos en ejecución.</span><span class="sxs-lookup"><span data-stu-id="16499-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="16499-109">GetJITCompilerFlags (método)</span><span class="sxs-lookup"><span data-stu-id="16499-109">GetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="16499-110">Obtiene las marcas que controlan la compilación just-in-time (JIT) para este `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="16499-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="16499-111">ResolveAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="16499-111">ResolveAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="16499-112">Resuelve el ensamblado al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="16499-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="16499-113">SetJITCompilerFlags (método)</span><span class="sxs-lookup"><span data-stu-id="16499-113">SetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="16499-114">Establece las marcas que controlan la compilación JIT para esta `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="16499-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="16499-115">SetJMCStatus (método)</span><span class="sxs-lookup"><span data-stu-id="16499-115">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="16499-116">Establece el estado de "sólo mi código" (JMC) de todos los métodos de todas las clases en este `ICorDebugModule2` en el valor especificado, excepto los de la `pTokens` matriz, que establece en el valor opuesto.</span><span class="sxs-lookup"><span data-stu-id="16499-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16499-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="16499-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16499-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="16499-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16499-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="16499-119">Requirements</span></span>  
 <span data-ttu-id="16499-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16499-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16499-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16499-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16499-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16499-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16499-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16499-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16499-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="16499-124">See Also</span></span>  
 [<span data-ttu-id="16499-125">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="16499-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)