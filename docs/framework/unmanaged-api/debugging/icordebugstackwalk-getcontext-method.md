---
title: Metodo ICorDebugStackWalk::GetContext
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1126842a30f19831cc845bcfccc0e08f4bf5f6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugstackwalkgetcontext-method"></a>Metodo ICorDebugStackWalk::GetContext
Restituisce il contesto per il fotogramma corrente il [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
#### <a name="parameters"></a>Parametri  
 `contextFlags`  
 [in] Flag che indicano il contenuto del buffer del contesto (definito in Winnt. H) richiesto.  
  
 `contextBufSize`  
 [in] Le dimensioni allocate del buffer del contesto.  
  
 `contextSize`  
 [out] Le dimensioni effettive del contesto. Questo valore deve essere minore o uguale alla dimensione del buffer del contesto.  
  
 `contextBuf`  
 [out] Il buffer del contesto.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Il contesto per il frame corrente è stato restituito correttamente.|  
|E_FAIL|Non è stato possibile restituire il contesto.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)|Il buffer del contesto è troppo piccolo.|  
|CORDBG_E_PAST_END_OF_STACK|Puntatore ai frame è già alla fine dello stack. Pertanto, non è possibile accedere ulteriori frame.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Note  
 Poiché la rimozione Ripristina solo un subset dei registri, ad esempio registri non volatili, il contesto potrebbe non corrispondere esattamente allo stato del registro al momento della chiamata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
