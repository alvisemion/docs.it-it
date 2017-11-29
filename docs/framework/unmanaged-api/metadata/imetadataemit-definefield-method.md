---
title: Metodo IMetaDataEmit::DefineField
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineField
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2a544d7e676b71fb00b8fd7a3d871867f7f55626
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="72b32-102">Metodo IMetaDataEmit::DefineField</span><span class="sxs-lookup"><span data-stu-id="72b32-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="72b32-103">Crea una definizione per un campo con la firma dei metadati specificati e ottiene un token per tale definizione.</span><span class="sxs-lookup"><span data-stu-id="72b32-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72b32-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72b32-104">Syntax</span></span>  
  
```  
HRESULT DefineField (   
    [in]  mdTypeDef   td,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwFieldFlags,   
    [in]  PCCOR_SIGNATURE pvSigBlob,   
    [in]  ULONG       cbSigBlob,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue,   
    [out] mdFieldDef  *pmd   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72b32-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="72b32-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="72b32-106">[in] Il `mdTypeDef` token per la classe o interfaccia contenitore.</span><span class="sxs-lookup"><span data-stu-id="72b32-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="72b32-107">[in] Il nome del campo in formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="72b32-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="72b32-108">[in] Gli attributi di campo.</span><span class="sxs-lookup"><span data-stu-id="72b32-108">[in] The field attributes.</span></span> <span data-ttu-id="72b32-109">Si tratta di una maschera di bit di `CorFieldAttr` valori.</span><span class="sxs-lookup"><span data-stu-id="72b32-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="72b32-110">[in] La firma del campo come BLOB.</span><span class="sxs-lookup"><span data-stu-id="72b32-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="72b32-111">[in] Il numero di byte in `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="72b32-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlage`  
 <span data-ttu-id="72b32-112">[in] Il `ELEMENT_TYPE_`  *\**  per il valore costante.</span><span class="sxs-lookup"><span data-stu-id="72b32-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="72b32-113">Si tratta di un `CorElementType` valore.</span><span class="sxs-lookup"><span data-stu-id="72b32-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="72b32-114">Se non si definisce un valore costante per il campo, utilizzare `ELEMENT_TYPE_END`.</span><span class="sxs-lookup"><span data-stu-id="72b32-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="72b32-115">[in] Il valore costante per il campo.</span><span class="sxs-lookup"><span data-stu-id="72b32-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="72b32-116">[in] La dimensione in caratteri (Unicode) di `pValue`.</span><span class="sxs-lookup"><span data-stu-id="72b32-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="72b32-117">[out] Il `mdFieldDef` token assegnato.</span><span class="sxs-lookup"><span data-stu-id="72b32-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72b32-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="72b32-118">Requirements</span></span>  
 <span data-ttu-id="72b32-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72b32-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72b32-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="72b32-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="72b32-121">**Libreria:** usata come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="72b32-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72b32-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72b32-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72b32-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72b32-123">See Also</span></span>  
 [<span data-ttu-id="72b32-124">IMetaDataEmit (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="72b32-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="72b32-125">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="72b32-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)