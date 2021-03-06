---
title: AcceptChanges e RejectChanges
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: 65e47bafda3e3e47241405c9c8b8e3b4b0055601
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="acceptchanges-and-rejectchanges"></a>AcceptChanges e RejectChanges
Dopo aver verificato la correttezza delle modifiche apportate ai dati in un <xref:System.Data.DataTable>, è possibile accettare le modifiche utilizzando il <xref:System.Data.DataRow.AcceptChanges%2A> metodo il <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, o <xref:System.Data.DataSet>, che imposterà il **corrente** riga per i valori di **originale** valori e imposterà il **RowState** proprietà **Unchanged**. L'accettazione o rifiuto delle modifiche consente di cancellare eventuali **RowError** informazioni e imposta il **HasErrors** proprietà **false**. È inoltre possibile che l'accettazione o il rifiuto delle modifiche influisca sui dati di aggiornamento nell'origine dati. Per ulteriori informazioni, vedere [l'aggiornamento di origini dati con DataAdapter](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).  
  
 Se i vincoli di chiave esterna presenti il **DataTable**, le modifiche accettate o rifiutate tramite **AcceptChanges** e **RejectChanges** vengono propagate alle righe figlio di  **DataRow** in base al **AcceptRejectRule**. Per ulteriori informazioni, vedere [vincoli DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 L'esempio seguente controlla se sono presenti righe con errori, risolve errori laddove è possibile e rifiuta le righe contenenti errori non risolvibili. Si noti che, per risolvere gli errori, il **RowError** valore viene reimpostato su una stringa vuota, provocando il **HasErrors** proprietà da impostare **false**. Quando tutte le righe con errori sono state risolte o rifiutate, **AcceptChanges** viene chiamato per accettare tutte le modifiche per l'intero **DataTable**.  
  
```vb  
If workTable.HasErrors Then  
  Dim errRow As DataRow  
  
  For Each errRow in workTable.GetErrors()  
  
    If errRow.RowError = "Total cannot exceed 1000." Then  
      errRow("Total") = 1000  
      errRow.RowError = ""    ' Clear the error.  
    Else  
      errRow.RejectChanges()  
    End If  
  Next  
End If  
  
workTable.AcceptChanges()  
```  
  
```csharp  
if (workTable.HasErrors)  
{  
  
  foreach (DataRow errRow in workTable.GetErrors())  
  {  
    if (errRow.RowError == "Total cannot exceed 1000.")  
    {  
      errRow["Total"] = 1000;  
      errRow.RowError = "";    // Clear the error.  
    }  
    else  
      errRow.RejectChanges();  
  }  
}  
  
workTable.AcceptChanges();  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [Manipolazione di dati in un oggetto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
