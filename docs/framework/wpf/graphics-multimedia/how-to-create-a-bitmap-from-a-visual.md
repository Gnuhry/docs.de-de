---
title: 'Gewusst wie: Erstellen einer Bitmap mit einem visuellen Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [WPF], rendering from visuals
- visuals [WPF], rendering to bitmaps
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7aabb01d35e02323785b6bae0764a8d8bc636e16
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-bitmap-from-a-visual"></a>Gewusst wie: Erstellen einer Bitmap mit einem visuellen Element
Dieses Beispiel zeigt die Erstellung einer Bitmap aus einem <xref:System.Windows.Media.Visual>. Ein <xref:System.Windows.Media.DrawingVisual> wird beim Rendering <xref:System.Windows.Media.FormattedText>. Die <xref:System.Windows.Media.Visual> wird dann gerendert werden, auf die <xref:System.Windows.Media.Imaging.RenderTargetBitmap> Erstellen eines Bitmaps des angegebenen Texts.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.DrawingContext>  
 [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Verwenden von DrawingVisual-Objekten](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
