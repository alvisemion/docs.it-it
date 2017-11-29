---
title: Metodo ICorDebugStepper::StepRange
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.StepRange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 72a68000691dd23a55b77265cae839bea8b4ae1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugsteppersteprange-method"></a><span data-ttu-id="50625-102">Metodo ICorDebugStepper::StepRange</span><span class="sxs-lookup"><span data-stu-id="50625-102">ICorDebugStepper::StepRange Method</span></span>
<span data-ttu-id="50625-103">Fa sì che ICorDebugStepper passo a passo del thread e da restituire quando raggiunge il codice oltre l'ultimo degli intervalli specificati.</span><span class="sxs-lookup"><span data-stu-id="50625-103">Causes this ICorDebugStepper to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50625-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50625-104">Syntax</span></span>  
  
```  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="50625-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="50625-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="50625-106">[in] Impostare su `true` al passaggio a una funzione che viene chiamata all'interno del thread.</span><span class="sxs-lookup"><span data-stu-id="50625-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="50625-107">Impostare su `false` per Esegui istruzione/routine di funzione.</span><span class="sxs-lookup"><span data-stu-id="50625-107">Set to `false` to step over the function.</span></span>  
  
 `ranges`  
 <span data-ttu-id="50625-108">[in] Matrice di strutture COR_DEBUG_STEP_RANGE, ognuno dei quali specifica un intervallo.</span><span class="sxs-lookup"><span data-stu-id="50625-108">[in] An array of COR_DEBUG_STEP_RANGE structures, each of which specifies a range.</span></span>  
  
 `cRangeCount`  
 <span data-ttu-id="50625-109">[in] Dimensione della matrice `ranges`.</span><span class="sxs-lookup"><span data-stu-id="50625-109">[in] The size of the `ranges` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50625-110">Note</span><span class="sxs-lookup"><span data-stu-id="50625-110">Remarks</span></span>  
 <span data-ttu-id="50625-111">Il `StepRange` metodo opera come il [ICorDebugStepper:: Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) metodo, ad eccezione del fatto che non viene completata fino al codice di fuori dell'intervallo specificato viene raggiunto.</span><span class="sxs-lookup"><span data-stu-id="50625-111">The `StepRange` method works like the [ICorDebugStepper::Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) method, except that it does not complete until code outside the given range is reached.</span></span>  
  
 <span data-ttu-id="50625-112">Può essere più efficiente rispetto al debug di un'istruzione alla volta.</span><span class="sxs-lookup"><span data-stu-id="50625-112">This can be more efficient than stepping one instruction at a time.</span></span> <span data-ttu-id="50625-113">Gli intervalli vengono specificati come elenco di coppie di offset dall'inizio del frame del gestore di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="50625-113">Ranges are specified as a list of offset pairs from the start of the stepper's frame.</span></span>  
  
 <span data-ttu-id="50625-114">Gli intervalli sono relativi al codice Microsoft intermediate language (MSIL) di un metodo.</span><span class="sxs-lookup"><span data-stu-id="50625-114">Ranges are relative to the Microsoft intermediate language (MSIL) code of a method.</span></span> <span data-ttu-id="50625-115">Chiamare [ICorDebugStepper:: SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) con `false` per rendere gli intervalli relativi al codice nativo di un metodo.</span><span class="sxs-lookup"><span data-stu-id="50625-115">Call [ICorDebugStepper::SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) with `false` to make the ranges relative to the native code of a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50625-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="50625-116">Requirements</span></span>  
 <span data-ttu-id="50625-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50625-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50625-118">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="50625-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50625-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50625-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50625-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50625-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>