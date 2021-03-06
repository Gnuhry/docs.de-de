---
title: Erstellen eines "DataViews"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 28a2f6f299d2f904dc3f842c0c778f30081240b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="creating-a-dataview"></a>Erstellen eines "DataViews"
Es gibt zwei Möglichkeiten zum Erstellen einer <xref:System.Data.DataView>: Können Sie die **"DataView"** -Konstruktor verwenden, oder Sie erstellen einen Verweis auf die <xref:System.Data.DataTable.DefaultView%2A> Eigenschaft von der <xref:System.Data.DataTable>. Die **"DataView"** Konstruktor kann leer sein oder akzeptiert entweder eine **DataTable** als ein einzelnes Argument oder eine **DataTable** zusammen mit Filterkriterien, Sortierkriterien und eine Zeile Statusfilter. Weitere Informationen über die zusätzlichen Argumente für die Verwendung mit der **"DataView"**, finden Sie unter [sortieren und Filtern von Daten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
 Da der Index für eine **"DataView"** basiert sowohl bei der **"DataView"** erstellt wurde, und wenn Änderungen an der **sortieren**, **RowFilter**, oder  **RowStateFilter** Eigenschaften geändert werden, Sie optimale Leistung erzielen, indem Angabe alle anfänglichen Sortierreihenfolge- oder Filterkriterien als Konstruktorargumente, bei der Erstellung der **"DataView"**. Erstellen einer **"DataView"** ohne Sortier- oder Filterkriterien angeben sowie das anschließende Festlegen der **sortieren**, **RowFilter**, oder **RowStateFilter** Eigenschaften höher führt dazu, dass den Index mindestens zweimal erstellt werden sollen: Sobald bei der **"DataView"** erstellt wurde, und erneut Wenn eine der Sortier- oder Filtereigenschaften geändert.  
  
 Beachten Sie, dass bei der Erstellung einer **"DataView"** mithilfe des Konstruktors, der keine Argumente akzeptiert, Sie ist nicht möglich, verwenden Sie die **"DataView"** , bis Sie festgelegt haben die **Tabelle** Eigenschaft .  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie zum Erstellen einer **"DataView"** mithilfe der **DataView** Konstruktor. Ein **RowFilter**, **sortieren** Spalte und **"DataViewRowState"** bereitgestellt werden, zusammen mit den **DataTable**.  
  
```vb  
Dim custDV As DataView = New DataView(custDS.Tables("Customers"), _  
    "Country = 'USA'", _  
    "ContactName", _  
    DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView custDV = new DataView(custDS.Tables["Customers"],   
    "Country = 'USA'",   
    "ContactName",   
    DataViewRowState.CurrentRows);  
```  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie einen Verweis auf den Standardwert abgerufen **"DataView"** von einer **DataTable** mithilfe der **DefaultView** -Eigenschaft der Tabelle.  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [Sortieren und Filtern von Daten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
