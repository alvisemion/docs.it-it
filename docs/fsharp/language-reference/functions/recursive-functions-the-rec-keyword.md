---
title: 'Funzioni ricorsive: parola chiave rec (F#)'
description: "Informazioni su come la parola chiave 'rec' F # viene utilizzata con la parola chiave 'let' per definire una funzione ricorsiva."
ms.date: 05/16/2016
ms.openlocfilehash: 6039a48eae2b16aa1d82617176460d727a878d87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="recursive-functions-the-rec-keyword"></a>Funzioni ricorsive: parola chiave rec

Il `rec` parola chiave viene utilizzata in combinazione con il `let` (parola chiave) per definire una funzione ricorsiva.


## <a name="syntax"></a>Sintassi

```fsharp
// Recursive function:
let rec function-nameparameter-list =
function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
function1-body
and function2-nameparameter-list =
function2-body
...
```

## <a name="remarks"></a>Note
Funzioni ricorsive, le funzioni che chiamano se stesse, vengono identificate in modo esplicito nel linguaggio F #. Ciò rende disponibile l'identificatore che viene definito nell'ambito della funzione.

Il codice seguente viene illustrata una funzione ricorsiva che calcola il *n*o numero di Fibonacci.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

>[!NOTE]
In pratica, codice come quello precedente è causano un elevato utilizzo di memoria e tempo processore perché prevede la il ricalcolo di valori calcolati in precedenza.


I metodi sono implicitamente ricorsiva all'interno del tipo; non è necessario aggiungere il `rec` (parola chiave). Associazioni let nelle classi non sono implicitamente ricorsivi.


## <a name="mutually-recursive-functions"></a>Funzioni ricorsive reciproche
Talvolta le funzioni sono *ricorsive reciproche*, ovvero le chiamate formano un cerchio, in cui una funzione chiama un'altra che a sua volta chiama la prima, con un numero qualsiasi di chiamate tra. È necessario definire tali funzioni in quella `let` binding, utilizzando il `and` (parola chiave) per collegarle.

Nell'esempio seguente vengono illustrati due reciprocamente funzioni ricorsive.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a>Vedere anche
[Funzioni](index.md)
