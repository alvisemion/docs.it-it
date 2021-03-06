---
title: '&lt;AppContextSwitchOverrides&gt; elemento'
ms.custom: updateeachrelease
ms.date: 04/19/2018
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d16ce7f2744869c812b9988e91edd153d9cb4fd2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltappcontextswitchoverridesgt-element"></a>&lt;AppContextSwitchOverrides&gt; elemento
Definisce una o più opzioni di compatibilità usate dalla classe <xref:System.AppContext> per fornire un meccanismo di rifiuto esplicito per la nuova funzionalità.  
  
 \<configuration>  
 \<runtime>  
\<AppContextSwitchOverrides >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<AppContextSwitchOverrides value="name1=value1[[;name2=value2];...]" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`value`|Attributo obbligatorio.<br /><br /> Definisce uno o più nomi di parametro e i relativi valori booleani associati.|  
  
### <a name="value-attribute"></a>valore attributo  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|"nome = valore"|Un nome di parametro predefinito insieme al relativo valore (`true` o `false`). Più coppie nome/valore di parametro sono separate da punti e virgola (";"). Per un elenco di nomi di parametro predefiniti supportati da .NET Framework, vedere la sezione Osservazioni.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Note  
 A partire da .NET Framework 4.6, il `<AppContextSwitchOverrides>` elemento in un file di configurazione consente ai chiamanti di un'API per determinare se l'app può sfruttare i vantaggi delle nuove funzionalità o mantenere la compatibilità con le versioni precedenti di una libreria. Ad esempio, se è stato modificato il comportamento di un'API tra le due versioni di una libreria, il `<AppContextSwitchOverrides>` elemento consente ai chiamanti di API per rifiutare esplicitamente il nuovo comportamento nelle versioni della libreria che supportano le nuove funzionalità. Per le app che chiamano le API in .NET Framework, il `<AppContextSwitchOverrides>` elemento può anche consentire chiamanti cui App come destinazione una versione precedente di .NET Framework per acconsentire esplicitamente nuove funzionalità, se l'app è in esecuzione in una versione di .NET Framework che include tale funzionalità.  
  
 Il `value` attributo del `<AppContextSwitchOverrides>` elemento è costituito da una singola stringa costituita da uno o più coppie nome/valore delimitato da punto e virgola.  Ogni nome identifica un'opzione di compatibilità e il relativo valore corrispondente è un valore booleano (`true` o `false`) che indica se l'opzione è impostata. Per impostazione predefinita, l'opzione è `false`, e librerie di forniscono la nuova funzionalità. Forniscono la funzionalità precedente solo se è impostata l'opzione (ovvero, il relativo valore è `true`). Questo consente alle librerie fornire nuovo comportamento per un'API esistente, consentendo ai chiamanti che dipendono dal comportamento precedente per rifiutare esplicitamente la nuova funzionalità.  
  
 .NET Framework supporta le seguenti opzioni:  
  
