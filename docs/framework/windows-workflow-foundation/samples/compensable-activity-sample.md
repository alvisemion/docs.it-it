---
title: Esempio di CompensableActivity
ms.date: 03/30/2017
ms.assetid: 58f4898c-b2b8-44a4-9a73-3bef4da6d5ba
ms.openlocfilehash: 8008eaaca062723cab1efabfb1b25018353c73b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="compensable-activity-sample"></a>Esempio di CompensableActivity
In questo esempio viene illustrato come usare l'attività `CompensableActivity` per definire il lavoro da eseguire per un'azione specificata durante la normale esecuzione e il lavoro che è necessario eseguire per compensare tale azione, se necessario in un secondo tempo.  La prima parte dell'esempio viene illustrato come unità di lavoro compensabile possono essere definite in Windows Workflow Foundation (WF) utilizzando un `CompensableActivity` attività e come vengono eseguiti in un'esecuzione riuscita.  Nella seconda parte dell'esempio viene illustrato in che modo le stesse unità di lavoro compensabile eseguono automaticamente la compensazione quando viene rilevato un evento imprevisto e l'istanza del flusso di lavoro viene annullata.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Tramite Visual Studio 2010 aprire CompensableActivity.sln.  
  
2.  Premere CTRL+MAIUSC+B per compilare la soluzione,  
  
3.  Eseguire l'applicazione premendo F5.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\BasicCompensableActivity`