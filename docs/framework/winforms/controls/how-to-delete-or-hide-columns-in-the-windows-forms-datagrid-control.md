---
title: "Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], deleting columns
- DataGrid control [Windows Forms], deleting columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
- columns [Windows Forms], deleting in data grids
- DataGrid control [Windows Forms], hiding columns
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1d89f14d034c1050d364282c04424b1326bcff9e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a>Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Programmgesteuert löschen oder Ausblenden von Spalten in Windows Forms <xref:System.Windows.Forms.DataGrid> mithilfe der Eigenschaften und Methoden des Steuerelements die <xref:System.Windows.Forms.GridColumnStylesCollection> und <xref:System.Windows.Forms.DataGridColumnStyle> Objekte (Member der der <xref:System.Windows.Forms.DataGridTableStyle> Klasse).  
  
 Die gelöschten oder ausgeblendeten Spalten sind weiterhin vorhanden, in der Datenquelle, die dem Raster gebunden ist und weiterhin programmgesteuert aufgerufen werden können. Sie sind gerade nicht mehr in das DataGrid-Steuerelement angezeigt.  
  
> [!NOTE]
>  Wenn Ihre Anwendung greift nicht auf bestimmte Spalten der Daten und nicht in das DataGrid-Steuerelement angezeigt werden möchten, ist es wahrscheinlich nicht erforderlich, um ursprünglich in der Datenquelle einzuschließen.  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a>So löschen Sie eine Spalte programmgesteuert aus dem DataGrid  
  
1.  Deklarieren Sie eine neue Instanz der im Deklarationsbereich des Formulars die <xref:System.Windows.Forms.DataGridTableStyle> Klasse.  
  
2.  Legen Sie die <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> Eigenschaft, um die Tabelle in der Datenquelle, die der Stil angewendet werden sollen. Im folgenden Beispiel wird die <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> -Eigenschaft, die es wird vorausgesetzt, ist bereits festgelegt.  
  
3.  Fügen Sie der neuen <xref:System.Windows.Forms.DataGridTableStyle> -Objekt, das Datenraster Tabellenformate der Auflistung.  
  
4.  Rufen Sie die <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> Methode der <xref:System.Windows.Forms.DataGrid>des <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> -Auflistung, den Spaltenindex der zu löschenden Spalte angeben.  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub DeleteColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Delete the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles.RemoveAt(0)  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void deleteColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Delete the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles.RemoveAt(0);  
    }  
    ```  
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a>So blenden Sie eine Spalte in das DataGrid-Steuerelement programmgesteuert aus  
  
1.  Deklarieren Sie eine neue Instanz der im Deklarationsbereich des Formulars die <xref:System.Windows.Forms.DataGridTableStyle> Klasse.  
  
2.  Festlegen der <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> Eigenschaft von der <xref:System.Windows.Forms.DataGridTableStyle> auf die Tabelle in der Datenquelle, die der Stil angewendet werden sollen. Im folgenden Codebeispiel wird mit der <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> -Eigenschaft, die es wird vorausgesetzt, ist bereits festgelegt.  
  
3.  Fügen Sie der neuen <xref:System.Windows.Forms.DataGridTableStyle> -Objekt, das Datenraster Tabellenformate der Auflistung.  
  
4.  Ausblenden der Spalte durch Festlegen seiner `Width` -Eigenschaft auf 0 festlegen des Spaltenindexes der Spalte ausgeblendet.  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub HideColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Hide the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles(0).Width = 0  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void hideColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Hide the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles[0].Width = 0;  
    }  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Ändern der angezeigten Daten im DataGrid-Steuerelement in Windows Forms zur Laufzeit](../../../../docs/framework/winforms/controls/change-displayed-data-at-run-time-wf-datagrid-control.md)  
 [Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
