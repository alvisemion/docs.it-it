---
title: Esecuzione di unit test selettivi
description: Illustra come utilizzare un'espressione di filtro per eseguire unit test selettivi con il comando dotnet test.
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 77ac7ab5a46150bd3654d50e6686087c804b8440
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="running-selective-unit-tests"></a>Esecuzione di unit test selettivi

Negli esempi seguenti viene usato `dotnet test`. Se si utilizza `vstest.console.exe`, sostituire `--filter ` con `--testcasefilter:`.

## <a name="mstest"></a>MSTest

```csharp
namespace MSTestNamespace
{
    using Microsoft.VisualStudio.TestTools.UnitTesting;

    [TestClass]
    public class UnitTestClass1
    {
        [Priority(2)]
        [TestMethod]
        public void TestMethod1()
        {
        }

        [TestCategory("CategoryA")]
        [Priority(3)]
        [TestMethod]
        public void TestMethod2()
        {
        }
    }
}
```

| Espressione | Risultato |
| ---------- | ------ |
| `dotnet test --filter Method` | Esegue i test il cui `FullyQualifiedName` contiene `Method`. Disponibile in `vstest 15.1+`. |
| `dotnet test --filter Name~TestMethod1` | Esegue i test il cui nome contiene `TestMethod1`. |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTestClass1` | Esegue i test inclusi nella classe `MSTestNamespace.UnitTestClass1`.<br>**Nota:** il valore `ClassName` deve avere uno spazio dei nomi, pertanto `ClassName=UnitTestClass1` non funziona. |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTestClass1.TestMethod1` | Esegue tutti i test tranne `MSTestNamespace.UnitTestClass1.TestMethod1`. |
| `dotnet test --filter TestCategory=CategoryA` | Esegue i test annotati con `[TestCategory("CategoryA")]`. |
| `dotnet test --filter Priority=3` | Esegue i test annotati con `[Priority(3)]`.<br>**Nota:** `Priority~3` è un valore non valido, in quanto non è una stringa. |

**Utilizzo degli operatori condizionali | e &amp;**

| Espressione | Risultato |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTestClass1&#124;TestCategory=CategoryA"</code> | Esegue i test che hanno `UnitTestClass1` in `FullyQualifiedName` **o la cui**  `TestCategory` è `CategoryA`. |
| `dotnet test --filter "FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA"` | Esegue i test che hanno `UnitTestClass1` in `FullyQualifiedName` **e la cui**  `TestCategory` è `CategoryA`. |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA)&#124;Priority=1"</code> | Esegue i test che hanno `FullyQualifiedName` contenente `UnitTestClass1` **e la cui**  `TestCategory` è `CategoryA` **o** `Priority` è 1. |

## <a name="xunit"></a>xUnit

```csharp
namespace XUnitNamespace
{
    public class TestClass1
    {
        [Trait("Category", "bvt")]
        [Trait("Priority", "1")]
        [Fact]
        public void foo()
        {
        }

        [Trait("Category", "Nightly")]
        [Trait("Priority", "2")]
        [Fact]
        public void bar()
        {
        }
    }
}
```

| Espressione | Risultato |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | Esegue solo un test, `XUnitNamespace.TestClass1.Test1`. |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | Esegue tutti i test tranne `XUnitNamespace.TestClass1.Test1`. |
| `dotnet test --filter DisplayName~TestClass1` | Esegue i test il cui nome visualizzato contiene `TestClass1`. |

Nell'esempio di codice, i tratti definiti con le chiavi `Category` e `Priority` possono essere utilizzati per il filtraggio.

| Espressione | Risultato |
| ---------- | ------ |
| `dotnet test --filter XUnit` | Esegue i test il cui `FullyQualifiedName` contiene `XUnit`.  Disponibile in `vstest 15.1+`. |
| `dotnet test --filter Category=bvt` | Esegue i test che hanno `[Trait("Category", "bvt")]`. |

**Utilizzo degli operatori condizionali | e &amp;**

| Espressione | Risultato |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=Nightly"</code> | Esegue i test che hanno `TestClass1` in `FullyQualifiedName` **o la cui**  `Category` è `Nightly`. |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=Nightly"` | Esegue i test che hanno `TestClass1` in `FullyQualifiedName` **e la cui**  `Category` è `Nightly`. |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=Nightly)&#124;Priority=1"</code> | Esegue i test che hanno `FullyQualifiedName` contenente `TestClass1` **e la cui**  `Category` è `CategoryA` **o la cui**  `Priority` è 1. |
