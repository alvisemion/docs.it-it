---
title: Considerazioni aggiuntive sulla sicurezza in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, secure calls to Windows API
- security [Windows Forms]
- security [Windows Forms], calling APIs
- Clipboard [Windows Forms], securing access
ms.assetid: 15abda8b-0527-47c7-aedb-77ab595f2bf1
ms.openlocfilehash: a1d8606eb972a6e3bea52f6230cb893a4bbb5aac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="additional-security-considerations-in-windows-forms"></a>Considerazioni aggiuntive sulla sicurezza in Windows Form
Le impostazioni di sicurezza di [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] potrebbero modificare l'esecuzione di un'applicazione in un ambiente ad attendibilità parziale rispetto al computer locale. [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] limita l'accesso a tali risorse locali critiche, ad esempio il file system, la rete e le API non gestite. Le impostazioni di sicurezza influiscono sulla capacità di chiamare l'API Microsoft Win32 o altre API non verificabili dal sistema di sicurezza. La sicurezza influisce inoltre su altri aspetti dell'applicazione, inclusi l'accesso ai file e ai dati e la stampa. Per altre informazioni sull'accesso a file e dati in un ambiente ad attendibilità parziale, vedere [More Secure File and Data Access in Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md) (Accesso più sicuro a file e dati in Windows Form). Per altre informazioni sulla stampa in un ambiente ad attendibilità parziale, vedere [More Secure Printing in Windows Forms](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md) (Stampa più sicura in Windows Form).  
  
 Le sezioni seguenti illustrano come usare gli Appunti, modificare le finestre e chiamare l'API Win32 dalle applicazioni in esecuzione in un ambiente ad attendibilità parziale.  
  
## <a name="clipboard-access"></a>Accesso agli Appunti  
 Il <xref:System.Security.Permissions.UIPermission> classe controlla l'accesso a negli Appunti e associato <xref:System.Security.Permissions.UIPermissionClipboard> valore di enumerazione indica il livello di accesso. Nella tabella seguente sono elencati i livelli di autorizzazione possibili.  
  
|Valore UIPermissionClipboard|Descrizione|  
|---------------------------------|-----------------|  
|<xref:System.Security.Permissions.UIPermissionClipboard.AllClipboard>|È possibile usare gli Appunti senza restrizioni.|  
|<xref:System.Security.Permissions.UIPermissionClipboard.OwnClipboard>|È possibile usare gli Appunti con alcune restrizioni. Possibilità di inserire dati negli Appunti (operazioni dei comandi Copia o Taglia) senza restrizioni. I controlli intrinseci che accettano operazioni Incolla, ad esempio una casella di testo, possono accettare i dati negli Appunti, ma i controlli utente non possono leggere a livello di codice dagli Appunti.|  
|<xref:System.Security.Permissions.UIPermissionClipboard.NoClipboard>|Impossibile usare gli Appunti.|  
  
 Per impostazione predefinita, l'area Intranet locale riceve <xref:System.Security.Permissions.UIPermissionClipboard.AllClipboard> accesso e l'area Internet riceve <xref:System.Security.Permissions.UIPermissionClipboard.OwnClipboard> accesso. Ciò significa che l'applicazione può copiare dati negli Appunti, ma non può incollare negli Appunti o leggere dagli Appunti a livello di codice. Queste restrizioni impediscono ai programmi senza attendibilità totale di leggere il contenuto copiati negli Appunti da un'altra applicazione. Se l'applicazione richiede l'accesso completo agli Appunti ma non disporre delle autorizzazioni, sarà necessario elevarne le autorizzazioni. Per altre informazioni sull'elevazione delle autorizzazioni, vedere [General Security Policy Administration](http://msdn.microsoft.com/library/5121fe35-f0e3-402c-94ab-4f35b0a87b4b) (Amministrazione generale dei criteri di sicurezza).  
  
