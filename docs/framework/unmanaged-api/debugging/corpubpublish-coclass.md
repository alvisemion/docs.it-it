---
title: Coclasse CorpubPublish
ms.date: 03/30/2017
api_name:
- CorpubPublish Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorpubPublish
helpviewer_keywords:
- CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9941a9be7d9f68255636b405db29a623be8d37e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="corpubpublish-coclass"></a>Coclasse CorpubPublish
Fornisce interfacce per la pubblicazione di informazioni sui domini dell'applicazione e sui processi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a>Interfacce  
  
|Interfaccia|Descrizione|  
|---------------|-----------------|  
|[Interfaccia ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|Fornisce metodi per la pubblicazione delle informazioni sui processi e i domini applicazione di tali processi.|  
|[Interfaccia ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|Rappresenta e fornisce informazioni su un dominio applicazione in un processo.|  
|[Interfaccia ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|Fornisce metodi che scorrono una raccolta di domini applicazione attualmente esistenti all'interno di un processo.|  
|[Interfaccia ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|Rappresenta un processo in esecuzione in un computer.|  
|[Interfaccia ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|Fornisce metodi che scorrono una raccolta di processi in esecuzione in un computer.|  
  
## <a name="remarks"></a>Note  
 Un tipico scenario di pubblicazione comporta uno sviluppatore che desidera eseguire il debug di codice gestito che è in esecuzione in un computer all'interno di un dominio applicazione. L'ambiente host potrebbe essere più di un dominio applicazione all'interno di un processo in esecuzione. Lo sviluppatore desidera utilizzare un'interfaccia utente grafica o in altro modo per visualizzare l'elenco di tutti i processi in esecuzione nel computer e scegliere un processo specifico. L'elenco deve includere tutti i domini applicazione all'interno di processi che eseguono codice gestito. Lo sviluppatore può quindi identificare il dominio di applicazione specifico e collegare un debugger a quel dominio.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Corpub. idl  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
