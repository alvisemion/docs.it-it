---
title: Guida di interoperabilità dei protocolli di servizi Web
ms.date: 03/30/2017
ms.assetid: f2981678-ebdb-433d-899b-467f7df95fb2
ms.openlocfilehash: 1ee8b485d8a46d2599958db2c71f4a6e84875169
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="web-services-protocols-interoperability-guide"></a>Guida di interoperabilità dei protocolli di servizi Web
Windows Communication Foundation (WCF) implementa un numero di protocolli di servizi Web. Molti di questi protocolli includono diverse opzioni e punti estendibilità lasciati alla discrezione dell'implementatore. In questo argomento fornisce un elenco di protocolli di servizi Web che WCF implementa. Altri argomenti di questa sezione forniscono dettagli di implementazione per ogni protocollo supportato.  
  
## <a name="web-services-protocols-implemented-by-wcf"></a>Protocolli di servizi Web implementati da WCF  
 WCF fornisce il supporto per protocolli dell'infrastruttura di Web services (WS) attraverso canali e protocolli di applicazioni tramite la funzionalità dei contratti di servizi Web. L'interoperabilità per i protocolli di applicazioni è ottenuta tramite il linguaggio XSD (XML Description Language) 1.0 e il linguaggio WSDL (Web Services Description Language) 1.1.  
  
 L'interoperabilità dei protocolli dell'infrastruttura è garantita dalle specifiche WS-*. Canali WCF forniscono il supporto per un numero di WS -\* protocolli dell'infrastruttura. Canali WCF vengono configurati mediante elementi di associazione. Le tabelle seguenti contengono l'elenco completo di WS -\* protocolli di infrastruttura implementati da vari elementi di associazione di WCF.  
  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement> supporta le specifiche indicate nella tabella seguente.  
  
