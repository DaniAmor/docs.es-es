---
title: "ISymENCUnmanagedMethod::GetLineFromOffset (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymENCUnmanagedMethod.GetLineFromOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymENCUnmanagedMethod::GetLineFromOffset
helpviewer_keywords:
- GetLineFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetLineFromOffset method [.NET Framework debugging]
ms.assetid: cc09bad2-fb34-4d13-a521-6ec7b1a1d915
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2f18357b3a58a5409da93d4d2491997e9ca1cc70
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a><span data-ttu-id="df66e-102">ISymENCUnmanagedMethod::GetLineFromOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="df66e-102">ISymENCUnmanagedMethod::GetLineFromOffset Method</span></span>
<span data-ttu-id="df66e-103">Obtiene la información de línea asociada con un desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="df66e-103">Gets the line information associated with an offset.</span></span> <span data-ttu-id="df66e-104">Si el parámetro de desplazamiento (`dwOffset`) no es un punto de secuencia, este método obtiene la información de línea asociada con el desplazamiento anterior.</span><span class="sxs-lookup"><span data-stu-id="df66e-104">If the offset parameter (`dwOffset`) is not a sequence point, this method gets the line information associated with the previous offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df66e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df66e-105">Syntax</span></span>  
  
```  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df66e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="df66e-106">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="df66e-107">[in] Un `ULONG32` que contiene el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="df66e-107">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `pline`  
 <span data-ttu-id="df66e-108">[out] Un puntero a un `ULONG32` que recibe la línea.</span><span class="sxs-lookup"><span data-stu-id="df66e-108">[out] A pointer to a `ULONG32` that receives the line.</span></span>  
  
 `pcolumn`  
 <span data-ttu-id="df66e-109">[out] Un puntero a un `ULONG32` que recibe la columna.</span><span class="sxs-lookup"><span data-stu-id="df66e-109">[out] A pointer to a `ULONG32` that receives the column.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="df66e-110">[out] Un puntero a un `ULONG32` que recibe la línea de finalización.</span><span class="sxs-lookup"><span data-stu-id="df66e-110">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
 `pendColumn`  
 <span data-ttu-id="df66e-111">[out] Un puntero a un `ULONG32` que recibe la columna final.</span><span class="sxs-lookup"><span data-stu-id="df66e-111">[out] A pointer to a `ULONG32` that receives the end column.</span></span>  
  
 `pdwStartOffset`  
 <span data-ttu-id="df66e-112">[out] Un puntero a un `ULONG32` que recibe el punto de secuencia asociado.</span><span class="sxs-lookup"><span data-stu-id="df66e-112">[out] A pointer to a `ULONG32` that receives the associated sequence point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df66e-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="df66e-113">Return Value</span></span>  
 <span data-ttu-id="df66e-114">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="df66e-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df66e-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df66e-115">Requirements</span></span>  
 <span data-ttu-id="df66e-116">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="df66e-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df66e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="df66e-117">See Also</span></span>  
 [<span data-ttu-id="df66e-118">ISymENCUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="df66e-118">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)