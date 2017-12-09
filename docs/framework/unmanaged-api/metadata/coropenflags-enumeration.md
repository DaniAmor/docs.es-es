---
title: "CorOpenFlags (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorOpenFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorOpenFlags
helpviewer_keywords: CorOpenFlags enumeration [.NET Framework metadata]
ms.assetid: e27a83b5-2698-4996-9032-1e0fed8b91ca
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c7599a4b85a166aedd7a2293b79699b3ef03d14d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="coropenflags-enumeration"></a><span data-ttu-id="6ee2f-102">CorOpenFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6ee2f-102">CorOpenFlags Enumeration</span></span>
<span data-ttu-id="6ee2f-103">Contiene valores de marca que controlan el comportamiento de los metadatos al abrir archivos de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-103">Contains flag values that control metadata behavior upon opening manifest files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ee2f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ee2f-104">Syntax</span></span>  
  
```  
typedef enum CorOpenFlags  
{  
    ofRead              =   0x00000000,  
    ofWrite             =   0x00000001,  
    ofReadWriteMask     =   0x00000001,  
    ofCopyMemory        =   0x00000002,  
    ofCacheImage        =   0x00000004,  
    ofManifestMetadata  =   0x00000008,  
    ofReadOnly          =   0x00000010,  
    ofTakeOwnership     =   0x00000020,  
    ofCacheImage        =   0x00000004,  
    ofNoTypeLib         =   0x00000080,  
    ofNoTransform       =   0x00001000,  
    ofReserved1         =   0x00000100,  
    ofReserved2         =   0x00000200,  
    ofReserved          =   0xffffff40  
} CorOpenFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="6ee2f-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="6ee2f-105">Members</span></span>  
  
|<span data-ttu-id="6ee2f-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="6ee2f-106">Member</span></span>|<span data-ttu-id="6ee2f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6ee2f-107">Description</span></span>|  
|------------|-----------------|  
|`ofRead`|<span data-ttu-id="6ee2f-108">Indica que el archivo se debe abrir solo para lectura.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-108">Indicates that the file should be opened for reading only.</span></span>|  
|`ofWrite`|<span data-ttu-id="6ee2f-109">Indica que el archivo se debe abrir para escritura.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-109">Indicates that the file should be opened for writing.</span></span><br /><br /> <span data-ttu-id="6ee2f-110">Si usa la marca `ofWrite` al abrir un archivo .winmd, debe pasar también la marca `ofNoTransform`.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-110">If you are using the `ofWrite` flag when opening a .winmd file, you should also pass the `ofNoTransform` flag.</span></span>|  
|`ofReadWriteMask`|<span data-ttu-id="6ee2f-111">Máscara para lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-111">A mask for reading and writing.</span></span>|  
|`ofCopyMemory`|<span data-ttu-id="6ee2f-112">Indica que el archivo se debe leer en la memoria.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-112">Indicates that the file should be read into memory.</span></span> <span data-ttu-id="6ee2f-113">Los metadatos deben mantener su propia copia.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-113">Metadata should maintain its own copy.</span></span>|  
|`ofCacheImage`|<span data-ttu-id="6ee2f-114">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-114">Obsolete.</span></span> <span data-ttu-id="6ee2f-115">Esta marca se omite.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-115">This flag is ignored.</span></span>|  
|`ofManifestMetadata`|<span data-ttu-id="6ee2f-116">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-116">Obsolete.</span></span> <span data-ttu-id="6ee2f-117">Esta marca se omite.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-117">This flag is ignored.</span></span>|  
|`ofReadOnly`|<span data-ttu-id="6ee2f-118">Indica que el archivo se debe abrir para lectura y que una llamada a `QueryInterface` para un [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) no se puede realizar.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-118">Indicates that the file should be opened for reading, and that a call to `QueryInterface` for an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) cannot be made.</span></span>|  
|`ofTakeOwnership`|<span data-ttu-id="6ee2f-119">Indica que se asignó la memoria mediante una llamada a [CoTaskMemAlloc](http://msdn.microsoft.com/en-us/c4cb588d-9482-4f90-a92e-75b604540d5c) y se liberarán los metadatos.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-119">Indicates that the memory was allocated using a call to [CoTaskMemAlloc](http://msdn.microsoft.com/en-us/c4cb588d-9482-4f90-a92e-75b604540d5c) and will be freed by the metadata.</span></span>|  
|`ofNoTypeLib`|<span data-ttu-id="6ee2f-120">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-120">Obsolete.</span></span> <span data-ttu-id="6ee2f-121">Esta marca se omite.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-121">This flag is ignored.</span></span>|  
|`ofNoTransform`|<span data-ttu-id="6ee2f-122">Indica que se deben deshabilitar las transformaciones automáticas de archivos .winmd.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-122">Indicates that automatic transforms of .winmd files should be disabled.</span></span> <span data-ttu-id="6ee2f-123">En otras palabras, se debe deshabilitar la proyección de un tipo de Windows Runtime en un tipo de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-123">In other words, the projection of a Windows Runtime type to a .NET Framework type should be disabled.</span></span> <span data-ttu-id="6ee2f-124">Para obtener más información, consulte [debajo de la directiva the Hood con .NET y el tiempo de ejecución de Windows](http://msdn.microsoft.com/magazine/jj651569.aspx).</span><span class="sxs-lookup"><span data-stu-id="6ee2f-124">For more information, see [Underneath the Hood with .NET and the Windows Runtime](http://msdn.microsoft.com/magazine/jj651569.aspx).</span></span>|  
|`ofReserved1`|<span data-ttu-id="6ee2f-125">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-125">Reserved for internal use.</span></span>|  
|`ofReserved2`|<span data-ttu-id="6ee2f-126">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-126">Reserved for internal use.</span></span>|  
|`ofReserved`|<span data-ttu-id="6ee2f-127">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="6ee2f-127">Reserved for internal use.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6ee2f-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ee2f-128">Requirements</span></span>  
 <span data-ttu-id="6ee2f-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ee2f-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ee2f-130">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="6ee2f-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6ee2f-131">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ee2f-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ee2f-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ee2f-132">See Also</span></span>  
 [<span data-ttu-id="6ee2f-133">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="6ee2f-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)