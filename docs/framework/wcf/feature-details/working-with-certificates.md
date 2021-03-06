---
title: Utilizzo dei certificati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF]
ms.assetid: 6ffb8682-8f07-4a45-afbb-8d2487e9dbc3
ms.openlocfilehash: f5566eacaabb5d3eb5579d015fad8149a2ed4f3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="working-with-certificates"></a>Utilizzo dei certificati
Per programmare sicurezza Windows Communication Foundation (WCF), certificati digitali X.509 sono utilizzati per autenticare i client e server, crittografare e firmare digitalmente i messaggi. In questo argomento viene fornita una breve le funzionalità di certificati digitali X.509 e illustra come utilizzarle in WCF e include collegamenti ad argomenti che trattano questi concetti ulteriormente o che descrivono come eseguire attività comuni utilizzando i certificati e WCF.  
  
 In breve, un certificato digitale è una parte di un *infrastruttura a chiave pubblica* (PKI), che è un sistema di certificati digitali, autorità di certificazione e altre autorità di registrazione che verificano e autenticano la validità di ogni parte coinvolta in una transazione elettronica tramite l'utilizzo di crittografia a chiave pubblica. Un'autorità di certificazione rilascia certificati e ogni certificato ha un set di campi che contengono dati, ad esempio *soggetto* (l'entità a cui viene rilasciato il certificato), le date di validità (quando il certificato è valido), (l'autorità emittente entità che ha emesso il certificato) e una chiave pubblica. In WCF, ognuna di queste proprietà viene elaborato come un <xref:System.IdentityModel.Claims.Claim>, e ogni attestazione viene ulteriormente divisa in due tipi: identità e a destra. Per ulteriori informazioni su x. 509 Vedere certificati [certificati a chiave pubblica X.509](http://go.microsoft.com/fwlink/?LinkId=209952)per ulteriori informazioni sulle attestazioni e autorizzazioni in, vedere WCF [gestione attestazioni e autorizzazioni con il modello di identità](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md). Per ulteriori informazioni sull'implementazione di un'infrastruttura PKI, vedere [Windows Server 2008 R2 - Servizi certificati](http://go.microsoft.com/fwlink/?LinkId=209949).  
  
 Una delle funzionalità principali di un certificato è consentire l'autenticazione dell'identità del proprietario del certificato presso altre entità. Contiene un certificato di *chiave pubblica* del proprietario, mentre il proprietario conserva la chiave privata. La chiave pubblica può essere utilizzata per crittografare i messaggi inviati al proprietario del certificato. In quanto unico detentore della chiave privata, solo il proprietario è in grado di decrittografare questi messaggi.  
  
 I certificati devono essere rilasciati da un autorità di certificazione, che spesso è un'emittente di certificati di terze parti. Nei domini Windows è disponibile un'autorità di certificazione utilizzabile per rilasciare certificati ai computer appartenenti al dominio.  
  
## <a name="viewing-certificates"></a>Visualizzazione dei certificati  
 Quando si utilizzano i certificati, spesso è necessario visualizzarli e analizzarne le proprietà. A tale scopo è possibile ricorrere allo snap-in Microsoft Management Console (MMC), uno strumento di facile utilizzo. Per ulteriori informazioni, vedere [procedura: visualizzare certificati con lo Snap-in MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
## <a name="certificate-stores"></a>Archivi certificati  
 I certificati vengono memorizzati in appositi archivi. Sono disponibili due posizioni principali di archiviazione, ognuna delle quali è composta da più sottoarchivi. Gli amministratori di un computer possono visualizzare entrambi gli archivi principali mediante lo snap-in MMC. Gli altri utenti, invece, sono in grado di visualizzare soltanto l'archivio utente corrente.  
  
-   **Archivio del computer locale**. contiene i certificati utilizzati dai processi del computer, ad esempio [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Utilizzare questa posizione per archiviare i certificati utilizzati per l'autenticazione del server presso i client.  
  
-   **L'archivio utente corrente**. questa posizione in genere viene utilizzata dalle applicazioni interattive per memorizzare i certificati relativi all'utente corrente del computer. Se si crea un'applicazione client, utilizzare questa posizione per archiviare i certificati utilizzati per l'autenticazione degli utenti presso un servizio.  
  
 Ognuno di questi due archivi è composto da più sottoarchivi. La più importante fra queste quando la programmazione con WCF includono:  
  
-   **Autorità di certificazione radice attendibili**. i certificati contenuti in questo archivio possono essere utilizzati per creare una catena di certificati che consente di risalire a un certificato di autorità di certificazione di questo archivio.  
  
    > [!IMPORTANT]
    >  Il computer locale considera implicitamente attendibile qualsiasi certificato posizionato in questo archivio, anche se il certificato non è stato rilasciato da un autorità di certificazione di terze parti attendibile. È pertanto necessario garantire che questo archivio contenga soltanto certificati rilasciati da emittenti completamente attendibili, nonché comprendere quali problemi possono verificarsi qualora questa indicazione non venga rispettata.  
  
-   **Personale**. questo archivio viene utilizzato per i certificati associati a un utente di un computer. In genere questo archivio viene utilizzato per i certificati rilasciati mediante uno dei certificati di autorità di certificazione contenuti nell'archivio Autorità di certificazione radice disponibile nell'elenco locale. In alternativa, questo archivio può contenere certificati autocertificati ritenuti attendibili da un'applicazione.  
  
 Per ulteriori informazioni sugli archivi certificati, vedere [archivi certificati](http://go.microsoft.com/fwlink/?LinkId=88912).  
  
### <a name="selecting-a-store"></a>Scelta di un archivio  
 La scelta della posizione in cui archiviare un certificato dipende dalla modalità di esecuzione del servizio o del client. In particolare, la scelta si basa sulle regole di carattere generale seguenti:  
  
-   Se il servizio WCF è ospitato in un servizio Windows utilizzare il **computer locale** archiviare. Si noti che per memorizzare certificati in questo archivio è necessario disporre dei privilegi di amministratore.  
  
-   Se il servizio o il client è un'applicazione che viene eseguito con un account utente, utilizzare il **utente corrente** archiviare.  
  
### <a name="accessing-stores"></a>Accesso agli archivi  
 Analogamente alle cartelle di un computer, anche gli archivi vengono protetti tramite gli elenchi di controllo di accesso (ACL, Access Control List). Quando si crea un servizio ospitato in Internet Information Services (IIS), il processo [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] è in esecuzione nell'account [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Tale account deve essere autorizzato ad accedere all'archivio contenente i certificati utilizzati da un servizio. Ogni archivio principale viene protetto mediante un ACL predefinito, che tuttavia può essere modificato. Se si crea un ruolo a parte per accedere a un archivio, a tale ruolo è necessario concedere l'autorizzazione di accesso. Per informazioni su come modificare l'elenco di accesso utilizzando lo strumento WinHttpCertConfig.exe, vedere [procedura: creare certificati temporanei da usare durante lo sviluppo](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md). Per ulteriori informazioni sull'uso dei certificati client con IIS, vedere [come chiamare un servizio Web usando un certificato client per l'autenticazione in un'applicazione Web ASP.NET](http://go.microsoft.com/fwlink/?LinkId=88914).  
  
## <a name="chain-trust-and-certificate-authorities"></a>Catena di trust e autorità di certificazione  
 I certificati vengono creati in una gerarchia dove ogni singolo certificato è collegato alla CA che ha emesso il certificato. Questo collegamento è per il certificato della CA. Il certificato della CA collega quindi la CA che ha emesso il certificato della CA originale. Questo processo si ripete fino a raggiungere il certificato della CA radice. Il certificato della CA radice è considerato naturalmente attendibile.  
  
 I certificati digitali vengono utilizzati per autenticare un'entità basandosi questa gerarchia, detta anche un *catena di certificati*. È possibile visualizzare qualsiasi catena di certificato utilizzando lo snap-in MMC facendo doppio clic su qualsiasi certificato e scegliendo il **percorso certificato** scheda. Per ulteriori informazioni sull'importazione di catene di certificati per un'autorità di certificazione, vedere [procedura: specificare il certificato dell'Autorità certificato catena usato per verificare le firme](../../../../docs/framework/wcf/feature-details/specify-the-certificate-authority-chain-verify-signatures-wcf.md).  
  
> [!NOTE]
>  Qualsiasi emittente può essere definito come un'autorità radice attendibile. A tale scopo, aggiungere il certificato di tale emittente nell'archivio Autorità di certificazione radice attendibili.  
  
### <a name="disabling-chain-trust"></a>Disabilitazione della catena di trust  
 Quando si crea un nuovo servizio è possibile che si utilizzi un certificato che non è stato rilasciato tramite un certificato radice attendibile oppure che il certificato emittente non sia contenuto nell'archivio Autorità di certificazione radice attendibili. In questo caso, e solo per scopi di sviluppo, è possibile disabilitare temporaneamente il meccanismo che verifica la catena di trust di un certificato. A tale scopo, impostare la proprietà `CertificateValidationMode` su `PeerTrust` oppure su `PeerOrChainTrust`. Queste modalità specificano rispettivamente che il certificato può essere autocertificato (trust peer) o appartenere a una catena di trust. Questa proprietà può essere impostata in una qualsiasi delle classi seguenti:  
  
|Classe|Proprietà|  
|-----------|--------------|  
|<xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>|<xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>|<xref:System.ServiceModel.Security.X509PeerCertificateAuthentication.CertificateValidationMode%2A?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>|<xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.IssuedTokenServiceCredential>|<xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A?displayProperty=nameWithType>|  
  
 La proprietà può anche essere impostata in configurazione. Gli elementi seguenti vengono utilizzati per specificare la modalità di convalida:  
  
-   [\<authentication>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)  
  
-   [\<peerAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)  
  
-   [\<messageSenderAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)  
  
## <a name="custom-authentication"></a>Autenticazione personalizzata  
 La proprietà `CertificateValidationMode` consente inoltre di personalizzare la modalità di autenticazione dei certificati. Per impostazione predefinita, il livello è impostato su `ChainTrust`. Per usare il valore <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom> è necessario impostare anche l'attributo `CustomCertificateValidatorType` sull'assembly e sul tipo usati per convalidare il certificato. Per creare un validator personalizzato è necessario ereditare una classe dalla classe astratta <xref:System.IdentityModel.Selectors.X509CertificateValidator>.  
  
 Quando si crea un autenticatore personalizzato è fondamentale eseguire l'override del metodo <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A>. Per un esempio di autenticazione personalizzata, vedere il [Validator del certificato x. 509](../../../../docs/framework/wcf/samples/x-509-certificate-validator.md) esempio. Per altre informazioni, vedere [credenziale personalizzata e convalida delle credenziali](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md).  
  
## <a name="using-makecertexe-to-build-a-certificate-chain"></a>Utilizzo dello strumento Makecert.exe per compilare una catena di certificati  
 Lo strumento di creazione dei certificati Makecert.exe crea certificati X.509 e coppie di chiavi privata/pubblica. La chiave privata può essere salvata su disco e quindi utilizzata per rilasciare e firmare nuovi certificati, simulando in questo modo una gerarchia di certificati concatenati. Questo strumento deve essere utilizzato esclusivamente come risorsa ausiliare durante la fase di sviluppo dei servizi. È pertanto necessario evitare di utilizzarlo per creare i certificati da utilizzare nella distribuzione definitiva. Quando si sviluppa un servizio WCF, utilizzare la procedura seguente per compilare una catena di trust con Makecert.exe.  
  
#### <a name="to-build-a-chain-of-trust-with-makecertexe"></a>Per compilare una catena di trust tramite lo strumento Makecert.exe  
  
1.  Utilizzare lo strumento MakeCert.exe per creare un certificato temporaneo dell'autorità radice (autofirmato). Salvare la chiave privata su disco.  
  
2.  Utilizzare il nuovo certificato per rilasciare un altro certificato contenente la chiave pubblica.  
  
3.  Importare il certificato dell'autorità radice nell'archivio Autorità di certificazione radice attendibili.  
  
4.  Per istruzioni dettagliate, vedere [procedura: creare certificati temporanei da usare durante lo sviluppo](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md).  
  
## <a name="which-certificate-to-use"></a>Scelta del certificato da utilizzare  
 Quando si utilizzano i certificati spesso sorgono dubbi su quale certificato scegliere e sul motivo per cui sceglierlo. La soluzione a questi dubbi varia a seconda che la programmazione riguardi un client o un servizio. Le informazioni seguenti rappresentano una linea guida generale e non forniscono una risposta esauriente a questi dubbi.  
  
### <a name="service-certificates"></a>Certificati di servizio  
 Lo scopo principale dei certificati di servizio è autenticare il server presso i client. Uno dei primi controlli svolti quando un client esegue l'autenticazione di un server consiste nel confrontare il valore di **soggetto** campo per l'identificatore URI (Uniform Resource) usato per contattare il servizio: deve corrispondere il DNS di entrambi. Se, ad esempio, l'URI del servizio è "http://www.contoso.com/endpoint/" la **soggetto** campo deve contenere anche il valore "www.contoso.com".  
  
 Si noti che il campo può contenere più valori, ognuno avente un prefisso iniziale che ne indica il valore. Nella maggior parte dei casi viene utilizzato il prefisso iniziale "CN" per indicare un nome comune. Ad esempio, "CN = www.contoso.com". È anche possibile che il **soggetto** campo sia vuoto, nel qual caso il **nome alternativo soggetto** campo può contenere il **nome DNS** valore.  
  
 Si noti inoltre il valore della **scopi designati** campo del certificato deve includere un valore appropriato, ad esempio "Server Authentication" o "Autenticazione Client".  
  
### <a name="client-certificates"></a>Certificati client  
 Anziché essere rilasciati da un'autorità di certificazione di terze parti, in genere i certificati client vengono memorizzati da un'autorità radice nell'archivio Personale dell'utente corrente. Il campo Scopi designati in questo caso viene impostato su "Autenticazione client". Un client può utilizzare un certificato client quando è necessario eseguire l'autenticazione reciproca.  
  
## <a name="online-revocation-and-offline-revocation"></a>Revoca online e revoca offline  
  
### <a name="certificate-validity"></a>Validità del certificato  
 Ogni certificato è valido solo per un determinato periodo di tempo, detto di *periodo di validità*. Il periodo di validità è definito per il **valido da** e **valido a** i campi di un certificato x. 509. Durante l'autenticazione questi due campi vengono verificati per stabilire se il certificato è nel periodo di validità.  
  
### <a name="certificate-revocation-list"></a>Elenco di revoche di certificati (CRL, Certificate Revocation List)  
 Durante il periodo di validità, l'autorità di certificazione può revocare un certificato in qualsiasi momento. Ciò può verificarsi per vari motivi, ad esempio se la chiave privata del certificato viene compromessa.  
  
 In questo caso, tutti i certificati appartenenti alle catene di trust aventi origine dal certificato revocato sono anch'essi considerati non validi e durante le procedure di autenticazione vengono considerati non attendibili. Per scoprire quali certificati vengono revocati, ogni emittente pubblica un e data-timestamp *elenco certificati revocati* (CRL). Questo elenco può essere controllato tramite la revoca online oppure la revoca offline impostando la proprietà `RevocationMode` o la proprietà `DefaultRevocationMode` delle classi seguenti su uno dei valori dell'enumerazione <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>: <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>, <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>, <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication> e <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>. Il valore predefinito di tutte le proprietà è `Online`.  
  
 È inoltre possibile impostare la modalità di configurazione utilizzando il `revocationMode` attributo di entrambi i [ \<autenticazione >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) (del [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)) e il [ \<autenticazione >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) (del [ \<endpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)).  
  
## <a name="the-setcertificate-method"></a>Metodo SetCertificate  
 In WCF, è spesso necessario specificare un certificato o set di certificati che un servizio o client consiste nell'utilizzare per autenticare, crittografare o firmare digitalmente un messaggio. Questa operazione può essere eseguita a livello di programmazione mediante il metodo `SetCertificate` di varie classi che rappresentano i certificati X.509. Le classi seguenti utilizzano il metodo `SetCertificate` per specificare un certificato.  
  
|Classe|Metodo|  
|-----------|------------|  
|<xref:System.ServiceModel.Security.PeerCredential>|<xref:System.ServiceModel.Security.PeerCredential.SetCertificate%2A>|  
|<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>|<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>|  
|<xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>|<xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>|  
|<xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>|  
|<xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.SetCertificate%2A>|  
  
 Il metodo `SetCertificate` si basa sulla definizione di una posizione di archivio, di un archivio, di un tipo "di ricerca" (ovvero il parametro `x509FindType` )" che specifica un campo del certificato e un valore da ricercare nel campo. Ad esempio, il codice seguente crea un <xref:System.ServiceModel.ServiceHost> istanza e imposta il certificato di servizio utilizzato per autenticare il servizio client con il `SetCertificate` metodo.  
  
 [!code-csharp[c_WorkingWithCertificates#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_workingwithcertificates/cs/source.cs#1)]
 [!code-vb[c_WorkingWithCertificates#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_workingwithcertificates/vb/source.vb#1)]  
  
### <a name="multiple-certificates-with-the-same-value"></a>Certificati aventi lo stesso valore  
 Un archivio può contenere più certificati aventi lo stesso nome del soggetto. Ciò significa che se si specifica che il `x509FindType` viene <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectName> o <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectDistinguishedName>e una o più certificati con lo stesso valore, viene generata un'eccezione perché non esiste alcun modo per distinguere quale certificato è obbligatorio. Per risolvere questo problema, impostare la proprietà `x509FindType` su <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint>. Il campo dell'identificazione personale ("Thumbprint") contiene infatti un valore univoco che può essere utilizzato per individuare un certificato specifico all'interno di un archivio. Tuttavia, ciò comporta uno svantaggio: se il certificato viene revocato o rinnovato, il metodo `SetCertificate` ha esito negativo poiché in questi casi l'identificazione personale viene rispettivamente eliminata o alterata. Oppure, se il certificato non è più valido, l'autenticazione ha esito negativo. Per risolvere questo problema è possibile impostare il parametro `x590FindType` su <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByIssuerName> e specificare quindi nome dell'emittente. Se non è richiesto alcun emittente specifico, è anche possibile impostare uno degli altri valori dell'enumerazione <xref:System.Security.Cryptography.X509Certificates.X509FindType>, ad esempio <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByTimeValid>.  
  
## <a name="certificates-in-configuration"></a>Impostazione dei certificati in configurazione  
 I certificati possono anche essere impostati in configurazione. Se si sta creando un servizio, vengono specificate credenziali, inclusi i certificati, sotto il [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md). Quando si programma un client, i certificati sono specificati all'interno di [ \<endpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md).  
  
## <a name="mapping-a-certificate-to-a-user-account"></a>Mapping di un certificato a un account utente  
 Una funzionalità di IIS e di Active Directory è la possibilità di eseguire il mapping di un certificato a un account utente di Windows. Per ulteriori informazioni sulla funzionalità, vedere [eseguire il mapping dei certificati per account utente di](http://go.microsoft.com/fwlink/?LinkId=88917).  
  
 Per ulteriori informazioni sull'utilizzo di mapping di Active Directory, vedere [Mapping certificati Client con il Mapping del servizio Directory](http://go.microsoft.com/fwlink/?LinkId=88918).  
  
 Se questa funzionalità è abilitata è possibile impostare la proprietà <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.MapClientCertificateToWindowsAccount%2A> della classe <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> su `true`. Nella configurazione, è possibile impostare il `mapClientCertificateToWindowsAccount` attributo del [ \<autenticazione >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) elemento `true`, come illustrato nel codice seguente.  
  
```xml  
<serviceBehaviors>  
 <behavior name="MappingBehavior">  
  <serviceCredentials>  
   <clientCertificate>  
    <authentication certificateValidationMode="None" mapClientCertificateToWindowsAccount="true" />  
   </clientCertificate>  
  </serviceCredentials>  
 </behavior>  
</serviceBehaviors>  
```  
  
 L'esecuzione del mapping di un certificato X.509 al token che rappresenta un account utente di Windows è considerata un'elevazione dei privilegi perché, una volta eseguito tale mapping, il token di Windows può essere utilizzato per accedere alle risorse protette. Pertanto, il criterio del dominio richiede che il certificato X.509 sia conforme al proprio criterio prima di eseguire il mapping. Il *SChannel* pacchetto di protezione applica questo requisito.  
  
 Quando si utilizza [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] o versione successiva, WCF assicura il certificato sia conforme ai criteri di dominio prima che venga mappato a un account di Windows.  
  
 Nella prima versione di WCF, mapping viene eseguito senza consultare i criteri di dominio. È pertanto possibile che le applicazioni che funzionano correttamente con la prima versione presentano problemi se il mapping viene abilitato e il certificato X.509 non soddisfa il criterio del dominio.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels>  
 <xref:System.ServiceModel.Security>  
 <xref:System.ServiceModel>  
 <xref:System.Security.Cryptography.X509Certificates.X509FindType>  
 [Protezione di servizi e client](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
