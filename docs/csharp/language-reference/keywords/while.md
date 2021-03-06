---
title: while (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 420b409689d877c3e1ac744e8d7a65500cf8f964
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="while-c-reference"></a>while (Riferimenti per C#)
L'istruzione `while` esegue un'istruzione o un blocco di istruzioni finché un'espressione specificata non restituisce `false`.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]  
  
## <a name="example"></a>Esempio  
 Poiché il test dell'espressione `while` viene eseguito prima di ogni esecuzione del ciclo, un ciclo `while` viene eseguito zero o più volte. Questo comportamento è diverso dal ciclo [do](../../../csharp/language-reference/keywords/do.md), che viene eseguito una o più volte.  
  
 Un ciclo `while` può essere terminato quando un'istruzione [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md) trasferisce il controllo all'esterno del ciclo. Per passare il controllo all'iterazione successiva senza uscire dal ciclo, usare l'istruzione [continue](../../../csharp/language-reference/keywords/continue.md). Si noti la differenza di output nei tre esempi precedenti, a seconda di dove `int n` viene incrementato. Nell'esempio seguente non viene generato alcun output.  
  
 [!code-csharp[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Istruzione while (C++)](/cpp/cpp/while-statement-cpp)  
 [Istruzioni di iterazione](../../../csharp/language-reference/keywords/iteration-statements.md)
