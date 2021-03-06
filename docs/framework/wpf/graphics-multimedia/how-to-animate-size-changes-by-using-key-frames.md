---
title: "Gewusst wie: Animieren von Größenänderungen mithilfe von Keyframes"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9577f9f08fa1d19aa214bda5a1aef997c2cfa2a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a>Gewusst wie: Animieren von Größenänderungen mithilfe von Keyframes
In diesem Beispiel wird das Animieren von Größenänderungen mithilfe von Keyframes veranschaulicht.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> Klasse zum Animieren der <xref:System.Windows.Media.ArcSegment.Size%2A> Eigenschaft ein <xref:System.Windows.Media.ArcSegment>. In dieser Animation werden drei Keyframes folgendermaßen verwendet:  
  
1.  Bei der ersten halben Sekunde der Animation verwendet eine Instanz von der <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> Klasse, um die Größe des Bogens allmählich erhöhen. Lineare Keyframes wie <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> einen smooth linearen Übergang zwischen den Werten zu erstellen.  
  
2.  Am Ende der nächsten halben Sekunde wird eine Instanz von der <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> Klasse, um die Größe des Bogens abrupt zu erhöhen. Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> erstellen Sie einen plötzlichen Sprünge zwischen Werten, d. h., die größenveränderung der plötzlich auftreten und nicht feine.  
  
3.  Über den letzten zwei Sekunden nutzt eine Instanz von der <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> Klasse, um die Größe des Bogens zu erhöhen. Spline-Keyframes wie <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> erstellen Sie einen variablen Übergang zwischen Werten, die von der <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> Eigenschaft. In diesem Beispiel wächst die Größe des Bogens zunächst nur langsam und steigt dann exponentiell zum Ende des Zeitabschnitts.  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für KeyFrame-Animationen](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.ArcSegment.Size%2A>  
 <xref:System.Windows.Media.ArcSegment>  
 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>  
 [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
