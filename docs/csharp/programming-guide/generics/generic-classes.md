---
title: Classi generiche (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, generic classes
- generics [C#], classes
ms.assetid: 27d6f256-cd61-41e3-bc6e-b990a53b0224
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: afeca9fc49221551470f90f6f57d1b40e0142521
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2018
---
# <a name="generic-classes-c-programming-guide"></a>Classi generiche (Guida per programmatori C#)
Le classi generiche incapsulano operazioni che non sono specifiche di un determinato tipo di dati. L'uso più comune per le classi generiche è con raccolte come elenchi collegati, tabelle hash, stack, code, alberi e così via. Le operazioni come l'aggiunta e la rimozione di elementi dalla raccolta vengono eseguite praticamente allo stesso modo, indipendentemente dal tipo dei dati archiviati.  
  
 Per la maggior parte degli scenari che richiedono classi di raccolta, l'approccio consigliato consiste nell'usare quelle disponibili nella libreria di classi .NET. Per altre informazioni sull'uso di queste classi, vedere [Generic Collections in .NET](../../../standard/generics/collections.md) (Raccolte generiche in .NET).  
  
 Normalmente, per creare classi generiche è possibile iniziare da una classe concreta esistente, modificando quindi i tipi in parametri di tipo uno per volta fino a raggiungere l'equilibrio ottimale tra generalizzazione e usabilità. Ecco alcuni aspetti importanti di cui tenere conto quando si creano classi generiche personalizzate:  
  
-   Tipi da generalizzare in parametri di tipo.  
  
     Di norma, maggiore è il numero di tipi che è possibile parametrizzare, più flessibile e riutilizzabile sarà il codice. Tuttavia, una generalizzazione eccessiva può creare codice difficile da leggere e comprendere per gli altri sviluppatori.  
  
-   Vincoli, se presenti, da applicare ai parametri di tipo. Vedere [Vincoli sui parametri di tipo](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).  
  
     Una buona regola consiste nell'applicare il numero massimo di vincoli possibile, ma che permetta di continuare a gestire tutti i tipi necessari. Se, ad esempio, la classe generica è destinata solo all'uso con tipi riferimento, applicare il vincolo di classe. In questo modo, si eviterà l'uso indesiderato della classe con tipi valore e sarà possibile usare l'operatore `as` in `T` e verificare la presenza di valori null.  
  
-   Se suddividere il comportamento generico in classi e sottoclassi base.  
  
     Poiché le classi generiche possono fungere da classi base, valgono le stesse considerazioni di progettazione relative alle classi non generiche. Vedere le regole sull'ereditarietà da classi base generiche più avanti in questo argomento.  
  
-   Se implementare una o più interfacce generiche.  
  
     Se, ad esempio, si progetta una classe che verrà usata per creare elementi in una raccolta basata su generics, potrebbe essere necessario implementare un'interfaccia come <xref:System.IComparable%601>, dove `T` è il tipo della classe.  
  
 Per un esempio di una classe generica semplice, vedere [Introduzione ai generics](../../../csharp/programming-guide/generics/introduction-to-generics.md).  
  
 Le regole per i parametri di tipo e i vincoli hanno diverse implicazioni per il comportamento delle classi generiche, in particolare riguardo a ereditarietà e accessibilità dei membri. Prima di continuare, è utile comprendere alcuni termini. Per una classe generica, il codice client `Node<T>,` può fare riferimento alla classe specificando un argomento tipo, per creare un tipo costruito chiuso (`Node<int>`). In alternativa, può lasciare il parametro di tipo non specificato, ad esempio quando si specifica una classe base generica, per creare un tipo costruito aperto (`Node<T>`). Le classi generiche possono ereditare da classi concrete, classi costruite chiuse o classi base costruite aperte:  
  
 [!code-csharp[csProgGuideGenerics#16](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_1.cs)]  
  
 Le classi non generiche, ovvero concrete, possono ereditare da classi base costruite chiuse, ma non da classi costruite aperte o da parametri di tipo, perché in fase di esecuzione il codice client non può in alcun modo specificare l'argomento tipo necessario per creare un'istanza della classe base.  
  
 [!code-csharp[csProgGuideGenerics#17](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_2.cs)]  
  
 Le classi generiche che ereditano da tipi costruiti aperti devono specificare gli argomenti tipo per qualsiasi parametro di tipo di classe base che non viene condiviso dalla classe che eredita, come mostrato nel codice seguente:  
  
 [!code-csharp[csProgGuideGenerics#18](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_3.cs)]  
  
 Le classi generiche che ereditano da tipi costruiti aperti devono specificare vincoli che implichino o siano un superset dei vincoli sul tipo di base:  
  
 [!code-csharp[csProgGuideGenerics#19](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_4.cs)]  
  
 I tipi generici possono usare più parametri di tipo e vincoli, in questo modo:  
  
 [!code-csharp[csProgGuideGenerics#20](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_5.cs)]  
  
 I tipo costruiti aperti e i tipi costruiti chiusi possono essere usati come parametri di metodo:  
  
 [!code-csharp[csProgGuideGenerics#21](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_6.cs)]  
  
 Se una classe generica implementa un'interfaccia, è possibile eseguire il cast di tutte le istanze della classe all'interfaccia.  
  
 Le classi generiche sono invariabili. In altri termini, se un parametro di input specifica un oggetto `List<BaseClass>`, se si prova a specificare un oggetto `List<DerivedClass>`, viene restituito un errore in fase di compilazione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Collections.Generic>  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Generics](../../../csharp/programming-guide/generics/index.md)  
 [Saving the State of Enumerators](https://blogs.msdn.microsoft.com/wesdyer/2006/01/13/saving-the-state-of-enumerators/) (Salvataggio dello stato degli enumeratori)  
 [An Inheritance Puzzle, Part One](https://blogs.msdn.microsoft.com/ericlippert/2007/07/27/an-inheritance-puzzle-part-one/) (Indovinello sull'ereditarietà - Parte 1)
