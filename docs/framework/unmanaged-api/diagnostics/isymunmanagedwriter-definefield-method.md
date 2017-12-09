---
title: "ISymUnmanagedWriter::DefineField (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineField
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c44c4ba4a2fd8959299bce6c9f3b4dc361174922
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterdefinefield-method"></a><span data-ttu-id="6d918-102">ISymUnmanagedWriter::DefineField (Método)</span><span class="sxs-lookup"><span data-stu-id="6d918-102">ISymUnmanagedWriter::DefineField Method</span></span>
<span data-ttu-id="6d918-103">Define una única variable que no está dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="6d918-103">Defines a single variable that is not within a method.</span></span> <span data-ttu-id="6d918-104">Este método es usado por determinados campos en clases, campos de bits y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="6d918-104">This method is used for certain fields in classes, bit fields, and so on.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d918-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d918-105">Syntax</span></span>  
  
```  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d918-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6d918-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="6d918-107">[in] El tipo de metadatos o el método de token.</span><span class="sxs-lookup"><span data-stu-id="6d918-107">[in] The metadata type or method token.</span></span>  
  
 `name`  
 <span data-ttu-id="6d918-108">[in] El nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="6d918-108">[in] The field name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="6d918-109">[in] Los atributos del campo.</span><span class="sxs-lookup"><span data-stu-id="6d918-109">[in] The field attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="6d918-110">[in] Un `ULONG32` que es el tamaño, en caracteres, del búfer necesario para contener la firma del campo.</span><span class="sxs-lookup"><span data-stu-id="6d918-110">[in] A `ULONG32` that is the size, in characters, of the buffer required to contain the field signature.</span></span>  
  
 `signature`  
 <span data-ttu-id="6d918-111">[in] La matriz de firmas de campo.</span><span class="sxs-lookup"><span data-stu-id="6d918-111">[in] The array of field signatures.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="6d918-112">[in] El tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="6d918-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="6d918-113">[in] La primera dirección para la especificación de campo.</span><span class="sxs-lookup"><span data-stu-id="6d918-113">[in] The first address for the field specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="6d918-114">[in] La segunda dirección para la especificación de campo.</span><span class="sxs-lookup"><span data-stu-id="6d918-114">[in] The second address for the field specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="6d918-115">[in] La tercera dirección para la especificación de campo.</span><span class="sxs-lookup"><span data-stu-id="6d918-115">[in] The third address for the field specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d918-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6d918-116">Return Value</span></span>  
 <span data-ttu-id="6d918-117">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="6d918-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d918-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d918-118">Requirements</span></span>  
 <span data-ttu-id="6d918-119">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6d918-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d918-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d918-120">See Also</span></span>  
 [<span data-ttu-id="6d918-121">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d918-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)