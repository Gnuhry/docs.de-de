---
title: "Benutzeroberflächenautomatisierung und Microsoft Active Accessibility"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Active Accessibility
- UI Automation, Active Accessibility compared to
- UI Automation, Microsoft Active Accessibility
- Active Accessibility, UI Automation compared to
ms.assetid: 87bee662-0a3e-4232-a421-20e7a5968321
caps.latest.revision: "24"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: dd3adbeebc0cc2a9e201bbe6492eb311f18a711d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ui-automation-and-microsoft-active-accessibility"></a>Benutzeroberflächenautomatisierung und Microsoft Active Accessibility
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)] war die vorherige Lösung zum Ermöglichen des Zugriffs auf Clientanwendungen. [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] ist das neue Zugriffsmodell für [!INCLUDE[TLA#tla_win](../../../includes/tlasharptla-win-md.md)] und richtet sich an die Bedürfnisse von Hilfstechnologieprodukten und automatisierte Testtools. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] bietet gegenüber [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]viele Verbesserungen.  
  
 In diesem Thema werden die wesentlichen Features von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] sowie die Unterschiede dieser Features zu [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]erläutert.  
  
<a name="Programming_Languages_compare"></a>   
## <a name="programming-languages"></a>Programmiersprachen  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] basiert auf der [!INCLUDE[TLA#tla_com](../../../includes/tlasharptla-com-md.md)] mit Unterstützung für duale Schnittstellen und kann daher in C/C++, [!INCLUDE[TLA#tla_vb6](../../../includes/tlasharptla-vb6-md.md)]und Skriptsprachen programmiert werden. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] (einschließlich der clientseitigen Anbieterbibliothek für Standardsteuerelemente) wurde in verwaltetem Code geschrieben und Benutzeroberflächenautomatisierungs-Clientanwendungen werden am einfachsten mit [!INCLUDE[TLA#tla_vcshrp](../../../includes/tlasharptla-vcshrp-md.md)] oder [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]programmiert. Benutzeroberflächenautomatisierungs-Anbieter, die Schnittstellenimplementierungen darstellen, können in verwaltetem Code oder in C/C++ geschrieben werden.  
  
<a name="Support_in_Windows_Presentation_Foundation_"></a>   
## <a name="support-in-windows-presentation-foundation"></a>Unterstützung in der Windows Presentation Foundation  
 [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] ist das neue Modell zum Erstellen von Benutzeroberflächen. [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] -Elemente bieten keine systemeigene Unterstützung für [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. Sie unterstützen jedoch die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], die die überbrückende Unterstützung für [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] -Clients umfasst. Nur speziell für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] geschriebene Clients können die Barrierefreiheitsfeatures von [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]optimal nutzen, z. B. die umfangreiche Unterstützung für Text.  
  
<a name="Servers_and_Clients_compare"></a>   
## <a name="servers-and-clients"></a>Server und Clients  
 In [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]können Server und Clients direkt miteinander kommunizieren, hauptsächlich durch die Implementierung des Servers von `IAccessible`.  
  
 In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]liegt ein Kerndienst zwischen Server (auch als Anbieter bezeichnet) und Client. Der Kerndienst führt Aufrufe an die von Anbietern implementierten Schnittstellen aus und bietet zusätzliche Dienste, z. B. das Generieren eindeutiger Laufzeitbezeichner für Elemente. Clientanwendungen verwenden Bibliotheksfunktionen zum Aufrufen des [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Diensts.  
  
 Benutzeroberflächenautomatisierungs-Anbieter können Informationen zu [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] -Clients bereitstellen, während [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] -Server Informationen zu Clientanwendungen für die Automatisierung der Benutzeroberfläche bereitstellen können. Da [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] jedoch nicht so viele Informationen wie [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]bereitstellt, sind die beiden Modelle nicht vollständig kompatibel.  
  
<a name="UI_Elements_compare"></a>   
## <a name="ui-elements"></a>Benutzeroberflächenelemente  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] stellt [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Elemente entweder als `IAccessible` -Schnittstelle oder als untergeordneten Bezeichner dar. Es ist schwierig, zwei `IAccessible` -Zeiger zu vergleichen, um festzustellen, ob sie auf dasselbe Element verweisen.  
  
 In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]wird jedes Element als <xref:System.Windows.Automation.AutomationElement> -Objekt dargestellt. Der Vergleich erfolgt mithilfe des Gleichheitsoperators oder der <xref:System.Windows.Automation.AutomationElement.Equals%2A> -Methode, die beide die eindeutigen Laufzeitbezeichner der Elemente vergleichen.  
  
