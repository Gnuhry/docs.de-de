---
title: 'Gewusst wie: Verwenden von Ressourcen in lokalisierbaren Anwendungen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d803989292e2fc6b0945c397df5ce32d318147fc
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-resources-in-localizable-applications"></a>Gewusst wie: Verwenden von Ressourcen in lokalisierbaren Anwendungen
Lokalisierung bezeichnet die Anpassung einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] auf unterschiedliche Kulturen. Dazu müssen Text (z.B. Titel), Beschriftungen, Listenfeldelemente usw. übersetzt werden. Damit die Übersetzung vereinfacht wird, werden die zu übersetzten Elemente in Ressourcendateien gesammelt. Finden Sie unter [Lokalisieren einer Anwendung](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md) Informationen zum Erstellen einer Ressourcendatei für die Lokalisierung. Vornehmen einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung lokalisiert werden kann. Entwickler müssen alle lokalisierbaren Ressourcen in einer Ressourcenassembly zu erstellen. Die Ressourcenassembly wird in verschiedenen Sprachen lokalisiert und das Code-Behind-Modell verwendet ressourcenverwaltung [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] geladen. Eine der erforderlichen Dateien für eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung ist eine Projektdatei (".proj"). Alle Ressourcen, die Sie in Ihrer Anwendung verwenden, sollten in der Projektdatei enthalten sein. Dies wird im folgenden Codebeispiel gezeigt.  
  
## <a name="example"></a>Beispiel  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 Um eine Ressource in der Anwendung zu verwenden, instanziieren Sie <xref:System.Resources.ResourceManager> und Laden Sie die Ressource, die Sie verwenden möchten. Im folgenden Beispiel wird die hierfür erforderliche Vorgehensweise veranschaulicht:  
  
 [!code-csharp[LocalizationResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]
