---
title: 'Esempi di sintassi di query basate sul metodo: raggruppamento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb23c25c-1075-4cc3-a8ff-4db72e536c0d
ms.openlocfilehash: 1bc2ab6f7dbfb3b2babcc5a9565a7bfd9fd962c4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="method-based-query-syntax-examples-grouping"></a>Esempi di sintassi di query basate sul metodo: raggruppamento
Gli esempi in questo argomento viene illustrato come utilizzare il `GroupBy` metodo per eseguire query di [modello Sales di AdventureWorks](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) utilizzando la sintassi di query basate su metodo. Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.  
  
 Gli esempi in questo argomento usano seguenti `using` / `Imports` istruzioni:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato il metodo `GroupBy` per restituire oggetti `Address` raggruppati in base al codice postale. I risultati vengono proiettati in un tipo anonimo.  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3_mq)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato il metodo `GroupBy` per restituire oggetti `Contact` raggruppati in base alla prima lettera del cognome del contatto. I risultati vengono anche ordinati in base alla prima lettera del cognome e proiettati in un tipo anonimo.  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2_mq)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato il metodo `GroupBy` per restituire oggetti `SalesOrderHeader` raggruppati in base all'ID cliente. Viene restituito anche il numero di vendite per ogni cliente.  
  
 [!code-csharp[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount_mq)]
 [!code-vb[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount_mq)]  
  
## <a name="see-also"></a>Vedere anche  
 [Query in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
