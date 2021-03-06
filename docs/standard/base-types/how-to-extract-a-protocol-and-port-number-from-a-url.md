---
title: 'Procedura: Estrarre un protocollo e un numero di porta da un URL'
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
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- pattern-matching with regular expressions, examples
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 62931273acd41768d131c08510e14ff187d64296
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a>Procedura: Estrarre un protocollo e un numero di porta da un URL
L'esempio seguente estrae un protocollo e un numero di porta da un URL.  
  
## <a name="example"></a>Esempio  
 L'esempio usa il metodo <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> per restituire il protocollo seguito da due punti e dal numero di porta.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 Il modello di espressione regolare `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` può essere interpretato come indicato nella tabella seguente.  
  
|Modello|Descrizione|  
|-------------|-----------------|  
|`^`|Iniziare la ricerca della corrispondenza all'inizio della stringa.|  
|`(?<proto>\w+)`|Trova la corrispondenza di uno o più caratteri alfanumerici. Assegnare al gruppo il nome `proto`.|  
|`://`|Trovare la corrispondenza di due punti seguiti da due barre.|  
|`[^/]+?`|Trovare la corrispondenza di una o più occorrenze (ma il minor numero possibile) di qualsiasi carattere diverso da una barra.|  
|`(?<port>:\d+)?`|Trovare la corrispondenza di zero o una occorrenza di due punti seguiti da una o più cifre. Assegnare al gruppo il nome `port`.|  
|`/`|Trovare la corrispondenza di una barra.|  
  
 Il metodo <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> espande la sequenza di sostituzione `${proto}${port}`, che concatena il valore dei due gruppi denominati acquisiti nel modello di espressione regolare. Si tratta di una pratica alternativa alla concatenazione esplicita delle stringhe recuperate dall'oggetto raccolta restituito dalla proprietà <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType>.  
  
 L'esempio usa il metodo <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> con due sostituzioni, `${proto}` e `${port}`, per includere i gruppi acquisiti nella stringa di output. È invece possibile recuperare i gruppi acquisiti dall'oggetto <xref:System.Text.RegularExpressions.GroupCollection> della corrispondenza, come mostrato dal codice seguente.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 [Espressioni regolari .NET](../../../docs/standard/base-types/regular-expressions.md)
