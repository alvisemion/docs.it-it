---
title: 'Procedura: intercettare gli errori di analisi (C#)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: bfb612d4-5605-48ef-8c93-915cf9d5dcfb
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e541a004833ccd2aaecfd4ea13652b03a1270186
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-catch-parsing-errors-c"></a>Procedura: intercettare gli errori di analisi (C#)
In questo argomento viene illustrato come rilevare XML non corretto o non valido.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] viene implementato usando <xref:System.Xml.XmlReader>. Se a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] viene passato XML non corretto o non valido, la classe <xref:System.Xml.XmlReader> sottostante genererà un'eccezione. I vari metodi che analizzano il codice XML, ad esempio <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, non intercettano l'eccezione, che può quindi essere intercettata dall'applicazione.  
  
## <a name="example"></a>Esempio  
 Nel codice seguente si tenta di analizzare XML non valido:  
  
```csharp  
try {  
    XElement contacts = XElement.Parse(  
        @"<Contacts>  
            <Contact>  
                <Name>Jim Wilson</Name>  
            </Contact>  
          </Contcts>");  
  
    Console.WriteLine(contacts);  
}  
catch (System.Xml.XmlException e)  
{  
    Console.WriteLine(e.Message);  
}  
```  
  
 Quando viene eseguito, questo codice genera la seguente eccezione:  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 Per informazioni sulle eccezioni che si può prevedere vengano generate dai metodi <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> e <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, vedere la documentazione relativa a <xref:System.Xml.XmlReader>.  
  
## <a name="see-also"></a>Vedere anche  
 [Analisi di codice XML (C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)
