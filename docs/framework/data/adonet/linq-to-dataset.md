---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 8a16e3fe0cea04813be50a83f906170199e78e3e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="linq-to-dataset"></a>LINQ to DataSet
Con [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] è più facile e veloce eseguire una query su dati memorizzati nella cache di un oggetto <xref:System.Data.DataSet>. In particolare, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] semplifica l'esecuzione di query consentendo agli sviluppatori di scrivere query dal linguaggio di programmazione stesso, anziché tramite un linguaggio di query separata. Ciò è particolarmente utile per gli sviluppatori di Visual Studio, che possono trarre vantaggio del controllo della sintassi in fase di compilazione, tipizzazione statica e supporto IntelliSense resi disponibili da Visual Studio nelle query.  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] può inoltre essere usato per eseguire query su dati che sono stati consolidati da una o più origini dati. In tal modo sono possibili molti scenari in cui è necessario rappresentare e gestire i dati con flessibilità, ad esempio per le query su dati aggregati localmente e la memorizzazione nella cache di livello intermedio nelle applicazioni Web. In particolare, questo tipo di modifiche sono richieste nelle applicazioni generiche per la creazione di rapporti, di analisi e di Business Intelligence.  
  
 Il [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] funzionalità è esposta principalmente tramite i metodi di estensione di <xref:System.Data.DataRowExtensions> e <xref:System.Data.DataTableExtensions> classi. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] basa e sfrutta esistenti [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] architettura e non è progettato per sostituire [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] nel codice dell'applicazione. Il codice ADO.NET 2.0 esistente continuerà a funzionare nelle applicazioni [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. Nel diagramma seguente viene illustrata la relazione tra [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] e  [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] e l'archivio dati.  
  
 ![LINQ to DataSet è basato sul Provider ADO.NET](../../../../docs/framework/data/adonet/media/linqtodataset.gif "LINQtoDataSet")  
  
## <a name="in-this-section"></a>In questa sezione  
 [Introduzione](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [Guida per programmatori](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a>Vedere anche  
 [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [LINQ e ADO.NET](../../../../docs/framework/data/adonet/linq-and-ado-net.md)  
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)
