---
title: Esecuzione di query su XDocument e su Query di XElement (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 2d111f84-0ded-4cde-8d93-5440557a726d
ms.openlocfilehash: 6bc7af08544f00a87246b748d0419f11b57ed2da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="querying-an-xdocument-vs-querying-an-xelement-visual-basic"></a>Esecuzione di query su XDocument e su Query di XElement (Visual Basic)
Quando si carica un documento tramite <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, si noterà che è necessario scrivere le query in modo leggermente diverso rispetto a quando si carica un documento tramite <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>.  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a>Confronto tra XDocument.Load e XElement.Load  
 Quando si carica un documento XML in un oggetto <xref:System.Xml.Linq.XElement> tramite <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, l'oggetto <xref:System.Xml.Linq.XElement> nella radice dell'albero XML contiene l'elemento radice del documento caricato. Tuttavia, quando si carica lo stesso documento XML in un oggetto <xref:System.Xml.Linq.XDocument> tramite <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, la radice dell'albero è un nodo <xref:System.Xml.Linq.XDocument>, mentre l'elemento radice del documento caricato è l'unico nodo <xref:System.Xml.Linq.XElement> figlio consentito di <xref:System.Xml.Linq.XDocument>. Gli assi di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] eseguono operazioni in relazione al nodo radice.  
  
 Nel primo esempio viene caricato un albero XML usando <xref:System.Xml.Linq.XElement.Load%2A>. Viene quindi eseguita una query per gli elementi figlio della radice dell'albero.  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XElement.Load")  
Console.WriteLine("----")  
Dim doc As XElement = XElement.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 Come previsto, nell'esempio viene prodotto il seguente output:  
  
```  
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 L'esempio seguente è identico a quello precedente, con l'eccezione che l'albero XML viene caricato in un oggetto <xref:System.Xml.Linq.XDocument> anziché in <xref:System.Xml.Linq.XElement>.  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XDocument.Load")  
Console.WriteLine("----")  
Dim doc As XDocument = XDocument.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 Questo esempio produce il seguente output:  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
</Root>  
```  
  
 Notare che la stessa query ha restituito l'unico nodo `Root` anziché i tre nodi figlio.  
  
 Per gestire questa situazione, è possibile usare la proprietà <xref:System.Xml.Linq.XDocument.Root%2A> prima di accedere ai metodi degli assi, come illustrato di seguito:  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XDocument.Load")  
Console.WriteLine("----")  
Dim doc As XDocument = XDocument.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Root.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 Questa query viene ora eseguita in modo identico alla query sull'albero inserito nella radice di <xref:System.Xml.Linq.XElement>. Questo esempio produce il seguente output:  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Le query di base (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
