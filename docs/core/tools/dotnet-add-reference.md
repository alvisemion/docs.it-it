---
title: Comando dotnet-add reference - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet add reference offre un'opzione utile per aggiungere riferimenti da progetto a progetto.
author: mairaw
ms.author: mairaw
ms.date: 09/19/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: c82696eee2fbe4bbad86e59cf5de1c2e74d048f6
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-add-reference"></a>dotnet-add reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet add reference`: aggiunge riferimenti da progetto a progetto.

## <a name="synopsis"></a>Riepilogo

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>Descrizione

Il comando `dotnet add reference` offre un'opzione utile per aggiungere i riferimenti al progetto in un progetto. Dopo l'esecuzione del comando, al file di progetto vengono aggiunti gli elementi [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items).

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a>Argomenti

`PROJECT`

Specifica il file di progetto. Se non specificato, il comando ne cerca uno nella directory corrente.

`PROJECT_REFERENCES`

Riferimenti da progetto a progetto da aggiungere. Specificare uno o più progetti. I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei sistemi basati su Unix/Linux.

## <a name="options"></a>Opzioni

`-h|--help`

Stampa una breve guida per il comando.

`-f|--framework <FRAMEWORK>`

Aggiunge riferimenti al progetto solo quando la destinazione è un [framework](../../standard/frameworks.md) specifico.

## <a name="examples"></a>Esempi

Aggiungere un riferimento al progetto:

`dotnet add app/app.csproj reference lib/lib.csproj`

Aggiungere più riferimenti al progetto nella directory corrente:

`dotnet add reference lib1/lib1.csproj lib2/lib2.csproj`

Aggiungere più riferimenti al progetto usando un criterio GLOB in Linux/Unix:

`dotnet add app/app.csproj reference **/*.csproj`
