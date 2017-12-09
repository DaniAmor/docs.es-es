---
title: "ICLRValidator::Validate (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRValidator.Validate
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRValidator::Validate
helpviewer_keywords:
- Validate method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::Validate method [.NET Framework hosting]
ms.assetid: 0b1b432a-d234-4002-839b-81366c3a8bdc
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 50915201b6e57bd116b80f067f01b8862372bc5b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="b8430-102">ICLRValidator::Validate (Método)</span><span class="sxs-lookup"><span data-stu-id="b8430-102">ICLRValidator::Validate Method</span></span>
<span data-ttu-id="b8430-103">Valida el archivo ejecutable portable (PE) o lenguaje intermedio de Microsoft (MSIL) en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="b8430-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8430-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8430-104">Syntax</span></span>  
  
```  
HRESULT Validate (  
    [in] IVEHandler        *veh,  
    [in] unsigned long      ulAppDomainId,  
    [in] unsigned long      ulFlags,  
    [in] unsigned long      ulMaxError,  
    [in] unsigned long      token,  
    [in] LPWSTR             fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long      ulSize  
);      
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8430-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b8430-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="b8430-106">[in] Un puntero a un `IVEHandler` instancia que controla los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="b8430-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="b8430-107">[in] El identificador actual <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="b8430-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="b8430-108">[in] Una combinación de [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) valores, que indica el tipo de validación que se debe realizar.</span><span class="sxs-lookup"><span data-stu-id="b8430-108">[in] A combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="b8430-109">[in] El número máximo de errores permitido antes de salir de la validación.</span><span class="sxs-lookup"><span data-stu-id="b8430-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="b8430-110">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="b8430-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="b8430-111">[in] El nombre del archivo que se debe validar.</span><span class="sxs-lookup"><span data-stu-id="b8430-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="b8430-112">[in] Un puntero al búfer del archivo.</span><span class="sxs-lookup"><span data-stu-id="b8430-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="b8430-113">[in] El tamaño, en bytes, del archivo que se debe validar.</span><span class="sxs-lookup"><span data-stu-id="b8430-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8430-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b8430-114">Return Value</span></span>  
  
|<span data-ttu-id="b8430-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b8430-115">HRESULT</span></span>|<span data-ttu-id="b8430-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8430-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b8430-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="b8430-117">S_OK</span></span>|<span data-ttu-id="b8430-118">`Validate`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b8430-118">`Validate` returned successfully.</span></span>|  
|<span data-ttu-id="b8430-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b8430-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b8430-120">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b8430-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b8430-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b8430-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b8430-122">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b8430-122">The call timed out.</span></span>|  
|<span data-ttu-id="b8430-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b8430-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b8430-124">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b8430-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b8430-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b8430-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b8430-126">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="b8430-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b8430-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b8430-127">E_FAIL</span></span>|<span data-ttu-id="b8430-128">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="b8430-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b8430-129">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="b8430-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b8430-130">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b8430-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b8430-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8430-131">Requirements</span></span>  
 <span data-ttu-id="b8430-132">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8430-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8430-133">**Encabezado:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="b8430-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="b8430-134">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b8430-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8430-135">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8430-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8430-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8430-136">See Also</span></span>  
 [<span data-ttu-id="b8430-137">ICLRValidator (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8430-137">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)