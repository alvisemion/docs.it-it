---
title: Cenni preliminari sul controllo FlowLayoutPanel
ms.date: 03/30/2017
f1_keywords:
- FlowLayoutPanel
helpviewer_keywords:
- forms [Windows Forms], dynamic layout
- layout [Windows Forms], dynamic
- Windows Forms, dynamic layout
- FlowLayoutPanel control [Windows Forms], about FlowLayoutPanel control
ms.assetid: 3883e024-f5a0-456d-9c27-b4dfa1cc9045
ms.openlocfilehash: 58d95c2238687b4822155916177172a34c3abb87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="flowlayoutpanel-control-overview"></a>Cenni preliminari sul controllo FlowLayoutPanel
Il controllo <xref:System.Windows.Forms.FlowLayoutPanel> dispone i contenuti in una direzione di flusso orizzontale o verticale. È possibile eseguire il wrapping dei contenuti del controllo da una riga a quella successiva o da una colonna a quella successiva. In alternativa, è possibile troncare i contenuti.  
  
 È possibile specificare la direzione del flusso impostando il valore della proprietà <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>. Il controllo <xref:System.Windows.Forms.FlowLayoutPanel> inverte correttamente la direzione del flusso nei layout da destra a sinistra (RTL, Right-To-Left). È anche possibile specificare se i contenuti del controllo <xref:System.Windows.Forms.FlowLayoutPanel> vengono sottoposti a wrapping o troncati impostando il valore della proprietà <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A>.  
  
 Il controllo <xref:System.Windows.Forms.FlowLayoutPanel> viene automaticamente ridimensionato in base ai contenuti quando si imposta la proprietà <xref:System.Windows.Forms.Control.AutoSize%2A> su `true`. Fornisce inoltre un **FlowBreak** proprietà ai controlli figlio. Impostando il valore della proprietà FlowBreak su `true` , il controllo <xref:System.Windows.Forms.FlowLayoutPanel> interrompe il layout dei controlli nella direzione di flusso corrente ed esegue il wrapping alla riga o colonna successiva.  
  
 Qualsiasi controllo Windows Form può essere figlio del controllo <xref:System.Windows.Forms.FlowLayoutPanel>, tra cui altre istanze di <xref:System.Windows.Forms.FlowLayoutPanel>. Con questa funzionalità, è possibile costruire layout sofisticati in grado di adattarsi alle dimensioni del form in fase di esecuzione.  
  
 Vedere anche [procedura dettagliata: disposizione dei controlli in Windows Form utilizzando FlowLayoutPanel](http://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\)).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [Controllo FlowLayoutPanel](../../../../docs/framework/winforms/controls/flowlayoutpanel-control-windows-forms.md)
