---
title: "Gewusst wie: Hinzufügen eines Besitzertyps für eine Abhängigkeitseigenschaft"
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
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 079f08e1c330b710748ea6bb1aab8ccfb7ae7016
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a>Gewusst wie: Hinzufügen eines Besitzertyps für eine Abhängigkeitseigenschaft
Dieses Beispiel zeigt, wie eine Klasse als Besitzer einer Abhängigkeitseigenschaft für einen anderen Typ registriert hinzugefügt wird. Durch diese Vorgehensweise wird die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Reader und Eigenschaftensystem werden sowohl die Klasse als weiteren Besitzer der Eigenschaft erkennen zu können. Durch das optional als Besitzer hinzufügen, kann die hinzufügenden Klasse um typspezifische Metadaten bereitzustellen.  
  
 Im folgenden Beispiel `StateProperty` eine Eigenschaft wird registriert werden, indem die `MyStateControl` Klasse. Die Klasse `UnrelatedStateControl` fügt sich selbst als Besitzer der `StateProperty` mithilfe der <xref:System.Windows.DependencyProperty.AddOwner%2A> Methode unter Verwendung speziell die Signatur, die neue Metadaten für die Abhängigkeitseigenschaft ermöglicht, wie sie auf der hinzufügen-Typ vorhanden ist. Beachten Sie, die Sie bereitstellen sollten [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Accessoren für die Eigenschaft, die ähnlich wie das Beispiel in der [Implementieren einer Abhängigkeitseigenschaft](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) , sowie die Bezeichner der Abhängigkeitseigenschaft für die Klasse, die hinzugefügt wird, erneut verfügbar machen als Besitzer.  
  
 Ohne Wrapper die Abhängigkeitseigenschaft funktioniert trotzdem aus der Perspektive des programmgesteuerten Zugriffs mit <xref:System.Windows.DependencyObject.GetValue%2A> oder <xref:System.Windows.DependencyObject.SetValue%2A>. In der Regel parallel dieses Eigenschaftensystem Verhalten mit möchten jedoch die [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Eigenschaftenwrapper. Der Wrapper erleichtern die Abhängigkeitseigenschaft programmgesteuert festgelegt und können sie zum Festlegen der Eigenschaften als [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Attribute.  
  
 Um herauszufinden, wie die standardmäßigen Metadaten überschrieben, finden Sie unter [Überschreiben von Metadaten für eine Abhängigkeitseigenschaft](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
