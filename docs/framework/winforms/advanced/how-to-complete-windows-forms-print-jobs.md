---
title: 'Procedura: completare processi di stampa in Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: 74a8e3721df72415437dd0c39b3298d67c19990b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-complete-windows-forms-print-jobs"></a>Procedura: completare processi di stampa in Windows Form
Spesso, elaboratori di testo e altre applicazioni che eseguono processi di stampa fornirà l'opzione per visualizzare un messaggio agli utenti che un processo di stampa è stato completato. È possibile fornire questa funzionalità in Windows Form mediante la gestione di <xref:System.Drawing.Printing.PrintDocument.EndPrint> evento del <xref:System.Drawing.Printing.PrintDocument> componente.  
  
 La procedura seguente presuppone che sia stato creato un'applicazione basata su Windows con un <xref:System.Drawing.Printing.PrintDocument> componente su di esso, che è il metodo standard per consentire la stampa da un'applicazione basata su Windows. Per ulteriori informazioni sulla stampa di Windows Form utilizzando la <xref:System.Drawing.Printing.PrintDocument> componente, vedere [procedura: creare Windows Form processi di stampa Standard](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md).  
  
### <a name="to-complete-a-print-job"></a>Per completare un processo di stampa  
  
1.  Impostare il <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> proprietà del <xref:System.Drawing.Printing.PrintDocument> componente.  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2.  Scrivere codice per gestire l'evento <xref:System.Drawing.Printing.PrintDocument.EndPrint>.  
  
     Nell'esempio di codice seguente, viene visualizzata una finestra di messaggio, che indica che il documento è terminata la stampa.  
  
    ```vb  
    Private Sub PrintDocument1_EndPrint(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintEventArgs) Handles PrintDocument1.EndPrint  
       MessageBox.Show(PrintDocument1.DocumentName + " has finished printing.")  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_EndPrint(object sender,   
    System.Drawing.Printing.PrintEventArgs e)  
    {  
       MessageBox.Show(printDocument1.DocumentName +   
          " has finished printing.");  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_EndPrint(System::Object ^ sender,  
          System::Drawing::Printing::PrintEventArgs ^ e)  
       {  
          MessageBox::Show(String::Concat(printDocument1->DocumentName,  
             " has finished printing."));  
       }  
    ```  
  
     (Visual c# e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.  
  
    ```csharp  
    this.printDocument1.EndPrint += new  
       System.Drawing.Printing.PrintEventHandler  
       (this.printDocument1_EndPrint);  
    ```  
  
    ```cpp  
    this->printDocument1->EndPrint += gcnew  
       System::Drawing::Printing::PrintEventHandler  
       (this, &Form1::printDocument1_EndPrint);  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Printing.PrintDocument>  
 [Supporto per la stampa in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
