---
title: "Abrufen von Textattributen mithilfe der Benutzeroberflächenautomatisierung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting, text attributes
- UI Automation, getting text attributes
- text attributes, getting
ms.assetid: fdefc6c3-b836-4cfe-8dec-1484bfdc5551
caps.latest.revision: "13"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: c95fbbe2917261e6b8a4a911a7ea5978da00d662
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="obtain-text-attributes-using-ui-automation"></a>Abrufen von Textattributen mithilfe der Benutzeroberflächenautomatisierung
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In diesem Thema wird gezeigt, wie mit [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Textattribute aus einem Textbereich abgerufen werden können. Ein Textbereich kann der aktuellen Position der Einfügemarke (oder der degenerierten Auswahl) in einem Dokument, einer zusammenhängenden Auswahl von Text, einer Reihe nicht zusammenhängender ausgewählter Textstellen oder dem gesamten Text eines Dokuments entsprechen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie <xref:System.Windows.Automation.TextPattern.FontNameAttribute> aus einem Textbereich abgerufen wird.  
  
 [!code-csharp[UIATextPattern_snip#StartTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#starttarget)]
 [!code-vb[UIATextPattern_snip#StartTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#starttarget)]  
[!code-csharp[UIATextPattern_snip#GetTextElement](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#gettextelement)]
[!code-vb[UIATextPattern_snip#GetTextElement](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#gettextelement)]  
[!code-csharp[UIATextPattern_snip#FontName](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#fontname)]
[!code-vb[UIATextPattern_snip#FontName](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#fontname)]  
  
 Das <xref:System.Windows.Automation.TextPattern> -Steuerelementmuster unterstützt zusammen mit der <xref:System.Windows.Automation.Text.TextPatternRange> -Klasse grundlegende Textattribute, Eigenschaften und Methoden. Für steuerelementspezifische Funktionalität, die von <xref:System.Windows.Automation.TextPattern> oder <xref:System.Windows.Automation.Text.TextPatternRange> nicht unterstützt wird, stellt die <xref:System.Windows.Automation.AutomationElement>-Klasse Methoden für einen Benutzeroberflächenautomatisierungs-Client zur Verfügung, um auf das entsprechende systemeigene Objektmodell zuzugreifen.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über TextPattern für Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)  
 [Hinzufügen von Inhalt zu einem Textfeld mithilfe von Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)  
 [Suchen und Hervorheben von Text mit Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)  
 [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [Abrufen von Textattributdetails mithilfe der Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/obtain-mixed-text-attribute-details-using-ui-automation.md)
