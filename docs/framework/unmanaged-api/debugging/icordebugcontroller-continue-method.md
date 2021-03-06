---
title: Metodo ICorDebugController::Continue
ms.date: 03/30/2017
api_name:
- ICorDebugController.Continue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 529a65285203ac831e1bcab9dc1bea69ac28a282
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugcontrollercontinue-method"></a>Metodo ICorDebugController::Continue
Riprende l'esecuzione dei thread gestiti dopo una chiamata a [metodo Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Continue (  
    [in] BOOL fIsOutOfBand  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `fIsOutOfBand`  
 [in] Impostare su `true` Se continui da un evento out of band; in caso contrario, è impostato su `false`.  
  
## <a name="remarks"></a>Note  
 `Continue` continua il processo dopo una chiamata al `ICorDebugController::Stop` metodo.  
  
 Quando si esegue il debug in modalità mista, non chiamare `Continue` sul Win32 evento thread a meno che non si continui da un evento fuori banda.  
  
 Un *evento in banda* è un evento gestito o un normale evento non gestito durante il quale il debugger supporta l'interazione con lo stato del processo gestito. In questo caso, il debugger riceve il [ICorDebugUnmanagedCallback::](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) callback con il relativo `fOutOfBand` parametro impostato su `false`.  
  
 Un *out of band evento* è un evento non gestito durante il quale è possibile interagire con lo stato del processo gestito durante il processo viene arrestato a causa dell'evento. In questo caso, il debugger riceve il `ICorDebugUnmanagedCallback::DebugEvent` callback con il relativo `fOutOfBand` parametro impostato su `true`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 
