---
title: Attribute in Windows Forms-Steuerelementen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- attributes [Windows Forms]
- attributes [Windows Forms], data binding properties
- attributes [Windows Forms], control properties
- attributes [Windows Forms], classes
ms.assetid: 2c5640e9-6c6c-49d7-a5e4-a768f6be7853
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 21f39aa1f85e06f1967d278e07731b73dcf7cb10
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="attributes-in-windows-forms-controls"></a>Attribute in Windows Forms-Steuerelementen
Das .NET Framework bietet eine Vielzahl von Attributen, die Sie auf die Member der benutzerdefinierten Steuerelemente und Komponenten anwenden können. Einige dieser Attribute haben Auswirkungen auf das Laufzeitverhalten einer Klasse, während andere Auswirkungen auf das Entwurfszeitverhalten haben.  
  
## <a name="attributes-for-control-and-component-properties"></a>Attribute für Steuerelement- und Komponenteneigenschaften  
 Die folgende Tabelle enthält die Attribute, die Sie auf Eigenschaften oder andere Member der benutzerdefinierten Steuerelemente und Komponenten anwenden können. Ein Beispiel, in dem viele dieser Attribute verwendet werden, finden Sie unter [Vorgehensweise: Anwenden von Attributen auf Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|<xref:System.ComponentModel.AmbientValueAttribute>|Gibt den Wert an, der an eine Eigenschaft übergeben werden soll, damit die Eigenschaft den zugehörigen Wert von einer anderen Quelle abrufen kann. Dies wird als *Umgebung* bezeichnet.|  
|<xref:System.ComponentModel.BrowsableAttribute>|Gibt an, ob eine Eigenschaft oder ein Ereignis im Fenster **Eigenschaften** angezeigt werden soll.|  
|<xref:System.ComponentModel.CategoryAttribute>|Gibt den Namen der Kategorie, in der Gruppe die Eigenschaft oder das Ereignis bei der Anzeige in einem <xref:System.Windows.Forms.PropertyGrid> Steuerelement festgelegt, dass <xref:System.Windows.Forms.PropertySort.Categorized> Modus.|  
|<xref:System.ComponentModel.DefaultValueAttribute>|Gibt den Standardwert für eine Eigenschaft an.|  
|<xref:System.ComponentModel.DescriptionAttribute>|Gibt die Beschreibung einer Eigenschaft oder eines Ereignisses an.|  
|<xref:System.ComponentModel.DisplayNameAttribute>|Gibt den Anzeigenamen für eine Eigenschaft, ein Ereignis oder eine `public``void`-Methode an, die keine Argumente akzeptiert.|  
|<xref:System.ComponentModel.EditorAttribute>|Gibt den Editor an, der zum Ändern einer Eigenschaft verwendet wird.|  
|<xref:System.ComponentModel.EditorBrowsableAttribute>|Gibt an, dass eine Eigenschaft oder Methode in einem Editor angezeigt werden kann.|  
|<xref:System.ComponentModel.Design.HelpKeywordAttribute>|Gibt das Kontextschlüsselwort für eine Klasse oder einen Member an.|  
|<xref:System.ComponentModel.LocalizableAttribute>|Gibt an, ob eine Eigenschaft lokalisiert werden soll.|  
|<xref:System.ComponentModel.PasswordPropertyTextAttribute>|Gibt an, dass die Textdarstellung eines Objekts von Zeichen wie Sternchen verdeckt wird.|  
|<xref:System.ComponentModel.ReadOnlyAttribute>|Gibt an, ob die Eigenschaft, an die dieses Attribut gebunden ist, schreibgeschützt ist oder ob zur Entwurfszeit Lese-/Schreibzugriff gewährt wird.|  
|<xref:System.ComponentModel.RefreshPropertiesAttribute>|Gibt an, dass das Eigenschaftenraster aktualisiert werden sollte, wenn sich der zugehörige Eigenschaftswert ändert.|  
|<xref:System.ComponentModel.TypeConverterAttribute>|Gibt an, welcher Typ als Konverter für das Objekt verwendet werden sollte, an das dieses Attribut gebunden ist.|  
  
## <a name="attributes-for-data-binding-properties"></a>Attribute für Datenbindungseigenschaften  
 In der folgenden Tabelle werden die Attribute angezeigt, die Sie für die Angabe anwenden können, wie Ihre benutzerdefinierten Steuerelemente und Komponenten mit der Datenbindung interagieren.  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|<xref:System.ComponentModel.BindableAttribute>|Gibt an, ob eine Eigenschaft in der Regel für die Bindung verwendet wird.|  
|<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>|Gibt die Eigenschaften der Datenquelle und des Datenmembers für eine Komponente an.|  
|<xref:System.ComponentModel.DefaultBindingPropertyAttribute>|Gibt die Standardbindungseigenschaft für eine Komponente an.|  
|<xref:System.ComponentModel.LookupBindingPropertiesAttribute>|Gibt die Eigenschaften der Datenquelle und des Datenmembers für eine Komponente an.|  
|<xref:System.ComponentModel.AttributeProviderAttribute>|Ermöglicht die Umleitung von Attributen.|  
  
## <a name="attributes-for-classes"></a>Attribute für Klassen  
 In der folgenden Tabelle werden die Attribute angezeigt, die Sie anwenden können, um das Verhalten Ihrer benutzerdefinierten Steuerelemente und Komponenten zur Entwurfszeit anzugeben.  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|<xref:System.ComponentModel.DefaultEventAttribute>|Gibt das Standardereignis für eine Komponente an.|  
|<xref:System.ComponentModel.DefaultPropertyAttribute>|Gibt die Standardeigenschaft für eine Komponente an.|  
|<xref:System.ComponentModel.DesignerAttribute>|Gibt die Klasse an, die zum Implementieren von Entwurfszeitdiensten für eine Komponente verwendet wird.|  
|<xref:System.ComponentModel.DesignerCategoryAttribute>|Gibt an, dass der Designer für eine Klasse zu einer bestimmten Kategorie gehört.|  
|<xref:System.ComponentModel.ToolboxItemAttribute>|Stellt ein Attribut eines Werkzeugkastenelements dar.|  
|<xref:System.ComponentModel.ToolboxItemFilterAttribute>|Gibt die Filterzeichenfolge und den Filtertyp an, die für ein Werkzeugkastenelement verwendet werden sollen.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Attribute>  
 [Vorgehensweise: Anwenden von Attributen auf Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)  
 [Erweitern der Entwurfszeitunterstützung](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)
