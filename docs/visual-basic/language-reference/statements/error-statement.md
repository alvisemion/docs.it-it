---
title: Istruzione Error
ms.date: 07/20/2015
f1_keywords:
- vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
ms.openlocfilehash: 3ecfe18392de15dc937d90565b49641415dd7e0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="error-statement"></a>Istruzione Error
Simula il verificarsi di un errore.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a>Parti  
 `errornumber`  
 Obbligatorio. Può essere qualsiasi numero di errore valido.  
  
## <a name="remarks"></a>Note  
 Il `Error` istruzione è supportata per compatibilità con le versioni precedenti. Nel nuovo codice, in particolare quando si creano oggetti, utilizzare il `Err` dell'oggetto `Raise` metodo per generare errori di run-time.  
  
 Se `errornumber` è definito, il `Error` istruzione chiama il gestore errori dopo le proprietà del `Err` oggetto vengono assegnati i valori predefiniti seguenti:  
  
|Proprietà|Valore|  
|--------------|-----------|  
|`Number`|Valore specificato come argomento per `Error` istruzione. Può essere qualsiasi numero di errore valido.|  
|`Source`|Nome del progetto corrente di Visual Basic.|  
|`Description`|Espressione stringa corrispondente al valore restituito del `Error` funzione per l'oggetto specificato `Number`, se questa stringa è presente. Se la stringa non esiste, `Description` contiene una stringa di lunghezza zero ("").|  
|`HelpFile`|L'unità completo, percorso e nome file del file della Guida di Visual Basic appropriato.|  
|`HelpContext`|La Guida di Visual Basic di ID del contesto relativo all'errore corrispondente al file il `Number` proprietà.|  
|`LastDLLError`|Zero.|  
  
 Se non esiste alcun gestore errori o non è attivato, un messaggio di errore verrà creato e visualizzato dal `Err` proprietà dell'oggetto.  
  
> [!NOTE]
>  Alcune applicazioni host di Visual Basic non è possibile creare oggetti. Vedere la documentazione dell'applicazione host per determinare se è possibile creare classi e oggetti.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il `Error` istruzione per generare il numero di errore 11.  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a>Requisiti  
 **Namespace:** [VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Assembly:** libreria di Runtime di Visual Basic (in VisualBasic)  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>  
 <xref:Microsoft.VisualBasic.Information.Err%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>  
 [Istruzione On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)  
 [Istruzione Resume](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [Messaggi di errore](../../../visual-basic/language-reference/error-messages/index.md)