## <a name="window-manipulation"></a>Modifica delle finestre  
 Il <xref:System.Security.Permissions.UIPermission> classe controlla anche dell'autorizzazione per eseguire la modifica delle finestre e altre azioni correlate all'interfaccia utente e associato <xref:System.Security.Permissions.UIPermissionWindow> valore di enumerazione indica il livello di accesso. Nella tabella seguente sono elencati i livelli di autorizzazione possibili.  
  
 Per impostazione predefinita, l'area Intranet locale riceve <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> accesso e l'area Internet riceve <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> accesso. Ciò significa che, nell'area Internet, l'applicazione può eseguire la maggior parte delle azioni legate a finestre e interfaccia utente, con conseguente modifica dell'aspetto della finestra. La finestra modificata visualizza una notifica alla prima esecuzione, contiene testo modificato nella barra del titolo e richiede un pulsante di chiusura nella medesima barra. La notifica e la barra del titolo indicano all'utente dell'applicazione che quest'ultima è in esecuzione ad attendibilità parziale.  
  
|Valore UIPermissionWindow|Descrizione|  
|------------------------------|-----------------|  
|<xref:System.Security.Permissions.UIPermissionWindow.AllWindows>|Gli utenti possono usare tutte le finestre e tutti gli eventi input utente senza restrizioni.|  
|<xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows>|Gli utenti possono usare solo le più sicure finestre principali e secondarie per il disegno e possono usare solo gli eventi input utente dell'interfaccia all'interno di tali finestre. Queste finestre sicure sono contrassegnate in modo chiaro e dispongono di restrizioni per la dimensione minima e massima. Le restrizioni impediscono attacchi di spoofing potenzialmente dannosi, ad esempio imitazione delle schermate di accesso di sistema o il desktop e limita l'accesso a livello di codice per padre l'utilizzo di windows e le API correlate lo stato attivo di <xref:System.Windows.Forms.ToolTip> (controllo),|  
|<xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows>|Gli utenti possono usare solo le più sicure finestre secondarie per il disegno e possono usare solo gli eventi input utente dell'interfaccia all'interno di tali finestre. Un controllo visualizzato all'interno di un browser è un esempio di finestra secondaria sicura.|  
|<xref:System.Security.Permissions.UIPermissionWindow.NoWindows>|Gli utenti non possono usare finestre o eventi dell'interfaccia utente. Non è possibile usare l'interfaccia utente.|  
  
 Ogni livello di autorizzazione identificata le <xref:System.Security.Permissions.UIPermissionWindow> enumerazione consente meno azioni rispetto al livello superiore. Nelle tabelle seguenti indicano le azioni che sono limitate dal <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> e <xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows> valori. Per le autorizzazioni esattamente necessarie per ogni membro, vedere il riferimento per tale membro nella documentazione della libreria di classi .NET Framework.  
  
 <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> autorizzazione limita le azioni elencate nella tabella seguente.  
  
|Componente|Azioni limitate|  
|---------------|------------------------|  
|<xref:System.Windows.Forms.Application>|-   Impostazione della proprietà <xref:System.Windows.Forms.Application.SafeTopLevelCaptionFormat%2A>.|  
|<xref:System.Windows.Forms.Control>|-Ottenere la <xref:System.Windows.Forms.Control.Parent%2A> proprietà.<br />-   Impostazione della proprietà `Region`.<br />-La chiamata di <xref:System.Windows.Forms.Control.FindForm%2A> , <xref:System.Windows.Forms.Control.Focus%2A>, <xref:System.Windows.Forms.Control.FromChildHandle%2A> e <xref:System.Windows.Forms.Control.FromHandle%2A>, <xref:System.Windows.Forms.Control.PreProcessMessage%2A>, <xref:System.Windows.Forms.Control.ReflectMessage%2A>, o <xref:System.Windows.Forms.Control.SetTopLevel%2A> metodo.<br />-La chiamata di <xref:System.Windows.Forms.Control.GetChildAtPoint%2A> metodo se il controllo restituito non è un figlio del controllo chiamante.<br />-   Modifica del focus del controllo all'interno di un controllo contenitore.|  
|<xref:System.Windows.Forms.Cursor>|-   Impostazione della proprietà <xref:System.Windows.Forms.Cursor.Clip%2A>.<br />-La chiamata di <xref:System.Windows.Forms.Control.Hide%2A> metodo.|  
|<xref:System.Windows.Forms.DataGrid>|-La chiamata di <xref:System.Windows.Forms.ContainerControl.ProcessTabKey%2A> metodo.|  
|<xref:System.Windows.Forms.Form>|-Ottenere la <xref:System.Windows.Forms.Form.ActiveForm%2A> o <xref:System.Windows.Forms.Form.MdiParent%2A> proprietà.<br />-Impostazione di <xref:System.Windows.Forms.Form.ControlBox%2A>, <xref:System.Windows.Forms.Form.ShowInTaskbar%2A>, o <xref:System.Windows.Forms.Form.TopMost%2A> proprietà.<br />-Impostazione di <xref:System.Windows.Forms.Form.Opacity%2A> proprietà inferiore al 50%.<br />-Impostazione di <xref:System.Windows.Forms.Form.WindowState%2A> proprietà <xref:System.Windows.Forms.FormWindowState.Minimized> a livello di codice.<br />-La chiamata di <xref:System.Windows.Forms.Form.Activate%2A> metodo.<br />-Utilizzo di <xref:System.Windows.Forms.FormBorderStyle.None>, <xref:System.Windows.Forms.FormBorderStyle.FixedToolWindow>, e <xref:System.Windows.Forms.FormBorderStyle.SizableToolWindow> <xref:System.Windows.Forms.FormBorderStyle> valori di enumerazione.|  
|<xref:System.Windows.Forms.NotifyIcon>|-Utilizzo di <xref:System.Windows.Forms.NotifyIcon> componente è completamente limitato.|  
  
 Il <xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows> valore limita le azioni elencate nella tabella seguente, inoltre, per le restrizioni applicate per il <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> valore.  
  
