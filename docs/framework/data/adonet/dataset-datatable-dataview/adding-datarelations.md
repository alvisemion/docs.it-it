---
title: Aggiunta di oggetti DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: 451ee0eee466efca86345ea7112e9b178a2c66e2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="adding-datarelations"></a>Aggiunta di oggetti DataRelation
In un <xref:System.Data.DataSet> contenente più oggetti <xref:System.Data.DataTable> è possibile usare gli oggetti <xref:System.Data.DataRelation> per creare relazioni tra le tabelle, navigare tra di esse e restituire le righe padre o figlio da una tabella correlata.  
  
 Gli argomenti necessari per creare un **DataRelation** sono un nome per il **DataRelation** creato e una matrice di uno o più <xref:System.Data.DataColumn> i riferimenti alle colonne che fungono da padre e figlio colonne nella relazione. Dopo aver creato un **DataRelation**, è possibile utilizzare per navigare tra le tabelle e recuperare i valori.  
  
 Aggiunta di un **DataRelation** per un <xref:System.Data.DataSet> aggiunge, per impostazione predefinita, un <xref:System.Data.UniqueConstraint> alla tabella padre e un <xref:System.Data.ForeignKeyConstraint> alla tabella figlio. Per ulteriori informazioni sui vincoli predefiniti, vedere [vincoli DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 L'esempio di codice seguente crea un **DataRelation** utilizzando due <xref:System.Data.DataTable> gli oggetti in un <xref:System.Data.DataSet>. Ogni <xref:System.Data.DataTable> contiene una colonna denominata **CustID**, che funge da collegamento tra i due <xref:System.Data.DataTable> oggetti. Nell'esempio viene aggiunto un singolo **DataRelation** per il **relazioni** insieme il <xref:System.Data.DataSet>. Il primo argomento dell'esempio specifica il nome del **DataRelation** da creare. Il secondo argomento imposta l'elemento padre **DataColumn** e il terzo argomento imposta l'elemento figlio **DataColumn**.  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 A **DataRelation** dispone anche di un **Nested** proprietà che, se impostato su **true**, fa sì che le righe della tabella figlio all'interno della riga associata nella tabella padre Quando scritte come elementi XML tramite <xref:System.Data.DataSet.WriteXml%2A> . Per altre informazioni, vedere [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
