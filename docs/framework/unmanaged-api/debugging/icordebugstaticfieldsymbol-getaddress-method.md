---
title: "ICorDebugStaticFieldSymbol::GetAddress (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 20c0c934772625d27057957d00e53fb4b485c4fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="e336a-102">ICorDebugStaticFieldSymbol::GetAddress (método)</span><span class="sxs-lookup"><span data-stu-id="e336a-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="e336a-103">Obtiene la dirección de un campo estático.</span><span class="sxs-lookup"><span data-stu-id="e336a-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e336a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e336a-104">Syntax</span></span>  
  
```  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e336a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e336a-105">Parameters</span></span>  
 <span data-ttu-id="e336a-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="e336a-106">pRVA</span></span>  
 <span data-ttu-id="e336a-107">[out] Puntero a la dirección virtual relativa (RVA) del campo estático.</span><span class="sxs-lookup"><span data-stu-id="e336a-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e336a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e336a-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e336a-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e336a-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e336a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e336a-110">Requirements</span></span>  
 <span data-ttu-id="e336a-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e336a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e336a-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e336a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e336a-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e336a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e336a-114">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e336a-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e336a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e336a-115">See Also</span></span>  
 [<span data-ttu-id="e336a-116">ICorDebugStaticFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e336a-116">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="e336a-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e336a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)