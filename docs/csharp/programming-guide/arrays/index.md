---
title: Matrici (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: e01b9463eca88858633b847be256ae5b063459b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="arrays-c-programming-guide"></a>Matrici (Guida per programmatori C#)
È possibile archiviare più variabili dello stesso tipo in una struttura di dati a matrice. Una matrice viene dichiarata specificando il tipo degli elementi.  
  
 `type[] arrayName;`  
  
 L'esempio seguente consente di creare matrici unidimensionali, multidimensionali e irregolari:  
  
 [!code-csharp[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]  
  
## <a name="array-overview"></a>Panoramica delle matrici  
 Le matrici hanno le proprietà seguenti:  
  
-   Una matrice può essere [unidimensionale](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [multidimensionale](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) o [irregolare](../../../csharp/programming-guide/arrays/jagged-arrays.md).  
  
-   Il numero di dimensioni e la lunghezza di ogni dimensione sono definiti durante la creazione dell'istanza della matrice. Questi valori non possono essere modificati per la durata dell'istanza.  
  
-   I valori predefiniti degli elementi numerici della matrice sono impostati su zero, mentre gli elementi di riferimento sono impostati su null.  
  
-   Una matrice irregolare è una matrice di matrici, quindi i relativi elementi sono tipi di riferimento inizializzati su `null`.  
  
-   Le matrici sono a indice zero. Una matrice con `n` elementi viene indicizzata da `0` a `n-1`.  
  
-   Gli elementi di una matrice possono essere di qualsiasi tipo, anche di tipo matrice.  
  
-   I tipi matrice sono [tipi di riferimento](../../../csharp/language-reference/keywords/reference-types.md) derivati dal tipo di base astratto <xref:System.Array>. Poiché questo tipo implementa <xref:System.Collections.IEnumerable> e <xref:System.Collections.Generic.IEnumerable%601>, è possibile usare l'iterazione [foreach](../../../csharp/language-reference/keywords/foreach-in.md) su tutte le matrici in C#.  
  
## <a name="related-sections"></a>Sezioni correlate  
  
-   [Matrici come oggetti](../../../csharp/programming-guide/arrays/arrays-as-objects.md)  
  
-   [Uso di foreach con matrici](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
-   [Passaggio di matrici come argomenti](../../../csharp/programming-guide/arrays/passing-arrays-as-arguments.md)  
  
-   [Passaggio di matrici usando ref e out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)   
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Raccolte](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)  
 [Tipo di raccolta Array](http://msdn.microsoft.com/library/8a9964de-8941-47b1-a3cf-a01bc88db9e8)
