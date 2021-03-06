---
title: 'Procedura: rilevare eventuali modifiche del testo in un oggetto TextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 1befd18220488334319a55bce2ce602aef20d3d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a>Procedura: rilevare eventuali modifiche del testo in un oggetto TextBox
In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> evento per eseguire un metodo ogni volta che il testo in un <xref:System.Windows.Controls.TextBox> controllo è stato modificato.  
  
 Nella classe code-behind per il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che contiene il <xref:System.Windows.Controls.TextBox> controllo che si desidera monitorare per le modifiche, inserire un metodo da chiamare quando il <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> viene generato l'evento.  Questo metodo deve avere una firma che corrisponde a quella prevista dal <xref:System.Windows.Controls.TextChangedEventHandler> delegato.  
  
 Il gestore eventi viene chiamato ogni volta che il contenuto del <xref:System.Windows.Controls.TextBox> controllo vengono modificati, da un utente o a livello di codice.  
  
 **Nota:** questo evento viene generato quando il <xref:System.Windows.Controls.TextBox> controllo viene creato e popolato inizialmente con testo.  
  
## <a name="example"></a>Esempio  
 Nel [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] che definisce il <xref:System.Windows.Controls.TextBox> di controllo, specificare il <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attributo con un valore che corrisponde al nome di metodo del gestore eventi.  
  
 [!code-xaml[TextBox_MiscCode#_TextChangedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]  
  
## <a name="example"></a>Esempio  
 Nella classe code-behind per il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che contiene il <xref:System.Windows.Controls.TextBox> controllo che si desidera monitorare per le modifiche, inserire un metodo da chiamare quando il <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> viene generato l'evento.  Questo metodo deve avere una firma che corrisponde a quella prevista dal <xref:System.Windows.Controls.TextChangedEventHandler> delegato.  
  
 [!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
 [!code-vb[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]  
  
 Il gestore eventi viene chiamato ogni volta che il contenuto del <xref:System.Windows.Controls.TextBox> controllo vengono modificati, da un utente o a livello di codice.  
  
 **Nota:** questo evento viene generato quando il <xref:System.Windows.Controls.TextBox> controllo viene creato e popolato inizialmente con testo.  
  
 Commenti  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.TextChangedEventArgs>  
 [Cenni preliminari sulla classe TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [Cenni preliminari sul controllo RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
