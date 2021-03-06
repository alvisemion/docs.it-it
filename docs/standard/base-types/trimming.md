---
title: Eliminazione di spazi iniziali e finali e rimozione di caratteri dalle stringhe in .NET
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
- cpp
helpviewer_keywords:
- strings [.NET Framework], removing characters
- Remove method
- TrimEnd method
- Trim method
- trimming characters
- TrimStart method
- removing characters
ms.assetid: ab248dab-70d4-4413-81c6-542d153fd195
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: dac047c7efefcacb959401aedcb96080810f2278
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="trimming-and-removing-characters-from-strings-in-net"></a>Eliminazione di spazi iniziali e finali e rimozione di caratteri dalle stringhe in .NET
Se si sta analizzando una frase in singole parole, è possibile che si ottengano parole con spazi vuoti alle estremità. In questo caso è possibile usare uno dei metodi trim della classe **System.String** per rimuovere un numero qualsiasi di spazi o altri caratteri da una posizione specificata nella stringa. La tabella seguente illustra i metodi trim disponibili.  
  
|Nome metodo|Usa|  
|-----------------|---------|  
|<xref:System.String.Trim%2A?displayProperty=nameWithType>|Rimuove gli spazi vuoti o i caratteri specificati in una matrice di caratteri all'inizio e alla fine di una stringa.|  
|<xref:System.String.TrimEnd%2A?displayProperty=nameWithType>|Rimuove i caratteri specificati in una matrice di caratteri alla fine di una stringa.|  
|<xref:System.String.TrimStart%2A?displayProperty=nameWithType>|Rimuove i caratteri specificati in una matrice di caratteri all'inizio di una stringa.|  
|<xref:System.String.Remove%2A?displayProperty=nameWithType>|Rimuove un numero specificato di caratteri da una posizione di indice specificata in una stringa.|  
  
## <a name="trim"></a>Trim  
 È possibile rimuovere facilmente gli spazi vuoti da entrambe le estremità di una stringa utilizzando il metodo <xref:System.String.Trim%2A?displayProperty=nameWithType>, come illustrato nell'esempio seguente.  
  
 [!code-cpp[Conceptual.String.BasicOps#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#17)]
 [!code-csharp[Conceptual.String.BasicOps#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#17)]
 [!code-vb[Conceptual.String.BasicOps#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#17)]  
  
 È anche possibile rimuovere i caratteri specificati in una matrice di caratteri all'inizio e alla fine di una stringa. Nell'esempio seguente vengono rimossi gli spazi vuoti, i punti e gli asterischi.  
  
 [!code-csharp[Conceptual.String.BasicOps#22](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trim2.cs#22)]
 [!code-vb[Conceptual.String.BasicOps#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trim2.vb#22)]  
  
## <a name="trimend"></a>TrimEnd  
 Il metodo **TrimEnd** rimuove caratteri alla fine di una stringa, creando un nuovo oggetto stringa. Una matrice di caratteri viene passata a questo metodo per specificare i caratteri da rimuovere. L'ordine degli elementi nella matrice di caratteri non influenza l'operazione di rimozione. La rimozione si interrompe quando viene trovato un carattere non specificato nella matrice.  
  
 L'esempio seguente rimuove le ultime lettere di una stringa con il metodo **TrimEnd**. In questo esempio la posizione dei caratteri `'r'` e `'W'` viene invertita per indicare che l'ordine dei caratteri nella matrice non è importante. Si noti che questo codice rimuove l'ultima parola di `MyString` e una parte della prima parola.  
  
 [!code-cpp[Conceptual.String.BasicOps#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#18)]
 [!code-csharp[Conceptual.String.BasicOps#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#18)]
 [!code-vb[Conceptual.String.BasicOps#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#18)]  
  
 Il codice visualizza `He` nella console.  
  
 L'esempio seguente rimuove l'ultima parola di una stringa con il metodo **TrimEnd**. In questo codice la parola `Hello` è seguita da una virgola: dato che la virgola non è specificata nella matrice di caratteri da tagliare, l'operazione di taglio termina in corrispondenza della virgola.  
  
 [!code-cpp[Conceptual.String.BasicOps#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#19)]
 [!code-csharp[Conceptual.String.BasicOps#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#19)]
 [!code-vb[Conceptual.String.BasicOps#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#19)]  
  
 Il codice visualizza `Hello,` nella console.  
  
## <a name="trimstart"></a>TrimStart  
 Il metodo **String.TrimStart** è simile al metodo **String.TrimEnd** ma crea una nuova stringa rimuovendo caratteri dall'inizio di un oggetto stringa esistente. Una matrice di caratteri viene passata al metodo **TrimStart** per specificare i caratteri da rimuovere. Come per il metodo **TrimEnd**, l'ordine degli elementi nella matrice di caratteri non è importante per l'operazione di rimozione. La rimozione si interrompe quando viene trovato un carattere non specificato nella matrice.  
  
 L'esempio seguente rimuove la prima parola di una stringa. In questo esempio la posizione dei caratteri `'l'` e `'H'` viene invertita per indicare che l'ordine dei caratteri nella matrice non è importante.  
  
 [!code-cpp[Conceptual.String.BasicOps#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#20)]
 [!code-csharp[Conceptual.String.BasicOps#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#20)]
 [!code-vb[Conceptual.String.BasicOps#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#20)]  
  
 Il codice visualizza `World!` nella console.  
  
## <a name="remove"></a>Rimuovi  
 Tramite il metodo <xref:System.String.Remove%2A?displayProperty=nameWithType> viene rimosso un numero specificato di caratteri a partire da una posizione specificata in una stringa esistente. Questo metodo presuppone un indice a base zero.  
  
 L'esempio seguente rimuove dieci caratteri da una stringa a partire dalla posizione cinque di un indice a base zero della stringa.  
  
 [!code-cpp[Conceptual.String.BasicOps#21](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#21)]
 [!code-csharp[Conceptual.String.BasicOps#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#21)]
 [!code-vb[Conceptual.String.BasicOps#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#21)]  
  
 È anche possibile rimuovere da una stringa una sottostringa o un carattere specificato chiamando il metodo <xref:System.String.Replace%28System.String%2CSystem.String%29?displayProperty=nameWithType> e specificando, in sostituzione, una stringa vuota (<xref:System.String.Empty?displayProperty=nameWithType>). Nell'esempio seguente vengono rimosse tutte le virgole da una stringa.  
  
 [!code-csharp[Conceptual.String.BasicOps#23](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/replace1.cs#23)]
 [!code-vb[Conceptual.String.BasicOps#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/replace1.vb#23)]  
  
## <a name="see-also"></a>Vedere anche  
 [Operazioni di base su stringhe](../../../docs/standard/base-types/basic-string-operations.md)