<a name="Tree_Views_and_Navigation_compare"></a>   
## <a name="tree-views-and-navigation"></a>Strukturansichten und Navigation  
 Die [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] -Elemente auf dem Bildschirm können als Baumstruktur betrachtet werden, wobei der Desktop den Stamm, die Anwendungsfenster direkt untergeordnete Elemente und Elemente in Anwendungen weitere Nachfolger darstellen.  
  
 In [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]werden viele Automatisierungselemente, die für Endbenutzer nicht relevant sind, in der Struktur verfügbar gemacht. Clientanwendungen müssen alle Elemente betrachten, um die erforderlichen Elemente zu ermitteln.  
  
 Benutzeroberflächenautomatisierungs-Clientanwendungen betrachten die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] über eine gefilterte Ansicht. Die Ansicht enthält nur relevante Elemente: Elemente, die dem Benutzer Informationen bieten oder die Interaktion ermöglichen. Es sind vordefinierte Ansichten verfügbar, die nur Steuerelemente und nur Inhaltselemente enthalten. Zusätzlich können Anwendungen benutzerdefinierte Ansichten definieren. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] vereinfacht die Beschreibung der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] für den Benutzer und unterstützt die Benutzer bei der Interaktion mit der Anwendung.  
  
 Die Navigation zwischen Elementen in [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]erfolgt entweder räumlich (z. B. beim Wechsel zum Element, das auf der linken Seite des Bildschirms liegt), logisch (z. B. beim Wechsel zum nächsten Menüelement oder zum nächsten Element in der Aktivierreihenfolge eines Dialogfelds) oder hierarchisch (z. B. beim Wechsel zum ersten untergeordneten Element in einem Container oder vom untergeordneten zum übergeordneten Element). Die hierarchische Navigation erweist sich durch die Tatsache als kompliziert, dass untergeordnete Elemente nicht immer Objekte sind, die `IAccessible`implementieren.  
  
 In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]sind alle [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Elemente <xref:System.Windows.Automation.AutomationElement> -Objekte, die dieselbe grundlegende Funktionalität unterstützen. (Aus Sicht des Anbieters, sind sie Objekte, die Implementierung einer Schnittstelle geerbt von <xref:System.Windows.Automation.Provider.IRawElementProviderSimple>.) Die Navigation erfolgt überwiegend hierarchisch: von übergeordneten zu untergeordneten Elementen sowie von einem gleichgeordneten Element zum nächsten. (Die Navigation zwischen gleichgeordneten Elementen weist ein logisches Element auf, da sie möglicherweise der Aktivierreihenfolge folgt.) Sie können Navigieren von einem beliebigen Startpunkt, eine beliebige gefilterte Ansicht der Struktur mithilfe der <xref:System.Windows.Automation.TreeWalker> Klasse. Sie können auch mithilfe der <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> und <xref:System.Windows.Automation.AutomationElement.FindAll%2A>zu bestimmten untergeordneten Elementen oder Nachfolgerelementen navigieren. Es ist z. B. ganz einfach, alle Elemente in einem Dialogfeld abzurufen, die ein bestimmtes Steuerelementmuster unterstützen.  
  
 Die Navigation in der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ist konsistenter als bei der [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. Einige Elemente wie Dropdownlisten und Popupfenster werden in der [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] -Struktur zweimal angezeigt und die Navigation von diesen Elementen kann möglicherweise zu unerwarteten Ergebnissen führen. Es ist eigentlich nicht möglich, [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] für ein Grundleistensteuerelement ordnungsgemäß zu implementieren. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ermöglicht die erneute Zuordnung zu übergeordneten Elementen und die Neupositionierung, sodass ein Element ungeachtet der Hierarchie, die sich durch den Besitz von Fenstern ergibt, an eine beliebige Stelle in der Struktur platziert werden kann.  
  
<a name="Roles_and_Control_Types"></a>   
## <a name="roles-and-control-types"></a>Rollen und Steuerelementtypen  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] verwendet die `accRole` -Eigenschaft (`IAccessible::get_actRole`) zum Abrufen einer Beschreibung der Rolle des Elements in der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], z. B. ROLE_SYSTEM_SLIDER oder ROLE_SYSTEM_MENUITEM. Die Rolle eines Elements ist der wichtigste Anhaltspunkt für seine verfügbaren Funktionen. Die Interaktion mit einem Steuerelement wird mithilfe fester Methoden wie `IAccessible::accSelect` und `IAccessible::accDoDefaultAction`erreicht. Die Interaktion zwischen der Clientanwendung und der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] ist durch die Möglichkeiten von `IAccessible`beschränkt.  
  
 Im Gegensatz dazu entkoppelt [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] den Steuerelementtyp des Elements (durch die <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> -Eigenschaft beschrieben) größtenteils von dessen zu erwartender Funktionalität. Die Funktionalität wird durch die Steuerelementmuster bestimmt, die vom Anbieter durch Implementieren spezieller Schnittstellen unterstützt werden. Steuerelementmuster können kombiniert werden, um sämtliche Funktionen zu beschreiben, die von einem bestimmten [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Element unterstützt werden. Einige Anbieter müssen ein bestimmtes Steuerelementmuster unterstützen. Der Anbieter für ein Kontrollkästchen muss z. B. ein Toggle-Steuerelementmuster unterstützen. Andere Anbieter müssen mindestens einen Satz von Steuerelementmustern unterstützen. Eine Schaltfläche muss z. B. entweder „Toggle“ oder „Invoke“ unterstützen. Wieder andere Anbieter unterstützen überhaupt keine Steuerelementmuster. Ein Bereich, der z. B. nicht vergrößert, verkleinert, verschoben oder angedockt werden kann, besitzt keine Steuerelementmuster.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] unterstützt benutzerdefinierte Steuerelemente, die durch die <xref:System.Windows.Automation.ControlType.Custom> -Eigenschaft gekennzeichnet sind und von der <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty> -Eigenschaft beschrieben werden können.  
  
 Die folgende Tabelle veranschaulicht die Zuordnung von [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] -Rollen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Steuerelementtypen.  
  
|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] -Rolle|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Steuerelementtyp|  
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------|  
|ROLE_SYSTEM_PUSHBUTTON|Schaltfläche|  
|ROLE_SYSTEM_CLIENT|Kalender|  
|ROLE_SYSTEM_CHECKBUTTON|Kontrollkästchen|  
|ROLE_SYSTEM_COMBOBOX|Kombinationsfeld|  
|ROLE_SYSTEM_CLIENT|Benutzerdefiniert|  
|ROLE_SYSTEM_LIST|Datenraster|  
|ROLE_SYSTEM_LISTITEM|Datenelement|  
|ROLE_SYSTEM_DOCUMENT|Dokument|  
|ROLE_SYSTEM_TEXT|Bearbeiten|  
|ROLE_SYSTEM_GROUPING|Gruppieren|  
|ROLE_SYSTEM_LIST|Header|  
|ROLE_SYSTEM_COLUMNHEADER|Headerelement|  
|ROLE_SYSTEM_LINK|Link|  
|ROLE_SYSTEM_GRAPHIC|Bild|  
|ROLE_SYSTEM_LIST|Liste|  
|ROLE_SYSTEM_LISTITEM|Listenelement|  
|ROLE_SYSTEM_MENUPOPUP|Menü|  
|ROLE_SYSTEM_MENUBAR|Menüleiste|  
|ROLE_SYSTEM_MENUITEM|Menüelement|  
|ROLE_SYSTEM_PANE|Bereich|  
|ROLE_SYSTEM_PROGRESSBAR|Statusanzeige|  
|ROLE_SYSTEM_RADIOBUTTON|Optionsfeld|  
|ROLE_SYSTEM_SCROLLBAR|Bildlaufleiste|  
|ROLE_SYSTEM_SEPARATOR|Trennzeichen|  
|ROLE_SYSTEM_SLIDER|Slider|  
|ROLE_SYSTEM_SPINBUTTON|Spinner|  
|ROLE_SYSTEM_SPLITBUTTON|Trennschaltfläche|  
|ROLE_SYSTEM_STATUSBAR|Statusleiste|  
|ROLE_SYSTEM_PAGETABLIST|Registerkarte|  
|ROLE_SYSTEM_PAGETAB|Registerkartenelement|  
|ROLE_SYSTEM_TABLE|Tabelle|  
|ROLE_SYSTEM_STATICTEXT|Text|  
|ROLE_SYSTEM_INDICATOR|Ziehpunkt|  
|ROLE_SYSTEM_TITLEBAR|Titelleiste|  
|ROLE_SYSTEM_TOOLBAR|Symbolleiste|  
|ROLE_SYSTEM_TOOLTIP|QuickInfo|  
|ROLE_SYSTEM_OUTLINE|Struktur|  
|ROLE_SYSTEM_OUTLINEITEM|Strukturelement|  
|ROLE_SYSTEM_WINDOW|Fenster|  
  
 Weitere Informationen zu den verschiedenen Steuerelementtypen finden Sie unter [UI Automation Control Types](../../../docs/framework/ui-automation/ui-automation-control-types.md).  
  
<a name="States_and_Properties"></a>   
## <a name="states-and-properties"></a>Zustände und Eigenschaften  
 In [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]unterstützen Elemente einen gemeinsamen Satz von Eigenschaften und einige dieser Eigenschaften (z. B. `accState`) müssen in Abhängigkeit von der Rolle des Elements sehr unterschiedliche Dinge beschreiben. Server müssen alle Methoden von `IAccessible` implementieren, die eine Eigenschaft zurückgeben, auch solche Methoden, die für das Element nicht relevant sind.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definiert viele weitere Eigenschaften, von denen einige den Zuständen in [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]entsprechen. Manche beziehen sich auf alle Elemente, während andere nur für Steuerelementtypen und Steuerelementmuster gelten. Eigenschaften werden durch eindeutige Bezeichner unterschieden, und die meisten Eigenschaften können über eine einzelne Methode, <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> oder <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, abgerufen werden. Viele Eigenschaften können auch leicht über die <xref:System.Windows.Automation.AutomationElement.Current%2A> - und <xref:System.Windows.Automation.AutomationElement.Cached%2A> - Eigenschaftenaccessoren abgerufen werden.  
  
 Ein Benutzeroberflächenautomatisierungs-Anbieter muss keine irrelevanten Eigenschaften implementieren, sondern kann einfach einen `null` -Wert für alle nicht unterstützten Eigenschaften zurückgeben. Darüber hinaus kann der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Kerndienst einige Eigenschaften aus dem Standardfenster abrufen. Diese werden dann mit Eigenschaften vereinigt, die vom Anbieter explizit implementiert wurden.  
  
 Zusätzlich zur Unterstützung vieler weiterer Eigenschaften bietet [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] bessere Leistungen, indem es ermöglicht wird, mehrere Eigenschaften mit einem einzigen prozessübergreifenden Aufruf abzurufen.  
  
 Die folgende Tabelle zeigt die Übereinstimmung zwischen Eigenschaften der beiden Modelle.  
  
|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] -Eigenschaftenaccessor|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaften-ID|Hinweise|  
|-----------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|-------------|  
|`get_accKeyboardShortcut`|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty> oder <xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|`AccessKeyProperty` hat Vorrang, wenn beide vorhanden sind.|  
|`get_accName`|<xref:System.Windows.Automation.AutomationElement.NameProperty>||  
|`get_accRole`|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|Informationen zur Zuordnung von Rollen zu Steuerelementtypen finden Sie in der vorherigen Tabelle.|  
|`get_accValue`|<xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=nameWithType>|Dies gilt nur für Steuerelementtypen, die „ValuePattern“ oder „RangeValuePattern“ unterstützen. RangeValue-Werte werden auf Werte zwischen 0 und 100 normalisiert, um dem MSAA-Verhalten zu entsprechen. Value-Elemente verwenden eine Zeichenfolge.|  
|`get_accHelp`|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>||  
|`accLocation`|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>||  
|`get_accDescription`|Nicht unterstützt in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Die`accDescription` hatte in MSAA keine eindeutige Spezifikation, was dazu geführt hat, dass Anbieter unterschiedliche Arten von Informationen in dieser Eigenschaft platziert haben.|  
|`get_accHelpTopic`|Nicht unterstützt in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]||  
  
 Die folgende Tabelle zeigt, welche [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaften den [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] -Zustandskonstanten entsprechen.  
  
|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] -Zustand|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaft|Löst Zustandsänderung aus?|  
|-----------------------------------------------------------------------|------------------------------------------------------------------------------------|----------------------------|  
|STATE_SYSTEM_CHECKED|Für Kontrollkästchen ist dies <xref:System.Windows.Automation.TogglePattern.ToggleStateProperty><br /><br /> Für Optionsfelder ist dies <xref:System.Windows.Automation.SelectionItemPattern.IsSelectedProperty>|J|  
|STATE_SYSTEM_COLLAPSED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> = <xref:System.Windows.Automation.ExpandCollapseState.Collapsed>|J|  
|STATE_SYSTEM_EXPANDED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> = <xref:System.Windows.Automation.ExpandCollapseState.Expanded> oder <xref:System.Windows.Automation.ExpandCollapseState.PartiallyExpanded>|J|  
|STATE_SYSTEM_FOCUSABLE|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|N|  
|STATE_SYSTEM_FOCUSED|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|N|  
|STATE_SYSTEM_HASPOPUP|<xref:System.Windows.Automation.ExpandCollapsePattern> für Menüelemente|N|  
|STATE_SYSTEM_INVISIBLE|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty> = True und <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A> führt zu <xref:System.Windows.Automation.NoClickablePointException>|N|  
|STATE_SYSTEM_LINKED|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> =<br /><br /> <xref:System.Windows.Automation.ControlType.Hyperlink>|N|  
|STATE_SYSTEM_MIXED|<xref:System.Windows.Automation.TogglePattern.TogglePatternInformation.ToggleState%2A> = <xref:System.Windows.Automation.ToggleState.Indeterminate>|N|  
|STATE_SYSTEM_MOVEABLE|<xref:System.Windows.Automation.TransformPattern.CanMoveProperty>|N|  
|STATE_SYSTEM_MUTLISELECTABLE|<xref:System.Windows.Automation.SelectionPattern.CanSelectMultipleProperty>|N|  
|STATE_SYSTEM_OFFSCREEN|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty> = True|N|  
|STATE_SYSTEM_PROTECTED|<xref:System.Windows.Automation.AutomationElement.IsPasswordProperty>|N|  
|STATE_SYSTEM_READONLY|<xref:System.Windows.Automation.RangeValuePattern.IsReadOnlyProperty?displayProperty=nameWithType> und <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty?displayProperty=nameWithType>|N|  
|STATE_SYSTEM_SELECTABLE|<xref:System.Windows.Automation.SelectionItemPattern> wird unterstützt|N|  
|STATE_SYSTEM_SELECTED|<xref:System.Windows.Automation.SelectionItemPattern.IsSelectedProperty>|N|  
|STATE_SYSTEM_SIZEABLE|<xref:System.Windows.Automation.TransformPattern.TransformPatternInformation.CanResize%2A>|N|  
|STATE_SYSTEM_UNAVAILABLE|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|J|  
  
 Die folgenden Zustände wurden entweder von den meisten [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] -Steuerelementservern nicht implementiert oder verfügen in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]über keine Entsprechung.  
  
