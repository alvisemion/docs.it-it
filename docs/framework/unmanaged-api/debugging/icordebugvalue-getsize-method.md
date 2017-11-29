---
title: Metodo ICorDebugValue::GetSize
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue.GetSize
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a412ec7fbc619ae01a981fefe10ce0e4f2874848
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="a4f70-102">Metodo ICorDebugValue::GetSize</span><span class="sxs-lookup"><span data-stu-id="a4f70-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="a4f70-103">Ottiene le dimensioni, in byte, di questo oggetto "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="a4f70-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4f70-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4f70-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a4f70-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a4f70-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="a4f70-106">[out] Le dimensioni in byte, di questo oggetto valore.</span><span class="sxs-lookup"><span data-stu-id="a4f70-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4f70-107">Note</span><span class="sxs-lookup"><span data-stu-id="a4f70-107">Remarks</span></span>  
 <span data-ttu-id="a4f70-108">Se il tipo del valore è un tipo riferimento, questo metodo restituisce le dimensioni dell'indicatore di misura anziché la dimensione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="a4f70-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="a4f70-109">Il `ICorDebugValue::GetSize` restituisce `COR_E_OVERFLOW` per gli oggetti che sono maggiori di 4 GB su piattaforme a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="a4f70-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="a4f70-110">Utilizzare il [icordebugvalue3:: Getsize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) metodo invece per gli oggetti che sono maggiori di 4 GB.</span><span class="sxs-lookup"><span data-stu-id="a4f70-110">Use the [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4f70-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a4f70-111">Requirements</span></span>  
 <span data-ttu-id="a4f70-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4f70-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4f70-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a4f70-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4f70-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4f70-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4f70-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4f70-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4f70-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4f70-116">See Also</span></span>  
    
 [<span data-ttu-id="a4f70-117">GetSize64 (metodo)</span><span class="sxs-lookup"><span data-stu-id="a4f70-117">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)