---
title: out (Modificatore generico) (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- covariance, out keyword [C#]
- out keyword [C#]
ms.assetid: f8c20dec-a8bc-426a-9882-4076b1db1e00
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 25019408387bbf085475482c74a3fc6001321b24
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="out-generic-modifier-c-reference"></a>out (Modificatore generico) (Riferimenti per C#)
Per i parametri di tipo generico, la parola chiave `out` specifica che il parametro di tipo è covariante. È possibile usare la parola chiave `out` in interfacce e delegati generici.  
  
 La covarianza consente di usare un tipo più derivato di quello specificato dal parametro generico. Ciò consente la conversione implicita di classi che implementano interfacce varianti e la conversione implicita di tipi delegati. La covarianza e la controvarianza sono supportate per i tipi di riferimento, ma non per i tipi di valore.  
  
 Un'interfaccia che dispone di un parametro di tipo covariante consente ai metodi di restituire tipi più derivati di quelli specificati dal parametro di tipo. Poiché, ad esempio, in .NET Framework 4, nell'interfaccia <xref:System.Collections.Generic.IEnumerable%601>, il tipo T è covariante, è possibile assegnare un oggetto di tipo `IEnumerable(Of String)` a un oggetto di tipo `IEnumerable(Of Object)` senza usare alcun metodo di conversione speciale.  
  
 A un delegato covariante può essere assegnato un altro delegato dello stesso tipo, ma con un parametro di tipo generico più derivato.  
  
 Per altre informazioni, vedere [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come dichiarare, estendere e implementare un'interfaccia generica covariante. L'esempio descrive anche come usare la conversione implicita per le classi che implementano un'interfaccia covariante.  
  
 [!code-csharp[csVarianceKeywords#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_1.cs)]  
  
 In un'interfaccia generica un parametro di tipo può essere dichiarato covariante se soddisfa le condizioni seguenti:  
  
-   Il parametro di tipo viene usato solo come tipo restituito di metodi di interfaccia e non viene usato come tipo di argomenti del metodo.  
  
    > [!NOTE]
    >  Esiste un'eccezione a questa regola. Se in un'interfaccia covariante è presente un delegato generico controvariante come parametro del metodo, è possibile usare il tipo covariante come parametro di tipo generico per questo delegato. Per altre informazioni sui delegati generici covarianti e controvarianti, vedere [Varianza nei delegati](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) e [Uso della varianza per i delegati generici Func e Action](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).  
  
-   Il parametro di tipo non viene usato come vincolo generico per i metodi di interfaccia.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come dichiarare, creare un'istanza e richiamare un delegato generico covariante. Viene anche descritto come convertire in modo implicito i tipi delegati.  
  
 [!code-csharp[csVarianceKeywords#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_2.cs)]  
  
 In un delegato generico un tipo può essere dichiarato covariante se viene usato solo come tipo restituito del metodo e non per gli argomenti del metodo.  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Varianza nelle interfacce generiche](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [in](../../../csharp/language-reference/keywords/in-generic-modifier.md)  
 [Modificatori](../../../csharp/language-reference/keywords/modifiers.md)
