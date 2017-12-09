---
title: "ICorPublish::EnumProcesses (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublish.EnumProcesses
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2c556cffa95b4d6471b8a07954ec7b93ddbdb21c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="5f7a4-102">ICorPublish::EnumProcesses (Método)</span><span class="sxs-lookup"><span data-stu-id="5f7a4-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="5f7a4-103">Obtiene un enumerador para los procesos administrados que se ejecutan en este equipo.</span><span class="sxs-lookup"><span data-stu-id="5f7a4-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f7a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f7a4-104">Syntax</span></span>  
  
```  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5f7a4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5f7a4-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="5f7a4-106">Un valor de la [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeración que especifica el tipo de proceso va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="5f7a4-106">A value of the [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="5f7a4-107">En la versión actual, solamente es válido COR_PUB_MANAGEDONLY.</span><span class="sxs-lookup"><span data-stu-id="5f7a4-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="5f7a4-108">Un puntero a la dirección de un [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instancia que es el enumerador de los procesos.</span><span class="sxs-lookup"><span data-stu-id="5f7a4-108">A pointer to the address of an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f7a4-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5f7a4-109">Remarks</span></span>  
 <span data-ttu-id="5f7a4-110">Colección del enumerador de procesos se basa en una instantánea de los procesos que se ejecutan cuando el `EnumProcesses` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="5f7a4-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="5f7a4-111">El enumerador no incluirá los procesos que finalicen antes o se inician después de `EnumProcesses` se llama.</span><span class="sxs-lookup"><span data-stu-id="5f7a4-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="5f7a4-112">El `EnumProcesses` método puede llamarse varias veces en el objeto [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instancia para crear una nueva colección actualizada de procesos.</span><span class="sxs-lookup"><span data-stu-id="5f7a4-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="5f7a4-113">Las colecciones existentes no se verán afectadas por las llamadas subsiguientes de la `EnumProcesses` método.</span><span class="sxs-lookup"><span data-stu-id="5f7a4-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f7a4-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f7a4-114">Requirements</span></span>  
 <span data-ttu-id="5f7a4-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f7a4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f7a4-116">**Encabezado:** Cordebug.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="5f7a4-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="5f7a4-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f7a4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f7a4-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f7a4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f7a4-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f7a4-119">See Also</span></span>  
 [<span data-ttu-id="5f7a4-120">ICorPublish (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f7a4-120">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)