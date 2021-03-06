---
title: 'Procedura: test del proxy di individuazione'
ms.date: 03/30/2017
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
ms.openlocfilehash: 35edbd03e912ae2d9c491afb28dee1c4a3055d14
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-test-the-discovery-proxy"></a>Procedura: test del proxy di individuazione
Di seguito viene illustrato il quarto di quattro argomenti che indica come implementare un proxy di individuazione. Nell'argomento precedente [procedura: implementare un'applicazione Client che utilizza il Proxy di individuazione per trovare un servizio](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), un'applicazione client WCF che utilizza il proxy di individuazione per trovare un servizio e quindi chiama il servizio è stata implementata. In questo argomento viene descritto come verificare che il proxy di individuazione, il servizio e l'applicazione client funzionino come previsto.  
  
### <a name="run-the-discovery-proxy"></a>Eseguire il proxy di individuazione  
  
1.  Aprire un prompt dei comandi come amministratore.  
  
2.  È possibile che venga visualizzata una finestra di dialogo con il testo seguente: Windows Firewall ha bloccato alcune funzionalità del programma. Se viene visualizzato questo messaggio, fare clic su di **Unblock** pulsante.  
  
3.  All'interno del prompt dei comandi eseguire il proxy di individuazione (DiscoveryProxy.exe).  
  
4.  Nell'applicazione viene visualizzato il testo seguente: `Proxy started. Hit Enter to exit`.  
  
### <a name="run-the-discoverable-service"></a>Eseguire il servizio individuabile  
  
1.  Aprire un prompt dei comandi come amministratore.  
  
2.  Al prompt dei comandi eseguire il servizio individuabile Service.exe.  
  
3.  Il DiscoveryProxy.exe viene visualizzato il testo seguente: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .  
  
### <a name="run-the-client-application"></a>Eseguire l'applicazione client  
  
1.  Aprire un prompt dei comandi.  
  
2.  Al prompt dei comandi eseguire l'applicazione client.exe.  
  
3.  Dopo alcuni secondi nell'applicazione client viene visualizzato il testo seguente: Connessione a [Endpoint-servizio] in corso.  
  
4.  In Service.exe viene quindi visualizzato il testo seguente: Greeting request received, I will respond.  
  
5.  In Client.exe viene quindi visualizzato il testo seguente: Hello Client!  
  
### <a name="shut-down-the-applications"></a>Chiudere le applicazioni  
  
1.  Chiudere l'applicazione client.  
  
2.  Chiudere il servizio. Il proxy di individuazione visualizza il testo seguente: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.  
  
3.  Chiudere il proxy di individuazione  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica di WCF Discovery](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [Procedura: Implementare un proxy di individuazione](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)  
 [Procedura: Implementare un servizio individuabile che esegue la registrazione al proxy di individuazione](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)  
 [Procedura: Implementare un'applicazione client che usa il proxy di individuazione per trovare un servizio](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)