|Specifica/documento|Collegamento|  
|-----------------------------|----------|  
|HTTP 1.1|[RFC 2616](http://go.microsoft.com/fwlink/?LinkId=90372)|  
|Associazione SOAP 1,1 HTTP|[Simple Object Access Protocol (SOAP) 1.1](http://go.microsoft.com/fwlink/?LinkId=90520), sezione 7|  
|Associazione SOAP 1,2 HTTP|[Versione di SOAP 1.2 parte 2: Componenti aggiuntivi (seconda edizione)](http://go.microsoft.com/fwlink/?LinkId=95329), sezione 7|  
  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> e <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> supportano le specifiche indicate nella tabella seguente.  
  
|Specifica/documento|Collegamento|  
|-----------------------------|----------|  
|XML|[Extensible Markup Language (XML) 1.0 (Fourth Edition)](http://go.microsoft.com/fwlink/?LinkId=15139)|  
|SOAP 1,1|[Simple Object Access Protocol (SOAP) 1.1](http://go.microsoft.com/fwlink/?LinkId=96687)|  
|SOAP 1.2 Core|[Versione di SOAP 1.2 parte 1: Framework di messaggistica (seconda edizione)](http://go.microsoft.com/fwlink/?LinkId=94664)|  
|WS-Addressing 2004/08|[Web Services Addressing (WS-Addressing)](http://go.microsoft.com/fwlink/?LinkId=81239)|  
|W3C Web Services Addressing 1.0 - Core|[1.0 - Core indirizzamento dei servizi Web](http://go.microsoft.com/fwlink/?LinkId=96688)|  
|W3C Web Services Addressing 1.0 - SOAP Binding|[Web Services Addressing 1.0 con associazione SOAP](http://go.microsoft.com/fwlink/?LinkId=96689)|  
|W3C Web Services Addressing 1.0 - WSDL Binding*|[Web Services Addressing 1.0 con associazione WSDL](http://go.microsoft.com/fwlink/?LinkId=96690)|  
|W3C Web Services Addressing 1.0 - Metadata|[Web Services Addressing 1.0 --Metadata](http://www.w3.org/TR/ws-addr-metadata/)|  
|Associazione WSDL SOAP1.1|[Web Services Description Language (WSDL) 1.1](http://go.microsoft.com/fwlink/?LinkId=96160)|  
|Associazione WSDL SOAP1.2|[Estensione di Binding 1.1 WSDL per SOAP 1.2](http://go.microsoft.com/fwlink/?LinkId=96691)|  
  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> supporta le specifiche indicate nella tabella seguente.  
  
|Specifica/documento|Collegamento|  
|-----------------------------|----------|  
|XOP|[XML binario con ottimizzazione per la creazione di pacchetti](http://go.microsoft.com/fwlink/?LinkId=96714)|  
|Associazione MTOM + SOAP1.2|[SOAP MTOM](http://go.microsoft.com/fwlink/?LinkId=96713)|  
|Associazione MTOM SOAP 1.1|[Associazione SOAP 1,1 per MTOM 1.0](http://go.microsoft.com/fwlink/?LinkId=96712)|  
|MTOM WS-PolicyAssertions|Non ancora pubblicato.|  
  
 <xref:System.ServiceModel.Channels.SecurityBindingElement> supporta le specifiche indicate nella tabella seguente.  
  
|Specifica/documento|Collegamento|  
|-----------------------------|----------|  
|WSS: SOAP Message Security 1,0|[Web Services Security: SOAP Message Security 1,0](http://go.microsoft.com/fwlink/?LinkId=94684)|  
|WSS: Username Token Profile 1.0|[Web Services Security UsernameToken Profile 1.0](http://go.microsoft.com/fwlink/?LinkId=95334)<br /><br /> Richiedi Password/@Type= PasswordText (impostazione predefinita)|  
|WSS: X.509 Token Profile 1.0|[Web Services Security X.509 Certificate Token Profile](http://go.microsoft.com/fwlink/?LinkId=95335)|  
|WSS: SAML 1.1 Token Profile 1.0|[Web Services Security: Profilo del Token SAML](http://go.microsoft.com/fwlink/?LinkId=96693)|  
|WSS: SOAP Message Security 1.1|[Web Services Security: SOAP Message Security 1.1](http://go.microsoft.com/fwlink/?LinkId=91240)|  
|WSS Username Token Profile 1.1|[Web Services Security UsernameToken Profile 1.1](http://go.microsoft.com/fwlink/?LinkId=95331)<br /><br /> non implementare la funzionalità di derivazione della chiave basata su password;<br /><br /> Richiedi Password/@Type= PasswordText (impostazione predefinita)|  
|WSS: X509 Token Profile 1.1|[Web Services Security X.509 Certificate Token Profile 1.1](http://go.microsoft.com/fwlink/?LinkId=95332)|  
|WSS: Kerberos Token Profile 1.1|[Web Services Security Kerberos Token Profile 1.1](http://go.microsoft.com/fwlink/?LinkId=95333)|  
|WSS: SAML 1.1 Token Profile 1.1|[Web Services Security SAML Token Profile 1.1](http://go.microsoft.com/fwlink/?LinkId=96694)|  
|WS-Secure Conversation|[Linguaggio di conversazione protetta dei servizi Web](http://go.microsoft.com/fwlink/?LinkId=95317)|  
|WS-Trust 1.4|[Linguaggio dell'attendibilità dei servizi Web](http://go.microsoft.com/fwlink/?LinkId=169514)|  
|WS-SecurityPolicy 2005/07|[Linguaggio di conversazione protetta dei servizi Web](http://go.microsoft.com/fwlink/?LinkId=95317)<br /><br /> Rettificato in base all'errata corrige inviato all'OASIS WS-SX TC.<br /><br /> [messaggio di ws-sx](http://go.microsoft.com/fwlink/?LinkId=96700)|  
|WS-ReliableMessaging 1.1|[Protocollo Reliable Messaging versione 1.1](../../../../docs/framework/wcf/feature-details/reliable-messaging-protocol-version-1-1.md)|  
  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> supporta le specifiche indicate nella tabella seguente.  
  
|Specifica/documento|Collegamento|  
|-----------------------------|----------|  
|WS-Coordination|[Coordinamento di servizi Web](http://go.microsoft.com/fwlink/?LinkId=95324)|  
|WS-AtomicTransaction|[Transazione atomica dei servizi Web](http://go.microsoft.com/fwlink/?LinkId=95323)|  
  
 Il <xref:System.ServiceModel.Description.MetadataExporter>, <xref:System.ServiceModel.Description.MetadataImporter>, <!--zz <xref:System.ServiceModel.Description.WSDLExporter>, <xref:System.ServiceModel.Description.WSDLImporter>, --> `System.ServiceModel.Description.MetadataImporter`, `System.ServiceModel.Description.WSDLImporter`, e <xref:System.ServiceModel.Description.MetadataResolver> classi forniscono supporto per le specifiche dei metadati seguenti:  
  
-   [XML Schema Part 1: Edizione di strutture](http://go.microsoft.com/fwlink/?LinkId=3536)  
  
-   [XML Schema Part 2: Tipi di dati Second Edition](http://go.microsoft.com/fwlink/?LinkId=40138)  
  
-   [WSDL 1.1](http://go.microsoft.com/fwlink/?LinkId=96160)  
  
-   [WS-Policy 1.2](http://go.microsoft.com/fwlink/?LinkId=96705)  
  
-   [WS-Policy 1.5](http://go.microsoft.com/fwlink/?LinkId=96706)  
  
-   [1.2 di WS-PolicyAttachment](http://go.microsoft.com/fwlink/?LinkId=96707)  
  
-   [1.1 di WS-MetadataExchange](http://go.microsoft.com/fwlink/?LinkId=94868)  
  
-   [WS-Transfer Get per il recupero di metadati](http://go.microsoft.com/fwlink/?LinkId=96708)  
  
 Inoltre, vengono implementati i seguenti profili di interoperabilità tra WCF:  
  
-   [Basic Profile 1.1](http://go.microsoft.com/fwlink/?LinkId=69313)  
  
-   [Simple SOAP Binding 1.0](http://go.microsoft.com/fwlink/?LinkId=96710)  
  
-   [Sicurezza di base del profilo 1.0 Working Draft](http://go.microsoft.com/fwlink/?LinkId=96711)  
  
## <a name="see-also"></a>Vedere anche  
 [Protocolli di servizi Web supportati da associazioni di interoperabilità fornite dal sistema](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
 [Protocolli di messaggistica](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)  
 [Informazioni di riferimento sullo schema del contratto di dati](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)  
 [WSDL e criteri](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)  
 [Protocolli di sicurezza](../../../../docs/framework/wcf/feature-details/security-protocols.md)  
 [Protocollo Reliable Messaging versione 1.0](../../../../docs/framework/wcf/feature-details/reliable-messaging-protocol-version-1-0.md)  
 [Protocollo Reliable Messaging versione 1.1](../../../../docs/framework/wcf/feature-details/reliable-messaging-protocol-version-1-1.md)  
 [Protocolli di transazione](../../../../docs/framework/wcf/feature-details/transaction-protocols.md)  
 [Protocollo di scambio del contesto](../../../../docs/framework/wcf/feature-details/context-exchange-protocol.md)
