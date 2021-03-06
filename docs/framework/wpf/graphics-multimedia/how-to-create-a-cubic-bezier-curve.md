---
title: 'Procedura: creare una curva di Bezier cubica'
ms.date: 03/30/2017
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
ms.openlocfilehash: 6332129179e1934e5a37c7a1a40ef5f46ab669a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-cubic-bezier-curve"></a>Procedura: creare una curva di Bezier cubica
In questo esempio viene illustrato come creare una curva di Bézier cubica. Per creare una curva di Bézier cubica, utilizzare il <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, e <xref:System.Windows.Media.BezierSegment> classi.  Per visualizzare la geometria risultante, utilizzare un <xref:System.Windows.Shapes.Path> elemento, o usarlo con un <xref:System.Windows.Media.GeometryDrawing> o <xref:System.Windows.Media.DrawingContext>. Negli esempi seguenti, viene disegnata una curva di Bézier cubica da (10, 100) a (300, 100). La curva presenta punti di controllo di (100, 0) e (200, 200).  
  
## <a name="example"></a>Esempio  
 [xaml]  
  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è possibile utilizzare sintassi abbreviata per descrivere un percorso.  
  
 [!code-xaml[GeometrySample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 [xaml]  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è anche possibile disegnare una curva di Bézier cubica con il tag object. L'esempio che segue equivale a quello [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] precedente.  
  
 [!code-xaml[GeometrySample#33](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>Vedere anche  
 [Creare un arco ellittico](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)  
 [Creare un oggetto LineSegment in un oggetto PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-linesegment-in-a-pathgeometry.md)  
 [Creare una curva di Bézier cubica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)  
 [Creare una curva di Bézier quadratica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)
