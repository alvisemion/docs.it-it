---
title: 'Procedura: registrare messaggi all''avvio o all''arresto dell''applicazione (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- event logs, shutdown
- My.Application.Log object, logging
- Startup event [Visual Basic]
- event logs, startup
- Shutdown event [Visual Basic]
- My.Log object, logging
ms.assetid: 67624d05-cddf-48b7-8c36-5c99baa4c621
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 16235e245fd71f16edb67003cf237bcee3a6855e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-log-messages-when-the-application-starts-or-shuts-down-visual-basic"></a>Procedura: registrare messaggi all'avvio o all'arresto dell'applicazione (Visual Basic)
È possibile usare gli oggetti `My.Application.Log` e `My.Log` per registrare informazioni sugli eventi che si verificano nell'applicazione. Questo esempio illustra come usare il metodo `My.Application.Log.WriteEntry` con gli eventi `Startup` e `Shutdown` per scrivere informazioni di traccia.  
  
### <a name="to-access-the-applications-event-handler-code"></a>Per accedere al codice del gestore eventi dell'applicazione  
  
1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.  
  
2.  Fare clic sulla scheda **Applicazione** .  
  
3.  Fare clic sul pulsante **Visualizza eventi applicazione** per aprire l'editor di codice.  
  
     Verrà aperto il file ApplicationEvents.vb.  
  
### <a name="to-log-messages-when-the-application-starts"></a>Per registrare messaggi all'avvio dell'applicazione  
  
1.  Aprire il file ApplicationEvents.vb nell'editor di codice. Scegliere **Eventi MyApplication** dal menu **Generale**.  
  
2.  Scegliere **Avvio** dal menu **Dichiarazioni**.  
  
     L'applicazione genera l'evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> prima dell'esecuzione dell'applicazione principale.  
  
3.  Aggiungere il metodo `My.Application.Log.WriteEntry` al gestore eventi `Startup` .  
  
     [!code-vb[VbVbalrMyApplicationLog#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_1.vb)]  
  
### <a name="to-log-messages-when-the-application-shuts-down"></a>Per registrare messaggi all'arresto dell'applicazione  
  
1.  Aprire il file ApplicationEvents.vb nell'editor di codice. Scegliere **Eventi MyApplication** dal menu **Generale**.  
  
2.  Scegliere **Arresto** dal menu **Dichiarazioni**.  
  
     L'applicazione genera l'evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> dopo l'esecuzione dell'applicazione principale, ma prima dell'arresto.  
  
3.  Aggiungere il metodo `My.Application.Log.WriteEntry` al gestore eventi `Shutdown` .  
  
     [!code-vb[VbVbalrMyApplicationLog#2](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_2.vb)]  
  
## <a name="example"></a>Esempio  
 Per accedere agli eventi dell'applicazione nell'editor del codice è possibile usare **Creazione progetti** . Per altre informazioni, vedere [Pagina Applicazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 [!code-vb[VbVbalrMyApplicationLog#3](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_3.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>  
 [Pagina Applicazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)  
 [Utilizzo dei log applicazione](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
