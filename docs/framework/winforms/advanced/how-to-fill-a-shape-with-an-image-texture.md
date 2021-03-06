---
title: "Procedura: riempire una forma con una trama basata su un'immagine"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: c1eb090bebcced125193c1db16087b6165d27ff3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a>Procedura: riempire una forma con una trama basata su un'immagine
È possibile riempire una forma chiusa con una trama utilizzando il <xref:System.Drawing.Image> classe e <xref:System.Drawing.TextureBrush> classe.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente inserisce un'ellisse con un'immagine. Nel codice viene creata un <xref:System.Drawing.Image> dell'oggetto e quindi passa l'indirizzo di tale <xref:System.Drawing.Image> oggetto come argomento a un <xref:System.Drawing.TextureBrush.%23ctor%2A> costruttore. La terza istruzione consente di ridimensionare l'immagine e la quarta si riempie l'ellisse con le copie ripetute di immagine ridimensionati.  
  
 Nel codice seguente, la <xref:System.Drawing.TextureBrush.Transform%2A> proprietà contiene la trasformazione applicata all'immagine prima che venga disegnato. Si supponga che l'immagine originale ha una larghezza di 640 pixel e un'altezza di 480 pixel. La trasformazione, l'immagine viene ridotta a 75 × 75 impostando i valori di scalabilità orizzontali e verticali.  
  
> [!NOTE]
>  Nell'esempio seguente, le dimensioni dell'immagine sono 75 × 75, e la dimensione di puntini di sospensione è 150 × 250. Perché l'immagine è minore dell'ellisse da riempire, con l'immagine viene affiancata l'ellisse. Affiancamento che l'immagine viene ripetuta orizzontalmente e verticalmente fino al limite della forma viene raggiunto. Per ulteriori informazioni sull'affiancamento, vedere [procedura: riempire una forma con un'immagine](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).  
  
 [!code-csharp[System.Drawing.UsingABrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di un oggetto Brush per il riempimento di forme](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
