---
title: Funzione GetRequestedRuntimeVersionForCLSID
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersionForCLSID
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersionForCLSID
helpviewer_keywords:
- GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8d3a7168ce0ee3484384ae0e2d10ca00367fc9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="getrequestedruntimeversionforclsid-function"></a>Funzione GetRequestedRuntimeVersionForCLSID
Ottiene le informazioni sulla versione di common language runtime (CLR) appropriato per la classe con l'oggetto specificato `CLSID`.  
  
 Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `rclsid`  
 [in]  Il `CLSID` del componente.  
  
 `pVersion`  
 [out]  Un buffer che contiene la stringa del numero di versione al completamento.  
  
 `cchBuffer`  
 [in]  Le dimensioni, in caratteri wide, del `pVersion` buffer.  
  
 `dwLength`  
 [out] La lunghezza, espressa in byte, del buffer restituito.  
  
 `dwResolutionFlags`  
 [in]  Uno dei valori di CLSID_RESOLUTION_FLAGS. Sono supportati i seguenti valori:  
  
-   CLSID_RESOLUTION_DEFAULT: (0x0) specifica il comportamento di interoperabilità predefinito deve essere utilizzato.  
  
-   CLSID_RESOLUTION_REGISTERED: (0x1) specifica che il Registro di sistema deve essere eseguita e criteri di shim deve essere applicato.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|La funzione ha restituito correttamente.|  
|E_INVALIDARG|Uno dei parametri contiene un formato o tipo non valido.|  
|ERROR_INSUFFICIENT_BUFFER|Il `pVersion` buffer non è sufficientemente grande da contenere l'intera stringa di versione.|  
|REGDB_E_CLASSNOTREG|Nessuna classe registrata con l'oggetto specificato `CLSID`.|  
|E_POINTER|`dwLength` è null, o `cchBuffer` è sufficientemente grande da contenere la stringa di versione, ma `pVersion` è null.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
