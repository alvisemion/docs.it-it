---
title: Metodo ICLRDomainManager::SetAppDomainManagerType
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea10f9b7d23d8ca6a94d05cac6e586b434c000d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a>Metodo ICLRDomainManager::SetAppDomainManagerType
Specifica il tipo, derivato dal <xref:System.AppDomainManager?displayProperty=nameWithType> (classe), l'applicazione del gestore di dominio che verrà utilizzato per inizializzare il dominio applicazione predefinito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `wszAppDomainManagerAssembly`  
 [in] Il nome visualizzato dell'assembly che contiene il tipo di gestione del dominio applicazione; ad esempio: "AdMgrExample, Version = 1.0.0.0, Culture = neutral, PublicKeyToken = 6856bccf150f00b3".  
  
 `wszAppDomainManagerType`  
 [in] Il nome del tipo del gestore di dominio di applicazione, incluso lo spazio dei nomi.  
  
 `dwInitializeDomainFlags`  
 [in] Una combinazione di [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) valori di enumerazione che forniscono informazioni sul gestore di dominio applicazione.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
  
## <a name="remarks"></a>Note  
 Attualmente, l'unico valore definito per `dwInitializeDomainFlags` è `eInitializeNewDomainFlags_NoSecurityChanges`, ovvero che il gestore di dominio di applicazione non modificherà le impostazioni di sicurezza durante l'esecuzione di common language runtime (CLR) di <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> metodo. Ciò consente a CLR di ottimizzare il caricamento di assembly i cui condizionale <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attributo (APTCA). Se la chiusura transitiva di questo set di assembly è grande, questo può comportare un miglioramento notevole nel tempo di avvio.  
  
> [!IMPORTANT]
>  Se l'host specifica `eInitializeNewDomainFlags_NoSecurityChanges` per la gestione del dominio applicazione, un <xref:System.InvalidOperationException> viene generata se si tenta di modificare la sicurezza del dominio dell'applicazione.  
  
 La chiamata di [SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)è equivalente alla chiamata al metodo `ICLRDomainManager::SetAppDomainManagerType` con `eInitializeNewDomainFlags_None`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [Interfaccia ICLRDomainManager](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 [Enumerazione EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
