---
title: Metodo IHostSyncManager::CreateMonitorEvent
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateMonitorEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateMonitorEvent
helpviewer_keywords:
- CreateMonitorEvent method [.NET Framework hosting]
- IHostSyncManager::CreateMonitorEvent method [.NET Framework hosting]
ms.assetid: 524c7fd3-9b5c-46e7-99ba-555fd2fe33f0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d7cff23fc0b58d316ce19950a982249e84b79ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a>Metodo IHostSyncManager::CreateMonitorEvent
Crea un oggetto evento di reimpostazione automatica monitorato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cookie`  
 [in] Cookie da associare all'oggetto evento.  
  
 `ppEvent`  
 [out] Un puntatore all'indirizzo di un [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) oppure null se non è stato possibile creare l'oggetto evento.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`CreateMonitorEvent` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|È disponibile per creare l'oggetto evento richiesto non è sufficiente memoria.|  
  
## <a name="remarks"></a>Note  
 `CreateMonitorEvent` Restituisce un `IHostAutoEvent` usati da CLR nella sua implementazione di gestito <xref:System.Threading.Monitor?displayProperty=nameWithType> tipo. Questo metodo riflette Win32 `CreateEvent` funzione, con un valore di `false` specificato per il `bManualReset` parametro.  
  
 L'host può utilizzare il cookie per determinare quale attività sono in attesa sul monitor chiamando il [ICLRSyncManager:: GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [Interfaccia IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [Interfaccia IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [Monitoraggi](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)
