---
title: Informazioni sul chiamante (C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: ffad3d24-2fb7-4641-9124-53b5bc91d339
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 05c153afd502da1f290b3bc36460ded27789e21c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="caller-information-c"></a>Informazioni sul chiamante (C#)
Gli attributi di informazioni sul chiamante consentono di ottenere informazioni sul chiamante di un metodo. È possibile ottenere il percorso del file del codice sorgente, il numero di riga nel codice sorgente e il nome del chiamante. Queste informazioni sono utili per la tracciatura, il debug e la creazione di strumenti diagnostici.  
  
 Per ottenere queste informazioni, utilizzare gli attributi applicati ai parametri facoltativi, a ognuno dei quali è associato un valore predefinito. Nella tabella seguente sono elencati gli attributi di informazioni sul chiamante definiti nello spazio dei nomi <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:  
  
|Attributo|Descrizione|Tipo|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|Percorso completo del file di origine contenente il chiamante. Si tratta del percorso del file al momento della compilazione.|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|Numero di riga nel file di origine in cui viene chiamato il metodo.|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|Nome di una proprietà o di un metodo del chiamante. Vedere [Nomi dei membri](#MEMBERNAMES) più avanti in questo argomento.|`String`|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare gli attributi di informazioni sul chiamante. Per ogni chiamata al metodo `TraceMessage`, le informazioni sul chiamante vengono sostituite come argomenti dei parametri facoltativi.  
  
```csharp  
public void DoProcessing()  
{  
    TraceMessage("Something happened.");  
}  
  
public void TraceMessage(string message,  
        [System.Runtime.CompilerServices.CallerMemberName] string memberName = "",  
        [System.Runtime.CompilerServices.CallerFilePath] string sourceFilePath = "",  
        [System.Runtime.CompilerServices.CallerLineNumber] int sourceLineNumber = 0)  
{  
    System.Diagnostics.Trace.WriteLine("message: " + message);  
    System.Diagnostics.Trace.WriteLine("member name: " + memberName);  
    System.Diagnostics.Trace.WriteLine("source file path: " + sourceFilePath);  
    System.Diagnostics.Trace.WriteLine("source line number: " + sourceLineNumber);  
}  
  
// Sample Output:  
//  message: Something happened.  
//  member name: DoProcessing  
//  source file path: c:\Users\username\Documents\Visual Studio 2012\Projects\CallerInfoCS\CallerInfoCS\Form1.cs  
//  source line number: 31  
```  
  
## <a name="remarks"></a>Note  
 È sempre necessario specificare un valore esplicito per ciascun parametro facoltativo. Non è possibile applicare attributi di informazioni sul chiamante ai parametri non specificati come facoltativi.  
  
 Gli attributi di informazioni sul chiamante non restituiscono un parametro facoltativo, ma influiscono sul valore predefinito passato quando l'argomento è omesso.  
  
 I valori delle informazioni sul chiamante vengono generati come valori letterali in Intermediate Language (IL) in fase di compilazione. A differenza dei risultati della proprietà <xref:System.Exception.StackTrace%2A> per le eccezioni, i risultati non sono interessati da offuscamento.  
  
 È possibile fornire esplicitamente gli argomenti facoltativi per esaminare o nascondere le informazioni sul chiamante.  
  
###  <a name="MEMBERNAMES"></a> Nomi dei membri  
 È possibile utilizzare l'attributo `CallerMemberName` per specificare il nome del membro come argomento `String` al metodo chiamato. Usando questa tecnica, si evita il problema per cui il **refactoring di ridenominazione** non modifica i valori `String`. Questo vantaggio è particolarmente utile per le attività seguenti:  
  
-   Utilizzo della tracciatura e delle routine di diagnostica.  
  
-   Implementazione dell'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged> durante l'associazione dei dati. Questa interfaccia consente alla proprietà di un oggetto di notificare a un controllo associato la modifica della proprietà stessa in modo che il controllo possa visualizzare le informazioni aggiornate. Senza l'attributo `CallerMemberName`, è necessario specificare il nome della proprietà come valore letterale.  
  
 Nel grafico seguente vengono mostrati i nomi dei membri restituiti quando si utilizza l'attributo `CallerMemberName`.  
  
|Elemento in cui si verificano le chiamate|Nome del membro restituito|  
|-------------------------|------------------------|  
|Metodo, proprietà o evento|Nome del metodo, della proprietà o dell'evento da cui la chiamata ha avuto origine.|  
|Costruttore|Stringa ".ctor"|  
|Costruttore statico|Stringa ".cctor"|  
|Distruttore|Stringa "Finalize"|  
|Operatori o conversioni definiti dall'utente|Nome generato per il membro, ad esempio "op_Addition".|  
|Costruttore dell'attributo|Nome del membro a cui viene applicato l'attributo. Se l'attributo è un qualsiasi elemento in un membro (ad esempio un parametro, un valore restituito o un parametro di tipo generico), il risultato è il nome del membro associato a tale elemento.|  
|Nessun membro contenitore (ad esempio a livello di assembly o attributi applicati a tipi)|Valore predefinito del parametro facoltativo.|  
  
## <a name="see-also"></a>Vedere anche  
 [Attributi (C#)](../../../csharp/programming-guide/concepts/attributes/index.md)  
 [Attributi comuni (C#)](../../../csharp/programming-guide/concepts/attributes/common-attributes.md)  
 [Argomenti denominati e facoltativi](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)  
 [Nozioni di base sulla programmazione (C#)](../../../csharp/programming-guide/concepts/index.md)