|Nome del commutatore|Descrizione|Introdotto|  
|-----------------|-----------------|----------------|  
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Controlla se Windows Presentation Foundation Usa un algoritmo legacy per il layout dei controlli. Per altre informazioni, vedere [Mitigazione: Layout WPF](~/docs/framework/migration-guide/mitigation-wpf-layout.md).|.NET Framework 4.6|  
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|Controlla se l'algoritmo predefinito utilizzato per la firma di parti di un pacchetto da principali è SHA1 o SHA256.|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|Se impostato su `false`, consente il debug di progetti di flusso di lavoro basato su XAML con Visual Studio quando FIPS è abilitata. In caso contrario, un <xref:System.NullReferenceException> viene generata in chiamate a metodi nell'assembly System. Activities.|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|Controlla se il valore di checksum per un'istanza del flusso di lavoro nel debugger Usa MD5 o SHA1. | .NET Framework 4.7|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|Controlla se le analisi dello stack ottenere quando si usano i PDB portatili possono includere informazioni sulla riga e file di origine. `false` Per includere le informazioni di file e riga di origine; in caso contrario, `true`.|.NET framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|Controlli se il <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> metodo genera un'eccezione quando un <xref:System.Drawing.Icon> oggetto presenta frame PNG. Per altre informazioni, vedere [Mitigazione: Frame PNG in oggetti icona](~/docs/framework/migration-guide/mitigation-png-frames-in-icon-objects.md).|.NET Framework 4.6|  
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|Determina se <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> gli oggetti vengono eliminati correttamente quando aggiunto alla raccolta in base al <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType> metodo. `true` Per mantenere il comportamento legacy; `false` per l'eliminazione di tutti gli oggetti di tipo di carattere privato. |.NET framework 4.7.2|
|`Switch.System.Drawing.Printing.`</br>`OptimizePrintPreview`|Controlli se le prestazioni del <xref:System.Windows.Forms.PrintPreviewDialog> è ottimizzato per le stampanti di rete. Per ulteriori informazioni, vedere [Cenni preliminari sul controllo PrintPreviewDialog](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md).|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|Controlla se le operazioni asincrone non passano dal contesto del thread chiamante. Per ulteriori informazioni, vedere [CurrentCulture e CurrentUICulture flusso tra attività](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks).|.NET Framework 4.6|  
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|Controlli se il <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> metodo nel tentativo di corrispondere al tipo di attestazione solo con l'ultima voce DNS. Per altre informazioni, vedere [Mitigazione: Metodo X509CertificateClaimSet.FindClaims](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|.NET Framework 4.6.1|  
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|Determina se consentire AuthorizationContext.Empty restituire un oggetto modificabile.|.NET Framework 4.6|  
|`Switch.System.IO.BlockLongPaths`|Controlli se i percorsi più `MAX_PATH` (260 caratteri) generano un <xref:System.IO.PathTooLongException>. Per ulteriori informazioni, vedere [lungo percorso supporto](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support).|.NET Framework 4.6.2|  
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|Controlla se le routine del sistema operativo native vengono utilizzate per la decompressione dal <xref:System.IO.Compression.DeflateStream> classe. `false` usare le API native; `true` da utilizzare il <xref:System.IO.Compression.DeflateStream> implementazione.|.NET framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|Utilizza la barra rovesciata ("\\") anziché la barra rovesciata ("/") come separatore nel percorso di <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> proprietà. Per ulteriori informazioni, vedere [attenuazione: separatore di percorso ZipArchiveEntry.FullName](~/docs/framework/migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md).|.NET Framework 4.6.1|  
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|Controlla se operativo eccezioni di sistema che vengono generate su thread in background creato con <xref:System.IO.Ports.SerialPort> flussi terminano il processo.|.NET Framework 4.7.1| 
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|Controlla se viene utilizzata la normalizzazione di percorso legacy e i percorsi URI supportati dal <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> e <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> metodi. Per ulteriori informazioni, vedere [attenuazione: percorso normalizzazione](~/docs/framework/migration-guide/mitigation-path-normalization.md) e [attenuazione: controlla i due punti percorso](~/docs/framework/migration-guide/mitigation-path-colon-checks.md).|.NET Framework 4.6.2|  
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|Controlla se un test per verificarne l'uguaglianza confronta il <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType> proprietà di un oggetto con il <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> proprietà del secondo oggetto. Per ulteriori informazioni, vedere [implementazione non corretta del MemberDescriptor.Equals](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals).|.NET Framework 4.6.2|  
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|Disabilita la convalida dell'identificatore (OID) Utilizzo chiavi avanzato (EKU) oggetto del certificato. Un'estensione di utilizzo chiavi avanzato (EKU) è una raccolta di identificatori di oggetto (OID) che indica le applicazioni che usano la chiave.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|Disabilita l'attenuazione TLS 1.0 Browser sfruttare contro SSL/TLS (BEAST), disabilitare l'utilizzo di SCH_SEND_AUX_RECORD.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|Controlli se il <xref:System.Net.ServicePointManager?displayProperty=nameWithType> e <xref:System.Net.Security.SslStream?displayProperty=nameWithType> le classi possono utilizzare il protocollo SSL 3.0. Per altre informazioni, vedere [Mitigazione: Protocolli TLS](~/docs/framework/migration-guide/mitigation-tls-protocols.md).|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|Disabilita le versioni di TLS SystemDefault eseguendo il ripristino di un valore predefinito di Tls12, Tls11, Tls.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|Disattiva gli avvisi di SslStream TLS sul lato server.|.NET Framework 4.7|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |Controlli se il [DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) serializza alcuni caratteri di controllo basati sugli standard ECMAScript V6 e V8. Per altre informazioni, vedere [Mitigazione: Serializzazione dei caratteri di controllo con DataContractJsonSerializer](Mitigation:%20Serialization%20of%20Control%20Characters%20with%20the%20DataContractJsonSerializer.md)| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|Controlli se il <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> supporta più le regolazioni o solo una singola rettifica per un fuso orario. Se `true`, Usa la <xref:System.TimeZoneInfo> tipo per serializzare e deserializzare i dati di data e ora; in caso contrario, viene utilizzato il <xref:System.TimeZone> tipo, che non supporta più regole di regolazione.|.NET Framework 4.6.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|Controlli se il <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=nameWithType> costruttore imposta il nuovo oggetto <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType> proprietà con un riferimento all'oggetto esistente. Per altre informazioni, vedere [Mitigazione: Costruttore ClaimsIdentity](~/docs/framework/migration-guide/mitigation-claimsidentity-constructor.md).|.NET Framework 4.6.2|  
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|Controlli se il tentativo di riutilizzare un <xref:System.Security.Cryptography.AesCryptoServiceProvider> simmetrica genera un <xref:System.Security.Cryptography.CryptographicException>. Per altre informazioni, vedere [simmetrica AesCryptoServiceProvider fornisce una trasformazione riutilizzabile](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|Controlli se il valore di [CspParameters.ParentWindowHandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) proprietà è un [IntPtr](xref:System.IntPtr) che rappresenta la posizione di memoria di una finestra di gestione, oppure è un handle di finestra (HWND). Per altre informazioni, vedere [Mitigazione: CspParameters.ParentWindowHandle prevede un HWND](Mitigation:%20CspParameters.ParentWindowHandle%20Expects%20an%20HWND.md). |.NET Framework 4.7|   
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|Determina se il valore predefinito per alcune operazioni SignedCMS è SHA1 o SHA256. |.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|Determina se il valore predefinito per alcune operazioni SignedXML è SHA1 o SHA256. |.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|Determina se il `TransportWithMessageCredential` modalità di sicurezza consente messaggi con un unsigned "intestazione to". Si tratta di un commutatore di consenso esplicito. Per ulteriori informazioni, vedere [modifiche al Runtime in .NET Framework 4.6.1](https://msdn.microsoft.com/library/mt592686.aspx#WCF).|.NET Framework 4.6.1| 
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|Controlli se il <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> costruttore genera un <xref:System.ArgumentException> se uno degli elementi è `null`.|.NET Framework 4.7.1| 
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|Determina che se il tentativo di utilizzare X509 certificati con un provider di archiviazione chiavi CSG genera un'eccezione. Per ulteriori informazioni, vedere [la sicurezza del trasporto WCF supporta i certificati archiviati usando CNG](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng).|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|Quando si utilizza il trasporto HTTP con un servizio indipendente, impostare questo valore su `true` fa sì che WCF ignorare l'aggiunta di un'applicazione di `Connection: close` intestazione per le intestazioni di risposta per una richiesta. Impostando questo valore su `false` consente l'aggiunta di `Connection: close` intestazione per le intestazioni di risposta, che comporta la chiusura di socket di richiesta dopo l'invio di una risposta.|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|Gestisce i deadlock derivanti dalla limitazione di istanze di un servizio rientrante per un singolo thread di esecuzione alla volta.|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|Insieme a `Switch.System.Net.DontEnableSchUseStrongCrypto`, determina se la sicurezza dei messaggi WCF Usa TLS 1.1 e TLS 1.2.|.NET Framework 4.7 |    
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|Il valore `false` imposta la configurazione predefinita per consentire al sistema operativo scegliere il protocollo. Il valore `true` imposta il valore predefinito per il protocollo più alto disponibile. (Disponibile anche nel ramo di versioni precedenti di framework di manutenzione)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|Determina se l'algoritmo per i messaggi MSMQ in WCF di firma del messaggio predefinito è SHA1 o SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|Controlla se WCF Usa un SHA1 o un hash SHA256 per generare nomi casuali per le named pipe.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|Controlla se generare una [NullReferenceException](xref:System.NullReferenceException) quando il messaggio dell'eccezione è null.|.NET Framework 4.7|  
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|Controlla se le eccezioni generate all'avvio del servizio vengono propagate al chiamante del <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> metodo.|.NET Framework 4.7.1|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|Determina se determinati caratteri codificati in percentuale che in alcuni casi sono state decodificate ora sono codificate in modo coerente a sinistra. Se `true`, vengono decodificati; in caso contrario, `false`.|.NET framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|Determina la gestione di caratteri bidirezionale Unicode negli URI. `true` per rimuoverli da URI. `false` consente di conservare e percentuale-codificarli.|.NET framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Determina se Windows Presentation Foundation applica un algoritmo precedente (`true`) o un nuovo algoritmo (`false`) per l'allocazione dello spazio per \*-colonne. Per altre informazioni, vedere [Mitigazione: Allocazione dello spazio di controllo della griglia alle colonne a stella](Mitigation:%20Grid%20Control's%20Space%20Allocation%20to%20Star-columns.md). |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|Evento di modifica se un selettore o una scheda di controllo sempre aggiorna il valore della proprietà di valore selezionato prima di generare la selezione di controlli.|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|Determina se il rendering di selezione in base Adorner non è disponibile per il <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.PasswordBox> controlla per impedire il testo nascosto (`false`), o se il testo viene eseguito il rendering solo al livello dell'Adorner (`true`).|.NET framework 4.7.2|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|Determina se le modifiche DPI si verificano in un sistema per (il valore `false`) o per ogni monitoraggio (un valore di `true`).|.NET Framework 4.6.2|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|Determina se lo sviluppatore deve gestire in modo specifico il <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> azione quando il controllo testo è presente. `true` per gestire il <xref:System.Windows.Forms.DomainUpDown.UpButton> azione; `false` per il <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> e <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> azioni siano sincronizzati correttamente.|.NET framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|Indica di rifiutare esplicitamente il codice che consente a un oggetto personalizzato <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementazione per filtrare in modo sicuro i messaggi senza generare un'eccezione quando il <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> metodo viene chiamato. Per altre informazioni, vedere [Mitigazione: Implementazioni IMessageFilter.PreFilterMessage personalizzate](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|.NET Framework 4.6.1|  
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|Determina se il <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> proprietà restituisce il controllo del codice sorgente quando l'utente apre il menu di scelta dal nidificato <xref:System.Windows.Forms.ToolStripMenuItem> controllo. `true` per restituire `null`, il comportamento legacy; `false` per restituire il controllo del codice sorgente.|.NET framework 4.7.2|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|Determina se un parametro facoltativo `WM_POINTER`-stack tocco base/dello stilo è abilitato nelle applicazioni WPF. Per altre informazioni, vedere [mitigazione: basata sul puntatore tocco e supporto dello stilo](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md)|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|Determina se l'algoritmo hash predefinito usato per i valori di checksum SHA256 (`false`) o SHA1 (`true`).|.NET framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|Controlla se un legacy [NullReferenceException](xref:System.NullReferenceException) viene generata un'eccezione anziché l'eccezione che indica in dettaglio la causa dell'eccezione (ad esempio un [DirectoryNotFoundException](xref:System.IO.DirectoryNotFoundException) o un [ FileNotFoundException](xref:System.IO.FileNotFoundException). È destinato da codice che dipende dalla gestione di [NullReferenceException](xref:System.NullReferenceException). | .NET Framework 4.7 |
|`Switch.UseLegacyAccessibilityFeatures`|Controlla se le funzionalità di accessibilità disponibile a partire da .NET Framework 4.7.1 è abilitato o disabilitato. | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|Funzionalità disponibili in .NET Framework 4.7.2 di accessibilità sono abilitati i controlli (`false`) o disabilitato (`true`). Se `true`, `Switch.UseLegacyAccessibilityFeatures` deve anche essere `true` per abilitare le funzionalità di accessibilità di .NET Framework 4.7.1.|.NET framework 4.7.2|
|`System.Xml.`<br /><br /> `IgnoreEmptyKeySequences`|Controlla se le sequenze vuote di chiavi nelle chiavi composte vengono ignorate da convalida dello schema XSD. Per ulteriori informazioni, vedere [attenuazione: convalida di XML Schema](~/docs/framework/migration-guide/mitigation-xml-schema-validation.md).|.NET Framework 4.6|  
  
> [!NOTE]
>  Anziché aggiungere un `AppContextSwitchOverrides` elemento da un file di configurazione dell'applicazione, è inoltre possibile impostare le opzioni a livello di codice chiamando il `static` (in c#) o `Shared` (in Visual Basic) <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> metodo.  
  
 Gli sviluppatori possono inoltre definire opzioni personalizzate per consentire ai chiamanti di rifiutare esplicitamente le funzionalità modificate introdotte nelle versioni più recenti delle librerie. Per altre informazioni, vedere la classe <xref:System.AppContext>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `AppContextSwitchOverrides` elemento per definire un'opzione di compatibilità singola applicazione, `Switch.System.Globalization.NoAsyncCurrentCulture`, che impedisce le impostazioni cultura che passano attraverso i thread nelle chiamate al metodo asincrono.  
  
```xml  
<configuration>  
   <runtime>  
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
   </runtime>  
</configuration>  
```  
  
 L'esempio seguente usa il `AppContextSwitchOverrides` elemento per definire due opzioni di compatibilità dell'applicazione, `Switch.System.Globalization.NoAsyncCurrentCulture` e `Switch.System.IO.BlockLongPaths`. Si noti che un punto e virgola separa le due coppie nome/valore.  
  
```xml  
<configuration>  
    <runtime>  
       <AppContextSwitchOverrides   
          value="Switch.System.Globalization.NoAsyncCurrentCulture=true;Switch.System.IO.BlockLongPaths=true" />  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.AppContext?displayProperty=nameWithType>  
 [\<runtime > elemento](runtime-element.md)  
 [Elemento \<configuration>](../configuration-element.md)
