---
title: 'Procedura: interrompere il caricamento di una pagina'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], stopping from loading
- methods [WPF], Stoploading
- events [WPF], NavigationStopped
- NavigationStopped properties [WPF]
- stopping pages from loading [WPF]
- loading [WPF], stopping
ms.assetid: e2b695b0-517e-462c-8ccf-90cc8d6ba864
ms.openlocfilehash: e5cd7d1b881b816636c3acdd4d33565304ca9b63
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-stop-a-page-from-loading"></a>Procedura: interrompere il caricamento di una pagina
In questo esempio viene illustrato come chiamare il <xref:System.Windows.Navigation.NavigationWindow.StopLoading%2A> metodo per interrompere l'esplorazione del contenuto prima che sia stato scaricato.  
  
## <a name="example"></a>Esempio  
 <xref:System.Windows.Navigation.NavigationWindow.StopLoading%2A> Interrompe il download del contenuto richiesto e causa il <xref:System.Windows.Navigation.NavigationWindow.NavigationStopped> dell'evento.  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateStopLoadingCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatestoploadingcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateStopLoadingCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatestoploadingcode)]
