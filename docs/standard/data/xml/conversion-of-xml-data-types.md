---
title: Conversione dei tipi di dati XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d18b69c2d5baeac77cbdf45bebd6f0c9d5c94d9f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="conversion-of-xml-data-types"></a>Conversione dei tipi di dati XML
La maggior parte dei metodi presenti in una classe **XmlConvert** viene usata per convertire i dati tra le stringhe e i formati fortemente tipizzati. I metodi sono indipendenti dalle impostazioni locali, il che significa che le impostazioni locali non vengono prese in considerazione al momento della conversione.  
  
## <a name="reading-string-as-types"></a>Lettura delle stringhe come tipi  
 Nell'esempio seguente viene illustrato come una stringa viene letta e convertita in un tipo **DateTime**.  
  
 Dato l'input XML seguente:  
  
 **Input**  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 la stringa viene convertita dal codice nel formato **DateTime**:  
  
```vb  
reader.ReadStartElement()  
Dim vDateTime As DateTime = XmlConvert.ToDateTime(reader.ReadString())  
Console.WriteLine(vDateTime)  
```  
  
```csharp  
reader.ReadStartElement();  
DateTime vDateTime = XmlConvert.ToDateTime(reader.ReadString());  
Console.WriteLine(vDateTime);  
```  
  
## <a name="writing-strings-as-types"></a>Scrittura delle stringhe come tipi  
 Nell'esempio seguente viene illustrato come un **Int32** viene letto e convertito in una stringa.  
  
 Dato l'input XML seguente:  
  
 **Input**  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 **Int32** viene convertito dal codice in una stringa **String**:  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Conversione delle stringhe in tipi di dati di .NET Framework](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)  
 [Conversione dei tipi di .NET Framework in stringhe](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
