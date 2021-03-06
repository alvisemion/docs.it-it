---
title: Cenni preliminari sullo stato attivo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], focus
- focus in applications [WPF]
ms.assetid: 0230c4eb-0c8a-462b-ac4b-ae3e511659f4
ms.openlocfilehash: 620839a0060469604d0affa6637c3cafac0f62c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="focus-overview"></a>Cenni preliminari sullo stato attivo
In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] lo stato attivo è basato su due concetti principali, lo stato attivo della tastiera e lo stato attivo logico.  Lo stato attivo della tastiera fa riferimento all'elemento che riceve l'input della tastiera, mentre lo stato attivo logico fa riferimento all'elemento di un ambito che ha ricevuto lo stato attivo.  In questa panoramica verranno illustrati in dettaglio questi concetti.  Comprendere le differenze esistenti tra questi concetti è fondamentale per la creazione di applicazioni complesse costituite da più aree in cui è possibile ottenere lo stato attivo.  
  
 Le classi principali che fanno parte di gestione dello stato attivo sono il <xref:System.Windows.Input.Keyboard> (classe), il <xref:System.Windows.Input.FocusManager> classe e l'elemento di base le classi, ad esempio <xref:System.Windows.UIElement> e <xref:System.Windows.ContentElement>.  Per altre informazioni sugli elementi di base, vedere [Cenni preliminari sugli elementi di base](../../../../docs/framework/wpf/advanced/base-elements-overview.md).  
  
 Il <xref:System.Windows.Input.Keyboard> classe riguarda principalmente lo stato attivo della tastiera e il <xref:System.Windows.Input.FocusManager> riguarda principalmente con lo stato attivo logico, ma non è una differenza assoluta.  Un elemento con lo stato attivo della tastiera presenta anche lo stato attivo logico, mentre un elemento che ha ottenuto lo stato attivo logico non ha necessariamente lo stato attivo della tastiera.  Questo è evidente quando si utilizza la <xref:System.Windows.Input.Keyboard> classe per impostare l'elemento con stato attivo della tastiera, che imposta anche lo stato attivo logico dell'elemento.  
  

  
<a name="Keyboard_Focus"></a>   
## <a name="keyboard-focus"></a>Stato attivo della tastiera  
 Lo stato attivo della tastiera fa riferimento all'elemento che riceve l'input dalla tastiera.  Su un desktop può esserci un solo elemento con lo stato attivo della tastiera.  In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], l'elemento con lo stato attivo avrà <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> impostato su `true`.  La proprietà statica <xref:System.Windows.Input.Keyboard.FocusedElement%2A> sulla <xref:System.Windows.Input.Keyboard> classe ottiene l'elemento che ha attualmente lo stato attivo.  
  
 Affinché un elemento ottenere lo stato attivo, il <xref:System.Windows.UIElement.Focusable%2A> e <xref:System.Windows.UIElement.IsVisible%2A> sugli elementi di base devono essere impostate su `true`.  Alcune classi, ad esempio il <xref:System.Windows.Controls.Panel> classe di base, avere <xref:System.Windows.UIElement.Focusable%2A> impostato su `false` per impostazione predefinita; pertanto, è necessario impostare <xref:System.Windows.UIElement.Focusable%2A> per `true` se si desidera essere in grado di ottenere lo stato attivo della tastiera tale elemento.  
  
 Lo stato attivo della tastiera può essere ottenuto tramite interazione dell'utente con l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], ad esempio usando il tasto TAB per spostarsi su un elemento o facendo clic con il mouse su alcuni elementi.  Stato attivo della tastiera può anche essere ottenuto a livello di codice utilizzando il <xref:System.Windows.Input.Keyboard.Focus%2A> metodo la <xref:System.Windows.Input.Keyboard> classe.  Il <xref:System.Windows.Input.Keyboard.Focus%2A> metodo tenta di assegnare lo stato attivo della tastiera di elemento specificato.  L'elemento restituito è l'elemento con lo stato attivo della tastiera e potrebbe non essere quello richiesto se l'oggetto stato attivo nuovo o quello precedente blocca la richiesta.  
  
 L'esempio seguente usa il <xref:System.Windows.Input.Keyboard.Focus%2A> per impostare lo stato attivo su un <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[focussample#FocusSampleSetFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 Il <xref:System.Windows.UIElement.IsKeyboardFocused%2A> proprietà sulle classi di elemento di base Ottiene un valore che indica se l'elemento ha lo stato attivo.  Il <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> proprietà sulle classi di elemento di base Ottiene un valore che indica se l'elemento o uno qualsiasi dei relativi elementi figlio visivi con lo stato attivo.  
  
 Quando si imposta lo stato attivo iniziale all'avvio dell'applicazione, l'elemento riceve lo stato attivo deve essere presente nella struttura visiva della finestra iniziale caricata dall'applicazione e l'elemento deve avere <xref:System.Windows.UIElement.Focusable%2A> e <xref:System.Windows.UIElement.IsVisible%2A> impostato su `true`.  La posizione consigliata per impostare lo stato attivo iniziale è il <xref:System.Windows.FrameworkElement.Loaded> gestore dell'evento.  Oggetto <xref:System.Windows.Threading.Dispatcher> callback può essere usato anche chiamando <xref:System.Windows.Threading.Dispatcher.Invoke%2A> o <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>.  
  
