---
title: Controlli costitutivi
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], constituent controls
- constituent controls [Windows Forms]
- user controls [Windows Forms], constituent controls
ms.assetid: 5565e720-198b-4bbd-a2bd-c447ba641798
ms.openlocfilehash: 6fb708b81089b4fcd3678b35d1bcf7da2244c6d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="constituent-controls"></a>Controlli costitutivi
I controlli che costituiscono un controllo utente, detti anche *controlli costitutivi*, offrono scarsa flessibilità in termini di rendering personalizzato della grafica. Tutti i controlli Windows Form di gestire le proprie per il rendering tramite i propri <xref:System.Windows.Forms.Control.OnPaint%2A> metodo. Poiché questo metodo è protetto, non è accessibile allo sviluppatore e quindi non è possibile evitarne l'esecuzione quando il controllo viene disegnato. Ciò non implica tuttavia che non sia possibile aggiungere codice per modificare l'aspetto dei controlli costitutivi. Per eseguire un altro rendering, è possibile aggiungere un gestore eventi. Ad esempio, si supponga di creare un <xref:System.Windows.Forms.UserControl> con un pulsante denominato `MyButton`. Se si desidera disporre di rendering aggiuntivi oltre a quello fornito dal <xref:System.Web.UI.WebControls.Button>, è necessario aggiungere codice al controllo utente simile al seguente:  
  
```vb  
Public Sub MyPaint(ByVal sender as Object, e as PaintEventArgs) Handles _  
   MyButton.Paint  
   'Additional rendering code goes here  
End Sub  
```  
  
```csharp  
// Add the event handler to the button's Paint event.  
MyButton.Paint +=   
   new System.Windows.Forms.PaintEventHandler (this.MyPaint);  
// Create the custom painting method.  
protected void MyPaint (object sender,   
System.Windows.Forms.PaintEventArgs e)  
{  
   // Additional rendering code goes here.  
}  
```  
  
> [!NOTE]
>  Controlli di alcuni moduli di Windows, ad esempio <xref:System.Windows.Forms.TextBox>, sono disegnati direttamente da Windows. In questi casi, il <xref:System.Windows.Forms.Control.OnPaint%2A> non viene mai chiamato e l'esempio precedente non verrà mai chiamato.  
  
 Viene quindi creato un metodo eseguito ogni volta che viene eseguito l'evento `MyButton.Paint`, aggiungendo in tal modo un'altra rappresentazione grafica al controllo. Si noti che ciò non impedisce l'esecuzione di `MyButton.OnPaint` e quindi tutti i disegni eseguiti normalmente da un pulsante continueranno a essere eseguiti in aggiunta al disegno personalizzato. Per informazioni dettagliate sulla tecnologia GDI+ e sul rendering personalizzato, vedere [Creazione di immagini grafiche con GDI+](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md). Per avere una rappresentazione univoca del controllo, è consigliabile creare un controllo ereditato per cui scrivere il codice di rendering personalizzato. Per informazioni dettagliate, vedere [Controlli creati dall'utente](../../../../docs/framework/winforms/controls/user-drawn-controls.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.UserControl>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [Controlli creati dall'utente](../../../../docs/framework/winforms/controls/user-drawn-controls.md)  
 [Procedura: Creare oggetti Graphics per disegnare](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Tipi di controlli personalizzati](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
