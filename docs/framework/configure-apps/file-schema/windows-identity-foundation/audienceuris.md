---
title: '&lt;audienceUris&gt;'
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7415cb3f1792d2de566161ae6c348ef591b4a0c3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltaudienceurisgt"></a>&lt;audienceUris&gt;
Specifica il set di URI accettabili identificatori delle relying party (RP). Token non verranno accettati, a meno che hanno come ambito per uno dei gruppi di destinatari consentiti gli URI.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<securityTokenHandlerConfiguration >  
\<audienceUris >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <audienceUris mode=xs:string>  
          <add value=xs:string />  
          <clear />  
          <remove value=xs:string />  
        </audienceUris>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|modalità|Un <xref:System.IdentityModel.Selectors.AudienceUriMode> valore che specifica se la restrizione di gruppo di destinatari deve essere applicata a un token in ingresso. I valori possibili sono "Sempre", "Mai" e "BearerKeyOnly". Il valore predefinito è "Sempre". Facoltativo.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`<add value=xs:string>`|Aggiunge l'URI specificato per il `value` attributo alla raccolta audienceUris. L'attributo `value` è obbligatorio. L'URI è tra maiuscole e minuscole.|  
|`<clear>`|Cancella la raccolta di audienceUris. Tutti gli identificatori vengono rimossi dalla raccolta.|  
|`<remove value=xs:string>`|Rimuove l'URI specificato per il `value` attributo dalla raccolta audienceUris. L'attributo `value` è obbligatorio. L'URI è tra maiuscole e minuscole.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Fornisce la configurazione per una raccolta di sicurezza gestori di token.|  
  
## <a name="remarks"></a>Note  
 Per impostazione predefinita, la raccolta è vuota. Utilizzare `<add>`, `<clear>`, e `<remove>` elementi per modificare la raccolta. <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> e <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> utilizzano i valori nella raccolta di URI i destinatari per configurare qualsiasi consentito audience restrizioni sugli URI in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> oggetti.  
  
 Il `<audienceUris>` elemento è rappresentato dalla <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> classe. Un URI singoli aggiunto alla raccolta è rappresentato dalla <xref:System.IdentityModel.Configuration.AudienceUriElement> classe.  
  
> [!NOTE]
>  L'utilizzo del `<audienceUris>` come un elemento figlio dell'elemento di [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento è stato deprecato, ma è ancora supportato per compatibilità con le versioni precedenti. Impostazioni di `<securityTokenHandlerConfiguration>` elemento prevalgono su quelle nel `<identityConfiguration>` elemento.  
  
## <a name="example"></a>Esempio  
 Il codice XML seguente viene illustrato come configurare il gruppo di destinatari accettabile gli URI per un'applicazione. In questo esempio consente di configurare un unico URI. I token nell'ambito per questo URI verranno accettati, tutti gli altri verranno rifiutati.  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
