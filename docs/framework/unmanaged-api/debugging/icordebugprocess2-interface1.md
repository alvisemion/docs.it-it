---
title: ICorDebugProcess2 Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2
helpviewer_keywords:
- ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a1588a37891d6a73c49cb1b9ccbc81d9dcdb7e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocess2-interface1"></a>ICorDebugProcess2 Interface1
Estensione logica dell'interfaccia ICorDebugProcess, che rappresenta un processo in esecuzione codice gestito.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|Rimuove un punto di interruzione in corrispondenza dell'offset specificato che è stato impostato da una precedente chiamata a `ICorDebugProcess2::SetUnmanagedBreakpoint`.|  
|[Metodo GetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|Ottiene i flag che devono essere impostati per common language runtime (CLR) per caricare l'immagine nel processo a cui fa riferimento `ICorDebugProcess2`.|  
|[Metodo GetReferenceValueFromGCHandle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|Ottiene un puntatore di riferimento all'oggetto gestito specificato dotato di gestire un'operazione di garbage collection.|  
|[Metodo GetThreadForTaskID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|Ottiene il thread su cui è in esecuzione l'attività con l'identificatore specificato.|  
|[Metodo GetVersion](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|Ottiene la versione di CLR in cui è in esecuzione il processo sottoposto a debug.|  
|[Metodo SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|Imposta i flag necessari per il compilatore di just-in-time (JIT) caricare un'immagine nel processo sottoposto a debug.|  
|[Metodo SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|Imposta un punto di interruzione non gestita in corrispondenza dell'offset specificato immagini native.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
