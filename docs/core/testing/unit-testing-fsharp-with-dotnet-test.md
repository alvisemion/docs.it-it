---
title: Testing unità di librerie F# in .NET Core usando il test dotnet e xUnit
description: Informazioni sui concetti relativi agli unit test in .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di esempio con test dotnet e xUnit.
author: billwagner
ms.author: wiwagn
ms.date: 08/30/2017
ms.topic: conceptual
dev_langs:
- fsharp
ms.prod: dotnet-core
ms.workload:
- dotnetcore
ms.openlocfilehash: 11fab52cb426b0dbb173c9c6e2bd7b5766501964
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-xunit"></a>Testing unità di librerie F# in .NET Core usando il test dotnet e xUnit

In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità. Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp/) prima di iniziare. Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="creating-the-source-project"></a>Creazione del progetto di origine

Aprire una finestra della shell. Creare una directory denominata *unit-testing-with-fsharp* in cui archiviare la soluzione.
In questa nuova directory eseguire [`dotnet new sln`](../tools/dotnet-new.md) per creare una nuova soluzione. Questo rende più semplice gestire sia la libreria di classi che il progetto di unit test.
All'interno della directory della soluzione creare una directory *MathService*. La struttura della directory e dei file fino a questo momento è la seguente:

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

Impostare *MathService* come directory corrente ed eseguire [`dotnet new classlib -lang F#`](../tools/dotnet-new.md) per creare il progetto di origine.  Per usare lo sviluppo basato su test (TDD) si creerà un'implementazione non funzionante del servizio matematico:

```fsharp
module MyMath =
    let squaresOfOdds xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

Tornare alla directory *unit-test-con-fsharp*. Eseguire [`dotnet sln add .\MathService\MathService.fsproj`](../tools/dotnet-sln.md) per aggiungere il progetto di libreria di classi alla soluzione.

## <a name="creating-the-test-project"></a>Creazione del progetto di test

Creare quindi la directory *MathService.Tests*. Di seguito è illustrata la struttura di directory:

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

Impostare *MathService.Tests* come directory corrente e creare un nuovo progetto usando [`dotnet new xunit -lang F#`](../tools/dotnet-new.md). In questo modo viene creato un progetto di test che usa xUnit come libreria di test. Il modello generato configura il Test Runner nel file *MathServiceTests.fsproj*:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti. Nel passaggio precedente `dotnet new` ha aggiunto xUnit e il Runner di xUnit. Aggiungere ora la libreria di classi `MathService` come un'altra dipendenza del progetto. Usare il comando [`dotnet add reference`](../tools/dotnet-add-reference.md):

```
dotnet add reference ../MathService/MathService.fsproj
```

È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) su GitHub.

Il layout della soluzione finale è il seguente:

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
        Test Source Files
        MathServiceTests.fsproj
```

Eseguire [`dotnet sln add .\MathService.Tests\MathService.Tests.fsproj`](../tools/dotnet-sln.md) nella directory *unit-testing-with-fsharp*. 

## <a name="creating-the-first-test"></a>Creazione del primo test

L'approccio di sviluppo basato su test richiede la creazione di un test con esito negativo. È quindi necessario che il test venga superato e che il processo venga ripetuto. Aprire *Tests.fs* e aggiungere il codice seguente:

```fsharp
[<Fact>]
let ``My test`` () =
    Assert.True(true)

[<Fact>]
let ``Fail every time`` () = Assert.True(false)
```

L'attributo `[<Fact>]` indica un metodo di test eseguito dal Test Runner. Da *unit-test-con-fsharp* eseguire [`dotnet test`](../tools/dotnet-test.md) per compilare i test e la libreria di classi, quindi eseguire i test. Il Test Runner di xUnit include il punto d'ingresso del programma per l'esecuzione dei test. `dotnet test` avvia il Test Runner usando il progetto di unit test creato.

Questi due test mostrano i test più semplici superati e non superati. `My test` viene superato e `Fail every time` non viene superato. A questo punto, creare un test per il metodo `squaresOfOdds`. Il metodo `squaresOfOdds` restituisce una sequenza di quadrati di tutti i valori interi dispari che fanno parte della sequenza di input. Anziché tentare di scrivere tutte queste funzioni in una sola volta, è possibile creare in modo iterativo test per la convalida della funzionalità. Fare in modo che ogni test venga superato significa creare le funzionalità necessarie per il metodo.

Il test più semplice che si può scrivere consiste nel chiamare `squaresOfOdds` con tutti i numeri pari. In questo caso il risultato dovrebbe essere una sequenza vuota di numeri interi.  Ecco questo test:

```fsharp
[<Fact>]
let ``Sequence of Evens returns empty collection`` () =
    let expected = Seq.empty<int>
    let actual = MyMath.squaresOfOdds [2; 4; 6; 8; 10]
    Assert.Equal<Collections.Generic.IEnumerable<int>>(expected, actual)
```

Il test ha esito negativo. Non è stata ancora creata l'implementazione. Fare in modo che questo test venga superato scrivendo il codice più semplice e funzionante nella classe `MathService`:

```csharp
let squaresOfOdds xs =
    Seq.empty<int>
```

Nella directory *unit-test-con-fsharp* eseguire di nuovo `dotnet test`. Il comando `dotnet test` esegue prima una compilazione del progetto `MathService` e quindi del progetto `MathService.Tests`. Dopo la compilazione di entrambi i progetti, verrà eseguito il test singolo, che viene superato.

## <a name="completing-the-requirements"></a>Completamento dei requisiti

Ora che il test è stato superato, è necessario scriverne altri. Il prossimo test case semplice opera su una sequenza in cui l'unico numero dispari è `1`. Il numero 1 è più semplice perché il quadrato di 1 è 1. Ecco questo test:

```fsharp
[<Fact>]
let ``Sequences of Ones and Evens returns Ones`` () =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.squaresOfOdds [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.Equal<Collections.Generic.IEnumerable<int>>(expected, actual)
```

L'esecuzione di `dotnet test` esegue i test e mostra che il nuovo test non viene superato. A questo punto, aggiornare il metodo `squaresOfOdds` per gestire il nuovo test. Filtrare tutti i numeri pari fuori sequenza per fare in modo che il test venga superato. È possibile farlo scrivendo una breve funzione di filtro e usando `Seq.filter`:

```fsharp
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
```

Manca un altro passaggio: elevare al quadrato ciascuno dei numeri di dispari. Per iniziare, scrivere un nuovo test:

```fsharp
[<Fact>]
let ``SquaresOfOdds works`` () =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.squaresOfOdds [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.Equal(expected, actual)
```

È possibile correggere il test tramite il piping della sequenza filtrata attraverso un'operazione di mapping per calcolare il quadrato di ogni numero dispari:

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs = 
    xs 
    |> Seq.filter isOdd 
    |> Seq.map square
```

È stata compilata una piccola libreria e un set di unit test per tale libreria. La soluzione è stata strutturata in modo che l'aggiunta di nuovi pacchetti e test faccia parte del normale flusso di lavoro. La maggior parte del tempo e dell'impegno è dedicata alla soluzione degli obiettivi dell'applicazione.
