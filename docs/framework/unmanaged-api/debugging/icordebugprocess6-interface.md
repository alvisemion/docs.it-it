---
title: Interfaccia ICorDebugProcess6
ms.date: 03/30/2017
ms.assetid: 34a10ac2-882c-4797-8369-f120e8e640c7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 103a37d7549d7ec18617b74c777506b3ad225a18
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocess6-interface"></a>Interfaccia ICorDebugProcess6
Estende logicamente l'interfaccia ICorDebugProcess per abilitare funzionalità come la decodifica degli eventi di debug gestiti, codificati negli eventi di debug di eccezioni native e la suddivisione dei moduli virtuali.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)|Decodifica gli eventi di debug gestiti incapsulati nel payload di eventi di debug per le eccezioni native appositamente predisposte.|  
|[Metodo EnableVirtualModuleSplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md)|Abilita o disabilita la suddivisione dei moduli virtuali.|  
|[Metodo GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getcode-method.md)|Ottiene informazioni sul codice gestito in un indirizzo di codice specifico.|  
|[Metodo GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md)|Fornisce informazioni sulle funzioni di runtime esportate per consentire l'esecuzione di codice gestito seguendo un'istruzione alla volta.|  
|[Metodo MarkDebuggerAttached](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-markdebuggerattached-method.md)|Modifica lo stato interno dell'oggetto del debug in modo che il metodo <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> nella libreria di classi .NET Framework restituisca `true`.|  
|[Metodo ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)|Notifica [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) che il processo è in esecuzione.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  L'interfaccia è disponibile solo con .NET Native. Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
