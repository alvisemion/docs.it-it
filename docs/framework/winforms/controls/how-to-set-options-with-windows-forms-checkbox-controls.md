---
title: 'Procedura: impostare opzioni con i controlli CheckBox di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- checked
helpviewer_keywords:
- CheckBox control [Windows Forms], checked state
- check boxes [Windows Forms], using to set options
- CheckBox control [Windows Forms], using to set options
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
ms.openlocfilehash: dc9e7b1aea74874c66bf9eb96a5b919ed9b4b73b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a>Procedura: impostare opzioni con i controlli CheckBox di Windows Form
Un Windows Form <xref:System.Windows.Forms.CheckBox> controllo le opzioni Yes/No o viene utilizzata per assegnare utenti a True o False. Quando è selezionata, il controllo Visualizza un segno di spunta.  
  
### <a name="to-set-options-with-checkbox-controls"></a>Per impostare le opzioni con i controlli CheckBox  
  
1.  Esaminare il valore della <xref:System.Windows.Forms.CheckBox.Checked%2A> proprietà per determinare lo stato e utilizzare tale valore per impostare un'opzione.  
  
     Nell'esempio di codice seguente, quando il <xref:System.Windows.Forms.CheckBox> del controllo <xref:System.Windows.Forms.CheckBox.CheckedChanged> viene generato l'evento, il modulo <xref:System.Windows.Forms.Control.AllowDrop%2A> è impostata su `false` se è selezionata la casella di controllo. Ciò è utile per le situazioni in cui si desidera limitare l'interazione dell'utente.  
  
    ```vb  
    Private Sub CheckBox1_CheckedChanged(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles CheckBox1.CheckedChanged  
       ' Determine the CheckState of the check box.  
       If CheckBox1.CheckState = CheckState.Checked Then  
          ' If checked, do not allow items to be dragged onto the form.  
          Me.AllowDrop = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_CheckedChanged(object sender, System.EventArgs e)  
    {  
       // Determine the CheckState of the check box.  
       if (checkBox1.CheckState == CheckState.Checked)   
       {  
          // If checked, do not allow items to be dragged onto the form.  
          this.AllowDrop = false;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Determine the CheckState of the check box.  
          if (checkBox1->CheckState == CheckState::Checked)   
          {  
             // If checked, do not allow items to be dragged onto the form.  
             this->AllowDrop = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.CheckBox>  
 [Panoramica sul controllo CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [Procedura: Rispondere alla selezione di controlli CheckBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)  
 [Controllo CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
