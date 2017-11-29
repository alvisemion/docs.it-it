---
title: Funzione CLRDataCreateInstance
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type: COM
f1_keywords: CLRDataCreateInstance
helpviewer_keywords: CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c611cc51417199aae7c595e4edd2e9a5360f0f9c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="30afe-102">Funzione CLRDataCreateInstance</span><span class="sxs-lookup"><span data-stu-id="30afe-102">CLRDataCreateInstance Function</span></span>
<span data-ttu-id="30afe-103">Crea un oggetto di interfaccia per l'elemento di destinazione specificato.</span><span class="sxs-lookup"><span data-stu-id="30afe-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30afe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30afe-104">Syntax</span></span>  
  
```  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,   
    [in]  ICLRDataTarget  *target,   
    [out] void           **iface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30afe-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="30afe-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="30afe-106">[in] Identificatore dell'interfaccia per creare un'istanza.</span><span class="sxs-lookup"><span data-stu-id="30afe-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="30afe-107">[in] Un puntatore a un utente implementato [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) oggetto che rappresenta l'elemento di destinazione per cui creare l'oggetto di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="30afe-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="30afe-108">[out] Un puntatore all'indirizzo dell'oggetto interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="30afe-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30afe-109">Note</span><span class="sxs-lookup"><span data-stu-id="30afe-109">Remarks</span></span>  
 <span data-ttu-id="30afe-110">Il `ICLRDataTarget` oggetto è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="30afe-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="30afe-111">L'implementazione varia a seconda del tipo di elemento di destinazione rappresentato.</span><span class="sxs-lookup"><span data-stu-id="30afe-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="30afe-112">L'elemento di destinazione potrebbe essere un processo, i dump di memoria, computer remoto e così via.</span><span class="sxs-lookup"><span data-stu-id="30afe-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30afe-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30afe-113">Requirements</span></span>  
 <span data-ttu-id="30afe-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30afe-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30afe-115">**Intestazione:** ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="30afe-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="30afe-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30afe-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30afe-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30afe-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30afe-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30afe-118">See Also</span></span>  
 [<span data-ttu-id="30afe-119">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="30afe-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)