---
title: 'Procedura: aprire una finestra di dialogo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- opening dialog boxes [WPF]
- dialog boxes [WPF], opening
ms.assetid: 6b1557d2-da98-4ef4-9f68-4089f04ab9ea
ms.openlocfilehash: 29fe8b0d516f20fcc742b91099a30e368dfe4548
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-open-a-dialog-box"></a>Procedura: aprire una finestra di dialogo
In questo esempio viene illustrato come aprire una finestra di dialogo.  
  
## <a name="example"></a>Esempio  
 Una finestra di dialogo è una finestra che viene aperta creando <xref:System.Windows.Window> e chiamando il <xref:System.Windows.Window.ShowDialog%2A> metodo. <xref:System.Windows.Window.ShowDialog%2A> Apre una finestra e non restituisce fino a quando non è stata chiusa la finestra di dialogo Nuovo. Questo tipo di finestra è noto anche come un *modale* finestra e limita l'input dell'utente.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 La chiamata <xref:System.Windows.Window.ShowDialog%2A> richiede l'autorizzazione per utilizzare tutte le finestre e gli eventi di input utente senza restrizioni.  
  
## <a name="see-also"></a>Vedere anche  
 [Restituire il risultato di una finestra di dialogo](../../../../docs/framework/wpf/app-development/how-to-return-a-dialog-box-result.md)
