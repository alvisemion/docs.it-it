---
title: Utilizzo di base delle attività SendParameters e ReceiveParameters
ms.date: 03/30/2017
ms.assetid: 1b6b1681-3d41-403f-bfe2-3f600f24aa8c
ms.openlocfilehash: 8732b10f3f96ccf9ed352f9b54c60a4ee0d1664c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="basic-usage-of-sendparameters-and-receiveparameters-activities"></a>Utilizzo di base delle attività SendParameters e ReceiveParameters
Nell'esempio seguente viene illustrato l'uso delle attività <xref:System.ServiceModel.Activities.SendParametersContent> e <xref:System.ServiceModel.Activities.ReceiveParametersContent>. Il servizio espone un'operazione che accetta un argomento di tipo stringa e restituisce l'input al client. Nell'esempio viene illustrato come configurare i parametri per queste attività di messaggistica.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\SendReceiveParameters`  
  
#### <a name="using-this-sample"></a>Utilizzo dell'esempio  
  
1.  Caricare la soluzione del progetto in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] e compilare il progetto.  
  
2.  Eseguire innanzitutto l'applicazione EchoWorkflowService, generata in [directory soluzione di base]\EchoWorkflowService\bin\debug.  
  
3.  In secondo luogo eseguire l'applicazione EchoWorkflowClient generata in [directory soluzione di base]\EchoWorkflowClient\bin\debug.  
  
4.  Il client chiama l'operazione Echo nel servizio e stampa i risultati. Al termine premere INVIO per uscire dal client e quindi dal servizio.