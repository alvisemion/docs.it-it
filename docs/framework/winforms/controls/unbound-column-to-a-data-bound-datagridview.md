---
title: 'Procedura: aggiungere una colonna non associata a un controllo DataGridView di Windows Form associato ai dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], unbound data
- data grids [Windows Forms], adding unbound columns
- DataGridView control [Windows Forms], unbound data
ms.assetid: f7bdc4d8-ba8e-421b-ad62-82d936f01372
ms.openlocfilehash: 8ba06457371bab5b81e18a307960a833d1d54199
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-an-unbound-column-to-a-data-bound-windows-forms-datagridview-control"></a>Procedura: aggiungere una colonna non associata a un controllo DataGridView di Windows Form associato ai dati
I dati visualizzati nel controllo <xref:System.Windows.Forms.DataGridView> in genere provengono da un'origine dati di qualche tipo, ma è possibile visualizzare una colonna di dati di origine diversa. Questo tipo di colonna è detto colonna non associata. Le colonne non associate possono assumere molte forme. Spesso vengono usate per fornire accesso ai dettagli di una riga di dati.  
  
 Esempio di codice riportato di seguito viene illustrato come creare una colonna non associata di **dettagli** pulsanti da visualizzare una tabella figlio correlata a una determinata riga in una tabella padre quando si implementa uno scenario master-details. Per rispondere alle selezioni dei pulsanti, implementare un gestore dell'evento <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> che visualizzi un form contenente la tabella figlio.  
  
 Questa attività è supportata in Visual Studio.  Vedere anche [procedura: aggiungere e rimuovere colonne nel Windows Form DataGridView controllo usando la finestra di progettazione](http://msdn.microsoft.com/library/dyyesckz\(v=vs.110\))  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#010](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#010)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#010](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#010)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
-   Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 [Visualizzazione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Modalità di visualizzazione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
