---
title: Convenzioni di denominazione generali
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], conflicts
- type names, conflicts
- language-specific type names
- names [.NET Framework], about naming guidelines
- names [.NET Framework], abbreviations
- abbreviation naming guidelines
- acronym naming guidelines
- Hungarian notation
- names [.NET Framework], type names
- names [.NET Framework], acronyms
ms.assetid: d3a77ea1-75d2-4969-a8c3-3e1e3e1aaedc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc54b8bdc96a5038dc75111d9833e70e7ffd2e9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="general-naming-conventions"></a>Convenzioni di denominazione generali
Questa sezione descrive convenzioni di denominazione generali correlate alla scelta delle parole, le linee guida sull'utilizzo di abbreviazioni e acronimi e indicazioni su come evitare di utilizzare nomi specifici della lingua.  
  
## <a name="word-choice"></a>Scelta di Word  
 **✓ SI** scegliere i nomi degli identificatori facilmente leggibili.  
  
 Ad esempio, una proprietà denominata `HorizontalAlignment` è più inglese-leggibile `AlignmentHorizontal`.  
  
 **✓ SI** privilegiare la leggibilità ragioni di brevità.  
  
 Il nome della proprietà `CanScrollHorizontally` è migliore `ScrollableX` (un riferimento all'asse x).  
  
 **X non** utilizzare caratteri di sottolineatura, trattini o altri caratteri non alfanumerici.  
  
 **X non** utilizzare la notazione ungherese.  
  
 **X evitare** utilizzando gli identificatori che sono in conflitto con le parole chiave di ampiamente utilizzato linguaggi di programmazione.  
  
 In base alla regola 4 della specifica CLS (Common Language), tutti i linguaggi conformi devono fornire un meccanismo che consente l'accesso agli elementi denominati che usano una parola chiave del linguaggio come identificatore. In c#, ad esempio, Usa il simbolo come meccanismo di escape in questo caso @. Tuttavia, è comunque consigliabile evitare di parole chiave comuni in quanto è molto più difficile usare un metodo con la sequenza di escape quello senza di esso.  
  
## <a name="using-abbreviations-and-acronyms"></a>Utilizzo di abbreviazioni e gli acronimi  
 **X non** utilizzare abbreviazioni o termini più semplici come parte dei nomi degli identificatori.  
  
 Ad esempio, utilizzare `GetWindow` anziché `GetWin`.  
  
 **X non** utilizzare acronimi che non sono molto diffusa e anche se sono solo quando necessario.  
  
## <a name="avoiding-language-specific-names"></a>Evitare nomi specifici della lingua  
 **✓ SI** utilizzare nomi significativi anziché le parole chiave specifiche della lingua per i nomi dei tipi.  
  
 Ad esempio, `GetLength` è un nome più significativo rispetto a `GetInt`.  
  
 **✓ SI** usare un nome di tipo generico di CLR, anziché un nome specifico della lingua, in rari casi in cui un identificatore non ha alcun significato semantico oltre il relativo tipo.  
  
 Ad esempio, un metodo di conversione in <xref:System.Int64> deve essere denominato `ToInt64`, non `ToLong` (perché <xref:System.Int64> è un nome CLR per c#-alias specifico `long`). Nella tabella seguente presenta vari tipi di dati di base utilizzando i nomi dei tipi CLR (nonché i nomi dei tipi corrispondenti per c#, Visual Basic e C++).  
  
|C#|Visual Basic|C++|CLR|  
|---------|------------------|-----------|---------|  
|**sbyte**|**SByte**|**char**|**SByte**|  
|**byte**|**Byte**|**unsigned char**|**Byte**|  
|**short**|**Short**|**short**|**Int16**|  
|**ushort**|**UInt16**|**unsigned short**|**UInt16**|  
|**int**|**Integer**|**int**|**Int32**|  
|**uint**|**UInt32**|**unsigned int**|**UInt32**|  
|**long**|**Long**|**__int64**|**Int64**|  
|**ulong**|**UInt64**|**unsigned __int64**|**UInt64**|  
|**float**|**Single**|**float**|**Single**|  
|**double**|**Double**|**double**|**Double**|  
|**bool**|**Boolean**|**bool**|**Boolean**|  
|**char**|**Char**|**wchar_t**|**Char**|  
|**string**|**String**|**String**|**String**|  
|**object**|**Oggetto**|**Oggetto**|**Oggetto**|  
  
 **✓ SI** utilizzare un nome comune, ad esempio `value` o `item`, piuttosto che ripetere il nome del tipo, in rari casi in cui un identificatore non ha alcun significato semantico e il tipo del parametro non è importante.  
  
## <a name="naming-new-versions-of-existing-apis"></a>Denominazione di nuove versioni delle API esistente  
 **✓ SI** utilizzare un nome simile all'API precedente durante la creazione di nuove versioni di un'API esistente.  
  
 Ciò consente di evidenziare la relazione tra le API.  
  
 **✓ SI** preferisce aggiunta di un suffisso anziché un prefisso per indicare una nuova versione di un'API esistente.  
  
 Questo modo viene agevolata individuazione durante l'esplorazione di documentazione, o l'utilizzo di Intellisense. La versione precedente dell'API verrà organizzata vicino a nuove API, poiché la maggior parte dei browser e Intellisense Mostra gli identificatori in ordine alfabetico.  
  
 **✓ Provare a** utilizzando un identificatore di nuovo, ma significativo, anziché aggiungere un prefisso o suffisso.  
  
 **✓ SI** utilizzare un suffisso numerico per indicare una nuova versione di un'API esistente, in particolare se il nome dell'API esistente è l'unico nome appropriato (ad esempio, se è uno standard del settore) e se si aggiungono qualsiasi significativo suffisso (o la modifica del nome) non è un'app opzione ropriate.  
  
 **X non** utilizzare "Ex" (o una simile) suffisso di un identificatore per distinguerlo da una versione precedente dell'API stessa.  
  
 **✓ SI** utilizzano il suffisso "64" quando si introduce le versioni delle API che operano su un valore integer a 64 bit (un valore long integer) anziché un intero a 32 bit. È necessario adottare questo approccio quando è presente l'API di 32 bit esistente. non eseguire l'operazione per la nuove API con solo una versione a 64 bit.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
