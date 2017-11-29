---
title: Metodo ICLRStrongName::GetHashFromAssemblyFile
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.GetHashFromAssemblyFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9a205f4225269f959efec9576bea047fb51ea946
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="58482-102">Metodo ICLRStrongName::GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="58482-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="58482-103">Ottiene un hash del file di assembly specificato, usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="58482-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58482-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58482-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58482-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="58482-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="58482-106">[in] Il percorso del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="58482-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="58482-107">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="58482-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="58482-108">Utilizzare zero per l'algoritmo hash predefinito.</span><span class="sxs-lookup"><span data-stu-id="58482-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="58482-109">[out] Il buffer di hash restituito.</span><span class="sxs-lookup"><span data-stu-id="58482-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="58482-110">[in] La dimensione massima richiesta del `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="58482-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="58482-111">[out] La dimensione restituita, in byte, di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="58482-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58482-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="58482-112">Return Value</span></span>  
 <span data-ttu-id="58482-113">`S_OK`Se il metodo viene completato correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](http://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="58482-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58482-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="58482-114">Requirements</span></span>  
 <span data-ttu-id="58482-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58482-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58482-116">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="58482-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="58482-117">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="58482-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58482-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58482-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58482-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58482-119">See Also</span></span>  
 [<span data-ttu-id="58482-120">GetHashFromAssemblyFileW (metodo)</span><span class="sxs-lookup"><span data-stu-id="58482-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="58482-121">ICLRStrongName (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="58482-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)