<a name="Logical_Focus"></a>   
## <a name="logical-focus"></a>Stato attivo logico  
 Lo stato attivo logico si intende il <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> in un ambito attivo.  Un ambito attivo è un elemento che tiene traccia del <xref:System.Windows.Input.FocusManager.FocusedElement%2A> all'interno dell'ambito.  Quando lo stato attivo della tastiera lascia un ambito di stato attivo, l'elemento con lo stato attivo perde lo stato attivo della tastiera, ma mantiene quello logico.  Quando lo stato attivo della tastiera torna nell'ambito di stato attivo, l'elemento con lo stato attivo ottiene lo stato attivo della tastiera.  In questo modo, lo stato attivo della tastiera può essere passato tra più ambiti, ma l'elemento con lo stato attivo nell'ambito di stato attivo ottiene sicuramente di nuovo lo stato attivo della tastiera quando lo stato attivo ritorna all'ambito di stato attivo.  
  
 In un'applicazione possono esserci più elementi con lo stato attivo logico, ma in un determinato ambito di stato attivo può esserci un solo elemento con lo stato attivo logico.  
  
 Un elemento con stato attivo della tastiera ha lo stato attivo logico per l'ambito a cui appartiene.  
  
 Un elemento può essere convertito in un ambito attivo in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] impostando il <xref:System.Windows.Input.FocusManager> proprietà associata <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> a `true`.  Nel codice, un elemento può essere convertito in un ambito attivo chiamando <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A>.  
  
 Nell'esempio seguente un <xref:System.Windows.Controls.StackPanel> in un ambito attivo impostando la <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> proprietà associata.  
  
 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 <xref:System.Windows.Input.FocusManager.GetFocusScope%2A> Restituisce l'ambito lo stato attivo per l'elemento specificato.  
  
 Le classi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] quali sono gli ambiti lo stato attivo per impostazione predefinita è <xref:System.Windows.Window>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.ToolBar>, e <xref:System.Windows.Controls.ContextMenu>.  
  
 <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A> Ottiene l'elemento con lo stato attivo per l'ambito specificato.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A> Imposta l'elemento con lo stato attivo nell'ambito specificato lo stato attivo.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A> in genere utilizzato per impostare l'elemento con lo stato attivo iniziale.  
  
 L'esempio seguente illustra come impostare e ottenere l'elemento con lo stato attivo in un ambito di stato attivo.  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>   
