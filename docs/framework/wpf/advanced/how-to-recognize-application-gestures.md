---
title: 'Gewusst wie: Erkennen von Bewegungen in Anwendungen'
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
- application gestures [WPF], recognizing
- gestures [WPF], recognizing
ms.assetid: d58b740f-5192-4a3e-af59-7aa162e6ca15
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 24d9e4435362f5f87185d04f911caf76517a0de9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-recognize-application-gestures"></a>Gewusst wie: Erkennen von Bewegungen in Anwendungen
Im folgenden Beispiel wird veranschaulicht, wie Freihandeingaben gelöscht, wenn ein Benutzer sendet eine <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> Gestenhandler auf einem <xref:System.Windows.Controls.InkCanvas>. In diesem Beispiel geht davon aus einer <xref:System.Windows.Controls.InkCanvas>namens `inkCanvas1`, der in der XAML-Datei deklariert ist.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[HowToRecognizeGestures#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRecognizeGestures/CSharp/Window1.xaml.cs#1)]
 [!code-vb[HowToRecognizeGestures#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToRecognizeGestures/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Ink.ApplicationGesture>  
 <xref:System.Windows.Controls.InkCanvas>  
 <xref:System.Windows.Controls.InkCanvas.Gesture>
