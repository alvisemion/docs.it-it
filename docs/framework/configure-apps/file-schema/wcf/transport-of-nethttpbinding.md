---
title: '&lt;transport&gt; di &lt;netHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: 6603e590632f0bc21a2d98482d1f42f03bb9d9e7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="lttransportgt-of-ltnethttpbindinggt"></a>&lt;transport&gt; di &lt;netHttpBinding&gt;
Definisce proprietà che controllano i parametri di autenticazione per il trasporto HTTP.  
  
\<system.serviceModel>  
\<le associazioni >  
\<netHttpBinding>  
\<binding>  
\<security>  
\<trasporto >  
  
## <a name="syntax"></a>Sintassi  
  
```xml
<netHttpBinding>  
  <binding>  
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">  
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"  
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows" realm="string">  
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"  
                                  protectionScenario="TransportSelected|TrustedProxy">  
          <customServiceNames></customServiceNames>  
        </extendedProtectionPolicy>  
      </transport>  
    </security>  
  </binding>  
</netHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|clientCredentialType|-Specifica il tipo di credenziale da usare quando si esegue l'autenticazione client mediante l'autenticazione HTTP.  Il valore predefinito è `None`. L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.|  
|proxyCredentialType|-Specifica il tipo di credenziale da usare quando si esegue l'autenticazione client all'interno di un dominio tramite un proxy su HTTP. Questo attributo è applicabile solo quando l'attributo `mode` dell'elemento `security` padre è `Transport` o `TransportCredentialsOnly`. L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.|  
|realm|Stringa che specifica l'area di autenticazione usata dallo schema di autenticazione HTTP per l'autenticazione digest o di base. Il valore predefinito è una stringa vuota.|  
|policyEnforcement|Questa enumerazione specifica il momento in cui deve essere applicato l'oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.<br /><br /> 1.  Never – I criteri non vengono mai applicati e la protezione estesa è disabilitata.<br />2.  WhenSupported – I criteri vengono applicati solo se il client supporta la protezione estesa.<br />3.  Always - I criteri vengono sempre applicati. L'autenticazione dei client che non supportano la protezione estesa avrà esito negativo.|  
|protectionScenario|Questa enumerazione specifica lo scenario di protezione applicato dai criteri.|  
  
## <a name="clientcredentialtype-attribute"></a>Attributo clientCredentialType  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|None|I messaggi non vengono protetti durante il trasferimento.|  
|Di base|Specifica l'autenticazione di base.|  
|Digest|Specifica l'autenticazione digest.|  
|Ntlm|Specifica l'autenticazione NTLM quando possibile e se l'autenticazione di Windows non riesce.|  
|WINDOWS|Specifica l'autenticazione Windows integrata.|  
  
## <a name="proxycredentialtype-attribute"></a>Attributo proxyCredentialType  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|Nessuno|-I messaggi non vengono protetti durante il trasferimento.|  
|Basic|Specifica l'autenticazione di base come definita da RFC 2617 – HTTP Authentication: Basic and Digest Authentication.|  
|Digest|Specifica l'autenticazione digest come definita da RFC 2617 – HTTP Authentication: Basic and Digest Authentication.|  
|Ntlm|Specifica l'autenticazione NTLM quando possibile e se l'autenticazione di Windows non riesce.|  
|WINDOWS|Specifica l'autenticazione Windows integrata.|  
|Certificato|Esegue l'autenticazione client mediante un certificato. Questa opzione funziona solo se l'attributo `Mode` dell'elemento `security` padre è impostato su Transport, mentre non funzionerà se viene impostato su TransportCredentialOnly.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nethttpbinding.md)|Definisce le funzionalità di sicurezza per il [ \<netHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nethttpbinding.md).|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente è dimostrato l'uso della sicurezza del trasporto SSL con l'associazione di base. Per impostazione predefinita, l'associazione di base supporta la comunicazione HTTP.  
  
```xml
<system.serviceModel>  
  <services>  
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
      <endpoint address=""  
                binding="netHttpBinding"  
                bindingConfiguration="Binding1"   
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  <bindings>  
    <netHttpBinding>  
      <!-- Configure basicHttpBinding with Transport security -- >  
      <!-- mode and clientCredentialType set to None.-->  
      <binding name="Binding1">  
        <security mode="Transport">  
          <transport clientCredentialType="None"  
                     proxyCredentialType="None">  
            <extendedProtectionPolicy policyEnforcement="WhenSupported"  
                                      protectionScenario="TransportSelected">  
              <customServiceNames></customServiceNames>  
            </extendedProtectionPolicy>
          </transport> 
        </security>  
      </binding>  
    </netHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Associazioni](../../../../../docs/framework/wcf/bindings.md)  
 [Configurazione di associazioni fornite dal sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Uso di associazioni per configurare i client e servizi Windows Communication Foundation](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<binding>](../../../../../docs/framework/misc/binding.md)
