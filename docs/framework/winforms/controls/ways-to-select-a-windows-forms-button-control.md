---
title: Modalità di selezione di un controllo Button Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: 39696be1286efa68fa70b698ba9623911c90e352
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="ways-to-select-a-windows-forms-button-control"></a>Modalità di selezione di un controllo Button Windows Form
È possibile selezionare un pulsante Windows Form nei modi seguenti:  
  
-   Utilizzare il mouse per fare clic sul pulsante.  
  
-   Richiamare il pulsante <xref:System.Windows.Forms.Control.Click> evento nel codice.  
  
-   Spostare lo stato attivo al pulsante premendo il tasto TAB e quindi scegliere il pulsante, premere la barra spaziatrice o INVIO.  
  
-   Premere il tasto di scelta (ALT + lettera sottolineata) per il pulsante. Per ulteriori informazioni sulle chiavi di accesso, vedere [procedura: creazione di chiavi per i controlli Windows Form](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).  
  
-   Se il pulsante è il pulsante "accetta" del form, premendo INVIO sceglie il pulsante, anche se un altro controllo ha lo stato attivo, a meno che non sia di altro tipo di controllo è un altro pulsante, una casella di testo multilinea o un controllo personalizzato che intercetta il tasto INVIO.  
  
-   Se il pulsante è il pulsante "Annulla" del modulo, premere ESC sceglie il pulsante, anche se un altro controllo ha lo stato attivo.  
  
-   Chiamare il <xref:System.Windows.Forms.Button.PerformClick%2A> metodo per selezionare il pulsante a livello di codice.  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica sul controllo Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Procedura: Rispondere alla selezione dei pulsanti di Windows Form](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Controllo Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
