---
title: 'Servizio: chiamate di sicurezza non autorizzate al secondo'
ms.date: 03/30/2017
ms.assetid: 1eeade5a-ea62-4757-b1f9-1b1b1746abd1
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: d1fa297536cbac174e77b2d19b53b642a577f949
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="service-security-calls-not-authorized-per-second"></a>Servizio: chiamate di sicurezza non autorizzate al secondo
Nome contatore: chiamate di sicurezza non autorizzate al secondo  
  
## <a name="description"></a>Descrizione  
 Numero di messaggi in ingresso al secondo provenienti da un utente valido e adeguatamente protetti, ma per cui l'utente non è autorizzato a eseguire attività specifiche.  
  
 Questo contatore viene incrementato quando il metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> restituisce `false`.  
  
 Questo contatore è di tipo di contatore prestazioni [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkId=94649), il cui valore viene calcolato usando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
