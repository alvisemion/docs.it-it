---
title: 'Procedura: definire una stringa di connessione'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 3f4de943392a8da9ebdf3743da2d6ef69d90d630
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-define-the-connection-string"></a>Procedura: definire una stringa di connessione
In questo argomento viene illustrato come definire la stringa di connessione usata per la connessione a un modello concettuale. Questo argomento è basato sul [Sales di AdventureWorks](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) modello concettuale. Il modello Sales di AdventureWorks viene usato in tutti gli argomenti correlati ad attività inclusi nella documentazione di [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Questo argomento si presuppone che sia già stato configurato il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] e definito il modello Sales di AdventureWorks. Per ulteriori informazioni, vedere [procedura: definire manualmente i file di modello e Mapping](http://msdn.microsoft.com/library/d4fd6864-f2a1-48f0-aa32-1e318775a99a). Le procedure descritte in questo argomento sono incluse anche in [procedura: configurare manualmente un progetto Entity Framework](http://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).  
  
> [!NOTE]
>  Se si utilizza il [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] procedura guidata in un progetto di Visual Studio, viene generato un file con estensione edmx e configurato automaticamente il progetto da utilizzare il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Per altre informazioni, vedere [procedura: utilizzare la procedura guidata Entity Data Model](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)  
  
### <a name="to-define-the-entity-framework-connection-string"></a>Per definire la stringa di connessione Entity Framework  
  
-   Aprire il file di configurazione dell'applicazione (app.config) del progetto e aggiungere la stringa di connessione seguente.  
  
  
  
     Se il progetto non dispone di un file di configurazione dell'applicazione, è possibile aggiungerne una selezionando **Aggiungi nuovo elemento** dal **progetto** dal menu selezionando il **generale** categoria selezione **File di configurazione applicazione**e quindi fare clic su **Aggiungi**.  
  
## <a name="see-also"></a>Vedere anche  
 [Guida rapida](http://msdn.microsoft.com/library/0bc534be-789f-4819-b9f6-76e51d961675)  
 [Procedura: creare un nuovo File con estensione edmx](http://msdn.microsoft.com/library/beb8189e-e51c-4051-839c-9902c224abf2)  
 [Strumenti di ADO.NET Entity Data Model](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
