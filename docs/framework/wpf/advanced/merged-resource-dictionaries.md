---
title: "Zusammengeführte Ressourcenwörterbücher"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- merged resource dictionaries [WPF]
- dictionaries [WPF], merged resources
ms.assetid: d159531f-05d4-49fd-b951-c332de51e5bc
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7ce02b772bacf2115a1bb74039fdff30a46fea8b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="merged-resource-dictionaries"></a>Zusammengeführte Ressourcenwörterbücher
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Ressourcen unterstützen eine Funktion für zusammengeführte Ressourcenwörterbücher. Diese Funktion bietet die Möglichkeit, den Ressourcenteil einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung außerhalb der kompilierten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Anwendung zu definieren. Die Ressourcen können dann anwendungsübergreifend freigegeben werden und auch bequemer für die Lokalisierung isoliert werden.  
  
## <a name="introducing-a-merged-resource-dictionary"></a>Einführung in ein zusammengeführtes Ressourcenwörterbuch  
 Verwenden Sie in Markup folgende Syntax, um ein zusammengeführtes Ressourcenwörterbuch in eine Seite einzubinden:  
  
 [!code-xaml[ResourceMergeDictionary#MergedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourceMergeDictionary/CS/default.xaml#mergedxaml)]  
  
 Beachten Sie, dass die <xref:System.Windows.ResourceDictionary> -Element verfügt nicht über ein [X: Key-Anweisung](../../../../docs/framework/xaml-services/x-key-directive.md), was in der Regel für alle Elemente in einer Auflistung Ressource erforderlich ist. Jedoch auf eine andere <xref:System.Windows.ResourceDictionary> verweisen, die innerhalb der <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> Auflistung ist ein Sonderfall, der für dieses Szenario mit zusammengeführten Wörterbuch reserviert. Die <xref:System.Windows.ResourceDictionary> wird ein zusammengeführtes Ressourcenwörterbuch sind kein [X: Key-Anweisung](../../../../docs/framework/xaml-services/x-key-directive.md). In der Regel jeder <xref:System.Windows.ResourceDictionary> innerhalb der <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> Auflistung gibt ein <xref:System.Windows.ResourceDictionary.Source%2A> Attribut. Der Wert der <xref:System.Windows.ResourceDictionary.Source%2A> sollte eine [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] , die aufgelöst wird, um den Speicherort der Ressourcendatei zusammengeführt werden sollen. Das Ziel, [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] muss eine andere [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Datei mit <xref:System.Windows.ResourceDictionary> als Stammelement.  
  
> [!NOTE]
>  Es ist zulässig, Definieren von Ressourcen innerhalb einer <xref:System.Windows.ResourceDictionary> , angegeben wird als ein Wörterbuch mit zusammengeführten entweder als Alternative zur Angabe <xref:System.Windows.ResourceDictionary.Source%2A>, oder zusätzlich zu den Ressourcen, die von der angegebenen Datenquelle enthalten sind. Das ist aber kein übliches Szenario. Das Hauptszenario für zusammengeführte Wörterbücher besteht in der Zusammenführung von Ressourcen aus externen Dateispeicherorten. Wenn Sie Ressourcen in das Markup für eine Seite angeben möchten, sollten Sie in der Regel definieren, diese im Hauptbearbeitungsfenster <xref:System.Windows.ResourceDictionary> und nicht in den zusammengeführten Wörterbüchern.  
  
## <a name="merged-dictionary-behavior"></a>Verhalten von zusammengeführten Wörterbüchern  
 Ressourcen in einem zusammengeführten Wörterbuch belegen einen Speicherort im Ressourcensuchbereich, der sich direkt hinter dem Bereich des Hauptressourcenwörterbuchs befindet, in dem sie zusammengeführt werden. Obwohl ein Ressourcenschlüssel in einem einzelnen Wörterbuch eindeutig sein muss, kann ein Schlüssel in einem Satz von zusammengeführten Wörterbüchern mehrmals vorkommen. In diesem Fall stammt die zurückgegebene Ressource aus dem letzten Wörterbuch sequenziell in der <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> Auflistung. Wenn die <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> Auflistung definiert wurde, im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], dann ist die Reihenfolge der in der Auflistung den zusammengeführten Wörterbüchern die Reihenfolge der Elemente im Markup bereitgestellt. Wenn ein Schlüssel sowohl im primären Wörterbuch als auch in einem zusammengeführten Wörterbuch definiert ist, stammt die zurückgegebene Ressource aus dem primären Wörterbuch. Diese Bereichsregeln gelten gleichermaßen für statische und dynamische Ressourcenverweise.  
  
### <a name="merged-dictionaries-and-code"></a>Zusammengeführte Wörterbücher und Code  
 Einem `Resources`-Wörterbuch können zusammengeführte Wörterbücher durch Code hinzugefügt werden. Der Standardwert, der anfänglich leer <xref:System.Windows.ResourceDictionary> , vorhanden ist, für eine beliebige `Resources` Eigenschaft verfügt auch über den Standardwert, der anfänglich leer <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> Auflistungseigenschaft. Um eine zusammengeführte Wörterbuch über Code hinzuzufügen, erhalten Sie einen Verweis auf das gewünschte primäre <xref:System.Windows.ResourceDictionary>, erhalten ihre <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> Eigenschaftswert, und rufen `Add` für den generischen `Collection` in enthaltenen <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A>. Das Objekt, das Sie hinzufügen, muss ein neues <xref:System.Windows.ResourceDictionary>. Im Code, legen Sie nicht die <xref:System.Windows.ResourceDictionary.Source%2A> Eigenschaft. Sie müssen stattdessen Abrufen einer <xref:System.Windows.ResourceDictionary> Objekt, indem Sie entweder erstellen oder laden. Eine Möglichkeit zum Laden einer vorhandenen <xref:System.Windows.ResourceDictionary> Aufrufen <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> auf einer vorhandenen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Dateidatenstrom, der verfügt über eine <xref:System.Windows.ResourceDictionary> Stamm, klicken Sie dann die Umwandlung der <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> Rückgabewert auf <xref:System.Windows.ResourceDictionary>.  
  
### <a name="merged-resource-dictionary-uris"></a>URIs für zusammengeführte Ressourcenwörterbücher  
 Um ein zusammengeführtes Ressourcenwörterbuch einzubinden, stehen mehrere Techniken zur Verfügung, die von dem von Ihnen verwendeten [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]-Format angegeben werden. Im Allgemeinen können diese Techniken in zwei Kategorien unterteilt werden: Ressourcen, die als Teil des Projekts kompiliert werden und Ressourcen, die nicht als Teil des Projekts kompiliert werden.  
  
 Bei Ressourcen, die als Teil des Projekts kompiliert werden, können Sie den relativen Pfad verwenden, der auf den Speicherort der Ressource verweist. Der relative Pfad wird während der Kompilierung ausgewertet. Die Ressource muss als Ressourcenbuildvorgang als Teil des Projekts definiert werden. Wenn Sie eine Ressourcen-.xaml-Datei im Projekt als Ressource einbinden, müssen Sie die Ressourcendatei nicht in das Ausgabeverzeichnis kopieren. Die Ressource ist bereits in der kompilierten Anwendung enthalten. Der Inhaltsbuildvorgang kann auch verwendet werden. Dann müssen Sie aber die Dateien in das Ausgabeverzeichnis kopieren. Außerdem müssen die Ressourcendateien in derselben Pfadbeziehung für die ausführbare Datei bereitgestellt werden.  
  
> [!NOTE]
>  Verwenden Sie nicht den Eingebettete-Ressource-Buildvorgang. Die Buildaktion selbst wird unterstützt, für die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen, sondern die Auflösung der <xref:System.Windows.ResourceDictionary.Source%2A> wird nicht eingebunden <xref:System.Resources.ResourceManager>, und daher kann nicht aus dem Datenstrom die jeweiligen Ressource zu trennen. Weiterhin können Sie eingebettete Ressource für andere Zwecke, solange Sie eingesetzt <xref:System.Resources.ResourceManager> auf die Ressourcen zugreifen.  
  
 Bei einer ähnlichen Methode wird ein Paket-URI für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Datei verwendet, auf die dann als Quelle verwiesen wird. Ein Paket-URI ermöglicht Verweise auf Komponenten der Assemblys, auf die verwiesen wird, sowie andere Methoden. Weitere Informationen zu Paket-URIs finden Sie unter [WPF-Anwendungsressource, Inhalts- und Datendateien](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).  
  
 Bei Ressourcen, die nicht als Teil des Projekts kompiliert werden, kann der URI zur Laufzeit ausgewertet werden. Sie können einen allgemeinen URI-Transport wie file: oder http: verwenden, um auf die Ressourcendatei zu verweisen. Der Nachteil beim Ansatz mit nicht kompilierten Ressourcen besteht darin, dass für file: zusätzliche Bereitstellungsschritte erforderlich werden und der http:-Zugriff die Internetsicherheitszone voraussetzt.  
  
### <a name="reusing-merged-dictionaries"></a>Wiederverwendung von zusammengeführten Wörterbüchern  
 Zusammengeführte Wörterbücher können wieder verwendet oder für mehrere Anwendungen freigegeben werden, da mit jedem gültigen [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] auf das zusammenzuführende Ressourcenwörterbuch verwiesen werden kann. Der genaue Ablauf dieses Vorgangs hängt von der Bereitstellungsstrategie für Ihre Anwendung und dem verwendeten Anwendungsmodell ab. Die bereits erwähnte Paket-URI-Strategie bietet eine Möglichkeit, mit der Freigabe eines Assemblyverweises während der Entwicklung eine zusammengeführte Ressource für viele Projekte als häufige Quelle zu verwenden. In diesem Szenario werden die Ressourcen weiterhin durch den Client verteilt, und mindestens eine der Anwendungen muss die Assembly bereitstellen, auf die verwiesen wird. Es ist auch möglich, durch einen verteilten URI, der das HTTP-Protokoll verwendet, auf zusammengeführte Ressourcen zu verweisen.  
  
 Das Schreiben zusammengeführter Wörterbücher als lokale Anwendungsdateien ist ein weiteres mögliches Szenario für zusammengeführte Wörterbücher/Anwendungsbereitstellung.  
  
### <a name="localization"></a>Lokalisierung  
 Wenn Ressourcen, die lokalisiert werden müssen, in Wörterbüchern isoliert werden, die in primäre Wörterbücher zusammengeführt und als lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] beibehalten werden, ist eine separate Lokalisierung dieser Dateien möglich. Diese Technik stellt eine einfache Alternative zur Lokalisierung der Satellitenressourcenassemblys dar. Weitere Informationen finden Sie unter [Übersicht über WPF-Globalisierung und -Lokalisierung](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.ResourceDictionary>  
 [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Ressourcen und Code](../../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [WPF-Anwendungsressource, Inhalts- und Datendateien](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)
