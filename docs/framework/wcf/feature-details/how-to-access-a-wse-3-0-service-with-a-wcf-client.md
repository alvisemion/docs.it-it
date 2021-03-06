---
title: 'Procedura: accedere a WSE 3.0 Service con un client WCF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1f9bcd9b-8f8f-47fa-8f1e-0d47236eb800
ms.openlocfilehash: 54d795858b85bd72a01f619b3603c9927df655d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-a-wse-30-service-with-a-wcf-client"></a>Procedura: accedere a WSE 3.0 Service con un client WCF
I client Windows Communication Foundation (WCF) sono compatibili a livello di transito con Web Services Enhancements (WSE) 3.0 per i servizi Microsoft .NET quando i client WCF vengono configurati per usare la versione di agosto 2004 della specifica WS-Addressing. Tuttavia, servizi WSE 3.0 non supportano il protocollo di exchange (MEX) i metadati, pertanto quando si usa il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per creare una classe client WCF, non vengono applicate le impostazioni di sicurezza all'oggetto generato Client WCF. Pertanto, è necessario specificare le impostazioni di sicurezza che il servizio WSE 3.0 richiede dopo la generazione di client di WCF.  
  
 È possibile applicare queste impostazioni di sicurezza utilizzando un'associazione personalizzata per prendere in considerazione i requisiti del servizio WSE 3.0 e i requisiti interoperativi tra un servizio WSE 3.0 e un client WCF. I requisiti di interoperabilità includono l'utilizzo della specifica dell'agosto 2004 di WS-Addressing e la protezione dei messaggi predefinita di WSE 3.0 di <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>. La protezione dei messaggi predefinita per WCF è <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>. In questo argomento viene illustrato come creare un'associazione WCF che interagisca con un servizio WSE 3.0. WCF fornisce inoltre un esempio in cui è incorporata questa associazione. Per ulteriori informazioni su questo esempio, vedere [interagisce con servizi Web ASMX](../../../../docs/framework/wcf/samples/interoperating-with-asmx-web-services.md).  
  
### <a name="to-access-a-wse-30-web-service-with-a-wcf-client"></a>Per accedere a un servizio Web WSE 3.0 con un client WCF  
  
1.  Eseguire la [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per creare un client WCF per il servizio Web WSE 3.0.  
  
     Per un servizio Web WSE 3.0, viene creato un client WCF. Dato che WSE 3.0 non supporta il protocollo MEX, non è possibile utilizzare lo strumento per recuperare i requisiti di sicurezza per il servizio Web. Lo sviluppatore dell'applicazione deve aggiungere le impostazioni di sicurezza per il client.  
  
     Per ulteriori informazioni sulla creazione di un client WCF, vedere la [procedura: creare un Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
2.  Creare una classe che rappresenta un'associazione che può comunicare con i servizi Web WSE 3.0.  
  
     La classe seguente fa parte di [interagisce con WSE](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41) esempio:  
  
    1.  Creare una classe che derivi dalla classe <xref:System.ServiceModel.Channels.Binding>.  
  
         Nell'esempio di codice seguente viene creata una classe denominata `WseHttpBinding` che deriva dalla classe <xref:System.ServiceModel.Channels.Binding>.  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  Aggiungere alla classe le proprietà che specificano l'asserzione turnkey WSE utilizzata dal servizio WSE, se sono necessarie chiavi derivate, se sono utilizzate sessioni protette, se sono necessarie conferme della firma e le impostazioni della protezione dei messaggi. In WSE 3.0, un'asserzione turnkey specifica i requisiti di sicurezza per un client o servizio Web, simile alla modalità di autenticazione di un'associazione in WCF.  
  
         Nell'esempio di codice seguente vengono definite le proprietà `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext` e `MessageProtectionOrder` che specificano l'asserzione turnkey WSE, se sono necessarie chiavi derivate, se sono utilizzate sessioni protette, se sono necessarie conferme di firma e le impostazioni di protezione dei messaggi.  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  Eseguire l'override del metodo <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> per impostare le proprietà dell'associazione.  
  
         Nell'esempio di codice seguente vengono specificati il trasporto, la codifica messaggi e le impostazioni della protezione dei messaggi ottenendo i valori delle proprietà `SecurityAssertion` e `MessageProtectionOrder`.  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3.  Nel codice dell'applicazione client, aggiungere il codice per impostare le proprietà dell'associazione.  
  
     Esempio di codice seguente specifica che il client WCF deve utilizzare la protezione del messaggio e l'autenticazione di base a quanto definito da WSE 3.0 `AnonymousForCertificate` asserzione di sicurezza turnkey. Sono inoltre necessarie sessioni protette e chiavi derivate.  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene definita un'associazione personalizzata che espone proprietà che corrispondono alle proprietà di una asserzione di sicurezza turnkey WSE 3.0. Associazione personalizzata, denominata `WseHttpBinding`, viene quindi utilizzato per specificare le proprietà di binding per un client WCF che comunica con l'esempio di Guida rapida WSSecurityAnonymous WSE 3.0.  
  
  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.Binding>  
 [Interoperabilità con WSE](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41)