## <a name="keyboard-navigation"></a>Navigazione tramite tastiera  
 La <xref:System.Windows.Input.KeyboardNavigation> classe è responsabile dell'implementazione spostamento dello stato attivo della tastiera predefinito quando si preme uno dei tasti di navigazione.  ovvero TAB, MAIUSC+TAB, CTRL+TAB, CTRL+MAIUSC+TAB, tasto FRECCIA SU, tasto FRECCIA GIÙ, tasto FRECCIA SINISTRA e tasto FRECCIA DESTRA.  
  
 Il comportamento di navigazione di un contenitore di spostamento può essere modificato impostando collegato <xref:System.Windows.Input.KeyboardNavigation> proprietà <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A>, <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A>, e <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A>.  Queste proprietà sono di tipo <xref:System.Windows.Input.KeyboardNavigationMode> e i valori possibili sono <xref:System.Windows.Input.KeyboardNavigationMode.Continue>, <xref:System.Windows.Input.KeyboardNavigationMode.Local>, <xref:System.Windows.Input.KeyboardNavigationMode.Contained>, <xref:System.Windows.Input.KeyboardNavigationMode.Cycle>, <xref:System.Windows.Input.KeyboardNavigationMode.Once>, e <xref:System.Windows.Input.KeyboardNavigationMode.None>.  Il valore predefinito è <xref:System.Windows.Input.KeyboardNavigationMode.Continue>, ovvero l'elemento non è un contenitore di spostamento.  
  
 Nell'esempio seguente viene creato un <xref:System.Windows.Controls.Menu> con un numero di <xref:System.Windows.Controls.MenuItem> oggetti.  Il <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> proprietà associata è impostata su <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> sul <xref:System.Windows.Controls.Menu>.  Quando viene modificato lo stato attivo usando il tasto tab all'interno di <xref:System.Windows.Controls.Menu>, stato attivo passa da ogni elemento e quando viene raggiunto l'ultimo elemento lo stato attivo ritornerà al primo elemento.  
  
 [!code-xaml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>   
## <a name="navigating-focus-programmatically"></a>Spostamento dello stato attivo a livello di codice  
 Ulteriori [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] per funzionare con stato attivo sono <xref:System.Windows.UIElement.MoveFocus%2A> e <xref:System.Windows.UIElement.PredictFocus%2A>.  
  
 <xref:System.Windows.FrameworkElement.MoveFocus%2A> Sposta lo stato attivo sull'elemento successivo nell'applicazione.  Oggetto <xref:System.Windows.Input.TraversalRequest> viene utilizzato per specificare la direzione.   Il <xref:System.Windows.Input.FocusNavigationDirection> passato a <xref:System.Windows.UIElement.MoveFocus%2A> specifica lo stato attivo direzioni diverse può essere spostato, ad esempio <xref:System.Windows.Input.FocusNavigationDirection.First>, <xref:System.Windows.Input.FocusNavigationDirection.Last>, <xref:System.Windows.Input.FocusNavigationDirection.Up> e <xref:System.Windows.Input.FocusNavigationDirection.Down>.  
  
 L'esempio seguente usa <xref:System.Windows.FrameworkElement.MoveFocus%2A> per modificare l'elemento.  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 <xref:System.Windows.FrameworkElement.PredictFocus%2A> Restituisce l'oggetto che riceve lo stato attivo se venisse modificato lo stato attivo.  Attualmente, solo <xref:System.Windows.Input.FocusNavigationDirection.Up>, <xref:System.Windows.Input.FocusNavigationDirection.Down>, <xref:System.Windows.Input.FocusNavigationDirection.Left>, e <xref:System.Windows.Input.FocusNavigationDirection.Right> sono supportati da <xref:System.Windows.FrameworkElement.PredictFocus%2A>.  
  
<a name="Focus_Events"></a>   
## <a name="focus-events"></a>Eventi di stato attivo  
 Gli eventi correlati allo stato attivo della tastiera sono <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus>, <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> e <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus>, <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>.  Gli eventi sono definiti come eventi associati nella <xref:System.Windows.Input.Keyboard> classe, ma sono maggiormente accessibili come eventi indirizzati equivalenti per le classi di elemento di base.  Per altre informazioni sugli eventi, vedere [Cenni preliminari sugli eventi indirizzati](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> viene generato quando l'elemento otterrà lo stato attivo della tastiera.  <xref:System.Windows.Input.Keyboard.LostKeyboardFocus> viene generato quando l'elemento perde lo stato attivo della tastiera.  Se il <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> evento o <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent> viene gestito l'evento e <xref:System.Windows.RoutedEventArgs.Handled%2A> è impostato su `true`, quindi non modificherà lo stato attivo.  
  
 L'esempio seguente viene collegato <xref:System.Windows.UIElement.GotKeyboardFocus> e <xref:System.Windows.UIElement.LostKeyboardFocus> gestori eventi per un <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[keyboardsample#KeyboardSampleXAMLHandlerHookup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 Quando il <xref:System.Windows.Controls.TextBox> otterrà lo stato attivo della tastiera, il <xref:System.Windows.Controls.Control.Background%2A> proprietà del <xref:System.Windows.Controls.TextBox> viene modificato in <xref:System.Windows.Media.Brushes.LightBlue%2A>.  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 Quando il <xref:System.Windows.Controls.TextBox> perde lo stato attivo della tastiera, il <xref:System.Windows.Controls.Control.Background%2A> proprietà del <xref:System.Windows.Controls.TextBox> ritorna bianco.  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 Gli eventi correlati allo stato attivo logico sono <xref:System.Windows.UIElement.GotFocus> e <xref:System.Windows.UIElement.LostFocus>.  Questi eventi sono definiti sul <xref:System.Windows.Input.FocusManager> come eventi associati, ma la <xref:System.Windows.Input.FocusManager> non espone wrapper di eventi CLR.  <xref:System.Windows.UIElement> e <xref:System.Windows.ContentElement> espongono questi eventi in modo più semplice.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Input.FocusManager>  
 <xref:System.Windows.UIElement>  
 <xref:System.Windows.ContentElement>  
 [Cenni preliminari sull'input](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [Cenni preliminari sugli elementi di base](../../../../docs/framework/wpf/advanced/base-elements-overview.md)
