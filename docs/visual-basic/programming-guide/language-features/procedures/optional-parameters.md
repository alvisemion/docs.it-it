---
title: Parametri facoltativi (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [Visual Basic], optional
- Visual Basic code, procedures
- procedures [Visual Basic], optional arguments
- optional arguments
- named arguments [Visual Basic], and optional arguments
- optional parameters
- Optional keyword [Visual Basic], optional arguments
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], and named arguments
ms.assetid: 398d2845-1069-4e94-b934-a73b545c8b87
ms.openlocfilehash: a438455668310769c5267a6d42a2e694bb7b01dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="optional-parameters-visual-basic"></a>Parametri facoltativi (Visual Basic)
È possibile specificare che un parametro di routine è facoltativo e non è necessario fornire alcun argomento quando la routine viene chiamata. *Parametri facoltativi* sono indicate con la `Optional` parola chiave nella definizione della routine. È necessario attenersi alle regole che seguono:  
  
-   È necessario che ciascun parametro facoltativo nella definizione della routine specifichi un valore predefinito.  
  
-   È necessario che tale valore predefinito per un parametro facoltativo sia un'espressione costante.  
  
-   Ciascun parametro che segue un parametro facoltativo nella definizione della routine deve essere anch'esso facoltativo.  
  
 Nella sintassi seguente viene illustrata una dichiarazione di routine con un parametro facoltativo:  
  
```vb  
Sub name(ByVal parameter1 As datatype1, Optional ByVal parameter2 As datatype2 = defaultvalue)  
```  
  
## <a name="calling-procedures-with-optional-parameters"></a>Chiamata di routine con parametri facoltativi  
 Quando si chiama una routine con un parametro facoltativo, è possibile scegliere se fornire l'argomento o meno. Se non lo si fornisce, la routine utilizza il valore predefinito dichiarato per quel parametro.  
  
 Quando si omettono uno o più argomenti facoltativi nell'elenco degli argomenti, utilizzare virgole in sequenza per contrassegnarne la posizione. La chiamata di esempio che segue fornisce il primo e il quarto argomento, ma non il secondo o il terzo:  
  
```vb  
Sub name(argument 1, , , argument 4)  
```  
  
 Nell'esempio riportato di seguito vengono effettuate diverse chiamate alla funzione `MsgBox`. `MsgBox` include un parametro obbligatorio e due parametri facoltativi.  
  
 Nella prima chiamata a `MsgBox` vengono forniti tutti e tre gli argomenti nell'ordine in cui sono definiti da `MsgBox`. Nella seconda chiamata viene fornito solo l'argomento obbligatorio. Nella terza e quarta chiamata vengono forniti il primo e il terzo argomento. Nella terza chiamata gli argomenti vengono forniti in base alla posizione, nella quarta in base al nome.  
  
 [!code-vb[VbVbcnProcedures#47](./codesnippet/VisualBasic/optional-parameters_1.vb)]  
  
## <a name="determining-whether-an-optional-argument-is-present"></a>Determinazione dell'eventuale presenza di un argomento facoltativo  
 Una routine non può rilevare, in fase di esecuzione, se un determinato argomento è stato omesso o se il codice di chiamata ha fornito in modo esplicito il valore predefinito. Se è necessario fare questa distinzione, è possibile impostare come predefinito un valore improbabile. La procedura seguente definisce il parametro facoltativo `office`e verifica il valore predefinito, `QJZ`, per vedere se è stato omesso nella chiamata:  
  
 [!code-vb[VbVbcnProcedures#46](./codesnippet/VisualBasic/optional-parameters_2.vb)]  
  
 Se il parametro facoltativo è un tipo di riferimento come `String`, è possibile utilizzare `Nothing` come valore predefinito, a meno che esso non sia un valore previsto per l'argomento.  
  
## <a name="optional-parameters-and-overloading"></a>Parametri facoltativi e overload  
 Un altro modo per definire una routine con parametri facoltativi consiste nell'utilizzare l'overload. Nel caso di un parametro facoltativo, è possibile definire due versioni di overload della routine, una con il parametro e l'altra senza. Questo metodo diventa più complesso con l'aumentare del numero dei parametri facoltativi, tuttavia ha il vantaggio di assicurare che il programma di chiamata fornisca tutti gli argomenti facoltativi.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)  
 [Passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md)  
 [Matrici di parametri](./parameter-arrays.md)  
 [Overload della routine](./procedure-overloading.md)  
 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)
