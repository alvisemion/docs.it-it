---
title: ConditionedActivityGroup
ms.date: 03/30/2017
ms.assetid: f76ef924-34ce-48ae-8c8d-48faf9697754
ms.openlocfilehash: 3560542b912f9697ec2e77c8d5c82e148a41d485
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="conditioned-activity-group"></a>ConditionedActivityGroup
Nell'esempio viene illustrata un'applicazione di prenotazione di viaggio. <xref:System.Workflow.Activities.ConditionedActivityGroup> (CAG) ha due attività di codice: un'attività Car e una attività Airline. Nel costruttore `SimpleCAGWorkflow`, un oggetto ArrayList "travelNeedType" viene popolato con i tipi di prenotazioni di viaggio richiesti. Tramite l'aggiunta di commenti a una o entrambe le istruzioni `travelNeeds.Add`, il comportamento di CAG viene modificato di conseguenza. Entrambi le attività Car e Airline dispongono della condizione <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> popolata con una <xref:System.Workflow.Activities.CodeCondition>. L'attività Car viene eseguita solo se la raccolta `travelNeeds` dispone di una voce `TravelNeeds.Car` e l'attività Airline viene eseguita solo se la raccolta `travelNeeds` dispone di una voce `TravelNeeds.Airline`.  
  
 L'esecuzione di ciascuna attività rimuove la voce corrispondente dalla raccolta. La condizione <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A> predefinita specifica che CAG debba essere chiuso se non sono presenti esecuzione da parte dei figli o se i figli sono pronti per l'esecuzione (in base alle condizioni <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>). In questo esempio, ciò vuole dire che CAG viene chiuso quando la raccolta `travelNeeds` è vuota.  
  
### <a name="to-build-the-sample"></a>Per compilare l'esempio  
  
1.  Aprire la soluzione in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Premere CTRL+MAIUSC+B per compilare la soluzione,  
  
3.  Eseguire la soluzione senza debug premendo CTRL+F5.  
  
### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
-   Nella finestra del prompt dei comandi di SDK eseguire il file con estensione exe nella cartella SimpleCAG\bin\debug (oppure nella cartella SimpleCAG\bin per la versione Visual Basic dell'esempio), collocata sotto la cartella principale dell'esempio.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\SimpleCAG`  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Workflow.Activities.ConditionedActivityGroup>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>  
 <xref:System.Workflow.Activities.CodeCondition>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A>
