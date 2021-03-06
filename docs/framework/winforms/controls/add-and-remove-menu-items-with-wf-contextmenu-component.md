---
title: 'Procedura: aggiungere e rimuovere voci di menu tramite il componente ContextMenu Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], removing items
- ContextMenu component [Windows Forms], adding items
- shortcut menus [Windows Forms], removing items
- shortcut menus [Windows Forms], examples
- context menus [Windows Forms], adding items
- shortcut menus [Windows Forms], adding items
- ContextMenu component [Windows Forms], removing items
- context menus [Windows Forms], examples
- examples [Windows Forms], context menus
ms.assetid: 426d1eaf-7fb8-4b0b-8a33-5e8721786ea4
ms.openlocfilehash: 7cc11eaf4a671c76933c2705b41a4df6c35c0536
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a>Procedura: aggiungere e rimuovere voci di menu tramite il componente ContextMenu Windows Form
Viene illustrato come aggiungere e rimuovere voci di menu di scelta rapida in Windows Form.  
  
 Windows Form <xref:System.Windows.Forms.ContextMenu> componente fornisce un menu dei comandi utilizzati frequentemente rilevanti per l'oggetto selezionato. È possibile aggiungere elementi al menu di scelta rapida aggiungendo <xref:System.Windows.Forms.MenuItem> oggetti per il <xref:System.Windows.Forms.Menu.MenuItems%2A> insieme.  
  
 È possibile rimuovere elementi da un menu di scelta rapida in modo permanente; in fase di esecuzione, tuttavia, potrebbe essere più opportuno nascondere o disabilitare le voci.  
  
> [!IMPORTANT]
>  Sebbene <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.ContextMenuStrip> sostituire e aggiungere funzionalità a di <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> controlli delle versioni precedenti, <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> vengono mantenuti per compatibilità con le versioni precedenti e un utilizzo futuro, se si sceglie.  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a>Per rimuovere gli elementi da un menu di scelta rapida  
  
1.  Utilizzare il <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> o <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> metodo il <xref:System.Windows.Forms.Menu.MenuItems%2A> insieme del <xref:System.Windows.Forms.ContextMenu> componente per rimuovere una determinata voce di menu.  
  
    ```vb  
    ' Removes the first item in the shortcut menu.  
    ContextMenu1.MenuItems.RemoveAt(0)  
    ' Removes a particular object from the shortcut menu.  
    ContextMenu1.MenuItems.Remove(mnuItemNew)  
    ```  
  
    ```csharp  
    // Removes the first item in the shortcut menu.  
    contextMenu1.MenuItems.RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1.MenuItems.Remove(mnuItemNew);  
    ```  
  
    ```cpp  
    // Removes the first item in the shortcut menu.  
    contextMenu1->MenuItems->RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1->MenuItems->Remove(mnuItemNew);  
    ```  
  
     oppure  
  
2.  Utilizzare il `Clear` metodo il `MenuItems` insieme del <xref:System.Windows.Forms.ContextMenu> dei componenti da rimuovere tutti gli elementi dal menu.  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ContextMenu>  
 [Componente ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-windows-forms.md)  
 [Panoramica sul componente ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)
