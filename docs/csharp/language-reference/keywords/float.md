---
title: float (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- float
- float_CSharpKeyword
helpviewer_keywords:
- float keyword [C#]
- floating-point numbers [C#], float keyword
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 846f132812fe90a285c81a020d440fc846f88b5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="float-c-reference"></a>float (Riferimenti per C#)
La parola chiave `float` indica un tipo semplice che archivia valori a virgola mobile a 32 bit. Nella tabella riportata di seguito sono indicati l'intervallo approssimativo e il grado di precisione del tipo `float`.  
  
|Tipo|Intervallo approssimativo|Precisione|Tipo .NET Framework|  
|----------|-----------------------|---------------|-------------------------|  
|`float`|da -3,4 × 10<sup>38</sup>a +3,4 × 10<sup>38</sup>|7 cifre|<xref:System.Single?displayProperty=nameWithType>|  
  
## <a name="literals"></a>Valori letterali  
 Per impostazione predefinita, un valore letterale numerico reale a destra dell'operatore di assegnazione viene gestito come tipo [double](double.md). Per inizializzare una variabile float è quindi necessario usare il suffisso `f` o `F`, come illustrato di seguito:  
  
```csharp
float x = 3.5F;  
```
  
 Se nella dichiarazione precedente non si usa il suffisso, verrà generato un errore di compilazione poiché si sta tentando di archiviare un valore [double](double.md) in una variabile `float`.  
  
## <a name="conversions"></a>Conversioni  
 In una stessa espressione è possibile combinare tipi integrali numerici e tipi a virgola mobile. In questo caso i tipi integrali vengono convertiti in tipi a virgola mobile. La valutazione dell'espressione viene eseguita in base alle regole seguenti:  
  
-   Se uno dei tipi a virgola mobile è [double](double.md), l'espressione restituirà un valore [double](double.md) o [bool](bool.md) in caso di espressioni relazionali o booleane.  
  
-   Se l'espressione non contiene alcun tipo [double](double.md), restituirà un valore `float` o [bool](bool.md) in caso di espressioni relazionali o booleane.  
  
 Un'espressione a virgola mobile può contenere gli insiemi di valori seguenti:  
  
-   Zero positivo e negativo  
  
-   Infinito positivo e negativo  
  
-   Non un numero  
  
-   Insieme finito di valori diversi da zero  
  
 Per altre informazioni su questi valori, vedere lo standard IEEE per l'aritmetica a virgola mobile binaria, disponibile nel sito Web [IEEE](http://www.ieee.org).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente [int](int.md), [short](short.md) e `float` sono inclusi in un'espressione matematica che dà come risultato un valore `float`. Tenere presente che `float` è un alias per il tipo <xref:System.Single?displayProperty=nameWithType>. Si noti che nell'istruzione non sono inclusi valori [double](double.md).  
  
 [!code-csharp[csrefKeywordsTypes#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/float_1.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Single>  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Cast e conversioni di tipi](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
 [Parole chiave di C#](index.md)  
 [Tabella dei tipi integrali](integral-types-table.md)  
 [Tabella dei tipi incorporati](built-in-types-table.md)  
 [Tabella delle conversioni numeriche implicite](implicit-numeric-conversions-table.md)  
 [Tabella delle conversioni numeriche esplicite](explicit-numeric-conversions-table.md)
