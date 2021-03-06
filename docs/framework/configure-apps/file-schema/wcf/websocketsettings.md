---
title: '&lt;webSocketSettings&gt;'
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 84aee31b6c15beb32732f89eae7c3d176f57971d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltwebsocketsettingsgt"></a>&lt;webSocketSettings&gt;
Elemento di configurazione usato per specificare le impostazioni relative a Web Socket.  
  
\<system.ServiceModel>  
\<le associazioni >  
\<netHttpBinding>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<netHttpBinding>  
  <binding>   
    <webSocketSettings createNotificationOnConnection="boolean" 
                       disablePayloadMasking="boolean" 
                       keepAliveInterval="TimeSpan" 
                       maxPendingConnections="Integer" 
                       receiveBufferSize="Integer" 
                       sendBufferSize="Integer" 
                       subProtocol="String" 
                       transportUsage="WhenDuplex/Always/Never"/>
  </binding>  
</netHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|createNotificationOnConnection|Specifica se una notifica viene inviata alla connessione.|  
|disablePayloadMasking|Specifica se il mascheramento di Web Socket è disabilitato.|  
|keepAliveInterval|Specifica l'intervallo keep-alive.|  
|maxPendingConnections|Specifica il numero massimo di connessioni in attesa dell'invio nel servizio.|  
|receiveBufferSize|Specifica le dimensioni del buffer di ricezione.|  
|sendBufferSize|Specifica le dimensioni del buffer di invio.|  
|subProtocol|Specifica il sottoprotocollo Web Socket.|  
|transportUsage|Specifica quando usare Web Sockets.|  
  
## <a name="transportusage-attribute"></a>transportUsage Attribute  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|WhenDuplex|Usare il protocollo Web Socket quando il contratto è di tipo duplex.|  
|Always|Usare sempre il protocollo Web Socket indipendentemente dal contratto.|  
|Never|Non usare mai il protocollo Web Socket.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|\<netHttpBinding>|Specifica NetHttpBinding|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare il \<webSocketSettings > elemento.  
  
```xml  
<netHttpBinding>  
        <binding>  
          <webSocketSettings createNotificationOnConnection="true"  
                              disablePayloadMasking="false  
                              keepAliveInterval="00:10:00"  
                              maxPendingConnections="100"  
                              receiveBufferSize="1000"  
                              sendBufferSize="1000"  
                              subProtocol="Soap"  
                              transportUsage="WhenDuplex/Always/Never"/>  
  
        </binding>  
      </netHttpBinding>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [Associazioni](../../../../../docs/framework/wcf/bindings.md)  
 [Configurazione di associazioni fornite dal sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Uso di associazioni per configurare i client e servizi Windows Communication Foundation](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<binding>](../../../../../docs/framework/misc/binding.md)
