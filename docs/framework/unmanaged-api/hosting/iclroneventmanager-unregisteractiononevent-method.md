---
title: "ICLROnEventManager::UnregisterActionOnEvent (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLROnEventManager.UnregisterActionOnEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLROnEventManager::UnregisterActionOnEvent
helpviewer_keywords:
- UnRegisterActionOnEvent method [.NET Framework hosting]
- ICLROnEventManager::UnRegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: 4c02ec37-cdf0-46b2-890e-235092741236
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5e8f922207ff347bb6570ede417fdeda71f92d0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclroneventmanagerunregisteractiononevent-method"></a><span data-ttu-id="aa24a-102">ICLROnEventManager::UnregisterActionOnEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="aa24a-102">ICLROnEventManager::UnregisterActionOnEvent Method</span></span>
<span data-ttu-id="aa24a-103">Anula el registro de un puntero de devolución de llamada registrada anteriormente para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="aa24a-103">Unregisters a previously registered callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa24a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa24a-104">Syntax</span></span>  
  
```  
HRESULT UnregisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aa24a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aa24a-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="aa24a-106">[in] Uno de los [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) valores, que indica el evento para el que se va a anular el registro del puntero de devolución de llamada descrito por `pAction`.</span><span class="sxs-lookup"><span data-stu-id="aa24a-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to unregister the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="aa24a-107">[in] Un puntero a un [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) objeto que se pasó como un parámetro a la [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="aa24a-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that was passed as a parameter to the [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa24a-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="aa24a-108">Return Value</span></span>  
  
|<span data-ttu-id="aa24a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aa24a-109">HRESULT</span></span>|<span data-ttu-id="aa24a-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa24a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aa24a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="aa24a-111">S_OK</span></span>|<span data-ttu-id="aa24a-112">`UnregisterActionOnEvent`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="aa24a-112">`UnregisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="aa24a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="aa24a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="aa24a-114">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="aa24a-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="aa24a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="aa24a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="aa24a-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="aa24a-116">The call timed out.</span></span>|  
|<span data-ttu-id="aa24a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="aa24a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="aa24a-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="aa24a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="aa24a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="aa24a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="aa24a-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="aa24a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="aa24a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="aa24a-121">E_FAIL</span></span>|<span data-ttu-id="aa24a-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="aa24a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="aa24a-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="aa24a-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="aa24a-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="aa24a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa24a-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa24a-125">Requirements</span></span>  
 <span data-ttu-id="aa24a-126">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa24a-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa24a-127">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="aa24a-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aa24a-128">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aa24a-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa24a-129">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa24a-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa24a-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa24a-130">See Also</span></span>  
 [<span data-ttu-id="aa24a-131">EClrEvent (enumeración)</span><span class="sxs-lookup"><span data-stu-id="aa24a-131">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="aa24a-132">IActionOnCLREvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa24a-132">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="aa24a-133">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa24a-133">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="aa24a-134">ICLROnEventManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa24a-134">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)