---
title: "Implementieren des Table-Steuerelementmusters der Benutzeroberflächenautomatisierung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, Table control pattern
- control patterns, Table
- TableControl pattern
ms.assetid: 880cd85c-aa8c-4fb5-9369-45491d34bb78
caps.latest.revision: "19"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 4a1fbe175abf07eaccfd177c6e32f5515e88c4ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-ui-automation-table-control-pattern"></a>Implementieren des Table-Steuerelementmusters der Benutzeroberflächenautomatisierung
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.ITableProvider>, einschließlich Informationen über Eigenschaften, Methoden und Ereignissen. Links zu zusätzlichen Referenzen sind am Ende dieser Übersicht aufgelistet.  
  
 Die <xref:System.Windows.Automation.TablePattern> -Steuerelementmuster dient zur Unterstützung von Steuerelementen, die als Container für eine Auflistung von untergeordneten Elementen dienen. Die untergeordneten Elemente dieses Elements müssen implementieren <xref:System.Windows.Automation.Provider.ITableItemProvider> und organisiert werden, in einem zweidimensionalen logischen Koordinatensystem Zeilen-und spaltenweise durchlaufen werden kann. Dieses Steuerelementmuster ist analog zu <xref:System.Windows.Automation.Provider.IGridProvider>, mit dem Unterschied, dass jedes implementieren Steuerelement <xref:System.Windows.Automation.Provider.ITableProvider> Spalten- und/oder Header, um eine Beziehung für jedes untergeordnete Element muss auch verfügbar machen. Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Implementierungsrichtlinien und -konventionen  
 Beachten Sie beim Implementieren des Table-Steuerelementmusters die folgenden Richtlinien und Konventionen:  
  
-   Zugriff auf den Inhalt der einzelnen Zellen erfolgt über einem zweidimensionalen logischen Koordinatensystem oder einer Matrix, die von der erforderlichen gleichzeitigen Implementierung von bereitgestellten <xref:System.Windows.Automation.Provider.IGridProvider>.  
  
-   Eine Spalten- oder Zeilenüberschrift kann in einem Tabellenobjekt enthalten sein oder ein separates Headerobjekt darstellen, das einem Tabellenobjekt zugeordnet ist.  
  
-   Spalten- und Zeilenüberschriften können sowohl eine primäre als auch beliebige unterstützende Überschriften enthalten.  
  
> [!NOTE]
>  Dieses Konzept wird offensichtlich in einem [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] Kalkulationstabelle, in dem ein Benutzer eine Spalte "Vorname" definiert wurde. Diese Spalte verfügt jetzt über zwei Überschriften. Die vom Benutzer definierte Überschrift „Vorname“ und die alphanumerische Bezeichnung der Spalte, die von der Anwendung zugewiesen wird.  
  
-   Finden Sie unter [implementieren das Grid-Steuerelementmusters der Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md) für Funktionen des zugehörigen Rasters.  
  
 ![Tabelle mit komplexen Headerelementen. ] (../../../docs/framework/ui-automation/media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")  
Beispiel für eine Tabelle mit komplexen Spaltenüberschriften  
  
 ![Tabelle mit mehrdeutiger RowOrColumnMajor-Eigenschaft. ] (../../../docs/framework/ui-automation/media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")  
Beispiel für eine Tabelle mit mehrdeutiger RowOrColumnMajor-Eigenschaft  
  
<a name="Required_Members_for_ITableProvider"></a>   
## <a name="required-members-for-itableprovider"></a>Erforderliche Member für ITableProvider  
 Für die ITableProvider-Schnittstelle werden die folgenden Eigenschaften und Methoden benötigt.  
  
|Erforderliche Member|Memberart|Notizen|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableProvider.RowOrColumnMajor%2A>|Eigenschaft|Keine|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetColumnHeaders%2A>|Methode|Keine|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetRowHeaders%2A>|Methode|Keine|  
  
 Diesem Steuerelementmuster sind keine Ereignisse zugeordnet.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Ausnahmen  
 Diesem Steuerelementmuster sind keine Ausnahmen zugeordnet.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [Implementieren des TableItem-Steuerelementmusters der Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/implementing-the-ui-automation-tableitem-control-pattern.md)  
 [Implementieren das Grid-Steuerelementmusters der Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)  
 [Übersicht über die Benutzeroberflächenautomatisierungs-Struktur](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [Verwenden der Zwischenspeicherung in der UI-Automatisierung](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
