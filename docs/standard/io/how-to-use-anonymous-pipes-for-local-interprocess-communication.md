---
title: 'Procedura: utilizzare le unnamed pipe per la comunicazione interprocesso locale'
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
- anonymous pipes [.NET Framework]
- parent-child communication [.NET Framework]
- pipes [.NET Framework]
- one-way communication [.NET Framework]
- local computer communication [.NET Framework], pipes
ms.assetid: e7773c77-c646-4a01-8a96-a003d59fc4c9
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0679e09a52fab68d8da83863afde1568794ba561
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-use-anonymous-pipes-for-local-interprocess-communication"></a>Procedura: utilizzare le unnamed pipe per la comunicazione interprocesso locale
Le unnamed pipe consentono la comunicazione interprocesso in un computer locale. Offrono meno funzionalità rispetto alle named pipe, ma richiedono anche meno overhead. È possibile usare le unnamed pipe per semplificare la comunicazione interprocesso in un computer locale. Non è possibile usare le unnamed pipe per la comunicazione in rete.  
  
 Per implementare le pipe anonime, utilizzare le classi <xref:System.IO.Pipes.AnonymousPipeServerStream> e <xref:System.IO.Pipes.AnonymousPipeClientStream>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come inviare una stringa da un processo padre a un processo figlio usando unnamed pipe. Questo esempio crea un oggetto <xref:System.IO.Pipes.AnonymousPipeServerStream> in un processo padre con un valore di <xref:System.IO.Pipes.PipeDirection> equivalente a <xref:System.IO.Pipes.PipeDirection.Out>. Il processo padre crea quindi un processo figlio usando un handle client per creare un oggetto <xref:System.IO.Pipes.AnonymousPipeClientStream>. Il processo figlio ha un valore di <xref:System.IO.Pipes.PipeDirection> equivalente a <xref:System.IO.Pipes.PipeDirection.In>.  
  
 Il processo padre invia quindi una stringa fornita dall'utente al processo figlio. La stringa viene visualizzata nella console del processo figlio.  
  
 L'esempio seguente mostra il processo server.  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/vb/program.vb#01)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra il processo client. Il processo server avvia il processo client e fornisce al processo un handle client. Il file eseguibile risultante dal codice client deve essere denominato `pipeClient.exe` e copiato nella stessa directory del file eseguibile server prima di eseguire il processo server.  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/vb/program.vb#01)]  
  
## <a name="see-also"></a>Vedere anche  
 [Pipe](../../../docs/standard/io/pipe-operations.md)  
 [Procedura: Usare le named pipe per la comunicazione interprocesso in rete](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
