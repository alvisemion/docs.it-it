---
title: Articoli sulla procedura (Guida a C#)
description: Raccolta di suggerimenti rapidi e brevi esempi di codice evidenziati
author: billwagner
ms.author: wiwagn
ms.date: 12/20/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 04c780980ef0665b40a0c3a698193fc9fa738424
ms.sourcegitcommit: bf8a3ba647252010bdce86dd914ac6c61b5ba89d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2018
---
# <a name="how-to-c"></a><span data-ttu-id="d0590-103">Procedura (C#)</span><span class="sxs-lookup"><span data-stu-id="d0590-103">How to (C#)</span></span>

<span data-ttu-id="d0590-104">Nella sezione della Guida a C# dedicata alla procedura è possibile trovare rapidamente le risposte alle domande più frequenti.</span><span class="sxs-lookup"><span data-stu-id="d0590-104">In the How to section of the C# Guide you can find quick answers to common questions.</span></span> <span data-ttu-id="d0590-105">In alcuni casi gli articoli possono essere elencati in più sezioni.</span><span class="sxs-lookup"><span data-stu-id="d0590-105">In some cases, articles may be listed in multiple sections.</span></span> <span data-ttu-id="d0590-106">Volevamo semplificarne la ricerca rendendoli disponibili in più percorsi.</span><span class="sxs-lookup"><span data-stu-id="d0590-106">We wanted to make them easy to find for multiple search paths.</span></span> 

## <a name="general-c-concepts"></a><span data-ttu-id="d0590-107">Concetti generali di C#</span><span class="sxs-lookup"><span data-stu-id="d0590-107">General C# concepts</span></span>

<span data-ttu-id="d0590-108">Esistono alcuni suggerimenti e consigli comuni per le procedure di sviluppo di C#.</span><span class="sxs-lookup"><span data-stu-id="d0590-108">There are several tips and tricks that are common C# developer practices.</span></span>

- <span data-ttu-id="d0590-109">[Inizializzare oggetti usando un inizializzatore di oggetto](../programming-guide/classes-and-structs/how-to-initialize-objects-by-using-an-object-initializer.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-109">[Initialize objects using an object initializer](../programming-guide/classes-and-structs/how-to-initialize-objects-by-using-an-object-initializer.md).</span></span>
- <span data-ttu-id="d0590-110">[Informazioni sulle differenze tra il passaggio a un metodo di uno struct e di una classe](../programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-110">[Learn the differences between passing a struct and a class to a method](../programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md).</span></span>
- <span data-ttu-id="d0590-111">[Come usare espressioni lambda](../programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-outside-linq.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-111">[How to use lambda expressions](../programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-outside-linq.md).</span></span>
- <span data-ttu-id="d0590-112">[Risolvere conflitti di nomi di tipo tramite l'alias dello spazio dei nomi globale](../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-112">[Resolve type name conflicts by using the global namespace alias](../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).</span></span>
- <span data-ttu-id="d0590-113">[Usare l'overload degli operatori](../programming-guide/statements-expressions-operators/how-to-use-operator-overloading-to-create-a-complex-number-class.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-113">[Use operator overloading](../programming-guide/statements-expressions-operators/how-to-use-operator-overloading-to-create-a-complex-number-class.md).</span></span>
- <span data-ttu-id="d0590-114">[Implementare e chiamare un metodo di estensione personalizzato](../programming-guide/classes-and-structs/how-to-implement-and-call-a-custom-extension-method.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-114">[Implement and call a custom extension method](../programming-guide/classes-and-structs/how-to-implement-and-call-a-custom-extension-method.md).</span></span>
- <span data-ttu-id="d0590-115">È possibile che i programmatori C# vogliano [usare lo spazio dei nomi `My` di VB](../programming-guide/namespaces/how-to-use-the-my-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-115">Even C# programmers may want to [use the `My` namespace from VB](../programming-guide/namespaces/how-to-use-the-my-namespace.md).</span></span>
- <span data-ttu-id="d0590-116">[Creare un nuovo metodo per un tipo `enum` usando i metodi di estensione](../programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-116">[Create a new method for an `enum` type using extension methods](../programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).</span></span>

### <a name="class-and-struct-members"></a><span data-ttu-id="d0590-117">Membri di classi e struct</span><span class="sxs-lookup"><span data-stu-id="d0590-117">Class and struct members</span></span>

<span data-ttu-id="d0590-118">Per implementare il programma è necessario creare classi e struct.</span><span class="sxs-lookup"><span data-stu-id="d0590-118">You create classes and structs to implement your program.</span></span> <span data-ttu-id="d0590-119">Queste tecniche sono comunemente usate durante la scrittura di classi o struct.</span><span class="sxs-lookup"><span data-stu-id="d0590-119">These techniques are commonly used when writing classes or structs.</span></span>

- <span data-ttu-id="d0590-120">[Dichiarare proprietà implementate automaticamente](../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-120">[Declare auto implemented properties](../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>
- <span data-ttu-id="d0590-121">[Dichiarare e usare proprietà di lettura/scrittura](../programming-guide/classes-and-structs/how-to-declare-and-use-read-write-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-121">[Declare and use read/write properties](../programming-guide/classes-and-structs/how-to-declare-and-use-read-write-properties.md).</span></span>
- <span data-ttu-id="d0590-122">[Definire costanti](../programming-guide/classes-and-structs/how-to-define-constants.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-122">[Define constants](../programming-guide/classes-and-structs/how-to-define-constants.md).</span></span>
- <span data-ttu-id="d0590-123">[Eseguire l'override del metodo `ToString` per specificare l'output della stringa](../programming-guide/classes-and-structs/how-to-override-the-tostring-method.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-123">[Override the `ToString` method to provide string output](../programming-guide/classes-and-structs/how-to-override-the-tostring-method.md).</span></span>
- <span data-ttu-id="d0590-124">[Definire proprietà astratte](../programming-guide/classes-and-structs/how-to-define-abstract-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-124">[Define abstract properties](../programming-guide/classes-and-structs/how-to-define-abstract-properties.md).</span></span>
- <span data-ttu-id="d0590-125">[Usare le funzionalità relative alla documentazione XML per documentare il codice](../programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-125">[Use the xml documentation features to document your code](../programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md).</span></span>
- <span data-ttu-id="d0590-126">[Implementare in modo esplicito i membri di interfaccia](../programming-guide/interfaces/how-to-explicitly-implement-interface-members.md) per mantenere concisa l'interfaccia pubblica.</span><span class="sxs-lookup"><span data-stu-id="d0590-126">[Explicitly implement interface members](../programming-guide/interfaces/how-to-explicitly-implement-interface-members.md) to keep your public interface concise.</span></span>
- <span data-ttu-id="d0590-127">[Implementare in modo esplicito i membri di due interfacce](../programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-127">[Explicitly implement members of two interfaces](../programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md).</span></span>

### <a name="working-with-collections"></a><span data-ttu-id="d0590-128">Uso delle raccolte</span><span class="sxs-lookup"><span data-stu-id="d0590-128">Working with collections</span></span>

<span data-ttu-id="d0590-129">Questi articoli contengono informazioni sull'uso delle raccolte di dati.</span><span class="sxs-lookup"><span data-stu-id="d0590-129">These articles help you work with collections of data.</span></span>

- <span data-ttu-id="d0590-130">[Inizializzare un dizionario con un inizializzatore di insieme](../programming-guide/classes-and-structs/how-to-initialize-a-dictionary-with-a-collection-initializer.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-130">[Initialize a dictionary with a collection initializer](../programming-guide/classes-and-structs/how-to-initialize-a-dictionary-with-a-collection-initializer.md).</span></span>
- <span data-ttu-id="d0590-131">[Accedere a tutti gli elementi in una raccolta tramite `foreach`](../programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-131">[Access all the elements in a collection using `foreach`](../programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md).</span></span>

## <a name="strings"></a><span data-ttu-id="d0590-132">stringhe</span><span class="sxs-lookup"><span data-stu-id="d0590-132">strings</span></span>

<span data-ttu-id="d0590-133">Le stringhe sono il tipo di dati di base usato per visualizzare o modificare il testo.</span><span class="sxs-lookup"><span data-stu-id="d0590-133">Strings are the fundamental data type used to display or manipulate text.</span></span> <span data-ttu-id="d0590-134">Questi articoli illustrano le procedure comuni da seguire con le stringhe.</span><span class="sxs-lookup"><span data-stu-id="d0590-134">These articles demonstrate common practices with strings.</span></span>

- <span data-ttu-id="d0590-135">[Confrontare stringhe](../programming-guide/strings/how-to-compare-strings.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-135">[Compare strings](../programming-guide/strings/how-to-compare-strings.md).</span></span>
- <span data-ttu-id="d0590-136">[Modificare il contenuto di una stringa](../programming-guide/strings/how-to-modify-string-contents.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-136">[Modify the contents of a string](../programming-guide/strings/how-to-modify-string-contents.md).</span></span>
- <span data-ttu-id="d0590-137">[Determinare se una stringa rappresenta un numero](../programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-137">[Determine if a string represents a number](../programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md).</span></span>
- <span data-ttu-id="d0590-138">[Usare <xref:System.String.Split%2A> per separare stringhe](../programming-guide/strings/how-to-parse-strings-using-string-split.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-138">[Use <xref:System.String.Split%2A> to separate strings](../programming-guide/strings/how-to-parse-strings-using-string-split.md).</span></span>
- <span data-ttu-id="d0590-139">[Unire più stringhe in una](../programming-guide/strings/how-to-concatenate-multiple-strings.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-139">[Combine multiple strings into one](../programming-guide/strings/how-to-concatenate-multiple-strings.md).</span></span>
- <span data-ttu-id="d0590-140">[Eseguire la ricerca di testo in una stringa](../programming-guide/strings/how-to-search-strings-using-string-methods.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-140">[Search for text in a string](../programming-guide/strings/how-to-search-strings-using-string-methods.md).</span></span>
- <span data-ttu-id="d0590-141">[Eseguire la ricerca di stringhe tramite espressioni regolari](../programming-guide/strings/how-to-search-strings-using-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-141">[Search strings using regular expressions](../programming-guide/strings/how-to-search-strings-using-regular-expressions.md).</span></span>

## <a name="convert-between-types"></a><span data-ttu-id="d0590-142">Eseguire la conversione tra tipi</span><span class="sxs-lookup"><span data-stu-id="d0590-142">Convert between types</span></span>

<span data-ttu-id="d0590-143">Potrebbe essere necessario convertire un oggetto in un tipo diverso.</span><span class="sxs-lookup"><span data-stu-id="d0590-143">You may need to convert an object to a different type.</span></span>

- <span data-ttu-id="d0590-144">[Determinare se una stringa rappresenta un numero](../programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-144">[Determine if a string represents a number](../programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md).</span></span>
- <span data-ttu-id="d0590-145">[Eseguire la conversione tra stringhe che rappresentano numeri esadecimali e numero](../programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-145">[Convert between strings that represent hexadecimal numbers and the number](../programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).</span></span>
- <span data-ttu-id="d0590-146">[Convertire una stringa in un oggetto <xref:System.DateTime>](../programming-guide/strings/how-to-convert-a-string-to-a-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-146">[Convert a string to a <xref:System.DateTime>](../programming-guide/strings/how-to-convert-a-string-to-a-datetime.md).</span></span>
- <span data-ttu-id="d0590-147">[Convertire una matrice di byte in un Integer](../programming-guide/types/how-to-convert-a-byte-array-to-an-int.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-147">[Convert a byte array to an int](../programming-guide/types/how-to-convert-a-byte-array-to-an-int.md).</span></span>
- <span data-ttu-id="d0590-148">[Convertire una stringa in un numero](../programming-guide/types/how-to-convert-a-string-to-a-number.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-148">[Convert a string to a number](../programming-guide/types/how-to-convert-a-string-to-a-number.md).</span></span>
- <span data-ttu-id="d0590-149">[Usare `as` e `is` per eseguire il cast sicuro di un tipo diverso](../programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-149">[Use `as` and `is` to safely cast to a different type](../programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md).</span></span>
- <span data-ttu-id="d0590-150">[Definire operatori di conversione per tipi `struct`](../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-150">[Define conversion operators for `struct` types](../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md).</span></span>
- <span data-ttu-id="d0590-151">[Determinare se un tipo è un tipo di valore nullable](../programming-guide/nullable-types/how-to-identify-a-nullable-type.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-151">[Determine if a type is a nullable value type](../programming-guide/nullable-types/how-to-identify-a-nullable-type.md).</span></span>
- <span data-ttu-id="d0590-152">[Eseguire la conversione tra tipi di valore nullable e non nullable](../programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-152">[Convert between nullable and non-nullable value types](../programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).</span></span>

## <a name="equality-and-ordering-comparisons"></a><span data-ttu-id="d0590-153">Confronti di uguaglianza e ordinamento</span><span class="sxs-lookup"><span data-stu-id="d0590-153">Equality and ordering comparisons</span></span>

<span data-ttu-id="d0590-154">È possibile creare tipi che definiscono regole specifiche per verificare l'uguaglianza o definire un ordinamento naturale tra oggetti di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="d0590-154">You may create types that define their own rules for equality or define a natural ordering among objects of that type.</span></span>

- <span data-ttu-id="d0590-155">[Testare l'uguaglianza di riferimenti](../programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-155">[Test for reference-based equality](../programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md).</span></span>
- <span data-ttu-id="d0590-156">[Definire l'uguaglianza di valori per un tipo](../programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-156">[Define value-based equality for a type](../programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md).</span></span>

## <a name="exception-handling"></a><span data-ttu-id="d0590-157">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="d0590-157">Exception handling</span></span>

<span data-ttu-id="d0590-158">I programmi .NET segnalano il lavoro incompleto dei metodi generando eccezioni.</span><span class="sxs-lookup"><span data-stu-id="d0590-158">.NET programs report that methods did not successfully complete their work by throwing exceptions.</span></span> <span data-ttu-id="d0590-159">Questi articoli contengono informazioni sull'uso delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="d0590-159">In these articles you'll learn to work with exceptions.</span></span>

- <span data-ttu-id="d0590-160">[Gestire eccezioni usando `try` e `catch`](../programming-guide/exceptions/how-to-handle-an-exception-using-try-catch.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-160">[Handle exceptions using `try` and `catch`](../programming-guide/exceptions/how-to-handle-an-exception-using-try-catch.md).</span></span>
- <span data-ttu-id="d0590-161">[Eseguire la pulizia delle risorse usando le clausole `finally`](../programming-guide/exceptions/how-to-execute-cleanup-code-using-finally.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-161">[Cleanup resources using `finally` clauses](../programming-guide/exceptions/how-to-execute-cleanup-code-using-finally.md).</span></span>
- <span data-ttu-id="d0590-162">[Recuperare eccezioni non CLS (Common Language Specification)](../programming-guide/exceptions/how-to-catch-a-non-cls-exception.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-162">[Recover from non-CLS (Common Language Specification) exceptions](../programming-guide/exceptions/how-to-catch-a-non-cls-exception.md).</span></span>

## <a name="delegates-and-events"></a><span data-ttu-id="d0590-163">Delegati ed eventi</span><span class="sxs-lookup"><span data-stu-id="d0590-163">Delegates and events</span></span>

<span data-ttu-id="d0590-164">I delegati e gli eventi offrono una funzionalità per strategie che riguardano blocchi di codice con accoppiamento libero.</span><span class="sxs-lookup"><span data-stu-id="d0590-164">Delegates and events provide a capability for strategies that involve loosely coupled blocks of code.</span></span>

- <span data-ttu-id="d0590-165">[Dichiarare, crearne un'istanza e usare delegati](../programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-165">[Declare, instantiate, and use delegates](../programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md).</span></span>
- <span data-ttu-id="d0590-166">[Combinare delegati multicast](../programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-166">[Combine multicast delegates](../programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md).</span></span>

<span data-ttu-id="d0590-167">Gli eventi offrono un meccanismo per pubblicare o sottoscrivere notifiche.</span><span class="sxs-lookup"><span data-stu-id="d0590-167">Events provide a mechanism to publish or subscribe to notifications.</span></span>

- <span data-ttu-id="d0590-168">[Eseguire e annullare la sottoscrizione di eventi](../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-168">[Subscribe and unsubscribe from events](../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>
- <span data-ttu-id="d0590-169">[Implementare eventi dichiarati in interfacce](../programming-guide/events/how-to-implement-interface-events.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-169">[Implement events declared in interfaces](../programming-guide/events/how-to-implement-interface-events.md).</span></span>
- <span data-ttu-id="d0590-170">[Conformità alle linee guida di .NET Framework quando il codice pubblica eventi](../programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-170">[Conform to .NET Framework guidelines when your code publishes events](../programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).</span></span>
- <span data-ttu-id="d0590-171">[Generare eventi definiti in classi base da classi derivate](../programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-171">[Raise events defined in base classes from derived classes](../programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md).</span></span>
- <span data-ttu-id="d0590-172">[Archiviare istanze di eventi in un dizionario](../programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-172">[Store event instances in a dictionary](../programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md).</span></span>
- <span data-ttu-id="d0590-173">[Implementare funzioni di accesso a eventi personalizzati](../programming-guide/events/how-to-implement-custom-event-accessors.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-173">[Implement custom event accessors](../programming-guide/events/how-to-implement-custom-event-accessors.md).</span></span>

## <a name="linq-practices"></a><span data-ttu-id="d0590-174">Procedure LINQ</span><span class="sxs-lookup"><span data-stu-id="d0590-174">LINQ practices</span></span>

<span data-ttu-id="d0590-175">LINQ consente di scrivere codice per eseguire query su qualsiasi origine dati che supporta il criterio di espressione di query LINQ.</span><span class="sxs-lookup"><span data-stu-id="d0590-175">LINQ enables you to write code to query any data source that supports the LINQ query expression pattern.</span></span> <span data-ttu-id="d0590-176">Questi articoli contengono informazioni sul criterio e sull'uso di origini dati diverse.</span><span class="sxs-lookup"><span data-stu-id="d0590-176">These articles help you understand the pattern and work with different data sources.</span></span>

- <span data-ttu-id="d0590-177">[Eseguire la query di una raccolta](../programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-177">[Query a collection](../programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md).</span></span>
- <span data-ttu-id="d0590-178">[Usare espressioni lambda in una query](../programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-in-a-query.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-178">[Use lambda expressions in a query](../programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-in-a-query.md).</span></span>
- <span data-ttu-id="d0590-179">[Usare `var` in espressioni di query](../programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-179">[Use `var` in query expressions](../programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span></span>
- <span data-ttu-id="d0590-180">[Restituire sottoinsiemi di proprietà degli elementi in una query](../programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-180">[Return subsets of element properties from a query](../programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).</span></span>
- <span data-ttu-id="d0590-181">[Scrivere query con filtro complesso](../programming-guide/concepts/linq/how-to-write-queries-with-complex-filtering.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-181">[Write queries with complex filtering](../programming-guide/concepts/linq/how-to-write-queries-with-complex-filtering.md).</span></span>
- <span data-ttu-id="d0590-182">[Ordinare elementi di un'origine dati](../programming-guide/concepts/linq/how-to-sort-elements.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-182">[Sort elements of a data source](../programming-guide/concepts/linq/how-to-sort-elements.md).</span></span>
- <span data-ttu-id="d0590-183">[Ordinare elementi in base a più chiavi](../programming-guide/concepts/linq/how-to-sort-elements-on-multiple-keys.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-183">[Sort elements on multiple keys](../programming-guide/concepts/linq/how-to-sort-elements-on-multiple-keys.md).</span></span>
- <span data-ttu-id="d0590-184">[Controllare il tipo di una proiezione](../programming-guide/concepts/linq/how-to-control-the-type-of-a-projection.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-184">[Control the type of a projection](../programming-guide/concepts/linq/how-to-control-the-type-of-a-projection.md).</span></span>
- <span data-ttu-id="d0590-185">[Contare le occorrenze di un valore in una sequenza di origine](../programming-guide/concepts/linq/how-to-count-occurrences-of-a-word-in-a-string-linq.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-185">[Count occurences of a value in a source sequence](../programming-guide/concepts/linq/how-to-count-occurrences-of-a-word-in-a-string-linq.md).</span></span>
- <span data-ttu-id="d0590-186">[Calcolare valori intermedi](../programming-guide/concepts/linq/how-to-calculate-intermediate-values.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-186">[Calculate intermediate values](../programming-guide/concepts/linq/how-to-calculate-intermediate-values.md).</span></span>
- <span data-ttu-id="d0590-187">[Unire dati di più origini](../programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-187">[Merge data from multiple sources](../programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md).</span></span>
- <span data-ttu-id="d0590-188">[Trovare la differenza dei set tra due sequenze](../programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-188">[Find the set difference between two sequences](../programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md).</span></span>
- <span data-ttu-id="d0590-189">[Eseguire il debug di risultati di query vuoti](../programming-guide/concepts/linq/how-to-debug-empty-query-results-sets.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-189">[Debug empty query results](../programming-guide/concepts/linq/how-to-debug-empty-query-results-sets.md).</span></span>
- <span data-ttu-id="d0590-190">[Aggiungere metodi personalizzati per le query LINQ](../programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-190">[Add custom methods to LINQ queries](../programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md).</span></span>

## <a name="multiple-threads-and-async-processing"></a><span data-ttu-id="d0590-191">Più thread ed elaborazione asincrona</span><span class="sxs-lookup"><span data-stu-id="d0590-191">Multiple threads and async processing</span></span>

<span data-ttu-id="d0590-192">I programmi moderni usano spesso operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="d0590-192">Modern programs often use asynchronous operations.</span></span> <span data-ttu-id="d0590-193">Questi articoli contengono informazioni sull'uso di queste tecniche.</span><span class="sxs-lookup"><span data-stu-id="d0590-193">These articles will help you learn to use these techniques.</span></span>

- <span data-ttu-id="d0590-194">[Migliorare le prestazioni di operazioni asincrone usando `System.Threading.Tasks.Task.WhenAll`](../programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-194">[Improve async performance using `System.Threading.Tasks.Task.WhenAll`](../programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>
- <span data-ttu-id="d0590-195">[Eseguire più richieste Web in parallelo tramite `async` e `await`](../programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-195">[Make multiple web requests in parallel using `async` and `await`](../programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md).</span></span>
- <span data-ttu-id="d0590-196">[Usare un pool di thread](../programming-guide/concepts/threading/how-to-use-a-thread-pool.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-196">[Use a thread pool](../programming-guide/concepts/threading/how-to-use-a-thread-pool.md).</span></span>

## <a name="command-line-args-to-your-program"></a><span data-ttu-id="d0590-197">Argomenti della riga di comando per il programma</span><span class="sxs-lookup"><span data-stu-id="d0590-197">Command line args to your program</span></span>

<span data-ttu-id="d0590-198">I programmi C# contengono generalmente argomenti della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="d0590-198">Typically, C# programs have command line arguments.</span></span> <span data-ttu-id="d0590-199">Questi articoli spiegano come accedere a tali argomenti ed elaborarli.</span><span class="sxs-lookup"><span data-stu-id="d0590-199">These articles teach you to access and process those command line arguments.</span></span>

- <span data-ttu-id="d0590-200">[Recuperare tutti gli argomenti della riga di comando con `for`](../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-200">[Retrieve all command line arguments with `for`](../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md).</span></span>
- <span data-ttu-id="d0590-201">[Recuperare tutti gli argomenti della riga di comando con `foreach`](../programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md).</span><span class="sxs-lookup"><span data-stu-id="d0590-201">[Retrieve all command line arguments with `foreach`](../programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md).</span></span>