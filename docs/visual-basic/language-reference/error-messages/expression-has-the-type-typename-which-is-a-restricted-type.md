---
title: Espressione è di tipo &#39; &lt;typename&gt; &#39; che è un tipo con restrizioni e non può essere utilizzato per accedere ai membri ereditati da &#39;oggetto&#39; o &#39;ValueType&#39;
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 2ba2298da77ac31abc0b1b4ad84328be7bc6dbb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="expression-has-the-type-39lttypenamegt39-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-39object39-or-39valuetype39"></a>Espressione è di tipo &#39; &lt;typename&gt; &#39; che è un tipo con restrizioni e non può essere utilizzato per accedere ai membri ereditati da &#39;oggetto&#39; o &#39;ValueType&#39;
Un'espressione restituisce un tipo che non può essere sottoposto a boxing tramite common language runtime (CLR), ma accede a un membro che richiede una conversione boxing.  
  
 Il termine*boxing* indica il processo di elaborazione necessario per la conversione di un tipo in `Object` o <xref:System.ValueType>. Common language runtime non supporta il boxing determinati tipi di struttura, ad esempio <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, e <xref:System.TypedReference>.  
  
 Questa espressione tenta di utilizzare il tipo con restrizioni per chiamare un metodo ereditato da <xref:System.Object> o <xref:System.ValueType>, ad esempio <xref:System.Object.GetHashCode%2A> o <xref:System.Object.ToString%2A>. Per accedere a questo metodo, Visual Basic è tentata una conversione boxing implicita che genera questo errore.  
  
 **ID errore:** BC31393  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Trovare l'espressione che restituisce il tipo citato.  
  
2.  Individuare la parte dell'istruzione che tenta di chiamare il metodo ereditato da <xref:System.Object> o <xref:System.ValueType>.  
  
3.  Riscrivere le istruzioni per evitare la chiamata al metodo.  
  
## <a name="see-also"></a>Vedere anche  
 [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
