---
title: Metodo IHostMAlloc::DebugAlloc
ms.date: 03/30/2017
api_name:
- IHostMAlloc.DebugAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::DebugAlloc
helpviewer_keywords:
- DebugAlloc method [.NET Framework hosting]
- IHostMAlloc::DebugAlloc method [.NET Framework hosting]
ms.assetid: 0bfbc527-bea2-43ce-b041-69186f4440dd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8447f6fa2771128c1bdf424cb9aac141b2dfd486
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="ihostmallocdebugalloc-method"></a>Metodo IHostMAlloc::DebugAlloc
Richiede che l'host di alloca la quantità specificata di memoria dall'heap e inoltre tenere traccia in cui è stata allocata la memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,   
    [in]  EMemoryCriticalLevel dwCriticalLevel,   
    [in]  char*   pszFileName,   
    [in]  int     iLineNo,   
    [out] void**  ppMem  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cbSize`  
 [in] Le dimensioni in byte, della richiesta di allocazione di memoria corrente.  
  
 `dwCriticalLevel`  
 [in] Uno del [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) valori, che indica l'impatto di un errore di allocazione.  
  
 `pszFileName`  
 [in] Il file di codice del file eseguibile in fase di debug.  
  
 `iLineNo`  
 [in] Il numero di riga in `pszFileName` in cui è stata richiesta l'allocazione.  
  
 `ppMem`  
 [out] Puntatore alla memoria allocata, oppure null se non è stato possibile completare la richiesta.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`DebugAlloc` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Memoria insufficiente è disponibile per completare la richiesta di allocazione.|  
  
## <a name="remarks"></a>Note  
 CLR ottiene un puntatore a interfaccia a un [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) istanza chiamando il [IHostMemoryManager::](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) metodo. `DebugAlloc` consente al runtime di ottenere informazioni sul file di codice per l'utilizzo durante il debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [Interfaccia IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
