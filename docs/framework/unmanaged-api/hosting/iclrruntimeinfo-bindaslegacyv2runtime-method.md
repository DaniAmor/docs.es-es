---
title: "ICLRRuntimeInfo::BindAsLegacyV2Runtime (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 229c5483c02357054f3d2821d8e024c78887e839
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="8e619-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime (Método)</span><span class="sxs-lookup"><span data-stu-id="8e619-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="8e619-103">Enlaza el runtime actual para todos los heredados common language runtime (CLR) versión 2 activación decisiones sobre la directiva.</span><span class="sxs-lookup"><span data-stu-id="8e619-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e619-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e619-104">Syntax</span></span>  
  
```  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8e619-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8e619-105">Return Value</span></span>  
 <span data-ttu-id="8e619-106">Este método devuelve los siguientes HRESULT concretos:</span><span class="sxs-lookup"><span data-stu-id="8e619-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="8e619-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8e619-107">HRESULT</span></span>|<span data-ttu-id="8e619-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e619-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8e619-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="8e619-109">S_OK</span></span>|<span data-ttu-id="8e619-110">El enlace se realizó correctamente o este runtime ya estaba enlazado como el runtime de la directiva de activación 2 de versión CLR heredado.</span><span class="sxs-lookup"><span data-stu-id="8e619-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="8e619-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="8e619-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="8e619-112">Un runtime diferente ya se enlazó a la directiva de activación 2 de versión CLR heredada.</span><span class="sxs-lookup"><span data-stu-id="8e619-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e619-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8e619-113">Remarks</span></span>  
 <span data-ttu-id="8e619-114">Si el tiempo de ejecución actual ya está enlazado para todos los heredados CLR versión 2 activación decisiones sobre la directiva (por ejemplo, mediante la `useLegacyV2RuntimeActivationPolicy` del atributo en el [ \<Inicio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) en el archivo de configuración), este método no devuelve un resultado de error; en su lugar, el resultado es S_OK, igual que sería si el método tenía enlazar correctamente la directiva de activación heredada.</span><span class="sxs-lookup"><span data-stu-id="8e619-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e619-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e619-115">Requirements</span></span>  
 <span data-ttu-id="8e619-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e619-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e619-117">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="8e619-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8e619-118">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8e619-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e619-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e619-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e619-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e619-120">See Also</span></span>  
 [<span data-ttu-id="8e619-121">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8e619-121">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="8e619-122">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="8e619-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="8e619-123">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="8e619-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="8e619-124">\<Inicio > elemento</span><span class="sxs-lookup"><span data-stu-id="8e619-124">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)