---
title: 'Procedura: creare ed eseguire una query PLINQ semplice'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create
ms.assetid: 983b4213-bddd-4a44-9262-cbe59186df4c
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 20b1be451e53a81dd0631a89310a5b884aa83166
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-create-and-execute-a-simple-plinq-query"></a>Procedura: creare ed eseguire una query PLINQ semplice
L'esempio seguente mostra come creare una semplice query Parallel LINQ usando il metodo di estensione <xref:System.Linq.ParallelEnumerable.AsParallel%2A> sulla sequenza di origine ed eseguendo la query tramite il metodo <xref:System.Linq.ParallelEnumerable.ForAll%2A>.  
  
> [!NOTE]
>  Le espressioni lambda sono usate nella documentazione per definire i delegati in PLINQ. Se non si ha familiarità con le espressioni lambda in C# o Visual Basic, vedere [Espressioni lambda in PLINQ e TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[PLINQ#11](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/create1.cs#11)]
 [!code-vb[PLINQ#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/create1.vb#11)]  
  
 Questo esempio illustra il modello di base per la creazione e l'esecuzione di qualsiasi query Parallel LINQ nei casi in cui l'ordine della sequenza di risultati non è importante. Le query non ordinate sono in genere più veloci delle query ordinate. La query partiziona l'origine in attività eseguita in modo asincrono su più thread. L'ordine di completamento di ogni attività dipende non solo dalla quantità di lavoro necessario per l'elaborazione degli elementi nella partizione, ma anche da fattori esterni, ad esempio il modo in cui il sistema operativo pianifica ogni thread. Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente. Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md). Per altre informazioni su come mantenere l'ordinamento degli elementi in una query, vedere [Procedura: Controllare l'ordinamento in una query PLINQ](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
