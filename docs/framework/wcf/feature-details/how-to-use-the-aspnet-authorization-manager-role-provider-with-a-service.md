---
title: 'Procedura: usare il provider di ruoli ASP.NET di Gestione autorizzazioni con un servizio'
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: 39103e86090ed57354efaf9c410a2733a58f06bc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a>Procedura: usare il provider di ruoli ASP.NET di Gestione autorizzazioni con un servizio
Quando [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] ospita un servizio Web, è possibile integrare Gestione autorizzazioni nell'applicazione per fornire l'autorizzazione al servizio. Gestione autorizzazioni consente a uno sviluppatore di applicazioni di definire singole operazioni che possono essere raggruppate per formare attività. Un amministratore può quindi autorizzare ruoli a eseguire attività specifiche o singole operazioni. Gestione autorizzazioni fornisce uno strumento di amministrazione come uno snap-in MMC (Microsoft Management Console) per gestire ruoli, attività, operazioni e utenti. Gli amministratori configurano un archivio criteri di Gestione autorizzazioni in un file XML, in Active Directory o in un archivio ADAM (Active Directory Application Mode).  
  
 Gestione autorizzazioni viene integrato nell'applicazione configurando il provider di ruoli [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] di Gestione autorizzazioni per l'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] che ospita il servizio Web. Come altri provider di ruoli [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], il provider di ruoli [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] di Gestione autorizzazioni viene configurato con l'elemento <`providers`>.  
  
 L'esempio di codice seguente costituisce una parte di un file di configurazione per un servizio Web che sta integrando Gestione autorizzazioni nell'applicazione.  
  
```xml  
<system.web>  
    <roleManager enabled="true" defaultProvider="AzManRoleProvider">  
      <providers>  
        <add name="AzManRoleProvider"  
             type="System.Web.Security.AuthorizationStoreRoleProvider, System.Web, Version=2.0.0.0, Culture=neutral, publicKeyToken=b03f5f7f11d50a3a"  
             connectionStringName="AzManPolicyStoreConnectionString"   
             applicationName="SecureService"/>  
      </providers>  
    </roleManager>  
</system.web>  
```  
  
 Per ulteriori informazioni sull'integrazione di un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] provider di ruoli con un'applicazione WCF, vedere [procedura: utilizzare il Provider di ruoli ASP.NET con un servizio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md). Per ulteriori informazioni sull'utilizzo di gestione autorizzazioni con [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], vedere [procedura: utilizzare Gestione autorizzazioni (AzMan) con ASP.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=71303).  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Usare il provider di ruoli ASP.NET con un servizio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
