---
title: Operatore % (Riferimenti per C#)
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 796b4a40347fc5881db27a8a8a28404c7c4e8c5b
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a>Operatore % (Riferimenti per C#)
L'operatore di resto (`%`) calcola il resto dopo aver diviso il primo operando per il secondo. Tutti i tipi numerici hanno operatori di resto predefiniti. 
  
## <a name="remarks"></a>Note  
 La formula `a % b` restituirà sempre un valore nell'intervallo `(-b, b)`, esclusi (non può mai restituire `b` o `-b`), mantenendo il segno del dividendo. Per la divisione di interi, l'operatore di resto soddisfa la regola `a % b = a - (a / b) * b`.
  
 Questa operazione non deve essere confusa con il modulo canonico, che soddisfa una regola simile ma con una divisione con arrotondamento all'intero più grande (floor) e restituisce valori nell'intervallo `[0, b)`. C# non include un operatore per il modulo canonico. Tuttavia, il comportamento è lo stesso per i dividendi positivi.
  
 I tipi definiti dall'utente possono eseguire l'overload dell'operatore `%` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)). Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/remainder-operator_1.cs)]  
  
## <a name="comments"></a>Commenti  
 Osservare gli errori di arrotondamento associati al tipo double.  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)
