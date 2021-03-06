---
title: Attività di messaggistica
ms.date: 03/30/2017
ms.assetid: 8498f215-1823-4aba-a6e1-391407f8c273
ms.openlocfilehash: 1ae03b1671aa5c938bb3897edb919643f795f8a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="messaging-activities"></a>Attività di messaggistica
Le attività di messaggistica consentono ai flussi di lavoro di inviare e ricevere messaggi WCF. Aggiungendo attività di messaggistica a un flusso di lavoro, è possibile modellare qualsiasi modello di scambio dei messaggi con la complessità desiderata.  
  
## <a name="message-exchange-patterns"></a>Modelli di scambio dei messaggi  
 Esistono tre modelli di scambio dei messaggi di base.  
  
-   **Datagramma** : quando si utilizza il modello di scambio di datagramma il client invia un messaggio al servizio, ma il servizio non risponde. Questo tipo di modello è talvolta denominato "Fire and Forget". Tale scambio richiede una conferma fuori banda di recapito con esito positivo. Il messaggio potrebbe infatti andare perso durante il transito e non raggiungere mai il servizio. Se il client invia correttamente un messaggio, non c'è garanzia che esso sia stato ricevuto dal servizio. Il datagramma è un blocco predefinito fondamentale per la messaggistica in quanto è possibile compilare modelli di scambio dei messaggi personalizzati sulla base di esso.  
  
-   **Richiesta-risposta** : quando tramite il modello di scambio richiesta-risposta il client invia un messaggio al servizio, il servizio esegue l'elaborazione necessaria e quindi invia una risposta al client. Il modello è costituito da coppie richiesta-risposta. Esempi di chiamate richiesta-risposta sono le chiamate RPC (Remote Procedure Call) e le richieste GET del browser. Questo modello è anche noto come half-duplex.  
  
-   **Duplex** : quando tramite il modello di scambio del client e il servizio duplex può inviare i messaggi tra loro in qualsiasi ordine. Tale modello è simile a una conversazione telefonica, in cui ogni parola pronunciata è un messaggio.  
  
 Le attività di messaggistica consentono di implementare uno o più dei modelli di scambio dei messaggi di base nonché modelli di qualsiasi complessità.  
  
## <a name="messaging-activities"></a>Attività di messaggistica  
 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] definisce le attività di messaggistica seguenti:  
  
-   <xref:System.ServiceModel.Activities.Send>- Utilizzare l'attività <xref:System.ServiceModel.Activities.Send> per inviare un messaggio.  
  
-   <xref:System.ServiceModel.Activities.SendReply> - Utilizzare l'attività <xref:System.ServiceModel.Activities.SendReply> per inviare una risposta a un messaggio ricevuto. Questa attività viene utilizzata dai servizi flusso di lavoro in caso di implementazione di un modello di scambio dei messaggi di tipo request/reply.  
  
-   <xref:System.ServiceModel.Activities.Receive>- Utilizzare l'attività <xref:System.ServiceModel.Activities.Receive> per ricevere un messaggio.  
  
-   <xref:System.ServiceModel.Activities.ReceiveReply>- Utilizzare l'attività <xref:System.ServiceModel.Activities.ReceiveReply> per ricevere un messaggio di risposta. Questa attività viene utilizzata dai client dei servizi flusso di lavoro in caso di implementazione di un modello di scambio dei messaggi di tipo request/reply.  
  
