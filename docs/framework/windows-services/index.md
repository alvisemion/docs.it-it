---
title: Sviluppo di applicazioni di servizio Windows
ms.date: 03/30/2017
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
author: ghogen
manager: douge
ms.openlocfilehash: af6e4bf7697b3139f6809295737fdd0d90b7f013
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="developing-windows-service-applications"></a>Sviluppo di applicazioni di servizio Windows
Utilizzando Microsoft Visual Studio o Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, è possibile creare facilmente servizi mediante la creazione di un'applicazione che viene installata come un servizio. Questo tipo di applicazione viene chiamato un servizio Windows. Con le funzionalità di framework, è possibile creare servizi, installati, avviare, arrestare e controllarne il funzionamento.  
  
> [!WARNING]
>  Il modello di servizio Windows per C++ non è stato incluso in Visual Studio 2010. Per creare un servizio Windows, è possibile creare un servizio nel codice gestito in Visual c# o Visual Basic, che può interagire con il codice C++ esistente se necessario, oppure è possibile creare un servizio Windows in C++ nativo tramite il [CreazioneguidataprogettoATL](/cpp/atl/reference/atl-project-wizard).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Introduzione alle applicazioni di servizio Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 Fornisce una panoramica delle applicazioni di servizio Windows, la durata di un servizio, le applicazioni di servizio e le differenze e da altri tipi di progetto comuni.  
  
 [Procedura dettagliata: creazione di un'applicazione di servizio Windows in Progettazione componenti](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 Fornisce un esempio di creazione di un servizio in Visual Basic e Visual c#.  
  
 [Architettura di programmazione delle applicazioni di servizio](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 Vengono illustrati gli elementi del linguaggio utilizzati nella programmazione dei servizi.  
  
 [Procedura: creare servizi Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 Descrive il processo di creazione e configurazione dei servizi Windows utilizzando il modello di progetto di servizio Windows.  
  
## <a name="related-sections"></a>Sezioni correlate  
 <xref:System.ServiceProcess.ServiceBase>  
 Vengono descritte le funzionalità principali del <xref:System.ServiceProcess.ServiceBase> (classe), che viene utilizzato per creare servizi.  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 Vengono descritte le funzionalità del <xref:System.ServiceProcess.ServiceProcessInstaller> (classe), che viene utilizzato insieme alla <xref:System.ServiceProcess.ServiceInstaller> classe per installare e disinstallare servizi.  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 Vengono descritte le funzionalità del <xref:System.ServiceProcess.ServiceInstaller> (classe), che viene utilizzato insieme alla <xref:System.ServiceProcess.ServiceProcessInstaller> classe per installare e disinstallare il servizio.  
  
 [Creazione di progetti da modelli](http://msdn.microsoft.com/library/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 Vengono descritti i progetti tipi utilizzati in questo capitolo e sulla scelta tra di essi.
