---
title: "Función InheritsFrom (referencia de API no administrada)"
description: "La función InheritsFrom determina si una clase o instancia se deriva de una clase principal concreta."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: InheritsFrom
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: InheritsFrom
helpviewer_keywords: InheritsFrom function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aedeec76f4fabb2f6bd32d7d06eb5a1a5734534e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="b7cf9-103">InheritsFrom (función)</span><span class="sxs-lookup"><span data-stu-id="b7cf9-103">InheritsFrom function</span></span>
<span data-ttu-id="b7cf9-104">Determina si la instancia o clase actual se deriva de una clase principal especificada.</span><span class="sxs-lookup"><span data-stu-id="b7cf9-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="b7cf9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7cf9-105">Syntax</span></span>  
  
```
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="b7cf9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7cf9-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b7cf9-107">[in] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="b7cf9-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b7cf9-108">[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="b7cf9-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="b7cf9-109">[in] El nombre de la clase.</span><span class="sxs-lookup"><span data-stu-id="b7cf9-109">[in] The name of the class.</span></span> <span data-ttu-id="b7cf9-110">`wszAncestor`debe apuntar a válido `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="b7cf9-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="b7cf9-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b7cf9-111">Return value</span></span>

<span data-ttu-id="b7cf9-112">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="b7cf9-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b7cf9-113">Constante</span><span class="sxs-lookup"><span data-stu-id="b7cf9-113">Constant</span></span>  |<span data-ttu-id="b7cf9-114">Valor</span><span class="sxs-lookup"><span data-stu-id="b7cf9-114">Value</span></span>  |<span data-ttu-id="b7cf9-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7cf9-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="b7cf9-116">0</span><span class="sxs-lookup"><span data-stu-id="b7cf9-116">0</span></span> | <span data-ttu-id="b7cf9-117">El objeto actual se hereda de `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="b7cf9-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="b7cf9-118">1</span><span class="sxs-lookup"><span data-stu-id="b7cf9-118">1</span></span> | <span data-ttu-id="b7cf9-119">El objeto actual no hereda de `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="b7cf9-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b7cf9-120">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="b7cf9-120">0x80041008</span></span> | <span data-ttu-id="b7cf9-121">El valor de `wszAncestor` es `null`.</span><span class="sxs-lookup"><span data-stu-id="b7cf9-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="b7cf9-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b7cf9-122">Remarks</span></span>

<span data-ttu-id="b7cf9-123">Esta función contiene una llamada a la [IWbemClassObject::InheritsFrom](https://msdn.microsoft.com/library/aa391452(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="b7cf9-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](https://msdn.microsoft.com/library/aa391452(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b7cf9-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7cf9-124">Requirements</span></span>  
 <span data-ttu-id="b7cf9-125">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7cf9-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7cf9-126">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b7cf9-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b7cf9-127">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b7cf9-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7cf9-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7cf9-128">See also</span></span>  
[<span data-ttu-id="b7cf9-129">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="b7cf9-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)