---
title: Architettura logica e architettura fisica
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Architettura logica e architettura fisica
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b08a5b8fb8f9df8a9a0a821fa85f1f6a94fce2d3
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="logical-architecture-versus-physical-architecture"></a>Architettura logica e architettura fisica

A questo punto, è utile fermarsi per esaminare la distinzione tra architettura logica e architettura fisica e valutare come si applica alla progettazione di applicazioni basate su microservizi.

Per iniziare, la creazione di microservizi non richiede l'uso di alcuna tecnologia specifica. Ad esempio, non è obbligatorio usare contenitori Docker per creare un'architettura basata su microservizi. I microservizi possono anche essere eseguiti come processi normali. I microservizi sono un'architettura logica.

Inoltre, anche quando è possibile implementare un microservizio fisicamente come un singolo servizio, processo o contenitore (per semplicità, questo è l'approccio adottato per la versione iniziale di [eShopOnContainers](http://aka.ms/MicroservicesArchitecture)), questa parità tra microservizi aziendali e contenitori o servizi fisici non è necessariamente richiesta in tutti i casi quando si crea un'applicazione complessa di grandi dimensioni costituita da dozzine o centinaia di servizi.

Qui sta la differenza tra l'architettura logica e l'architettura fisica di un'applicazione. L'architettura logica e i limiti logici di un sistema non presentano necessariamente un mapping di uno-a-uno rispetto all'architettura di distribuzione o fisica. Può verificarsi, ma spesso non accade.

Sebbene possano essere stati identificati alcuni microservizi aziendali o contesti delimitati, questo non significa che il miglior modo di implementarli sia sempre costituito dalla creazione di un singolo servizio, ad esempio un'API Web ASP.NET, o un singolo contenitore Docker per ogni microservizio aziendale. Una regola che prevede che ogni microservizio aziendale debba essere implementato con un singolo servizio o contenitore è troppo rigida.

Di conseguenza, un microservizio aziendale o un contesto delimitato è un'architettura logica che potrebbe coincidere (oppure no) con l'architettura fisica. Il punto importante è che un microservizio aziendale o un contesto delimitato deve essere autonomo e consentire al codice e allo stato il controllo delle versioni, la distribuzione e il ridimensionamento indipendenti.

Come mostrato nella figura 4-8, il microservizio aziendale del catalogo può essere composto da numerosi servizi o processi. Questi possono essere costituiti da più servizi API Web ASP.NET o da altre tipologie di servizi che usano HTTP o altri protocolli. Inoltre, i servizi possono condividere gli stessi dati, purché siano coesi rispetto allo stesso dominio aziendale.

![](./media/image8.png)

**Figura 4-8**. Microservizio aziendale con numerosi servizi fisici

I servizi nell'esempio condividono lo stesso modello di dati perché il servizio API Web usa gli stessi dati del servizio di ricerca. Nell'implementazione fisica del microservizio aziendale, si divide questa funzionalità per poter ridimensionare ogni servizio interno in base alle esigenze. Nella maggior parte dei casi il servizio API Web potrebbe richiedere un maggior numero di istanze rispetto al servizio di ricerca o viceversa.

In breve, l'architettura logica dei microservizi non deve sempre coincidere con l'architettura di distribuzione fisica. In questa guida ogni volta che viene citato un microservizio si intente un microservizio logico o aziendale che può essere mappato a uno o più servizi. Nella maggior parte dei casi, si tratterà di un singolo servizio, ma potrebbero anche essere più servizi.


>[!div class="step-by-step"]
[Indietro] (data-sovereignty-per-microservice.md) [Avanti] (distributed-data-management.md)
