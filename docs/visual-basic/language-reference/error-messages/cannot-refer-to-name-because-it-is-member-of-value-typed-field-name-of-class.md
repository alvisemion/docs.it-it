---
title: Non è possibile fare riferimento a &#39; &lt;nome&gt; &#39; perché è un membro del campo valori &#39; &lt;nome&gt; &#39; della classe &#39; &lt;classname&gt; &#39;che dispone di &#39;System. MarshalByRefObject&#39; come classe di base
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: f44d33c9d51148e6bbcfbf5db4dbc115101df1f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="cannot-refer-to-39ltnamegt39-because-it-is-a-member-of-the-value-typed-field-39ltnamegt39-of-class-39ltclassnamegt39-which-has-39systemmarshalbyrefobject39-as-a-base-class"></a>Non è possibile fare riferimento a &#39; &lt;nome&gt; &#39; perché è un membro del campo valori &#39; &lt;nome&gt; &#39; della classe &#39; &lt;classname&gt; &#39;che dispone di &#39;System. MarshalByRefObject&#39; come classe di base
La `System.MarshalByRefObject` classe consente alle applicazioni che supportano l'accesso remoto agli oggetti limiti del dominio applicazione. I tipi devono ereditare dalla `MarshalByRejectObject` classe quando i limiti del dominio applicazione viene utilizzato il tipo. Lo stato dell'oggetto non deve essere copiato perché i membri dell'oggetto non sono utilizzabili all'esterno del dominio applicazione in cui sono stati creati.  
  
 **ID errore:** BC30310  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Verificare il riferimento per assicurarsi che il membro a cui si fa riferimento è valido.  
  
2.  Qualificare in modo esplicito il membro con il `Me` (parola chiave).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.MarshalByRefObject>  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