|Componente|Azioni limitate|  
|---------------|------------------------|  
|<xref:System.Windows.Forms.CommonDialog>|-Che mostra una finestra di dialogo derivate dalla <xref:System.Windows.Forms.CommonDialog> classe.|  
|<xref:System.Windows.Forms.Control>|-La chiamata di <xref:System.Windows.Forms.Control.CreateGraphics%2A> metodo.<br />-   Impostazione della proprietà <xref:System.Windows.Forms.Control.Cursor%2A>.|  
|<xref:System.Windows.Forms.Control.Cursor%2A>|-   Impostazione della proprietà <xref:System.Windows.Forms.Cursor.Current%2A>.|  
|<xref:System.Windows.Forms.MessageBox>|-La chiamata di <xref:System.Windows.Forms.Form.Show%2A> metodo.|  
  
### <a name="hosting-third-party-controls"></a>Hosting di controlli di terze parti  
 Se i moduli ospitano controlli di terze parti, può verificarsi un altro tipo di modifica delle finestre. Un controllo di terze parti è personalizzato <xref:System.Windows.Forms.UserControl> di non aver sviluppato e compilato personalmente. Sebbene lo scenario di hosting sia difficile da sfruttare, un controllo di terze parti può almeno in teoria espandere la propria superficie di rendering per coprire l'intera area del modulo. Il controllo potrebbe quindi imitare una finestra di dialogo critica e richiedere informazioni come combinazioni di nome utente e password o numeri di conti corrente degli utenti.  
  
 Per limitare questo rischio, usare solo controlli di terze parti considerati attendibili. Se si usano controlli di terze parti scaricati da origini non verificabili, si consiglia di esaminarne il codice sorgente alla ricerca di exploit potenziali. Dopo aver verificato che l'origine non è dannosa, compilare l'assembly da sé per assicurarsi che l'origine corrisponda.  
  
## <a name="win32-api-calls"></a>Chiamate API Win32  
 Se la progettazione dell'applicazione richiede la chiamata a una funzione dell'API Win32, si accederà a codice non gestito. In questo caso, lavorando con le chiamate o i valori dell'API Win32, non è possibile determinare le azioni del codice relativamente alla finestra o al sistema operativo. Il <xref:System.Security.Permissions.SecurityPermission> classe e <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> valore il <xref:System.Security.Permissions.SecurityPermissionFlag> controlla l'accesso al codice non gestito. Un'applicazione può accedere il codice non gestito solo quando viene concessa il <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> autorizzazione. Per impostazione predefinita, solo le applicazioni in esecuzione in locale possono chiamare codice non gestito.  
  
 Alcuni membri di Windows Form forniscono l'accesso non gestita che richiede il <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> autorizzazione. Nella tabella seguente sono elencati i membri di <xref:System.Windows.Forms> dello spazio dei nomi che richiedono tale autorizzazione. Per altre informazioni sulle autorizzazioni necessarie per un membro, vedere la documentazione della libreria di classi .NET Framework.  
  