## <a name="messaging-activities-and-message-exchange-patterns"></a>Attività di messaggistica e modelli di scambio dei messaggi  
 Un modello di scambio dei messaggi di tipo datagramma prevede l'invio di un messaggio da parte di un client e la ricezione del messaggio da parte di un servizio. Se il client è un flusso di lavoro, utilizzare un'attività <xref:System.ServiceModel.Activities.Send> per inviare il messaggio. Per ricevere il messaggio in un flusso di lavoro, utilizzare un'attività <xref:System.ServiceModel.Activities.Receive>. Le attività <xref:System.ServiceModel.Activities.Send> e <xref:System.ServiceModel.Activities.Receive> dispongono ognuna di una proprietà denominata `Content`. Questa proprietà contiene i dati che vengono inviati o ricevuti. Quando si implementa il modello di scambio dei messaggi di tipo richiesta-risposta, sia il client che il servizio utilizzano coppie di attività. Il client utilizza un'attività <xref:System.ServiceModel.Activities.Send> per inviare il messaggio e un'attività <xref:System.ServiceModel.Activities.ReceiveReply> per ricevere la risposta dal servizio. Queste due attività sono associate tra loro mediante la proprietà <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A>. Questa proprietà viene impostata sull'attività <xref:System.ServiceModel.Activities.Send> che ha inviato il messaggio originale. Il servizio utilizza inoltre una coppia di attività associate: <xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.SendReply>. Queste due attività sono associate mediante la proprietà <xref:System.ServiceModel.Activities.SendReply.Request%2A>. Questa proprietà viene impostata sull'attività <xref:System.ServiceModel.Activities.Receive> che ha ricevuto il messaggio originale. Le attività <xref:System.ServiceModel.Activities.ReceiveReply> e <xref:System.ServiceModel.Activities.SendReply>, come <xref:System.ServiceModel.Activities.Send> e <xref:System.ServiceModel.Activities.Receive>, consentono di inviare un'istanza di <xref:System.ServiceModel.Channels.Message> o un tipo di contratto di messaggio.  
  
 Poiché i flussi di lavoro sono a esecuzione prolungata, è importante che il modello di comunicazione di tipo duplex supporti anche le conversazioni con esecuzione prolungata. Per supportare questo tipo di conversazioni, i client che iniziano la conversazione devono fornire al servizio una possibilità di richiamarlo in un secondo momento quando i dati diventano disponibili. Ad esempio, una richiesta di ordine di acquisto viene inviata per l'approvazione da parte del responsabile, tuttavia potrebbe essere elaborata per un giorno, una settimana o perfino un anno. Il flusso di lavoro che gestisce l'approvazione degli ordini di acquisto deve poter riprendere una volta ottenuta l'approvazione. Questo modello di comunicazione di tipo duplex è supportato in flussi di lavoro che usano la correlazione. Per implementare un modello duplex, utilizzare le attività <xref:System.ServiceModel.Activities.Send> e <xref:System.ServiceModel.Activities.Receive>. Nel <xref:System.ServiceModel.Activities.Receive> attività, inizializzare una correlazione utilizzando il valore della chiave speciale <!--zz <xref:System.ServiceModel.Activities.CorrelationHandle.CallbackHandleName%2A>--> `System.ServiceModel.Activities.CorrelationHandle.CallbackHandleName`. Nell'attività <xref:System.ServiceModel.Activities.Send> impostare l'handle di correlazione in questione come valore della proprietà <xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A>. Per altre informazioni, vedere [Duplex durevole](../../../../docs/framework/wcf/feature-details/durable-duplex-correlation.md).  
  
> [!NOTE]
>  Implementazione del flusso di lavoro di duplex con correlazione di callback ("Duplex durevole") è progettata per le conversazioni con esecuzione prolungata. Si tratta di un'implementazione diversa dal duplex WCF con contratti di callback, in cui la conversione è con esecuzione breve.  
  
## <a name="message-formatting-and-messaging-activities"></a>Formattazione dei messaggi e attività di messaggistica  
 Le attività <xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.ReceiveReply> dispongono di una proprietà denominata `Content`. Questa proprietà è di tipo <xref:System.ServiceModel.Activities.ReceiveContent> e rappresenta dati ricevuti dall'attività <xref:System.ServiceModel.Activities.Receive> o <xref:System.ServiceModel.Activities.ReceiveReply>. .NET Framework definisce due classi correlate chiamate <xref:System.ServiceModel.Activities.ReceiveMessageContent> e <xref:System.ServiceModel.Activities.ReceiveParametersContent>, le quali derivano entrambe da <xref:System.ServiceModel.Activities.ReceiveContent>. Nell'attività <xref:System.ServiceModel.Activities.Receive> o <xref:System.ServiceModel.Activities.ReceiveReply> impostare la proprietà `Content` su un'istanza di uno di questi tipi per ricevere i dati in un servizio flusso di lavoro. Il tipo da utilizzare dipende da quello dei dati ricevuti dall'attività. Se l'attività riceve un oggetto `Message` o un tipo di contratto di messaggio, utilizzare <xref:System.ServiceModel.Activities.ReceiveMessageContent>. Se l'attività riceve un set di tipi XML o di contratto dati serializzabili, utilizzare <xref:System.ServiceModel.Activities.ReceiveParametersContent>. <xref:System.ServiceModel.Activities.ReceiveParametersContent> consente di inviare più parametri, mentre <xref:System.ServiceModel.Activities.ReceiveMessageContent> consente di inviare un solo oggetto, il messaggio (o il tipo di contratto di messaggio).  
  