|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] -Zustand|Hinweise|  
|-----------------------------------------------------------------------|-------------|  
|STATE_SYSTEM_BUSY|Nicht verfügbar in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_DEFAULT|Nicht verfügbar in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_ANIMATED|Nicht verfügbar in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_EXTSELECTABLE|Von [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] -Servern nicht umfassend implementiert|  
|STATE_SYSTEM_MARQUEED|Von [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] -Servern nicht umfassend implementiert|  
|STATE_SYSTEM_SELFVOICING|Von [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] -Servern nicht umfassend implementiert|  
|STATE_SYSTEM_TRAVERSED|Nicht verfügbar in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_ALERT_HIGH|Von [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] -Servern nicht umfassend implementiert|  
|STATE_SYSTEM_ALERT_MEDIUM|Von [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] -Servern nicht umfassend implementiert|  
|STATE_SYSTEM_ALERT_LOW|Von [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] -Servern nicht umfassend implementiert|  
|STATE_SYSTEM_FLOATING|Von [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] -Servern nicht umfassend implementiert|  
|STATE_SYSTEM_HOTTRACKED|Nicht verfügbar in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_PRESSED|Nicht verfügbar in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
  
 Eine vollständige Liste von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaftenbezeichnern finden Sie unter [UI Automation Properties Overview](../../../docs/framework/ui-automation/ui-automation-properties-overview.md).  
  
