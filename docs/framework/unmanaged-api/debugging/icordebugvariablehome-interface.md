---
title: Interfaz ICorDebugVariableHome
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ICorDebugVariableHome
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome
helpviewer_keywords: ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 76f2bf3b-759f-4eed-bce7-119415b25915
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ea8f4033a6b0878288c49d6f6d964eb40675162d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablehome-interface"></a><span data-ttu-id="a6b8a-102">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="a6b8a-102">ICorDebugVariableHome Interface</span></span>
<span data-ttu-id="a6b8a-103">Representa una variable local o un argumento de una función.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-103">Represents a local variable or argument of a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a6b8a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a6b8a-104">Methods</span></span>  
  
|<span data-ttu-id="a6b8a-105">Método</span><span class="sxs-lookup"><span data-stu-id="a6b8a-105">Method</span></span>|<span data-ttu-id="a6b8a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6b8a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a6b8a-107">GetArgumentIndex (método)</span><span class="sxs-lookup"><span data-stu-id="a6b8a-107">GetArgumentIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getargumentindex-method.md)|<span data-ttu-id="a6b8a-108">Obtiene el índice de un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-108">Gets the index of a function argument.</span></span>|  
|[<span data-ttu-id="a6b8a-109">GetCode (método)</span><span class="sxs-lookup"><span data-stu-id="a6b8a-109">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getcode-method.md)|<span data-ttu-id="a6b8a-110">Obtiene la instancia de "ICorDebugCode" que contiene este `ICorDebugVariableHome` objeto.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-110">Gets the "ICorDebugCode" instance that contains this `ICorDebugVariableHome` object.</span></span>|  
|[<span data-ttu-id="a6b8a-111">GetLiveRange (método)</span><span class="sxs-lookup"><span data-stu-id="a6b8a-111">GetLiveRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getliverange-method.md)|<span data-ttu-id="a6b8a-112">Obtiene el rango nativo durante el cual esta variable es en vivo.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-112">Gets the native range over which this variable is live.</span></span>|  
|[<span data-ttu-id="a6b8a-113">GetLocationType (método)</span><span class="sxs-lookup"><span data-stu-id="a6b8a-113">GetLocationType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)|<span data-ttu-id="a6b8a-114">Obtiene el tipo de ubicación de la variable nativo.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-114">Gets the type of the variable's native location.</span></span>|  
|[<span data-ttu-id="a6b8a-115">GetOffset (método)</span><span class="sxs-lookup"><span data-stu-id="a6b8a-115">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getoffset-method.md)|<span data-ttu-id="a6b8a-116">Obtiene el desplazamiento desde el registro de base de una variable.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-116">Gets the offset from the base register for a variable.</span></span>|  
|[<span data-ttu-id="a6b8a-117">GetRegister (método)</span><span class="sxs-lookup"><span data-stu-id="a6b8a-117">GetRegister Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getregister-method.md)|<span data-ttu-id="a6b8a-118">Obtiene el registro que contiene una variable con un tipo de ubicación de `VLT_REGISTER`y el registro de base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-118">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>|  
|[<span data-ttu-id="a6b8a-119">GetSlotIndex (método)</span><span class="sxs-lookup"><span data-stu-id="a6b8a-119">GetSlotIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getslotindex-method.md)|<span data-ttu-id="a6b8a-120">Obtiene el índice de ranura administrado de una variable local.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-120">Gets the managed slot-index of a local variable.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a6b8a-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a6b8a-121">Example</span></span>  
 <span data-ttu-id="a6b8a-122">En el fragmento de código siguiente se utiliza la [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) objeto denominado `pCode4`.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-122">The following code fragment uses the [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) object named `pCode4`.</span></span>  
  
```cpp  
ICorDebugCode4 *pCode4 = NULL;  
pCode->QueryInterface(IID_ICorDebugCode4, &pCode4);  
  
ICorDebugVariableEnum *pVarLocEnum = NULL;  
pCode4->EnumerateVariableHomes(&pVarLocEnum);  
  
// retrieve local variables and arguments  
ULONG celt = 0;  
pVarLocEnum->GetCount(&celt);  
ICorDebugVariableHome **homes = new ICorDebugVariableHome *[celt];  
ULONG celtFetched = 0;  
pVarLocEnum->Next(celt, homes, &celtFetched);  
  
for (int i = 0; i < celtFetched; i++)  
{  
    VariableLocationType locType = VLT_INVALID;  
    homes[i].GetLocationType(&locType);  
    switch (locType)  
    {  
    case VLT_REGISTER:  
        CorDebugRegister register = 0;  
        locals[i].GetRegister(&register);  
        // now we know which register it is in  
        break;  
    case VLT_REGISTER_RELATIVE:  
        CorDebugRegister baseRegister = 0;  
        LONG offset = 0;  
        locals[i].GetRegister(&register);  
        locals[i].GetOffset(&offset);  
        // now we know the register-relative offset  
        break;  
    case VLT_INVALID:  
        // handle case where we can't access the location  
        break;  
    }  
}  
```  
  
## <a name="requirements"></a><span data-ttu-id="a6b8a-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a6b8a-123">Requirements</span></span>  
 <span data-ttu-id="a6b8a-124">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6b8a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6b8a-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6b8a-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6b8a-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6b8a-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6b8a-127">**Versiones de .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6b8a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6b8a-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6b8a-128">See Also</span></span>  
 [<span data-ttu-id="a6b8a-129">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="a6b8a-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a6b8a-130">Interfaz ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="a6b8a-130">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)