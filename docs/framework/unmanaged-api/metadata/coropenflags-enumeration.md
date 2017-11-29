---
title: Enumerazione CorOpenFlags
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
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="coropenflags-enumeration"></a><span data-ttu-id="9bef0-102">Enumerazione CorOpenFlags</span><span class="sxs-lookup"><span data-stu-id="9bef0-102">CorOpenFlags Enumeration</span></span>
<span data-ttu-id="9bef0-103">Contiene valori di flag che controllano il comportamento dei metadati all'apertura di file manifesto.</span><span class="sxs-lookup"><span data-stu-id="9bef0-103">Contains flag values that control metadata behavior upon opening manifest files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bef0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9bef0-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="9bef0-105">Membri</span><span class="sxs-lookup"><span data-stu-id="9bef0-105">Members</span></span>  
  
|<span data-ttu-id="9bef0-106">Membro</span><span class="sxs-lookup"><span data-stu-id="9bef0-106">Member</span></span>|<span data-ttu-id="9bef0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9bef0-107">Description</span></span>|  
|------------|-----------------|  
|`ofRead`|<span data-ttu-id="9bef0-108">Indica che il file deve essere aperto in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="9bef0-108">Indicates that the file should be opened for reading only.</span></span>|  
|`ofWrite`|<span data-ttu-id="9bef0-109">Indica che il file deve essere aperto in scrittura.</span><span class="sxs-lookup"><span data-stu-id="9bef0-109">Indicates that the file should be opened for writing.</span></span><br /><br /> <span data-ttu-id="9bef0-110">Se si usa il flag `ofWrite` quando si apre un file con estensione winmd, è anche necessario passare il flag `ofNoTransform`.</span><span class="sxs-lookup"><span data-stu-id="9bef0-110">If you are using the `ofWrite` flag when opening a .winmd file, you should also pass the `ofNoTransform` flag.</span></span>|  
|`ofReadWriteMask`|<span data-ttu-id="9bef0-111">Maschera per la lettura e la scrittura.</span><span class="sxs-lookup"><span data-stu-id="9bef0-111">A mask for reading and writing.</span></span>|  
|`ofCopyMemory`|<span data-ttu-id="9bef0-112">Indica che il file deve essere letto in memoria.</span><span class="sxs-lookup"><span data-stu-id="9bef0-112">Indicates that the file should be read into memory.</span></span> <span data-ttu-id="9bef0-113">I metadati devono mantenere la propria copia.</span><span class="sxs-lookup"><span data-stu-id="9bef0-113">Metadata should maintain its own copy.</span></span>|  
|`ofCacheImage`|<span data-ttu-id="9bef0-114">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="9bef0-114">Obsolete.</span></span> <span data-ttu-id="9bef0-115">Questo flag viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="9bef0-115">This flag is ignored.</span></span>|  
|`ofManifestMetadata`|<span data-ttu-id="9bef0-116">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="9bef0-116">Obsolete.</span></span> <span data-ttu-id="9bef0-117">Questo flag viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="9bef0-117">This flag is ignored.</span></span>|  
|`ofReadOnly`|<span data-ttu-id="9bef0-118">Indica che il file deve essere aperto in lettura e che una chiamata a `QueryInterface` per un [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) non può essere impostato.</span><span class="sxs-lookup"><span data-stu-id="9bef0-118">Indicates that the file should be opened for reading, and that a call to `QueryInterface` for an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) cannot be made.</span></span>|  
|`ofTakeOwnership`|<span data-ttu-id="9bef0-119">Indica che la memoria allocata tramite una chiamata a [CoTaskMemAlloc](http://msdn.microsoft.com/en-us/c4cb588d-9482-4f90-a92e-75b604540d5c) e verrà liberata dai metadati.</span><span class="sxs-lookup"><span data-stu-id="9bef0-119">Indicates that the memory was allocated using a call to [CoTaskMemAlloc](http://msdn.microsoft.com/en-us/c4cb588d-9482-4f90-a92e-75b604540d5c) and will be freed by the metadata.</span></span>|  
|`ofNoTypeLib`|<span data-ttu-id="9bef0-120">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="9bef0-120">Obsolete.</span></span> <span data-ttu-id="9bef0-121">Questo flag viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="9bef0-121">This flag is ignored.</span></span>|  
|`ofNoTransform`|<span data-ttu-id="9bef0-122">Indica che le trasformazioni automatiche dei file con estensione winmd devono essere disabilitate.</span><span class="sxs-lookup"><span data-stu-id="9bef0-122">Indicates that automatic transforms of .winmd files should be disabled.</span></span> <span data-ttu-id="9bef0-123">In altre parole, la proiezione di un tipo di Windows Runtime in un tipo di .NET Framework deve essere disabilitata.</span><span class="sxs-lookup"><span data-stu-id="9bef0-123">In other words, the projection of a Windows Runtime type to a .NET Framework type should be disabled.</span></span> <span data-ttu-id="9bef0-124">Per ulteriori informazioni, vedere [sottostante parte integrante di Windows Runtime e .NET](http://msdn.microsoft.com/magazine/jj651569.aspx).</span><span class="sxs-lookup"><span data-stu-id="9bef0-124">For more information, see [Underneath the Hood with .NET and the Windows Runtime](http://msdn.microsoft.com/magazine/jj651569.aspx).</span></span>|  
|`ofReserved1`|<span data-ttu-id="9bef0-125">Riservato per uso interno.</span><span class="sxs-lookup"><span data-stu-id="9bef0-125">Reserved for internal use.</span></span>|  
|`ofReserved2`|<span data-ttu-id="9bef0-126">Riservato per uso interno.</span><span class="sxs-lookup"><span data-stu-id="9bef0-126">Reserved for internal use.</span></span>|  
|`ofReserved`|<span data-ttu-id="9bef0-127">Riservato per uso interno.</span><span class="sxs-lookup"><span data-stu-id="9bef0-127">Reserved for internal use.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9bef0-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9bef0-128">Requirements</span></span>  
 <span data-ttu-id="9bef0-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bef0-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bef0-130">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="9bef0-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9bef0-131">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bef0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bef0-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bef0-132">See Also</span></span>  
 [<span data-ttu-id="9bef0-133">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="9bef0-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)