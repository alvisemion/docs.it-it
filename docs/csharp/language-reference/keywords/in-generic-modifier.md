---
title: in (Modificatore generico) (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2af4e27034af0067e81a52c81991edaf5a5415d8
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2018
---
# <a name="in-generic-modifier-c-reference"></a>in (Modificatore generico) (Riferimenti per C#)

Per i parametri di tipo generico, la parola chiave `in` specifica che il parametro di tipo è controvariante. È possibile usare la parola chiave `in` in interfacce e delegati generici.  
  
 La controvarianza consente di usare un tipo meno derivato di quello specificato dal parametro generico. Ciò consente la conversione implicita di classi che implementano interfacce varianti e la conversione implicita di tipi delegati. Nei parametri di tipo generico la covarianza e la controvarianza sono supportate per i tipi di riferimento, ma non per i tipi di valore.  
  
 Un tipo può essere dichiarato controvariante in un'interfaccia o in un delegato generico solo se definisce il tipo dei parametri di un metodo e non di un tipo restituito dal metodo. I parametri `In`, `ref` e `out` devono essere invarianti, ovvero non sono né covariante né controvariante.
  
 Un'interfaccia che dispone di un parametro di tipo controvariante consente ai metodi di accettare argomenti di tipi meno derivati di quelli specificati dal parametro di tipo di interfaccia. Ad esempio, nell'interfaccia <xref:System.Collections.Generic.IComparer%601>, il tipo T è controvariante, è possibile assegnare un oggetto di tipo `IComparer<Person>` a un oggetto di tipo `IComparer<Employee>` senza usare alcun metodo di conversione speciale se `Employee` eredita `Person`.  
  
 A un delegato controvariante può essere assegnato un altro delegato dello stesso tipo, ma con un parametro di tipo generico meno derivato.  
  
 Per altre informazioni, vedere [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md).  
  
## <a name="contravariant-generic-interface"></a>Interfaccia generica controvariante   

 L'esempio seguente illustra come dichiarare, estendere e implementare un'interfaccia generica controvariante. L'esempio descrive anche come usare la conversione implicita per le classi che implementano quest'interfaccia.  
  
 [!code-csharp[csVarianceKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_1.cs)]  
  
## <a name="contravariant-generic-delegate"></a>Delegato generico controvariante  

 L'esempio seguente illustra come dichiarare, creare un'istanza e chiamare un delegato generico controvariante. Illustra anche come convertire in modo implicito un tipo delegato.  
  
 [!code-csharp[csVarianceKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_2.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [out](../../../csharp/language-reference/keywords/out-generic-modifier.md)  
 [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md)  
 [Modificatori](../../../csharp/language-reference/keywords/modifiers.md)  