> [!NOTE]
>  <xref:System.ServiceModel.Activities.ReceiveMessageContent> può essere inoltre utilizzato con un singolo tipo XML o di contratto dati serializzabile. La differenza tra l'utilizzo di <xref:System.ServiceModel.Activities.ReceiveParametersContent> con un solo parametro e l'oggetto passato direttamente a <xref:System.ServiceModel.Activities.ReceiveMessageContent> è rappresentata dal formato wire. Viene eseguito il wrapping del contenuto del parametro in un elemento XML corrispondente al nome dell'operazione, nonché il wrapping dell'oggetto serializzato in un elemento XML utilizzando il nome del parametro (ad esempio, `<Echo><msg>Hello, World</msg></Echo>`). Non viene eseguito il wrapping del contenuto del messaggio in base al nome dell'operazione. Al contrario, l'oggetto serializzato viene inserito in un elemento XML che utilizza il nome del tipo XML qualificato (ad esempio, `<string>Hello, World</string>`).  
  
 Le attività <xref:System.ServiceModel.Activities.Send> e <xref:System.ServiceModel.Activities.SendReply> dispongono inoltre di una proprietà denominata `Content`. Questa proprietà è di tipo <xref:System.ServiceModel.Activities.SendContent> e rappresenta dati inviati dall'attività <xref:System.ServiceModel.Activities.Send> o <xref:System.ServiceModel.Activities.SendReply>. .NET Framework definisce due tipi correlati chiamati <xref:System.ServiceModel.Activities.SendMessageContent> e <xref:System.ServiceModel.Activities.SendParametersContent>, i quali derivano entrambi da <xref:System.ServiceModel.Activities.SendContent>. Nell'attività <xref:System.ServiceModel.Activities.Send> o <xref:System.ServiceModel.Activities.SendReply> impostare la proprietà `Content` su un'istanza di uno di questi tipi per inviare dati da un servizio flusso di lavoro. Il tipo da utilizzare dipende da quello dei dati inviati dall'attività. Se l'attività invia un oggetto `Message` o un tipo di contratto di messaggio, utilizzare <xref:System.ServiceModel.Activities.SendMessageContent>. Se l'attività invia un tipo di contratto dati, utilizzare <xref:System.ServiceModel.Activities.SendParametersContent>. <xref:System.ServiceModel.Activities.SendParametersContent> consente di inviare più parametri, mentre <xref:System.ServiceModel.Activities.SendMessageContent> consente di inviare un solo oggetto, il messaggio (o il tipo di contratto di messaggio).  
  
 Ai fini della programmazione in modo imperativo con le attività di messaggistica, si utilizzano gli elementi generici <xref:System.Activities.InArgument%601> e <xref:System.Activities.OutArgument%601> per eseguire il wrapping degli oggetti assegnati al messaggio o alle proprietà dei parametri delle attività <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, <xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.ReceiveReply>. Utilizzare <xref:System.Activities.InArgument%601> per il <xref:System.ServiceModel.Activities.Send> e <xref:System.ServiceModel.Activities.SendReply> le attività e <xref:System.Activities.OutArgument%601> per <xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.ReceiveReply> le attività. Con le attività di invio vengono utilizzati gli argomenti `In` perché i dati vengono passati nelle attività. Con le attività di ricezione vengono utilizzati gli argomenti `Out` perché i dati vengono passati all'esterno delle attività, come illustrato nell'esempio seguente.  
  
```  
Receive reserveSeat = new Receive  
{   
    ...   
    Content = new ReceiveParametersContent  
    {  
        Parameters =  
        {  
            { "ReservationInfo", new OutArgument<ReservationRequest>(reservationInfo) }  
        }  
    }  
};  
SendReply reserveSeat = new SendReply  
{   
    ...   
    Request = reserveSeat,  
    Content = new SendParametersContent  
    {  
        Parameters =  
        {  
            { "ReservationId", new InArgument<string>(reservationId) }  
        }  
    },  
};  
```  
  
 Quando si implementa un servizio flusso di lavoro che definisce un'operazione di richiesta-risposta che restituisce void, è necessario creare un'istanza di un'attività <xref:System.ServiceModel.Activities.SendReply> e impostare la proprietà <xref:System.ServiceModel.Activities.SendReply.Content%2A> su un'istanza vuota di uno dei tipi di contenuto (<xref:System.ServiceModel.Activities.SendMessageContent> o <xref:System.ServiceModel.Activities.SendParametersContent>), come illustrato nell'esempio seguente.  
  
