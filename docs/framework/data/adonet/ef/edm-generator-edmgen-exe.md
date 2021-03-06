---
title: EDM-Generator (EdmGen.exe)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe8297a1-1fc3-48ce-8eeb-f70f63f857aa
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: da99c43d9142ee754b2b48db45ca070d1ab7c4e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="edm-generator-edmgenexe"></a>EDM-Generator (EdmGen.exe)
EdmGen.exe ist ein Befehlszeilentool, das für die Arbeit mit [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Modell- und Zuordnungsdateien verwendet wird. Mit dem Tool EdmGen.exe können folgende Aufgaben ausgeführt werden:  
  
-   Herstellen einer Verbindung zu einer Datenquelle mithilfe eines datenquellenspezifischen .NET Framework-Datenanbieters, und Erstellen der Dateien für das konzeptionelle Modell (CSDL), das Speichermodell (SSDL) und die Zuordnungen (MSL), die von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] verwendet werden. Weitere Informationen finden Sie unter [Vorgehensweise: verwenden EdmGen.exe generiert die Modell- und Zuordnen von Dateien](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
-   Überprüfen eines bestehenden Modells. Weitere Informationen finden Sie unter [wie: Verwenden von EdmGen.exe Validate Model "und" Zuordnen von Dateien](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md).  
  
-   Erstellen einer C#- oder Visual Basic-Codedatei, die die Objektklassen enthält, die aus einer Datei für das konzeptionelle Modell (CSDL) generiert wurden. Weitere Informationen finden Sie unter [wie: Verwenden von EdmGen.exe zum Generieren von Objektebenencode](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md).  
  
-   Generieren einer C#- oder Visual Basic-Codedatei, die die vorab generierten Sichten für ein vorhandenes Modell enthält. Weitere Informationen [Vorgehensweise: Pre-Generate Ansichten zum Verbessern der Abfrageleistung](http://msdn.microsoft.com/en-us/b18a9d16-e10b-4043-ba91-b632f85a2579).  
  
 Das Tool EdmGen.exe wird im [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]-Verzeichnis installiert. Dieses befindet sich meist unter C:\Windows\Microsoft.NET\Framework\v4.0. Bei 64-Bit-Systemen befindet es sich unter C:\Windows\Microsoft.NET\Framework64\v4.0. Sie können auch das Tool EdmGen.exe zugreifen, von der Visual Studio-Eingabeaufforderung (klicken Sie auf **starten**, zeigen Sie auf **Programme**, zeigen Sie auf **Microsoft Visual Studio 2010**, zeigen Sie auf **Visual Studio-Tools**, und klicken Sie dann auf **Visual Studio 2010-Eingabeaufforderung**).  
  
## <a name="syntax"></a>Syntax  
  
```  
EdmGen /mode:choice [options]  
```  
  
## <a name="mode"></a>Modus  
 Wenn Sie das Tool EdmGen.exe verwenden, müssen Sie einen der folgenden Modi angeben.  
  
|Modus|Beschreibung|  
|----------|-----------------|  
|`/mode:ValidateArtifacts`|Überprüft die CSDL-, SSDL- und MSL-Dateien und zeigt alle Fehler und Warnungen an.<br /><br /> Diese Option erfordert mindestens eines der Argumente `/inssdl` oder `/incsdl`. Wenn `/inmsl` angegeben wird, sind auch die Argumente `/inssdl` und `/incsdl` erforderlich.|  
|`/mode:FullGeneration`|Verwendet die in der `/connectionstring`-Option angegebenen Informationen zur Datenbankverbindung, und erstellt die CSDL-, SSDL-, .MSL-, Objektebenen- und Sichtdateien.<br /><br /> Diese Option erfordert ein `/connectionstring`-Argument sowie entweder ein `/project`-Argument oder die Argumente `/outssdl`, `/outcsdl`, `/outmsdl`, `/outobjectlayer`, `/outviews`, `/namespace` und `/entitycontainer`.|  
|`/mode:FromSSDLGeneration`|Generiert CSDL- und MSL-Dateien, Quellcode und Sichten mithilfe der angegebenen SSDL-Datei.<br /><br /> Diese Option erfordert das `/inssdl`-Argument und entweder ein `/project`-Argument oder die Argumente `/outcsdl`, `/outmsl`, `/outobjectlayer`, `/outviews`, `/namespace,` und `/entitycontainer`.|  
|`/mode:EntityClassGeneration`|Erstellt eine Quellcodedatei, die die mithilfe der CSDL-Datei generierten Klassen enthält.<br /><br /> Diese Option erfordert das `/incsdl`-Argument sowie das `/project`-Argument oder das `/outobjectlayer`-Argument. Das `/language`-Argument ist optional.|  
|`/mode:ViewGeneration`|Erstellt eine Quellcodedatei, die die aus den CSDL-, SSDL- und MSL-Dateien generierten Sichten enthält.<br /><br /> Diese Option erfordert die Argumente `/inssdl`, `/incsdl` und `/inmsl,` sowie entweder das `/project`-Argument oder das `/outviews`-Argument. Das `/language`-Argument ist optional.|  
  
## <a name="options"></a>Optionen  
  
|Option|Beschreibung|  
|------------|-----------------|  
|`/p[roject]:`\<Zeichenfolge >|Gibt den zu verwendenden Projektnamen an. Der Projektname wird für die standardmäßige Namespaceeinstellung, die Namen der Modell- und Zuordnungsdateien, den Namen der Objektquelldatei und den Namen der Quelldatei für das Generieren von Ansichten verwendet. Name des Entitätencontainers festgelegt ist, um \<Projekt > Kontext.|  
|`/prov[ider]:`\<Zeichenfolge >|Der Name des [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]-Datenanbieters zum Erstellen der Speichermodelldatei (SSDL). Der Standardanbieter ist die [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] -Datenanbieter für SQL Server (<xref:System.Data.SqlClient?displayProperty=nameWithType>).|  
|`/c[onnectionstring]:`\<Verbindungszeichenfolge >|Gibt die Zeichenfolge an, die verwendet wird, um eine Verbindung mit der Datenquelle herzustellen.|  
|`/incsdl:`\<Datei >|Gibt die CSDL-Datei oder ein Verzeichnis an, in dem sich die CSDL-Dateien befinden. Dieses Argument kann mehrmals angegeben werden, damit Sie mehrere Verzeichnisse oder CSDL-Dateien angeben können. Das Angeben mehrerer Verzeichnisse ist beim Erstellen von Klassen (`/mode:EntityClassGeneration`) oder Sichten (`/mode:ViewGeneration`) hilfreich, wenn das konzeptionelle Modell in mehrere Dateien aufgeteilt ist. Dies kann auch nützlich sein, wenn Sie mehrere Modelle (`/mode:ValidateArtifacts`) überprüfen möchten.|  
|`/refcsdl:`\<Datei >|Gibt die zusätzliche CSDL-Datei bzw. -Dateien an, die verwendet werden, um die Verweise in der CSDL-Quelldatei aufzulösen. (Die CSDL-Quelldatei ist die mit der `/incsdl`-Option angegebene Datei). Die `/refcsdl`-Datei enthält Typen, von denen die CSDL-Quelldatei abhängt. Dieses Argument kann mehrmals angegeben werden.|  
|`/inmsl:`\<Datei >|Gibt die MSL-Datei oder ein Verzeichnis an, in dem sich die MSL-Dateien befinden. Dieses Argument kann mehrmals angegeben werden, um mehrere Verzeichnisse oder MSL-Dateien anzugeben. Das Angeben mehrerer Dateien ist beim Erstellen von Sichten (`/mode:ViewGeneration`) hilfreich, wenn das konzeptionelle Modell in mehrere Dateien aufgeteilt ist. Dies kann auch nützlich sein, wenn Sie mehrere Modelle (`/mode:ValidateArtifacts`) überprüfen möchten.|  
|`/inssdl:`\<Datei >|Gibt die SSDL-Datei oder ein Verzeichnis an, in dem sich die SSDL-Datei befindet. Dieses Argument kann mehrmals angegeben werden, damit Sie mehrere Verzeichnisse oder SSDL-Dateien angeben können. Dies kann auch nützlich sein, wenn Sie mehrere Modelle `(/mode:ValidateArtifacts)` überprüfen möchten.|  
|`/outcsdl:`\<Datei >|Gibt den Namen der CSDL-Datei an, die erstellt wird.|  
|`/outmsl:`\<Datei >|Gibt den Namen der MSL-Datei an, die erstellt wird.|  
|`/outssdl:`\<Datei >|Gibt den Namen der SSDL-Datei an, die erstellt wird.|  
|`/outobjectlayer:`\<Datei >|Gibt den Namen der Quellcodedatei an, die die mit der CSDL-Datei generierten Objekte enthält.|  
|`/outviews:`\<Datei >|Gibt den Namen der Quellcodedatei an, die die generierten Sichten enthält.|  
|`/language:`[VB &#124; CSharp]|Gibt die Sprache für die erstellten Quellcodedateien an. Die Standardsprache ist C#.|  
|`/namespace:`\<Zeichenfolge >|Gibt den zu verwendenden Namespace für das Modell an. Der Namespace wird beim Ausführen von `/mode:FullGeneration` oder `/mode:FromSSDLGeneration` in der CSDL-Datei festgelegt. Beim Ausführen `/mode:EntityClassGeneration` wird der Namespace nicht verwendet.|  
|`/entitycontainer:`\<Zeichenfolge >|Gibt den Namen an, der dem `<EntityContainer>`-Element in den generierten Modell- und Zuordnungsdateien hinzugefügt wird.|  
|`/pl[uralize]`|Wendet für das Englische geltende Regeln für Singular- und Pluralbildung auf die Namen von `Entity`, `EntitySet` und `NavigationProperty` im konzeptionellen Modell an. Diese Option führt die folgenden Aktionen aus:<br /><br /> -Stellen Sie alle `EntityType` Namen im singular.<br />-Stellen Sie alle `EntitySet` Namen im plural.<br />– Für jedes `NavigationProperty` , die höchstens eine Entität zurückgibt, stellen Sie den Namen im singular.<br />– Für jedes `NavigationProperty` , die mehr als eine Entität zurückgibt, stellen Sie den Namen im plural.|  
|`/SupressForeignKeyProperties or /nofk`|Verhindert, dass Fremdschlüsselspalten als skalare Eigenschaften von Entitätstypen im konzeptionellen Modell verfügbar gemacht werden.|  
|`/help` oder `?`|Zeigt Befehlssyntax und Optionen für das Tool an.|  
|`/nologo`|Unterdrückt die Anzeige der Copyrightmeldung.|  
|`/targetversion:`\<Zeichenfolge >|Die Version von .NET Framework, die zum Kompilieren des generierten Codes verwendet wird. Unterstützt werden Version 4 und 4.5. Der Standardwert ist 4.|  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Verwenden Sie EdmGen.exe, um die Modell- und Zuordnungsdateien zu generieren.](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)  
  
 [Vorgehensweise: Verwenden Sie zum Generieren von Objektebenencode EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)  
  
 [Vorgehensweise: Verwenden Sie zum Überprüfen von Modell- und Zuordnungsdateien EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)  
  
## <a name="see-also"></a>Siehe auch  
 [ADO.NET Entity Data Model Tools (ADO.NET Entity Data Model-Tools)](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)  
 [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md)  
 [CSDL, SSDL, and MSL Specifications (CSDL-, SSDL- und MSL-Spezifikationen)](../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
