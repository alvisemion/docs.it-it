---
title: Operatore &amp;= (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: bea90651faaafe7b754ce1cf16bddbab997d5f5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="amp-operator-c-reference"></a>Operatore &amp;= (Riferimenti per C#)
Operatore di assegnazione AND.  
  
## <a name="remarks"></a>Note  
 Un'espressione che usa l'operatore di assegnazione `&=`, ad esempio  
  
```  
x &= y  
```  
  
 equivale a  
  
```  
x = x & y  
```  
  
 con la differenza che `x` viene valutato una sola volta. L'[operatore &](../../../csharp/language-reference/operators/and-operator.md) esegue un'operazione con AND logico bit per bit su operandi integrali e un'operazione con AND logico sugli operandi `bool`.  
  
 L'operatore `&=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore &](../../../csharp/language-reference/operators/and-operator.md) binario (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)