```  
Receive rcv = new Receive()  
{  
ServiceContractName = "IService",  
OperationName = "NullReturningContract",  
Content = new ReceiveParametersContent( new Dictionary<string, OutArgument>() { { "message", new OutArgument<string>() } } )  
};  
SendReply sr = new SendReply()  
{  
Request = rcv  
   Content = new SendParametersContent();  
};  
```  
  
## <a name="add-service-reference"></a>Aggiungi riferimento al servizio  
 Quando si chiama un servizio di flusso di lavoro da un'applicazione di flusso di lavoro, in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] vengono generate attività di messaggistica personalizzate che incapsulano le normali attività <xref:System.ServiceModel.Activities.Send> e <xref:System.ServiceModel.Activities.ReceiveReply> utilizzate in un modello di scambio dei messaggi di tipo request/reply. Utilizzare questa funzionalità, fare clic sul progetto client in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] e selezionare **Aggiungi riferimento al servizio**. Digitare l'indirizzo di base del servizio nell'apposita casella e fare clic su Vai. I servizi disponibili sono visualizzati nel **servizi:** casella. Espandere il nodo del servizio per visualizzare i contratti supportati. Selezionare il contratto che si desidera chiamare e viene visualizzato l'elenco di operazioni disponibili nel **operazioni** casella. È quindi possibile specificare lo spazio dei nomi per l'attività generata e fare clic su **OK**. Verrà visualizzata una finestra di dialogo indicante che l'operazione è stata completata correttamente e che le attività personalizzate generate verranno inserite nella casella degli strumenti dopo aver ricompilato il progetto. Esiste una attività per ogni operazione definita nel contratto di servizio. Dopo avere ricompilato il progetto è possibile trascinare e rilasciare le attività personalizzate nel flusso di lavoro e impostare le eventuali proprietà necessarie nell'apposita finestra.  
  
<!--## Messaging Activity Templates  
 To make setting up a request/response MEP on the client and service easier, [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] provides two messaging activity templates. <xref:System.ServiceModel.Activities.Design.ReceiveAndSendReply> is used on the service and <xref:System.ServiceModel.Activities.Design.SendAndReceiveReply> is used on the client. In both cases the templates add the appropriate messaging activities to your workflow. On the service, the <xref:System.ServiceModel.Activities.Design.ReceiveAndSendReply> adds a <xref:System.ServiceModel.Activities.Receive> activity followed by a <xref:System.ServiceModel.Activities.SendReply> activity. The <xref:System.ServiceModel.Activities.SendReply.Request> property is automatically set to the <xref:System.ServiceModel.Activities.Receive> activity. On the client, the <xref:System.ServiceModel.Activities.Design.SendAndReceiveReply> adds a <xref:System.ServiceModel.Activities.Send> activity followed by a <xref:System.ServiceModel.Activities.ReceiveReply>. The <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A> property is automatically set to the <xref:System.ServiceModel.Activities.Send> activity. To use these templates, just drag and drop the appropriate template onto your workflow.  
-->
## <a name="messaging-activities-and-transactions"></a>Transazioni e attività di messaggistica  
 Quando si effettua una chiamata a un servizio flusso di lavoro potrebbe essere utile propagare una transazione all'operazione del servizio. A tale scopo, inserire l'attività <xref:System.ServiceModel.Activities.Receive> all'interno di un'attività <xref:System.ServiceModel.Activities.TransactedReceiveScope>. L'attività <xref:System.ServiceModel.Activities.TransactedReceiveScope> contiene un'attività `Receive` e un corpo. La transazione propagata al servizio rimane di ambiente in tutta l'esecuzione del corpo di <xref:System.ServiceModel.Activities.TransactedReceiveScope>. La transazione viene completata quando viene completata l'esecuzione del corpo. Per ulteriori informazioni sulle transazioni e flussi di lavoro, vedere [transazioni del flusso di lavoro](../../../../docs/framework/windows-workflow-foundation/workflow-transactions.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Come inviare e ricevere errori in Servizi flussi di lavoro](http://go.microsoft.com/fwlink/?LinkId=189151)  
 [Creazione di un servizio flusso di lavoro a esecuzione prolungata](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md)
