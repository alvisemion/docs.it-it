---
title: Data binding in un client ASP.NET
ms.date: 03/30/2017
ms.assetid: 68b49fa6-94e7-4d4c-a34e-902a2b3770b6
ms.openlocfilehash: c0f3cbb08f0078bf364ef720635f7afda3257611
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="data-binding-in-an-aspnet-client"></a>Data binding in un client ASP.NET
Questo esempio viene illustrato come associare i dati restituiti da un servizio tipico di Windows Communication Foundation (WCF) in un'applicazione Web Form.  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 In questo esempio viene illustrato un servizio che implementa un contratto in cui viene definito un modello di comunicazione request/reply. L'esempio è costituito da un'applicazione Web Form client accessibile da un browser e un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ospitato su Internet Information Services (IIS).  
  
 Il servizio implementa un contratto che definisce un modello di comunicazione richiesta/risposta. Il contratto viene definito mediante l'interfaccia `IWeatherService`, che espone un'operazione denominata `GetWeatherData`. Questa operazione accetta una matrice di città e restituisce una matrice di oggetti `WeatherData` che rappresentano la temperatura massima e minima prevista per una città.  
  
 Sulla pagina aspx del client [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], viene definito un controllo Web DataGrid che contiene la rappresentazione grafica dei dati restituiti dal servizio. Il codice presente sulla pagina aspx chiama il servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per ottenere i dati meteorologici e li restituisce a una matrice di oggetti `WeatherData`. Il DataGrid specifica dove ottenere i dati impostando la proprietà `DataSource` su quella matrice. Si verifica l'associazione dati con una chiamata al metodo `DataBind` del DataGrid. Tutto il codice è contenuto all'interno di.`aspx` della pagina `Page_Load` metodo, pertanto ogni volta che l'utente aggiorna la pagina del browser, i dati viene aggiornato in DataGrid.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Il client di questo esempio è un sito Web che è in esecuzione sotto un server Web di sviluppo. Per avviare il server di sviluppo Web, digitare quanto segue al prompt dei comandi: "`%SystemDrive%\Program Files\Common Files\Microsoft Shared\DevServer\9.0\WebDev.WebServer.EXE" /port:8000 /path:<WebFormsSamplePath>\CS\client /vpath:/client`. Quindi passare a http://localhost:8000/client. Per eseguire questo esempio tra più computer, sostituire tutti i riferimenti a `localhost` nel file Web.config del client con il nome del computer che ospita il server.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WebForms`  
  
## <a name="see-also"></a>Vedere anche
