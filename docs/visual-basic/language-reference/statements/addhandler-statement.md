---
title: Istruzione AddHandler
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: db8131dc82aed40e725c9375efef274fb6917d41
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="addhandler-statement"></a>Istruzione AddHandler
Associa un evento al gestore eventi in fase di esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Parti  
 `event`  
 Il nome dell'evento da gestire.  
  
 `eventhandler`  
 Il nome di una routine che gestisce l'evento.  
  
## <a name="remarks"></a>Note  
 Il `AddHandler` e `RemoveHandler` istruzioni consentono di avviare e arrestare la gestione degli eventi in qualsiasi momento durante l'esecuzione del programma.  
  
 La firma del `eventhandler` routine deve corrispondere alla firma dell'evento `event`.  
  
 La parola chiave `Handles` e l'istruzione `AddHandler` consentono entrambe di specificare che quelle particolari routine gestiscono particolari eventi, ma esistono alcune differenze. L'istruzione `AddHandler` connette le routine agli eventi in fase di esecuzione. Usare la parola chiave `Handles` quando si definisce una routine, per specificare che questa gestisce un particolare evento. Per ulteriori informazioni, vedere [gestisce](../../../visual-basic/language-reference/statements/handles-clause.md).  
  
> [!NOTE]
>  Per gli eventi personalizzati, il `AddHandler` istruzione richiama l'evento `AddHandler` della funzione di accesso. Per ulteriori informazioni sugli eventi personalizzati, vedere [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)
