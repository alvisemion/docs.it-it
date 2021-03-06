---
title: Hosting di servizi flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 2d55217e-8697-4113-94ce-10b60863342e
ms.openlocfilehash: 02d77b851dcd35108668ee6a42022e9721b84bd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="hosting-workflow-services"></a>Hosting di servizi flusso di lavoro
Per poter rispondere ai messaggi in arrivo, un servizio flusso di lavoro deve essere ospitato. I servizi flusso di lavoro utilizzano l'infrastruttura di messaggistica WCF e sono quindi ospitati in modi analoghi. Ad esempio i servizi WCF, servizi di flusso di lavoro possono essere ospitati in qualsiasi applicazione gestita, in Internet Information Services (IIS) o nel processo Windows Activation Services (WAS). I servizi flusso di lavoro possono inoltre essere ospitati in Windows Server AppFabric. Per ulteriori informazioni su Windows Server AppFabric, vedere [documentazione di Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=193037), [funzionalità di Hosting di AppFabric](http://go.microsoft.com/fwlink/?LinkId=196494), e [concetti di Hosting di AppFabric](http://go.microsoft.com/fwlink/?LinkId=196495). Per ulteriori informazioni sui diversi modi per ospitare WCF servizi vedere [servizi di Hosting](../../../../docs/framework/wcf/hosting-services.md).  
  
## <a name="hosting-in-a-managed-application"></a>Hosting in un'applicazione gestita  
 Per ospitare un servizio flusso di lavoro in un'applicazione gestita, utilizzare la classe <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Il costruttore <xref:System.ServiceModel.Activities.WorkflowServiceHost> consente di specificare un'istanza di servizio flusso di lavoro singleton, una definizione del servizio flusso di lavoro o un'attività che utilizza le attività di messaggistica del flusso di lavoro. La chiamata a <<!--zz xref:System.ServiceModel.Activities.WorkflowServiceHost.Open%2A--> `System.ServiceModel.Activities.WorkflowServiceHost.Open`>, il servizio avvia l'ascolto dei messaggi in arrivo.  
  
## <a name="hosting-under-iis-or-was"></a>Hosting in IIS o WAS  
 L'hosting di un servizio flusso di lavoro in IIS o WAS prevede la creazione di una directory virtuale e il posizionamento dei file nella directory virtuale che definiscono il servizio e il relativo comportamento. Quando si ospita un servizio flusso di lavoro in IIS o WAS esistono diverse possibilità:  
  
-   Posizionare un file con estensione xamlx che definisce il servizio flusso di lavoro in una directory virtuale IIS/WAS insieme a un file Web.config che specifica i comportamenti del servizio, gli endpoint e altri elementi di configurazione.  
  
-   Posizionare un file con estensione xamlx che definisce il servizio flusso di lavoro in una directory virtuale IIS/WAS. Il file con estensione xamlx specifica gli endpoint da esporre. Gli endpoint sono specificati in un elemento `WorkflowService.Endpoints`, come indicato nell'esempio seguente.  
  
    ```xml  
    <WorkflowService xmlns="http://schemas.microsoft.com/netfx/2009/xaml/servicemodel"  xmlns:p1="http://schemas.microsoft.com/netfx/2009/xaml/activities" xmlns:sad="clr-namespace:System.Activities.Debugger;assembly=System.Activities" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
      <WorkflowService.Endpoints>  
        <Endpoint ServiceContractName="IWorkFlowEchoService" AddressUri="">  
          <Endpoint.Binding>  
            <BasicHttpBinding />  
          </Endpoint.Binding>  
        </Endpoint>  
      </WorkflowService.Endpoints>  
    <!-- ... -->  
    </WorkflowService>  
    ```  
  
    > [!NOTE]
    >  Non è possibile specificare i comportamenti in un file con estensione xamlx, pertanto è richiesto un file Web.config se è necessario specificare impostazioni relative al comportamento.  
  
-   Posizionare un file con estensione xamlx che definisce il servizio flusso di lavoro in una directory virtuale IIS/WAS. Posizionare inoltre un file con estensione svc nella directory virtuale. Il file con estensione svc consente di specificare una factory di host di servizio Web personalizzata, applicare il comportamento personalizzato o caricare la configurazione da un percorso personalizzato.  
  
-   Posizionare un assembly nella directory virtuale IIS/WAS che contiene un'attività che utilizza le attività di messaggistica di WCF.  
  
 Un file con estensione xamlx che definisce un servizio flusso di lavoro deve contenere un <`Service`> radice o un elemento radice che contiene qualsiasi tipo derivato da <xref:System.Workflow.ComponentModel.Activity>. In caso di utilizzo del modello di attività [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], viene creato un file con estensione xamlx. In caso di utilizzo del modello di servizio flusso di lavoro WCF, viene creato un file con estensione xamlx.  
  
## <a name="hosting-workflow-services-under-windows-server-app-fabric"></a>Hosting di servizi flusso di lavoro in Windows Server AppFabric  
 L'hosting di un servizio flusso di lavoro in Windows Server AppFabric è simile all'hosting in IIS/WAS. L'unica differenza consiste nel fatto che Windows Server App Fabric viene installato. In Windows Server AppFabric vengono forniti gli strumenti aggiunti a Gestione Internet Information Services, nonché i cmdlet PowerShell. Tali strumenti semplificano la distribuzione, la gestione e il rilevamento dei servizi flusso di lavoro e dei servizi WCF. . Per ulteriori informazioni su Windows Server AppFabric vedere [Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=193037)  
  
## <a name="referencing-custom-activities"></a>Riferimento ad attività personalizzate  
 Aggiungere riferimenti alle attività personalizzate di <`Assemblies`> sezione nel <`System.Web.Compilation`> in modo che vengano caricati nel dominio applicazione e il deserializzatore XAML è in grado di individuare i tipi. È possibile configurare queste impostazioni a livello dell'applicazione o nel file Web.config radice, se tali impostazioni devono essere applicate a tutte le applicazioni nel computer.  
  
## <a name="deployment"></a>Distribuzione  
 Lo strumento Distribuzione Web è stato creato per agevolare il processo di distribuzione. Lo strumento consente di eseguire la migrazione delle applicazioni tra IIS 6.0 e IIS 7.0, sincronizzare server farm e inserire in pacchetti, archiviare e distribuire applicazioni Web. Per altre informazioni, vedere [dello strumento di distribuzione MS](http://go.microsoft.com/fwlink/?LinkId=178690)  
  
## <a name="see-also"></a>Vedere anche  
 [Elementi interni dell'host dei servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 [Configurazione di WorkflowServiceHost](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)
