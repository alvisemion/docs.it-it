---
title: Metodo ICLRDataTarget2::FreeVirtual
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget2.FreeVirtual
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget2::FreeVirtual
helpviewer_keywords:
- ICLRDataTarget::FreeVirtual method [.NET Framework debugging]
- FreeVirtual method [.NET Framework debugging]
ms.assetid: 26fb69f8-1467-4711-bd24-cb117c63938f
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1619e9eb02eec1985c3c550626ef955162d1b984
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget2freevirtual-method"></a><span data-ttu-id="e2e63-102">Metodo ICLRDataTarget2::FreeVirtual</span><span class="sxs-lookup"><span data-stu-id="e2e63-102">ICLRDataTarget2::FreeVirtual Method</span></span>
<span data-ttu-id="e2e63-103">Chiamato dai servizi di accesso ai dati di common language runtime (CLR) per liberare memoria precedentemente allocato nello spazio degli indirizzi del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e2e63-103">Called by the common language runtime (CLR) data access services to free memory that was previously allocated in the address space of the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2e63-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2e63-104">Syntax</span></span>  
  
```  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2e63-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e2e63-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="e2e63-106">[in] Oggetto `CLRDATA_ADDRESS` valore che specifica l'indirizzo iniziale della memoria da liberare.</span><span class="sxs-lookup"><span data-stu-id="e2e63-106">[in] A `CLRDATA_ADDRESS` value that specifies the starting address of the memory to be freed.</span></span>  
  
 `size`  
 <span data-ttu-id="e2e63-107">[in] Le dimensioni in byte, della memoria da liberare.</span><span class="sxs-lookup"><span data-stu-id="e2e63-107">[in] The size, in bytes, of the memory to be freed.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="e2e63-108">[in] Flag che controllano la liberazione della memoria.</span><span class="sxs-lookup"><span data-stu-id="e2e63-108">[in] Flags that control the freeing of memory.</span></span> <span data-ttu-id="e2e63-109">Vedere Win32 `VirtualFree` (funzione).</span><span class="sxs-lookup"><span data-stu-id="e2e63-109">See the Win32 `VirtualFree` function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2e63-110">Note</span><span class="sxs-lookup"><span data-stu-id="e2e63-110">Remarks</span></span>  
 <span data-ttu-id="e2e63-111">Il `FreeVirtual` metodo funge da wrapper logico per Win32 `VirtualFree` (funzione).</span><span class="sxs-lookup"><span data-stu-id="e2e63-111">The `FreeVirtual` method serves as a logical wrapper for the Win32 `VirtualFree` function.</span></span>  
  
 <span data-ttu-id="e2e63-112">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="e2e63-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2e63-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2e63-113">Requirements</span></span>  
 <span data-ttu-id="e2e63-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2e63-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2e63-115">**Intestazione:** ClrData.idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="e2e63-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e2e63-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2e63-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2e63-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2e63-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2e63-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2e63-118">See Also</span></span>  
 [<span data-ttu-id="e2e63-119">Interfaccia ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="e2e63-119">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="e2e63-120">AllocVirtual (metodo)</span><span class="sxs-lookup"><span data-stu-id="e2e63-120">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)