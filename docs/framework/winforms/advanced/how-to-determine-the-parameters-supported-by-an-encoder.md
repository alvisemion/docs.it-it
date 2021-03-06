---
title: 'Procedura: determinare i parametri supportati da un codificatore'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
ms.openlocfilehash: 7f7c270c4ae590c070103d51f116158869b678c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a>Procedura: determinare i parametri supportati da un codificatore
È possibile modificare i parametri di immagine, ad esempio livello di qualità e la compressione, ma è necessario conoscere quali parametri sono supportati da un codificatore di immagini specificato. Il <xref:System.Drawing.Image> classe fornisce il <xref:System.Drawing.Image.GetEncoderParameterList%2A> metodo in modo che è possibile determinare quali parametri di immagini sono supportate per un codificatore particolare. Specificare il codificatore con un GUID. Il <xref:System.Drawing.Image.GetEncoderParameterList%2A> il metodo restituisce una matrice di <xref:System.Drawing.Imaging.EncoderParameter> oggetti.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente restituisce i parametri supportati per il codificatore JPEG. Utilizzare l'elenco delle categorie di parametro e i GUID associati il <xref:System.Drawing.Imaging.Encoder> Cenni preliminari sulla classe per determinare la categoria per ogni parametro.  
  
 [!code-csharp[UsingImageEncodersDecoders#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Applicazione Windows Forms.  
  
-   Oggetto <xref:System.Windows.Forms.PaintEventArgs>, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Elencare i codificatori installati](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [Tipi di bitmap](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)  
 [Uso di codificatori e decodificatori di immagini nel codice gestito GDI+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
