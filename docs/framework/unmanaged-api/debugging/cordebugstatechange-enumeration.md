---
title: Enumerazione CorDebugStateChange
ms.date: 03/30/2017
api_name:
- CorDebugStateChange
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 841108457293e3377ee87f9c7d7c6898340e51b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="cordebugstatechange-enumeration"></a>Enumerazione CorDebugStateChange
Descrive la quantità di dati memorizzati nella cache da rimuovere in base alle modifiche apportate al processo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorDebugStateChange  
{  
    PROCESS_RUNNING = 0x0000001,   
    FLUSH_ALL       = 0x0000002,   
} CorDebugStateChange;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`PROCESS_RUNNING`|Il processo ha raggiunto un nuovo stato di memoria tramite l'esecuzione diretta.|  
|`SET_CONTEXT_FLAG_UNWIND_FRAME`|La memoria del processo può essere diversa in modo arbitrario rispetto allo stato precedente.|  
  
## <a name="remarks"></a>Note  
 Membro di `CorDebugStateChange` enumerazione viene fornita come argomento quando il debugger chiama il [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) (metodo)  
  
> [!NOTE]
>  Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
