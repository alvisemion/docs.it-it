---
title: Gestione dell'input dell'utente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user input using code
- custom controls [Windows Forms], keyboard events using code
- custom controls [Windows Forms], mouse events using code
ms.assetid: d9b12787-86f6-4022-8e0f-e12d312c4af2
ms.openlocfilehash: a230611bfbb0a7f21a96de22674377887cc93c2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="handling-user-input"></a>Gestione dell'input dell'utente
In questo argomento vengono descritti gli eventi di tastiera e mouse principali forniti da <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Quando si gestisce un evento, gli autori dei controlli devono eseguire l'override del metodo protetto `On`*EventName* anziché associare un delegato all'evento. Per una panoramica degli eventi, vedere [Generazione di eventi da un componente](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).  
  
> [!NOTE]
>  Se non sono presenti dati associati a un evento, un'istanza della classe di base <xref:System.EventArgs> viene passato come argomento per il `On` *EventName* metodo.  
  
## <a name="keyboard-events"></a>Eventi della tastiera  
 Gli eventi della tastiera che è in grado di gestire il controllo sono <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, e <xref:System.Windows.Forms.Control.KeyUp>.  
  
|Nome evento|Metodo di cui eseguire l'override|Descrizione dell'evento|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|Generato solo quando un tasto viene premuto inizialmente.|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|Generato ogni volta che un tasto viene premuto. Se una si tiene premuto, un <xref:System.Windows.Forms.Control.KeyPress> evento viene generato alla frequenza definita dal sistema operativo.|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|Viene generato quando un tasto viene rilasciato.|  
  
> [!NOTE]
>  La gestione dell'input da tastiera è notevolmente più complessa dell'override degli eventi nella tabella precedente ed esula dall'ambito di questo argomento. Per altre informazioni, vedere [Input dell'utente in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md).  
  
## <a name="mouse-events"></a>Eventi del mouse  
 Gli eventi del mouse in grado di gestire il controllo sono <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, e <xref:System.Windows.Forms.Control.MouseUp>.  
  
|Nome evento|Metodo di cui eseguire l'override|Descrizione dell'evento|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|Viene generato quando il pulsante del mouse viene premuto mentre il puntatore si trova sopra il controllo.|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|Viene generato quando il puntatore del mouse entra nell'area del controllo.|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|Viene generato quando il puntatore è posizionato sul controllo.|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|Viene generato quando il puntatore esce dall'area del controllo.|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|Viene generato quando il puntatore si sposta nell'area del controllo.|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|Viene generato quando il pulsante del mouse viene rilasciato mentre il puntatore si trova sul controllo o il puntatore esce dall'area del controllo.|  
  
 Frammento di codice seguente viene illustrato un esempio di override di <xref:System.Windows.Forms.Control.MouseDown> evento.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 Frammento di codice seguente viene illustrato un esempio di override di <xref:System.Windows.Forms.Control.MouseMove> evento.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 Frammento di codice seguente viene illustrato un esempio di override di <xref:System.Windows.Forms.Control.MouseUp> evento.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 Per il codice sorgente completo dell'esempio `FlashTrackBar`, vedere [Procedura: Creare un controllo di Windows Forms che visualizzi lo stato di avanzamento](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Eventi dei controlli di Windows Form](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [Definizione di un evento](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [Eventi](../../../../docs/standard/events/index.md)  
 [Input dell'utente in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md)
