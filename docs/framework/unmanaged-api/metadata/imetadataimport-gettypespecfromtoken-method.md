---
title: Metodo IMetaDataImport::GetTypeSpecFromToken
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetTypeSpecFromToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetTypeSpecFromToken
helpviewer_keywords:
- GetTypeSpecFromToken method [.NET Framework metadata]
- IMetaDataImport::GetTypeSpecFromToken method [.NET Framework metadata]
ms.assetid: ee518bda-3296-482e-a7b7-e9d51dd1a181
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 37a8c2580dad3e198290b72b49b0aacaf1804c25
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="8de25-102">Metodo IMetaDataImport::GetTypeSpecFromToken</span><span class="sxs-lookup"><span data-stu-id="8de25-102">IMetaDataImport::GetTypeSpecFromToken Method</span></span>
<span data-ttu-id="8de25-103">Ottiene la firma binaria dei metadati della specifica del tipo rappresentata dal token indicato.</span><span class="sxs-lookup"><span data-stu-id="8de25-103">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8de25-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8de25-104">Syntax</span></span>  
  
```  
HRESULT GetTypeSpecFromToken (   
   [in]  mdTypeSpec            typespec,   
   [out] PCCOR_SIGNATURE       *ppvSig,   
   [out] ULONG                 *pcbSig  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8de25-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8de25-105">Parameters</span></span>  
 `typespec`  
 <span data-ttu-id="8de25-106">[in] Il token TypeSpec associato alla firma richiesta dei metadati.</span><span class="sxs-lookup"><span data-stu-id="8de25-106">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="8de25-107">[out] Un puntatore per la firma binaria dei metadati.</span><span class="sxs-lookup"><span data-stu-id="8de25-107">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="8de25-108">[out] Le dimensioni in byte, della firma dei metadati.</span><span class="sxs-lookup"><span data-stu-id="8de25-108">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8de25-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8de25-109">Return Value</span></span>  
 <span data-ttu-id="8de25-110">Un valore HRESULT che indica l'esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="8de25-110">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="8de25-111">Gli errori possono essere verificati con la macro FAILED.</span><span class="sxs-lookup"><span data-stu-id="8de25-111">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8de25-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8de25-112">Requirements</span></span>  
 <span data-ttu-id="8de25-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8de25-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8de25-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8de25-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8de25-115">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8de25-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8de25-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8de25-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8de25-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8de25-117">See Also</span></span>  
 [<span data-ttu-id="8de25-118">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8de25-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="8de25-119">IMetaDataImport2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8de25-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)