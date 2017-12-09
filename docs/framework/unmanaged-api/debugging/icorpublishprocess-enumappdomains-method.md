---
title: "ICorPublishProcess::EnumAppDomains (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcess.EnumAppDomains
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcess::EnumAppDomains
helpviewer_keywords:
- EnumAppDomains method [.NET Framework debugging]
- ICorPublishProcess::EnumAppDomains method [.NET Framework debugging]
ms.assetid: 7da621fc-e7d0-4c00-9439-5c93619d7414
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 09d6a75fa5c0562f466dba45707795ef7fd161db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishprocessenumappdomains-method"></a><span data-ttu-id="2efdc-102">ICorPublishProcess::EnumAppDomains (Método)</span><span class="sxs-lookup"><span data-stu-id="2efdc-102">ICorPublishProcess::EnumAppDomains Method</span></span>
<span data-ttu-id="2efdc-103">Obtiene un enumerador para los dominios de aplicación en el proceso que se hace referencia este [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2efdc-103">Gets an enumerator for the application domains in the process that is referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2efdc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2efdc-104">Syntax</span></span>  
  
```  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2efdc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2efdc-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="2efdc-106">[out] Un puntero a la dirección de un [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instancia que permite recorrer en iteración la colección de dominios de aplicación en este proceso.</span><span class="sxs-lookup"><span data-stu-id="2efdc-106">[out] A pointer to the address of an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that allows iteration through the collection of application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2efdc-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2efdc-107">Remarks</span></span>  
 <span data-ttu-id="2efdc-108">La lista de dominios de aplicación se basa en una instantánea de los dominios de aplicación que existen cuando la `EnumAppDomains` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="2efdc-108">The list of application domains is based on a snapshot of the application domains that exist when the `EnumAppDomains` method is called.</span></span> <span data-ttu-id="2efdc-109">Este método puede llamarse varias veces para crear una nueva lista actualizada.</span><span class="sxs-lookup"><span data-stu-id="2efdc-109">This method may be called more than once to create a new up-to-date list.</span></span> <span data-ttu-id="2efdc-110">Las llamadas posteriores de este método no afectarán a las listas existentes.</span><span class="sxs-lookup"><span data-stu-id="2efdc-110">Existing lists will not be affected by subsequent calls of this method.</span></span>  
  
 <span data-ttu-id="2efdc-111">Si se ha finalizado el proceso, `EnumAppDomains` se producirá un error con un valor HRESULT de CORDBG_E_PROCESS_TERMINATED.</span><span class="sxs-lookup"><span data-stu-id="2efdc-111">If the process has been terminated, `EnumAppDomains` will fail with an HRESULT value of CORDBG_E_PROCESS_TERMINATED.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2efdc-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2efdc-112">Requirements</span></span>  
 <span data-ttu-id="2efdc-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2efdc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2efdc-114">**Encabezado:** Cordebug.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="2efdc-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2efdc-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2efdc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2efdc-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2efdc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2efdc-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2efdc-117">See Also</span></span>  
 [<span data-ttu-id="2efdc-118">ICorPublishProcess (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2efdc-118">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)