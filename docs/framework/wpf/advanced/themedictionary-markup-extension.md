---
title: ThemeDictionary-Markuperweiterung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ThemeDictionaryExtension
- ThemeDictionary
helpviewer_keywords:
- ThemeDictionary markup extension [WPF]
- XAML [WPF], ThemeDictionary markup extension
ms.assetid: aa75e10b-13dd-4989-972d-51bab63a05e2
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 45f878ce89dcf76ae800ade10a0e67f019741f65
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="themedictionary-markup-extension"></a>ThemeDictionary-Markuperweiterung
Bietet Autoren von benutzerdefinierten Steuerelementen oder Anwendungen, die Steuerelemente von Drittanbietern integrieren, eine Möglichkeit, designspezifische Ressourcenverzeichnisse für das Formatieren der Steuerelemente zu verwenden.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xml  
<object property="{ThemeDictionary assemblyUri}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>Verwendung von XAML-Objektelementen  
  
```xml  
<object>  
  <object.property>  
    <ThemeDictionary AssemblyName="assemblyUri"/>  
  <object.property>  
<object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`assemblyUri`|Die [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] der Assembly, die Designinformationen enthält. In der Regel ist dies eine Paket-URI, die auf eine Assembly in dem größeren Paket verweist. Assemblyressourcen und Paket-URIs vereinfachen die Bereitstellung. Weitere Informationen finden Sie unter [Paket-URIs in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md).|  
  
## <a name="remarks"></a>Hinweise  
 Diese Erweiterung ist vorgesehen, um nur einen bestimmten Eigenschaftswert zu füllen: einen Wert für <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>.  
  
 Mithilfe dieser Erweiterung können Sie eine einzelne Assembly angeben, die nur aus Ressourcen besteht und einige Stile enthält, die nur verwendet werden können, wenn das [!INCLUDE[TLA#tla_aero](../../../../includes/tlasharptla-aero-md.md)]-Design auf das System des Benutzers angewendet wird, sowie andere Stile, die nur verwendet werden können, wenn Luna aktiv ist, usw. Durch die Verwendung dieser Erweiterung kann der Inhalt eines steuerelementspezifischen Ressourcenverzeichnisses automatisch ungültig gemacht und erneut geladen werden, sodass er bei Bedarf für ein anderes Design angegeben werden kann.  
  
 Die `assemblyUri` Zeichenfolge (<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> Eigenschaftswert) bildet die Grundlage für eine Benennungskonvention, die angibt, welche Wörterbuch für ein bestimmtes Design gültig. Die <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> Logik für `ThemeDictionary` schließt die Konvention durch Generieren einer [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] , um ein bestimmtes Design Wörterbuch Variant zeigt, wie in einer vorkompilierten Ressourcenassembly enthalten. Diese Konvention und die Designinteraktionen mit allgemeinen Formatierungen von Steuerelementen und Formatierungen auf Seiten-/Anwendungsebene als Konzept werden hier nicht im Detail behandelt. Das grundlegende Szenario für die Verwendung von `ThemeDictionary` ist die Angabe der <xref:System.Windows.ResourceDictionary.Source%2A> Eigenschaft von einer `ResourceDictionary` auf Anwendungsebene deklariert. Wenn Sie einen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für die Assembly über eine `ThemeDictionary`-Erweiterung und nicht direkt als [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] bereitstellen, bietet die Erweiterungslogik eine Ungültigkeitslogik, die bei Änderungen des Systemdesigns gültig wird.  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `ThemeDictionary`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A>-Wert der zugrunde liegenden <xref:System.Windows.ThemeDictionaryExtension>-Erweiterungsklasse zugeordnet.  
  
 `ThemeDictionary` kann auch in der Objektelementsyntax verwendet werden. In diesem Fall geben Sie den Wert der <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> ist eine erforderliche Eigenschaft.  
  
 `ThemeDictionary` kann zudem in einer ausführlichen Attributverwendung verwendet werden, die die <xref:System.Windows.Markup.StaticExtension.Member%2A>-Eigenschaft als Eigenschaft=Wert-Paar angibt:  
  
```xml  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" .../>  
```  
  
 Die ausführliche Verwendung ist häufig hilfreich, wenn für eine Erweiterung mehr als eine Eigenschaft festgelegt werden kann oder wenn bestimmte Eigenschaften optional sind. Da für `ThemeDictionary` nur eine (erforderliche) Eigenschaft festgelegt werden kann, ist diese ausführliche Verwendung unüblich.  
  
 In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -prozessorimplementierung, die Handhabung für diese Markuperweiterung wird definiert, indem die <xref:System.Windows.ThemeDictionaryExtension> Klasse.  
  
 `ThemeDictionary` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [WPF-Anwendungsressource, Inhalts- und Datendateien](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)
