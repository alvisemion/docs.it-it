---
title: 'Procedura: Enumerare gli archivi per lo spazio di memorizzazione isolato'
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
helpviewer_keywords:
- enumerating stores
- data storage using isolated storage, enumerating stores
- storing data using isolated storage, enumerating stores
- stores, enumerating
- isolated storage, enumerating stores
- data stores, enumerating
ms.assetid: 0fcf279a-f241-48f0-8034-2e3d331f1fcb
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7c4fa63c5c7f966831a55c9103c9ba58cfa621d6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-enumerate-stores-for-isolated-storage"></a>Procedura: Enumerare gli archivi per lo spazio di memorizzazione isolato
È possibile enumerare tutti gli archivi isolati dell'utente corrente utilizzando il metodo statico <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType>. Questo metodo accetta un valore <xref:System.IO.IsolatedStorage.IsolatedStorageScope> e restituisce un enumeratore <xref:System.IO.IsolatedStorage.IsolatedStorageFile>. Per enumerare gli archivi, è necessario avere l'autorizzazione <xref:System.Security.Permissions.IsolatedStorageFilePermission> con il valore <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> specificato. Se si chiama il metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> con il valore <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User>, viene restituita una matrice di oggetti <xref:System.IO.IsolatedStorage.IsolatedStorageFile> definiti per l'utente corrente.  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente ottiene uno spazio di memorizzazione isolato in base all'utente e all'assembly, crea alcuni file e recupera i file usando il metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A>.  
  
 [!code-csharp[Conceptual.IsolatedStorage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source2.cs#2)]
 [!code-vb[Conceptual.IsolatedStorage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [Spazio di memorizzazione isolato](../../../docs/standard/io/isolated-storage.md)
