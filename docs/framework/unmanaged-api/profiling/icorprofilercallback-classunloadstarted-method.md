---
title: Metodo ICorProfilerCallback::ClassUnloadStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ClassUnloadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ClassUnloadStarted
helpviewer_keywords:
- ClassUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ClassUnloadStarted method [.NET Framework profiling]
ms.assetid: bc93bead-f3a9-415c-b919-ddd3ca80facc
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0056d97e7cf8286291292f27e942b7a846efb3f7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="9a936-102">Metodo ICorProfilerCallback::ClassUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="9a936-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="9a936-103">Notifica al profiler che è in corso lo scaricamento di una classe.</span><span class="sxs-lookup"><span data-stu-id="9a936-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a936-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a936-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a936-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a936-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="9a936-106">[in] Identifica la classe che sta per essere scaricata.</span><span class="sxs-lookup"><span data-stu-id="9a936-106">[in] Identifies the class that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a936-107">Note</span><span class="sxs-lookup"><span data-stu-id="9a936-107">Remarks</span></span>  
 <span data-ttu-id="9a936-108">Il valore di `classId` non è valido per una richiesta di informazioni dopo il `ClassUnloadStarted` metodo restituisce, si tratta di completamento per ottenere informazioni su questa classe.</span><span class="sxs-lookup"><span data-stu-id="9a936-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a936-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9a936-109">Requirements</span></span>  
 <span data-ttu-id="9a936-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a936-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a936-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9a936-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9a936-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a936-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a936-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a936-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a936-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a936-114">See Also</span></span>  
 [<span data-ttu-id="9a936-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="9a936-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="9a936-116">ClassUnloadFinished (metodo)</span><span class="sxs-lookup"><span data-stu-id="9a936-116">ClassUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)