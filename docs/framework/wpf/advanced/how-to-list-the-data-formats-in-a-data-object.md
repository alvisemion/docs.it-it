---
title: 'Procedura: elencare i formati dati in un oggetto dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], listing data formats
- DataFormats class [WPF]
- data formats [WPF], listing
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
ms.openlocfilehash: c0e5917d52d9253737a56307beed69bc0255807c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-list-the-data-formats-in-a-data-object"></a>Procedura: elencare i formati dati in un oggetto dati
Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.DataObject.GetFormats%2A> overload del metodo get di una matrice di stringhe indicano ogni formato di dati che è disponibile in un oggetto dati.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Il codice di esempio seguente usa il <xref:System.Windows.DataObject.GetFormats%2A> overload per ottenere una matrice di stringhe che indica tutti i formati di dati disponibili in un oggetto dati (nativo e conversione automatica).  
  
### <a name="code"></a>Codice  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Il codice di esempio seguente usa il <xref:System.Windows.DataObject.GetFormats%2A> overload per ottenere una matrice di stringhe che indica solo i formati di dati disponibili in un oggetto dati (dati convertibili automaticamente i formati sono filtrati).  
  
### <a name="code"></a>Codice  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.IDataObject>  
 [Cenni preliminari sul trascinamento della selezione](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
