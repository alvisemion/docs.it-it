---
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: 416feb4073b31178b016ae72c9cd85e15c4a68c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="39458---trackingrecordtruncated"></a>39458 - TrackingRecordTruncated
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|39458|  
|Parole chiave|WFTracking|  
|Livello|Avviso|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che un record di rilevamento è stato troncato. Variabili/annotazioni/dati utente rimossi.  
  
## <a name="message"></a>Messaggio  
 Record di rilevamento %1 troncato scritto nella sessione ETW con il provider %2. Variabili/annotazioni/dati utente rimossi  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|RecordNumber|xs:string|Numero del record di rilevamento.|  
|ProviderId|xs:string|ID del provider ETW.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