<a name="uiautomation_events_compare"></a>   
## <a name="events"></a>Ereignisse  
 Der Ereignismechanismus in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]beruht im Gegensatz zum Mechanismus in [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]nicht auf dem Windows-Ereignisrouting (das eng mit Fensterhandles verbunden ist) und erfordert von der Clientanwendung keine Einrichtung von Hooks. Abonnements von Ereignissen können nicht nur auf bestimmte Ereignisse, sondern auch auf bestimmte Teile der Struktur abgestimmt werden. Anbieter können zudem das Auslösen von Ereignissen optimieren, indem sie verfolgen, wofür Ereignisse aufgeführt werden.  
  
 Es ist für Clients außerdem einfacher, die Elemente abzurufen, die Ereignisse auslösen, da diese direkt an den Ereignisrückruf übergeben werden. Eigenschaften des Elements werden automatisch vorab abgerufen, wenn eine Cacheanforderung aktiv gewesen ist, als der Client das Ereignis abonniert hat.  
  
 In der folgende Tabelle wird die Übereinstimmung von [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] -WinEvents und [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignissen veranschaulicht.  
  
|WinEvent|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignisbezeichner|  
|--------------|--------------------------------------------------------------------------------------------|  
|EVENT_OBJECT_ACCELERATORCHANGE|<xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty> -Eigenschaftenänderung|  
|EVENT_OBJECT_CONTENTSCROLLED|<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> oder eine <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty> -Eigenschaftenänderung für die entsprechenden Bildlaufleisten|  
|EVENT_OBJECT_CREATE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_DEFACTIONCHANGE|Keine Entsprechung|  
|EVENT_OBJECT_DESCRIPTIONCHANGE|Keine genaue Entsprechung, vielleicht <xref:System.Windows.Automation.AutomationElement.HelpTextProperty> oder die <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty> -Eigenschaftenänderung|  
|EVENT_OBJECT_DESTROY|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_FOCUS|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|  
|EVENT_OBJECT_HELPCHANGE|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty> -Änderung|  
|EVENT_OBJECT_HIDE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_LOCATIONCHANGE|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> -Eigenschaftenänderung|  
|EVENT_OBJECT_NAMECHANGE|<xref:System.Windows.Automation.AutomationElement.NameProperty> -Eigenschaftenänderung|  
|EVENT_OBJECT_PARENTCHANGE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_REORDER|Nicht einheitlich verwendet in [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]ist kein direkt entsprechendes Ereignis definiert.|  
|EVENT_OBJECT_SELECTION|<xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>|  
|EVENT_OBJECT_SELECTIONADD|<xref:System.Windows.Automation.SelectionItemPattern.ElementAddedToSelectionEvent>|  
|EVENT_OBJECT_SELECTIONREMOVE|<xref:System.Windows.Automation.SelectionItemPattern.ElementRemovedFromSelectionEvent>|  
|EVENT_OBJECT_SELECTIONWITHIN|Keine Entsprechung|  
|EVENT_OBJECT_SHOW|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_STATECHANGE|Verschiedene durch geänderte Eigenschaften ausgelöste Ereignisse|  
|EVENT_OBJECT_VALUECHANGE|<xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=nameWithType>und <xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=nameWithType> geändert|  
|EVENT_SYSTEM_ALERT|Keine Entsprechung|  
|EVENT_SYSTEM_CAPTUREEND|Keine Entsprechung|  
|EVENT_SYSTEM_CAPTURESTART|Keine Entsprechung|  
|EVENT_SYSTEM_CONTEXTHELPEND|Keine Entsprechung|  
|EVENT_SYSTEM_CONTEXTHELPSTART|Keine Entsprechung|  
|EVENT_SYSTEM_DIALOGEND|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|  
|EVENT_SYSTEM_DIALOGSTART|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|  
|EVENT_SYSTEM_DRAGDROPEND|Keine Entsprechung|  
|EVENT_SYSTEM_DRAGDROPSTART|Keine Entsprechung|  
|EVENT_SYSTEM_FOREGROUND|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|  
|EVENT_SYSTEM_MENUEND|<xref:System.Windows.Automation.AutomationElement.MenuClosedEvent>|  
|EVENT_SYSTEM_MENUPOPUPEND|<xref:System.Windows.Automation.AutomationElement.MenuClosedEvent>|  
|EVENT_SYSTEM_MENUPOPUPSTART|<xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent>|  
|EVENT_SYSTEM_MENUSTART|<xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent>|  
|EVENT_SYSTEM_MINIMIZEEND|<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty> -Eigenschaftenänderung|  
|EVENT_SYSTEM_MINIMIZESTART|<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty> -Eigenschaftenänderung|  
|EVENT_SYSTEM_MOVESIZEEND|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> -Eigenschaftenänderung|  
|EVENT_SYSTEM_MOVESIZESTART|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> -Eigenschaftenänderung|  
|EVENT_SYSTEM_SCROLLINGEND|<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> oder <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty> -Eigenschaftenänderung|  
|EVENT_SYSTEM_SCROLLINGSTART|<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> oder <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty> -Eigenschaftenänderung|  
|EVENT_SYSTEM_SOUND|Keine Entsprechung|  
|EVENT_SYSTEM_SWITCHEND|Keine Entsprechung, aber ein <xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent> -Ereignis signalisiert, dass eine neue Anwendung den Fokus erhalten hat|  
|EVENT_SYSTEM_SWITCHSTART|Keine Entsprechung|  
|Keine Entsprechung|<xref:System.Windows.Automation.MultipleViewPattern.CurrentViewProperty> -Eigenschaftenänderung|  
|Keine Entsprechung|<xref:System.Windows.Automation.ScrollPattern.HorizontallyScrollableProperty> -Eigenschaftenänderung|  
|Keine Entsprechung|<xref:System.Windows.Automation.ScrollPattern.VerticallyScrollableProperty> -Eigenschaftenänderung|  
|Keine Entsprechung|<xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty> -Eigenschaftenänderung|  
|Keine Entsprechung|<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> -Eigenschaftenänderung|  
|Keine Entsprechung|<xref:System.Windows.Automation.ScrollPattern.HorizontalViewSizeProperty> -Eigenschaftenänderung|  
|Keine Entsprechung|<xref:System.Windows.Automation.ScrollPattern.VerticalViewSizeProperty> -Eigenschaftenänderung|  
|Keine Entsprechung|<xref:System.Windows.Automation.TogglePattern.ToggleStateProperty> -Eigenschaftenänderung|  
|Keine Entsprechung|<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty> -Eigenschaftenänderung|  
|Keine Entsprechung|<xref:System.Windows.Automation.AutomationElement.AsyncContentLoadedEvent> -Ereignis|  
|Keine Entsprechung|<xref:System.Windows.Automation.AutomationElement.ToolTipOpenedEvent>|  
  
<a name="Security_compare"></a>   
## <a name="security"></a>Sicherheit  
 Einige `IAccessible` -Anpassungsszenarien erfordern das Umschließen eines grundlegenden `IAccessible` und den Aufruf über dieses. Dadurch ergeben sich Sicherheitsrisiken, da eine teilweise vertrauenswürdige Komponente kein Zwischenelement eines Codepfads darstellen sollte.  
  
 Das [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Modell beseitigt die Notwendigkeit, dass Anbieter anderen Anbietercode aufrufen müssen. Der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Kerndienst führt alle erforderlichen Aggregationen aus.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen der Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/index.md)
