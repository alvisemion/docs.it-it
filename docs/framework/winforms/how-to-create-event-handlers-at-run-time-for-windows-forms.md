---
title: 'Procedura: creare gestori eventi in fase di esecuzione per Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handlers [Windows Forms], creating
- run time [Windows Forms], creating event handlers at
- examples [Windows Forms], event handling
- Button control [Windows Forms], event handlers
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
ms.openlocfilehash: 38453c751e6cc63827f3f1e9d20ad2ebdfc841d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a>Procedura: creare gestori eventi in fase di esecuzione per Windows Form
Oltre a creare gli eventi usando Progettazione Windows Form, è anche possibile creare un gestore eventi in fase di esecuzione. Questa azione consente di connettere i gestori eventi in base alle condizioni nel codice in fase di esecuzione invece di connetterli all'avvio iniziale del programma.  
  
### <a name="to-create-an-event-handler-at-run-time"></a>Per creare un gestore eventi in fase di esecuzione  
  
1.  Aprire il form nell'editor di codice in cui si desidera aggiungere un gestore eventi.  
  
2.  Aggiungere un metodo al modulo con la firma del metodo per l'evento che si desidera gestire.  
  
     Ad esempio, se si sta gestendo il <xref:System.Windows.Forms.Control.Click> evento di un <xref:System.Windows.Forms.Button> (controllo), creare un metodo come illustrato di seguito:  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As EventArgs)  
       ' Add event handler code here.  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
    // Add event handler code here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          // Add event handler code here.  
       }  
    ```  
  
3.  Aggiungere un codice al gestore dell'evento appropriato per l'applicazione.  
  
4.  Stabilire per quale modulo o controllo si desidera creare un gestore eventi.  
  
5.  In un metodo nella classe del modulo, aggiungere il codice che specifica il gestore eventi per gestire l'evento. Ad esempio, il codice seguente specifica il gestore dell'evento `button1_Click` handle di <xref:System.Windows.Forms.Control.Click> evento di un <xref:System.Windows.Forms.Button> controllo:  
  
    ```vb  
    AddHandler Button1.Click, AddressOf Button1_Click  
    ```  
  
    ```csharp  
    button1.Click += new EventHandler(button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     Il <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> metodo illustrato nel codice Visual Basic precedente imposta un gestore eventi click del pulsante.  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione di gestori eventi in Windows Form](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [Informazioni generali sui gestori eventi](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)  
 [Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
