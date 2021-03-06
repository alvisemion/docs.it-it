---
title: 'Procedura: Creare form padre MDI'
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms
- MDI [Windows Forms], creating forms
ms.assetid: 12c71221-2377-4bb6-b10b-7b4b300fd462
ms.openlocfilehash: 8d7a25b771488540d4867143a62c5c2487803a95
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-mdi-parent-forms"></a>Procedura: Creare form padre MDI
> [!IMPORTANT]
>  In questo argomento viene usato il controllo <xref:System.Windows.Forms.MainMenu> che è stato sostituito dal controllo <xref:System.Windows.Forms.MenuStrip>. Il controllo <xref:System.Windows.Forms.MainMenu> viene mantenuto per la compatibilità con le versioni precedenti e per l'uso futuro, se si desidera.  Per informazioni sulla creazione di una MDI Form padre tramite un <xref:System.Windows.Forms.MenuStrip>, vedere [procedura: creare un elenco di finestre MDI con MenuStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).  
  
 La base di un'applicazione MDI (interfaccia a documenti multipli, Multiple Document Interface) è il form padre MDI. Si tratta del form che contiene le finestre figlio MDI che rappresentano le sottofinestre in cui l'utente interagisce con l'applicazione MDI. La creazione di un form padre MDI è semplice sia in Progettazione Windows Form che a livello di codice.  
  
### <a name="to-create-an-mdi-parent-form-at-design-time"></a>Per creare un form padre MDI in fase di progettazione  
  
1.  Creare un progetto Applicazione Windows.  
  
2.  Nel **proprietà** finestra, impostare il <xref:System.Windows.Forms.Form.IsMdiContainer%2A> proprietà **true**.  
  
     Il form viene così designato come contenitore MDI per le finestre figlio.  
  
    > [!NOTE]
    >  Quando si impostano le proprietà nella finestra **Proprietà**, se si vuole è anche possibile impostare la proprietà `WindowState` su **Ingrandita** per semplificare la modifica delle finestre figlio MDI ingrandendo il form padre. Inoltre, tenere presente che il bordo del form padre MDI applica il colore del sistema (impostato nel Pannello di controllo del sistema Windows) e non il colore di sfondo impostato con la proprietà <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType>.  
  
3.  Dalla **Casella degli strumenti** trascinare un controllo **MenuStrip** nel form. Creare una voce di menu di primo livello con la proprietà **Testo** impostata su **&File** con voci di sottomenu chiamate **&Nuovo** e **&Chiudi**. Creare anche una voce di menu di primo livello chiamata **&Finestra**.  
  
     Il primo menu crea e nasconde le voci di menu al runtime, mentre il secondo tiene traccia delle finestre figlio MDI aperte. A questo punto è stata creata una finestra padre MDI.  
  
4.  Premere **F5** per eseguire l'applicazione. Per informazioni sulla creazione di finestre figlio MDI usate all'interno del form padre MDI, vedere [Procedura: Creare form figlio MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [Procedura: Creare form figlio MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [Procedura: Determinare il figlio MDI attivo](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [Procedura: Inviare dati al figlio MDI attivo](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 [Procedura: Disporre i form figlio MDI](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