|Componente|Member|  
|---------------|------------|  
|<xref:System.Windows.Forms.Application>|-    Metodo <xref:System.Windows.Forms.Application.AddMessageFilter%2A><br />-   <xref:System.Windows.Forms.Application.CurrentInputLanguage%2A> Proprietà<br />-    Metodo `Exit`<br />-    Metodo <xref:System.Windows.Forms.Application.ExitThread%2A><br />-   <xref:System.Windows.Forms.Application.ThreadException> Evento|  
|<xref:System.Windows.Forms.CommonDialog>|-    Metodo <xref:System.Windows.Forms.CommonDialog.HookProc%2A><br />-   <xref:System.Windows.Forms.CommonDialog.OwnerWndProc%2A>\ (metodo)<br />-    Metodo <xref:System.Windows.Forms.CommonDialog.Reset%2A><br />-    Metodo <xref:System.Windows.Forms.CommonDialog.RunDialog%2A>|  
|<xref:System.Windows.Forms.Control>|-    Metodo <xref:System.Windows.Forms.Control.CreateParams%2A><br />-    Metodo <xref:System.Windows.Forms.Control.DefWndProc%2A><br />-    Metodo <xref:System.Windows.Forms.Control.DestroyHandle%2A><br />-    Metodo <xref:System.Windows.Forms.Control.WndProc%2A>|  
|<xref:System.Windows.Forms.Help>|-   <xref:System.Windows.Forms.Help.ShowHelp%2A> Metodi<br />-    Metodo <xref:System.Windows.Forms.Help.ShowHelpIndex%2A>|  
|<xref:System.Windows.Forms.NativeWindow>|-   <xref:System.Windows.Forms.NativeWindow> Classe|  
|<xref:System.Windows.Forms.Screen>|-    Metodo <xref:System.Windows.Forms.Screen.FromHandle%2A>|  
|<xref:System.Windows.Forms.SendKeys>|-    Metodo <xref:System.Windows.Forms.SendKeys.Send%2A><br />-    Metodo <xref:System.Windows.Forms.SendKeys.SendWait%2A>|  
  
 Se l'applicazione non dispone dell'autorizzazione per chiamare codice non gestito, l'applicazione deve richiedere <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> autorizzazione oppure è necessario considerare i modi alternativi per implementare le funzionalità, in molti casi, Windows Form fornisce un'alternativa gestita per l'API Win32 funzioni. Se non esistono metodi alternativi e l'applicazione deve accedere a codice non gestito, sarà necessario elevare le autorizzazioni per l'applicazione.  
  
 L'autorizzazione a chiamare codice non gestito consente a un'applicazione di eseguire praticamente qualsiasi operazione. Fornire pertanto tale autorizzazione solo alle applicazioni provenienti da fonti attendibili. In alternativa, a seconda dell'applicazione, la caratteristica che esegue la chiamata al codice non gestite potrebbe essere facoltativa oppure abilitata solo in un ambiente ad attendibilità totale. Per altre informazioni sulle autorizzazioni pericolose, vedere [Autorizzazioni pericolose e amministrazione dei criteri](../../../docs/framework/misc/dangerous-permissions-and-policy-administration.md). Per altre informazioni sull'elevazione delle autorizzazioni, vedere [NIB: General Security Policy Administration](http://msdn.microsoft.com/library/5121fe35-f0e3-402c-94ab-4f35b0a87b4b) (NIB: Amministrazione generale dei criteri di sicurezza).  
  
## <a name="see-also"></a>Vedere anche  
 [Accesso più sicuro a file e dati in Windows Form](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 [Stampa più sicura in Windows Forms](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)  
 [Panoramica della sicurezza in Windows Forms](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 [Sicurezza di Windows Form](../../../docs/framework/winforms/windows-forms-security.md)  
 [Sicurezza di applicazioni ClickOnce](/visualstudio/deployment/securing-clickonce-applications)
