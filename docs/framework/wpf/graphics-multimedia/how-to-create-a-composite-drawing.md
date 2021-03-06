---
title: 'Gewusst wie: Erstellen einer zusammengesetzten Zeichnung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7789f9aa94db32d3dc61ccf01ef9ddfe1e777a37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-composite-drawing"></a>Gewusst wie: Erstellen einer zusammengesetzten Zeichnung
Dieses Beispiel zeigt, wie eine <xref:System.Windows.Media.DrawingGroup> komplexe Zeichnungen erstellen, durch die Kombination mehrerer <xref:System.Windows.Media.Drawing> Objekte in einem einzelnen zusammengesetzten Zeichnung.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.DrawingGroup> So erstellen eine zusammengesetzte Zeichnung aus der <xref:System.Windows.Media.GeometryDrawing> und <xref:System.Windows.Media.ImageDrawing> Objekte. In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.  
  
 ![Eine DrawingGroup mit mehreren Zeichnungen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "Graphicsmm_simple")  
Eine zusammengesetzte Zeichnung, die erstellt wird, mithilfe von DrawingGroup  
  
 Beachten Sie den grauen Rahmen, der die Grenzen der Zeichnung dargestellt wird.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Können Sie eine <xref:System.Windows.Media.DrawingGroup> Anwenden einer <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> festlegen, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, oder <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> , Pläne, die es enthält. Da eine <xref:System.Windows.Media.DrawingGroup> ist auch eine <xref:System.Windows.Media.Drawing>, andere <xref:System.Windows.Media.DrawingGroup> Objekte.  
  
 Im folgende Beispiel ähnelt dem vorherigen Beispiel identisch, jedoch zusätzliche verwendet <xref:System.Windows.Media.DrawingGroup> Objekte Bitmapeffekte und einer Deckkraftmaske einiger seiner Zeichnungen angewendet. In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.  
  
 ![Eine DrawingGroup mit mehreren Zeichnungen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-multiple.jpg "Graphicsmm_multiple")  
Zeichnung, Zusammensetzung verfügt über mehrere DrawingGroup-Objekte  
  
 Beachten Sie den grauen Rahmen, der die Grenzen der Zeichnung dargestellt wird.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 Weitere Informationen zu <xref:System.Windows.Media.Drawing> anzuzeigen, [Drawing Objects Overview](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>  
 <xref:System.Windows.Media.DrawingGroup.Transform%2A>  
 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>  
 <xref:System.Windows.Media.DrawingGroup.Opacity%2A>  
 <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>  
 <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>  
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
