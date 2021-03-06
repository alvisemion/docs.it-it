---
title: Duplex durevole
ms.date: 03/30/2017
ms.assetid: 4e76d1a1-f3d8-4a0f-8746-4a322cdff6eb
ms.openlocfilehash: 91490eb3ee6c11f29bb49d8343b807e74e8d3bc2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="durable-duplex"></a>Duplex durevole
In questo esempio viene illustrato come impostare e configurare lo scambio durevole di messaggi duplex usando le attività di messaggistica in Windows Workflow Foundation (WF). Un scambio durevole di messaggi duplex è un scambio di messaggi bidirezionale che si verifica in un lungo periodo di tempo. È possibile che la durata dello scambio di messaggi sia superiore alla durata del canale di comunicazione e alla durata in memoria delle istanze del servizio.  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 In questo esempio, due servizi di Windows Communication Foundation (WCF) implementati utilizzando Windows Workflow Foundation sono configurati per avere un scambio durevole di messaggi duplex. Lo scambio durevole di messaggi duplex è composta da due messaggi unidirezionali inviati tramite MSMQ e correlati usando [scambio del contesto .NET](http://go.microsoft.com/fwlink/?LinkID=166059). I messaggi vengono inviati tramite le attività di messaggistica <xref:System.ServiceModel.Activities.Send> e <xref:System.ServiceModel.Activities.Receive>. Lo scambio del contesto di .NET viene usato per specificare l'indirizzo di callback nei messaggi inviati. Entrambi i servizi sono ospitati tramite i servizi Attivazione processo Windows (WAS) e sono configurati per abilitare la persistenza delle istanze dei servizi.  
  
 Il primo servizio (Service1.xamlx) invia una richiesta al servizio di invio (Service2.xamlx) per l'esecuzione di un'operazione. Al termine, per indicare che l'operazione è stata completata, Service2.xamlx restituisce una notifica a Service1.xamlx. Un'applicazione console del flusso di lavoro configura le code su cui i servizi sono in ascolto e invia il messaggio di avvio per l'attivazione di Service1.xamlx. Una volta che Service1.xamlx ha ricevuto da Service2.xamlx la notifica che l'operazione richiesta è stata completata, il risultato viene salvato da Service1.xamlx in un file XML. In attesa del messaggio di callback, Service1.xamlx salva in modo permanente lo stato dell'istanza usando l'oggetto <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> predefinito. Service2.xamlx salva in modo permanente lo stato dell'istanza come parte del completamento dell'operazione richiesta da Service1.xamlx.  
  
 Per fare in modo che venga usato lo scambio del contesto di .NET su MSMQ, entrambi i servizi sono configurati per l'uso di un'associazione personalizzata costituita da <xref:System.ServiceModel.Channels.ContextBindingElement> e <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>. Un indirizzo di callback viene specificato con <xref:System.ServiceModel.Channels.ContextBindingElement> ed è incluso in un'intestazione del contesto di callback con tutti i messaggi inviati usando un'associazione personalizzata. Nel codice seguente viene definita l'associazione personalizzata.  
  
```xml  
<configuration>  
     <system.serviceModel>  
          …  
          <bindings>  
               <customBinding>  
                    <binding name="netMsmqContextBinding">  
                         <context clientCallbackAddress="net.msmq://localhost/private/DurableDuplex/Service1.xamlx"/>  
                         <msmqTransport exactlyOnce="False">  
                              <msmqTransportSecurity msmqAuthenticationMode="None" msmqProtectionLevel="None"/>  
                         </msmqTransport>  
                    </binding>  
               </customBinding>  
          </bindings>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  L'associazione usata da questo esempio non è sicura. In caso di distribuzione dell'applicazione è necessario configurare l'associazione in base ai requisiti di sicurezza dell'applicazione stessa.  
  
> [!NOTE]
>  Le code usate in questo esempio non sono transazionali. Per un esempio che illustra come configurare [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] scambi usando le code di transazione dei messaggi, vedere il [attivazione MSMQ](../../../../docs/framework/wcf/samples/msmq-activation.md) esempio.  
  
 Per l'invio del messaggio da Service1.xamlx a Service2.xamlx viene usato un endpoint client configurato con l'indirizzo di Service2.xamlx e con l'associazione personalizzata definita precedentemente. Il callback da Service2.xamlx a Service1.xamlx viene inviato usando un endpoint client senza indirizzo configurato in modo esplicito, perché l'indirizzo viene rilevato dal contesto di callback inviato da Service1.xamlx. Nel codice seguente vengono definiti gli endpoint client.  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
     <system.serviceModel>  
          …  
          <client>  
               <endpoint address="net.msmq://localhost/private/DurableDuplex/Service2.xamlx" binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="IDoWork"/>  
               <endpoint binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="INotify"/>  
          </client>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
 Nell'esempio di codice seguente vengono esposti endpoint tramite questa associazione personalizzata modificando il mapping del protocollo predefinito per gli indirizzi di base net.msmq, in modo che venga usata l'associazione personalizzata.  
  
```xml  
<configuration>  
     <system.serviceModel>  
          <protocolMapping>  
               <add scheme="net.msmq" binding="customBinding" bindingConfiguration="netMsmqContextBinding"/>  
          </protocolMapping>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
 Nell'esempio di codice seguente viene abilitata la persistenza per entrambi i servizi aggiungendo agli stessi il comportamento <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> e specificando la stringa di connessione per il database di persistenza.  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
    <system.serviceModel>  
          …  
          <behaviors>  
               <serviceBehaviors>  
                    <behavior>  
                         <serviceDebug includeExceptionDetailInFaults="True"/>  
                         <serviceMetadata httpGetEnabled="True"/>  
                         <sqlWorkflowInstanceStore connectionString="Data Source=.\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True"/>  
                    </behavior>  
               </serviceBehaviors>  
          </behaviors>  
     </system.serviceModel>  
</configuration>  
```  
  
## <a name="system-requirements"></a>Requisiti di sistema  
 Per questo esempio sono richiesti i componenti seguenti.  
  
1.  Internet Information Services.  
  
2.  Internet Information Services -> Compatibilità di gestione con IIS 6.0 -> Compatibilità metabase di IIS e configurazione di IIS 6.0.  
  
3.  Servizi World Wide Web -> Funzionalità per lo sviluppo di applicazioni -> ASP.NET  
  
4.  Microsoft Message Queuing (MSMQ) Server.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Impostare il database di persistenza e la directory dei risultati.  
  
    1.  Aprire il prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    2.  Passare alla cartella di questo esempio ed eseguire Setup.cmd.  
  
2.  Impostare l'applicazione virtuale.  
  
    1.  Da un prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] registrare ASP.NET tramite il comando seguente:  
  
        ```  
        aspnet_regiis -i  
        ```  
  
    2.  Eseguire [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con autorizzazioni di amministratore facendo clic [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] e selezionando **Esegui come amministratore**.  
  
    3.  Tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file DurableDuplex.sln.  
  
3.  Impostare le code del servizio:  
  
    1.  Per eseguire il client DurableDuplex, premere CTRL+F5.  
  
    2.  Aprire il **Gestione Computer** console eseguendo `Compmgmt.msc` da un prompt dei comandi.  
  
    3.  Espandere **servizi e applicazioni**, **Accodamento**. **Code private**.  
  
    4.  Le code durableduplex/service1.xamlx e durableduplex/service2.xamlx di mouse e scegliere **proprietà**.  
  
    5.  Selezionare il **sicurezza** scheda e consentono **tutti ricevono messaggi**, **Visualizza il messaggio** e **Invia messaggio** le autorizzazioni per entrambe le code.  
  
    6.  Aprire Gestione Internet Information Services (IIS).  
  
    7.  Passare a **Server**, **siti**, **sito Web predefinito**, **privata**, **Duplex durevole** e selezionare **Opzioni avanzate**.  
  
    8.  Modifica il **protocolli abilitati** a **MSMQ**.  
  
4.  Eseguire l'esempio.  
  
    1.  Passare a http://localhost/private/durableduplex/service1.xamlx e http://localhost/private/durableduplex/service2.xamlx per assicurarsi che entrambi i servizi siano in esecuzione.  
  
    2.  Premere F5 per eseguire DurableDuplexClient.  
  
         Quando lo scambio durevole di messaggi duplex è completato, viene salvato un file result.xml nella cartella C:\Inbox contenente il risultato dello scambio di messaggi.  
  
#### <a name="to-cleanup-optional"></a>Per eseguire la pulizia (facoltativo)  
  
1.  Eseguire Cleanup.cmd.  
  
    1.  Aprire il prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    2.  Passare alla cartella di questo esempio ed eseguire Cleanup.cmd.  
  
2.  Rimuovere l'applicazione virtuale per i servizi.  
  
    1.  Aprire Gestione Internet Information Services (IIS) eseguendo `Inetmgr.exe` da un prompt dei comandi.  
  
    2.  Passare al sito Web predefinito e rimuovere il **privata** directory virtuale.  
  
3.  Rimuovere le code impostate per questo esempio.  
  
    1.  Aprire la console Gestione Computer eseguendo `Compmgmt.msc` da un prompt dei comandi.  
  
    2.  Espandere **servizi e applicazioni**, **Accodamento**, **code Private**.  
  
    3.  Eliminare le code durableduplex/service1.xamlx e durableduplex/service2.xamlx.  
  
4.  Rimuovere la directory C:\Inbox.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDuplex`