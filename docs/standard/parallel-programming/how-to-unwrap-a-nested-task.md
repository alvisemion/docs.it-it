---
title: "Procedura: annullare il wrapping di un'attività annidata"
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
- tasks, how to unwrap nested tasks
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 06d54efe5c8bac58746a1e01a194af55fde901b1
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-unwrap-a-nested-task"></a>Procedura: annullare il wrapping di un'attività annidata
È possibile restituire un'attività da un metodo e quindi attendere o continuare da tale attività, come illustrato nell'esempio seguente:  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 Nell'esempio precedente la proprietà <xref:System.Threading.Tasks.Task%601.Result%2A> è di tipo `string` (`String` in Visual Basic).  
  
 In alcuni scenari, tuttavia, è consigliabile creare un'attività all'interno di un'altra attività e quindi restituire l'attività annidata. In questo caso, l'oggetto `TResult` dell'attività contenitore è esso stesso un'attività. Nell'esempio seguente la proprietà Result è di tipo `Task<Task<string>>` in C# o `Task(Of Task(Of String))` in Visual Basic.  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 Anche se è possibile scrivere codice per annullare il wrapping dell'attività esterna e recuperare l'attività originale e la relativa proprietà <xref:System.Threading.Tasks.Task%601.Result%2A>, tale codice non è semplice da scrivere perché è necessario gestire le eccezioni e anche le richieste di annullamento. In questo caso, è consigliabile usare uno dei metodi di estensione <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>, come illustrato nell'esempio seguente.  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 I metodi <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> possono essere usati per trasformare qualsiasi oggetto `Task<Task>` o `Task<Task<TResult>>` (`Task(Of Task)` o `Task(Of Task(Of TResult))` in Visual Basic) in un oggetto `Task` o `Task<TResult>` (`Task(Of TResult)` in Visual Basic). La nuova attività rappresenta completamente l'attività annidata interna e include lo stato di annullamento e tutte le eccezioni.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come usare i metodi di estensione <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>.  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.Tasks.TaskExtensions?displayProperty=nameWithType>  
 [Programmazione asincrona basata su attività](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
