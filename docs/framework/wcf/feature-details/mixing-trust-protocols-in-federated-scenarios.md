---
title: Combinazione di protocolli trust in scenari federati
ms.date: 03/30/2017
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: bca23ba16c69c6d21ed7cf49aaebb8d2ed079f5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a>Combinazione di protocolli trust in scenari federati
In alcuni scenari i client federati comunicano con un servizio e con un servizio token di sicurezza che non hanno la stessa versione Trust. Il WSDL del servizio può contenere un'asserzione `RequestSecurityTokenTemplate` con elementi WS-Trust di versioni diverse rispetto al servizio token di sicurezza. In questi casi, un client Windows Communication Foundation (WCF) converte gli elementi di WS-Trust ricevuti dal `RequestSecurityTokenTemplate` in base alla versione trust servizio token di sicurezza. WCF gestisce le versioni trust non corrispondenti solo per le associazioni standard. Tutti i parametri dell'algoritmo standard riconosciuti da WCF fanno parte dell'associazione standard. In questo argomento viene descritto il comportamento WCF con varie impostazioni di trust tra il servizio e il servizio token di sicurezza.  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a>Componente febbraio 2005 e servizio token di sicurezza febbraio 2005  
 Il WSDL per il componente contiene gli elementi seguenti all'interno della sezione `RequestSecurityTokenTemplate`:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 Il file di configurazione client contiene un elenco di parametri.  
  
 WCF non è possibile distinguere tra il client e il servizio ha parametri. Aggiunge tutti i parametri e li invia nel `RequestSecurityTokenTemplate` (RST).  
  
## <a name="rp-trust-13-and-sts-trust-13"></a>Componente Trust 1.3 e servizio token di sicurezza Trust 1.3  
 Il WSDL per il componente contiene gli elementi seguenti all'interno della sezione `RequestSecurityTokenTemplate`:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 Il file di configurazione client contiene un elemento `secondaryParameters` che esegue il wrapping dei parametri specificati dal componente.  
  
 WCF rimuove il `EncryptionAlgorithm`, `CanonicalizationAlgorithm` e `KeyWrapAlgorithm` elementi dall'elemento di primo livello sotto RST se sono presenti all'interno di `SecondaryParameters` elemento. WCF aggiunge il `SecondaryParameters` elemento RST in uscita senza modificata.  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a>Componente Trust febbraio 2005 e servizio token di sicurezza Trust 1.3  
 Il WSDL per il componente contiene i seguenti elementi nella sezione `RequestSecurityTokenTemplate`:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 Il file di configurazione client contiene un elenco di parametri.  
  
 Dal file di configurazione client WCF non è possibile distinguere tra i parametri del servizio e client. Pertanto WCF converte tutti i parametri in uno spazio dei nomi versione 1.3 di Trust.  
  
 WCF gestisce il `KeyType`, `KeySize`, e `TokenType` elementi come indicato di seguito:  
  
-   Scaricare il WSDL, creare il binding e assegnare `KeyType`, `KeySize` e `TokenType` dai parametri del componente. Viene quindi generato il file di configurazione client.  
  
-   Il client è ora in grado di modificare qualsiasi parametro nel file di configurazione.  
  
-   Durante la fase di esecuzione, WCF consente di copiare tutti i parametri specificati nel `AdditionalTokenParameters` sezione del file di configurazione client eccetto `KeyType`, `KeySize` e `TokenType`, perché questi parametri vengono presi in considerazione durante il file di configurazione generazione.  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a>Componente Trust 1.3 e servizio token di sicurezza Trust febbraio 2005  
 Il WSDL per il componente contiene i seguenti elementi nella sezione `RequestSecurityTokenTemplate`:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 Il file di configurazione client contiene un elemento `secondaryParamters` che esegue il wrapping dei parametri specificati dal componente.  
  
 WCF consente di copiare tutti i parametri specificati all'interno di `SecondaryParameters` sezione in cui l'elemento RST di primo livello, ma non li converte allo spazio dei nomi WS-Trust 2005.
