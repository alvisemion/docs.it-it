---
title: Visualizzazione dei log dei messaggi
ms.date: 03/30/2017
ms.assetid: 3012fa13-f650-45fb-aaea-c5cca8c7d372
ms.openlocfilehash: 56e4fb1ea8c67c35df440a2088034327788f6f15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="viewing-message-logs"></a>Visualizzazione dei log dei messaggi
In questo argomento viene illustrato come visualizzare i log dei messaggi.  
  
## <a name="viewing-message-logs-in-the-service-trace-viewer"></a>Visualizzazione dei log dei messaggi nel visualizzatore di tracce dei servizi  
 Un messaggio verrà trasformato dall'elaborazione di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Di conseguenza, un messaggio registrato riflette solo il suo contenuto nel momento in cui è stato registrato, non il contenuto in transito.  
  
 Poichè l'output della registrazione dei messaggi non ha alcuna relazione con il formato di trasferimento del messaggio, la registrazione genera sempre il messaggio decodificato. Se la registrazione del messaggio è stata configurata correttamente, i messaggi registrati devono essere visualizzati in testo normale. Ad esempio, il formato (testo normale) dei messaggi registrati non è influenzato dall'utilizzo di un codificatore di messaggi binario.  
  
 L'output di XmlWriterTraceListener è un file che contiene una sequenza di frammenti XML. È necessario sapere che il file non è un file XML valido. È consigliabile utilizzare il [strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) per visualizzare i file di log del messaggio. Per ulteriori informazioni su come utilizzare questo strumento, vedere [utilizzando Service Trace Viewer per la visualizzazione di tracce correlate e risoluzione dei problemi](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
 In Service Trace Viewer, i messaggi sono elencati nel **messaggio** scheda. I messaggi che hanno causato, o che sono correlati a un errore dell'elaborazione sono evidenziati in giallo (livello di avviso) o rosso (livello dell'errore), a seconda della gravità dell'errore. Un doppio clic sul messaggio ne rivela la traccia nel contesto della richiesta di elaborazione.  
  
> [!NOTE]
>  Se un messaggio non ha intestazione, non viene registrato alcun tag `<header/>`.  
  
## <a name="viewing-messages-logged-by-a-client-a-relay-and-a-service"></a>Visualizzazione dei messaggi registrati da client, relay e servizio  
 L'ambiente può contenere un client che invia un messaggio a un relay che successivamente lo inoltra al servizio. Quando è abilitata la registrazione dei messaggi in tutte e tre i percorsi e tutti e tre i registri di messaggio vengono visualizzati [strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) gli scambi di messaggi log contemporaneamente, verranno visualizzati in modo non corretto. Questa situazione si verifica perché `CorrelationId` e `ActivityId` nell'intestazione del messaggio non sono univoci per ogni coppia invio-ricezione.  
  
 Per risolvere il problema, utilizzare uno dei metodi seguenti:  
  
-   Visualizzare solo due dei tre log nel messaggio il [strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) in qualsiasi momento.  
  
-   Se è necessario visualizzare tutte e tre i log nel [strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) allo stesso tempo, è possibile modificare il servizio di inoltro creando un nuovo <xref:System.ServiceModel.Channels.Message> istanza. Tale istanza deve essere una copia del corpo del messaggio in arrivo, più tutte le intestazioni tranne quelle per le intestazioni `ActivityId` e `Action`. Nell'esempio di codice seguente viene illustrato come procedere.  
  
```  
Message outgoingMessage = Message.CreateMessage(incomingMessage.Version, incomingMessage.Headers.Action, incomingMessage.GetReaderAtBodyContents());  
  
for (int i = 0; i < incomingMessage.Headers.Count; i++)  
{  
   if (incomingMessage.Headers[i].Name.Equals("ActivityId", StringComparison.InvariantCultureIgnoreCase) ||  
incomingMessage.Headers[i].Name.Equals("Action", StringComparison.InvariantCultureIgnoreCase))  
   {  
      continue;  
    }  
    outgoingMessage.Headers.CopyHeaderFrom(incomingMessage, i);  
}  
```  
  
## <a name="exceptional-cases-for-inaccurate-message-logging-content"></a>Situazioni particolari di contenuto della registrazione del messaggio inaccurata  
 Nelle condizioni seguenti, i messaggi registrati potrebbero non rappresentare in modo esatto il flusso di ottetti in transito.  
  
-   Per BasicHttpBinding, le intestazioni di envelope vengono registrate per i messaggi in arrivo nello spazio dei nomi /addressing/none.  
  
-   Gli spazi vuoti possono essere interpretati erroneamente.  
  
-   Per i messaggi in arrivo, gli elementi vuoti possono essere rappresentati in modo diverso. Ad esempio, \<tag >\</tag > invece di \<tag / >  
  
-   Quando la registrazione di PII note è disattivata per impostazione predefinita o esplicita, enableLoggingKnownPii="true".  
  
-   È attivata la codifica per la trasformazione a UTF-8.  
  
## <a name="see-also"></a>Vedere anche  
 [Strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)  
 [Uso del visualizzatore di tracce dei servizi per la visualizzazione di tracce correlate e la risoluzione dei problemi](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 [Registrazione messaggi](../../../../docs/framework/wcf/diagnostics/message-logging.md)
