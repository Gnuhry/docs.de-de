---
title: 'Gewusst wie: Verwenden von Systemfarben in einem Farbverlauf'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 105e22588f68d999811f5482342d53851a4d25eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-system-colors-in-a-gradient"></a>Gewusst wie: Verwenden von Systemfarben in einem Farbverlauf
Um eine Systemfarbe in einem Farbverlauf zu verwenden, verwenden Sie die  *\<SystemColor >*Farbe und  *\<SystemColor >*ColorKey statische Eigenschaften der der <xref:System.Windows.SystemColors> Klasse zum Abrufen einer Verweis auf die Farbe, in denen  *\<SystemColor >* ist der Name des gewünschten Systemfarbe. Verwenden der  *\<SystemColor >*ColorKey-Eigenschaften, wenn Sie einen dynamischen Verweis erstellen, die das System Design ändert automatisch aktualisiert werden sollen. Verwenden Sie andernfalls die  *\<SystemColor >*Color-Eigenschaften.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Farbverlauf mithilfe dynamischer Systemfarbressourcen erstellt.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 Im nächsten Beispiel wird ein Farbverlauf mithilfe statischer Systemfarbressourcen erstellt.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.SystemColors>  
 [Zeichnen eines Bereichs mit einem Systempinsel](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
