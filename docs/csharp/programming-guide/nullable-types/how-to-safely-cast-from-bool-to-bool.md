---
title: 'Procedura: eseguire il cast sicuro da bool? a bool (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- casting [C#], nullable types
- nullable types [C#], casting bool? to bool
ms.assetid: e06e4274-a443-422d-8ef1-9dbf9df55237
caps.latest.revision: "9"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1a6fa65c15bb5f1da9960dbc17bd25b4087ab862
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-safely-cast-from-bool-to-bool-c-programming-guide"></a>Procedura: eseguire il cast sicuro da bool? a bool (Guida per programmatori C#)
Il tipo nullable `bool?` può contenere tre valori diversi: `true`, `false` e `null`. Pertanto il tipo `bool?` non può essere usato in istruzioni condizionali, ad esempio con `if`, `for` o `while`. Il codice seguente, ad esempio, causa un errore di compilazione.  
  
```  
bool? b = null;  
if (b) // Error CS0266.  
{  
}  
```  
  
 Questo codice non è consentito perché non è chiaro il significato di `null` nel contesto di un'istruzione condizionale. Prima di usare un tipo `bool?` in un'istruzione condizionale, verificare che il valore della proprietà <xref:System.Nullable%601.HasValue%2A> del tipo non sia `null`, quindi eseguire il cast a `bool`. Per altre informazioni, vedere [bool](../../../csharp/language-reference/keywords/bool.md). Se si esegue il cast per un `bool?` con valore `null`, nel testo condizionale viene aggiunta l'eccezione <xref:System.InvalidOperationException>. L'esempio seguente visualizza un modo sicuro per eseguire il cast da `bool?` a `bool`:  
  
## <a name="example"></a>Esempio  
  
```csharp  
bool? test = null;  
// Other code that may or may not  
// give a value to test.  
if(!test.HasValue) //check for a value  
{  
    // Assume that IsInitialized  
    // returns either true or false.  
    test = IsInitialized();  
}  
if((bool)test) //now this cast is safe  
{  
   // Do something.  
}  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave letterali](../../../csharp/language-reference/keywords/literal-keywords.md)  
 [Tipi nullable](../../../csharp/programming-guide/nullable-types/index.md)  
 [?? (operatore)](../../../csharp/language-reference/operators/null-conditional-operator.md)
