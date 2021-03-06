---
title: 'Gewusst wie: Erstellen einer GeometryDrawing'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7f0fa86a9786e5440db9fec0cee76c5ed28363b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-geometrydrawing"></a>Gewusst wie: Erstellen einer GeometryDrawing
In diesem Beispiel wird gezeigt, wie zum Erstellen und Anzeigen einer <xref:System.Windows.Media.GeometryDrawing>. Ein <xref:System.Windows.Media.GeometryDrawing> ermöglicht es Ihnen, die Form mit einer Füllung und Konturen zu erstellen, durch das Zuordnen einer <xref:System.Windows.Media.Pen> und ein <xref:System.Windows.Media.Brush> mit einer <xref:System.Windows.Media.Geometry>. Die <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> beschreibt die Struktur, die <xref:System.Windows.Media.GeometryDrawing.Brush%2A> beschreibt die Füllung der Form, und die <xref:System.Windows.Media.GeometryDrawing.Pen%2A> beschreibt den Rand der Form.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.GeometryDrawing> eine Form gerendert. Die Form wird beschrieben, indem eine <xref:System.Windows.Media.GeometryGroup> und zwei <xref:System.Windows.Media.EllipseGeometry> Objekte. Das Innere der Form gezeichnet wird, mit einem <xref:System.Windows.Media.LinearGradientBrush> und seine Kontur gezeichnet wird, mit einer <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>. Die <xref:System.Windows.Media.GeometryDrawing> wird angezeigt, mit einem <xref:System.Windows.Media.ImageDrawing> und ein <xref:System.Windows.Controls.Image> Element.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 Die folgende Abbildung zeigt die resultierenden <xref:System.Windows.Media.GeometryDrawing>.  
  
 ![Eine GeometryDrawing von zwei Ellipsen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "Graphicsmm_geodraw")  
  
 Sie können mehrere Zeichnungsobjekte in einem einzigen zusammengesetzten Zeichnung mithilfe von kombinieren, um komplexere Zeichnungen zu erstellen, eine <xref:System.Windows.Media.DrawingGroup>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.DrawingGroup>  
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Übersicht über Geometrien](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Erstellen einer zusammengesetzten Zeichnung](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-drawing.md)
