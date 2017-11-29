---
title: Interfaccia ICorProfilerInfo5
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo5
api_location: mscorwks.dll
api_type: COM
ms.assetid: 7bd48c34-37ed-4230-9eec-39a17280f05d
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 84744474b9eca96cae5e96b8c4eadc4109f85f82
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo5-interface"></a><span data-ttu-id="1f719-102">Interfaccia ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="1f719-102">ICorProfilerInfo5 Interface</span></span>
<span data-ttu-id="1f719-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="1f719-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="1f719-104">Una sottoclasse di [ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md) che fornisce metodi usati dal code profiler di comunicare con common language runtime (CLR) per controllare il monitoraggio degli eventi.</span><span class="sxs-lookup"><span data-stu-id="1f719-104">A subclass of [ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md) that provides methods for use by code profilers to communicate with the common language runtime (CLR) to control event monitoring.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1f719-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="1f719-105">Methods</span></span>  
  
|<span data-ttu-id="1f719-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="1f719-106">Method</span></span>|<span data-ttu-id="1f719-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1f719-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1f719-108">Metodo GetEventMask2</span><span class="sxs-lookup"><span data-stu-id="1f719-108">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)|<span data-ttu-id="1f719-109">Ottiene le categorie di eventi correnti per le quali il profiler richiede la ricezione delle notifiche da CLR.</span><span class="sxs-lookup"><span data-stu-id="1f719-109">Gets the current event categories for which the profiler wants to receive notifications from the CLR.</span></span>|  
|[<span data-ttu-id="1f719-110">Metodo SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="1f719-110">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)|<span data-ttu-id="1f719-111">Imposta un valore che specifica i tipi di eventi per i quali il profiler richiede la ricezione della notifica da CLR.</span><span class="sxs-lookup"><span data-stu-id="1f719-111">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f719-112">Note</span><span class="sxs-lookup"><span data-stu-id="1f719-112">Remarks</span></span>  
 <span data-ttu-id="1f719-113">I metodi disponibili in questa interfaccia sono progettati per sostituire il [ICorProfilerInfo:: GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) e [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) metodi.</span><span class="sxs-lookup"><span data-stu-id="1f719-113">The methods available on this interface are intended to replace the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f719-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1f719-114">Requirements</span></span>  
 <span data-ttu-id="1f719-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f719-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f719-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1f719-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1f719-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f719-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f719-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f719-118">See Also</span></span>  
 [<span data-ttu-id="1f719-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="1f719-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)