---
title: Comunicazione asincrona
ms.date: 03/30/2017
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
ms.openlocfilehash: 9eafeab89aefb181ae016dc0219f9155d9bd2a25
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="asynchronous-communication"></a>Comunicazione asincrona
Questo esempio viene illustrato come la comunicazione tra due diversi servizi di Windows Workflow Foundation (WF) viene eseguita in modo asincrono per impostazione predefinita.  
  
## <a name="demonstrates"></a>Dimostrazione  
 Comunicazione asincronica tra servizi [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  
  
## <a name="discussion"></a>Discussione  
 In questo esempio viene illustrata la modalità di esecuzione della comunicazione asincrona tra applicazioni [!INCLUDE[wf1](../../../../includes/wf1-md.md)] tramite le attività di messaggistica fornite da .NET Framework.  
  
 L'esempio è costituito dai tre progetti seguenti.  
  
 CreditCheckService  
 Questo servizio riceve il punteggio del credito di una particolare persona o il valore dell'elemento da acquisire, quindi stabilisce se viene concesso alla persona il credito.  
  
 RentalApprovalService  
 Questo servizio riceve un'applicazione da una persona che richiede credito. Il servizio comunica in modo asincrono con `CreditCheckService` per determinare se la richiesta di credito è valida.  
  
 Client  
 Il client comunica in modo sincrono con `RentalApprovalService` per sapere se il credito è approvato.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Fare doppio clic su di **AsynchronousCommunication** soluzioni e selezionare **proprietà**.  
  
2.  In **proprietà comuni**selezionare **progetto di avvio**e selezionare **più progetti di avvio**.  
  
3.  Spostare **RentalApprovalService** nella prima posizione nell'elenco, seguito da **CreditCheckService**, seguito da **Client**. Impostare il **avviare** azione in tutti e tre i progetti.  
  
4.  Fare clic su **OK**, premere F5 per eseguire l'esempio.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
