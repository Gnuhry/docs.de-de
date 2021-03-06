---
title: 'Gewusst wie: Navigieren durch die Objekte in einer Datenauflistungsansicht'
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
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f20881ed452f1ec78381d17a32b4cc2c77305e0e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a>Gewusst wie: Navigieren durch die Objekte in einer Datenauflistungsansicht
Ansichten können die gleichen Datensammlung unterschiedlich, je nach sortieren, filtern oder gruppieren angezeigt werden. Ansichten auch Geben Sie einen aktuellen Datensatzzeiger Konzept und verschieben den Zeiger zu aktivieren. In diesem Beispiel wird gezeigt, wie das aktuelle Objekt abgerufen sowie zum Navigieren durch die Objekte in einer Datensammlung, die mithilfe der Funktionen der <xref:System.Windows.Data.CollectionView> Klasse.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel `myCollectionView` ist ein <xref:System.Windows.Data.CollectionView> -Objekt, das eine Ansicht für eine gebundene Auflistung ist.  
  
 Im folgenden Beispiel `OnButton` ist ein Ereignishandler für das `Previous` und `Next` Schaltflächen in einer Anwendung, die Schaltflächen sind, mit denen den Benutzer die Datensammlung navigieren können. Beachten Sie, dass die <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> und <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> Eigenschaften Berichten, ob der Zeiger für der aktuelle Datensatz am Anfang und am Ende der Liste daher, die hat <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> und <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> kann je nach Bedarf aufgerufen werden.  
  
 Die <xref:System.Windows.Data.CollectionView.CurrentItem%2A> -Eigenschaft der Ansicht umgewandelte ein `Order` auf das aktuelle Element der Reihenfolge in der Auflistung zurück.  
  
 [!code-csharp[CollectionView#OnButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Sortieren von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [Filtern von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [Sortieren und Gruppieren von Daten mit einer Ansicht in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
