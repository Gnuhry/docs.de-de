---
title: "Gewusst wie: Bereitstellen einer Toolboxbitmap für ein Steuerelement"
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
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2d1ab49b6596c6feaa2ead5bbb92525f0ddb356d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a>Gewusst wie: Bereitstellen einer Toolboxbitmap für ein Steuerelement
Wenn Sie möchten ein besonderes Symbol für das Steuerelement angezeigt werden, der **Toolbox**, können, geben Sie ein bestimmtes Abbild mithilfe der <xref:System.Drawing.ToolboxBitmapAttribute>. Diese Klasse ist ein *Attribut*, eine besondere Klassenform, die Sie an andere Klassen anfügen können. Weitere Informationen zu Attributen finden Sie unter [NICHT IM BUILD: Übersicht über Attribute in Visual Basic](http://msdn.microsoft.com/en-us/0d0cff64-892d-4f57-83bd-bef388553d4f) für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], und [Attributes (Attribute)](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205) für [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].  
  
 Mithilfe der <xref:System.Drawing.ToolboxBitmapAttribute>, können Sie angeben, eine Zeichenfolge, die den Pfad und den Namen für eine 16 x 16-Pixel-Bitmap angibt. Diese Bitmap wird dann neben dem Steuerelement angezeigt, wenn sie zur **Toolbox** hinzugefügt wird. Sie können auch angeben, ein <xref:System.Type>, in diesem Fall die Bitmap, die diesem Typ zugeordnete geladen wird. Wenn Sie beide angeben einer <xref:System.Type> und eine Zeichenfolge, das Steuerelement für eine Bildressource sucht, mit dem Namen gemäß der Zeichenfolgenparameter in die Assembly mit den vom angegebenen Typ der <xref:System.Type> Parameter.  
  
### <a name="to-specify-a-toolbox-bitmap-for-your-control"></a>So geben sie eine Toolboxbitmap für Ihr Steuerelement an  
  
1.  Hinzufügen der <xref:System.Drawing.ToolboxBitmapAttribute> der Klassendeklaration des Steuerelements vor dem `Class` Schlüsselwort für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], und oberhalb der Klassendeklaration für [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].  
  
    ```vb  
    ' Specifies the bitmap associated with the Button type.  
    <ToolboxBitmap(GetType(Button))> Class MyControl1  
    ' Specifies a bitmap file.  
    End Class  
    <ToolboxBitmap("C:\Documents and Settings\Joe\MyPics\myImage.bmp")> _  
       Class MyControl2  
    End Class  
    ' Specifies a type that indicates the assembly to search, and the name   
    ' of an image resource to look for.  
    <ToolboxBitmap(GetType(MyControl), "MyControlBitmap")> Class MyControl  
    End Class  
    ```  
  
    ```csharp  
    // Specifies the bitmap associated with the Button type.  
    [ToolboxBitmap(typeof(Button))]  
    class MyControl1 : UserControl  
    {  
    }  
    // Specifies a bitmap file.  
    [ToolboxBitmap(@"C:\Documents and Settings\Joe\MyPics\myImage.bmp")]  
    class MyControl2 : UserControl  
    {  
    }  
    // Specifies a type that indicates the assembly to search, and the name   
    // of an image resource to look for.  
    [ToolboxBitmap(typeof(MyControl), "MyControlBitmap")]  
    class MyControl : UserControl  
    {  
    }  
    ```  
  
2.  Erstellen Sie das Projekt neu.  
  
    > [!NOTE]
    >  Die Bitmap wird nicht in der Toolbox für automatisch generierte Steuerelemente und Komponenten angezeigt. Laden Sie das Steuerelement mithilfe des Dialogfelds **Toolboxelemente auswählen** neu, um die Bitmap anzuzeigen. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.ToolboxBitmapAttribute>  
 [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 [Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [Attribute (Visual Basic)](~/docs/visual-basic/language-reference/attributes.md)  
 [Attribute](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205)
