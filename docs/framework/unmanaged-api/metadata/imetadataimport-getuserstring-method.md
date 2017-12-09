---
title: "IMetaDataImport::GetUserString (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetUserString
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetUserString
helpviewer_keywords:
- IMetaDataImport::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 0fd3bb47-58b5-4083-b241-b9719df7a285
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 340d5cdfcb218f74a43ed6e88f5175a1d215a1b9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetuserstring-method"></a><span data-ttu-id="13804-102">IMetaDataImport::GetUserString (Método)</span><span class="sxs-lookup"><span data-stu-id="13804-102">IMetaDataImport::GetUserString Method</span></span>
<span data-ttu-id="13804-103">Obtiene la cadena literal representada por el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="13804-103">Gets the literal string represented by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13804-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13804-104">Syntax</span></span>  
  
```  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13804-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="13804-105">Parameters</span></span>  
 `stk`  
 <span data-ttu-id="13804-106">[in] El token de cadena para devolver la cadena asociada.</span><span class="sxs-lookup"><span data-stu-id="13804-106">[in] The String token to return the associated string for.</span></span>  
  
 `szString`  
 <span data-ttu-id="13804-107">[out] Una copia de la cadena solicitada.</span><span class="sxs-lookup"><span data-stu-id="13804-107">[out] A copy of the requested string.</span></span>  
  
 `cchString`  
 <span data-ttu-id="13804-108">[in] El tamaño máximo en caracteres anchos de solicitado `szString`.</span><span class="sxs-lookup"><span data-stu-id="13804-108">[in] The maximum size in wide characters of the requested `szString`.</span></span>  
  
 `pchString`  
 <span data-ttu-id="13804-109">[out] El tamaño en caracteres anchos de devuelto `szString`.</span><span class="sxs-lookup"><span data-stu-id="13804-109">[out] The size in wide characters of the returned `szString`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13804-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13804-110">Requirements</span></span>  
 <span data-ttu-id="13804-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13804-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13804-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="13804-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13804-113">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="13804-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13804-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13804-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13804-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="13804-115">See Also</span></span>  
 [<span data-ttu-id="13804-116">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="13804-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="13804-117">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="13804-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)