---
title: XSLT-Compiler (xsltc.exe)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 672a5ac8-8305-4d28-ba10-11089c2c0924
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2b4ede7bdb8dad65e9cd959dfaa2f8956a877762
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xslt-compiler-xsltcexe"></a>XSLT-Compiler (xsltc.exe)
Der XSLT-Compiler (xsltc.exe) kompiliert XSLT-Stylesheets und generiert eine Assembly. Das kompilierte Stylesheet kann dann direkt in die <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType>-Methode übergeben werden. Sie können mit xsltc.exe keine signierten Assemblys generieren.  
  
 Das Tool <legacyBold>xsltc.exe</legacyBold> ist Bestandteil von Visual Studio 2008. Weitere Informationen finden Sie unter der [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkId=89463).  
  
## <a name="syntax"></a>Syntax  
  
```  
xsltc [options] [/class:<name>] <sourceFile> [[/class:<name>] <sourceFile>...]  
```  
  
## <a name="argument"></a>Argument  
  
|Argument|Beschreibung|  
|--------------|-----------------|  
|`sourceFile`|Gibt den Namen des Stylesheets an. Das Stylesheet muss eine lokale Datei sein oder sich im Intranet befinden.|  
  
## <a name="options"></a>Optionen  
  
|Option|Beschreibung|  
|------------|-----------------|  
|`/c[lass]:` `name`|Gibt den Namen der Klasse für das folgende Stylesheet an. Der Klassenname kann vollqualifiziert sein.<br /><br /> In der Standardeinstellung ist der Klassenname mit dem Namen des Stylesheets identisch. Wenn zum Beispiel das Stylesheet <legacyBold>customers.xsl</legacyBold> kompiliert wird, lautet der standardmäßige Klassenname <legacyBold>customers</legacyBold>.|  
|`/debug[`+&#124;-`]`|Gibt an, ob Debuginformationen generiert werden sollen.<br /><br /> Wenn `+` oder `/debug` angegeben wird, generiert der Compiler Debuginformationen und speichert sie in einer Programmdatenbankdatei (PDB-Datei). Der Name der generierten PDB-Datei lautet `assemblyName`.pdb.<br /><br /> Wenn Sie `-` angeben, was im Endeffekt dasselbe ist, wie `/debug` nicht anzugeben, werden keine Debuginformationen erstellt. Es wird eine Retailassembly generiert. **Hinweis:** Kompilieren im Debugmodus befinden, kann die XSLT-Leistung erheblich beeinträchtigen.|  
|`/help`|Zeigt Befehlssyntax und Optionen für das Tool an.|  
|`/nologo`|Unterdrückt die Anzeige der Compilercopyrightmeldung.|  
|`/platform:` `string`|Gibt die Plattformen an, auf denen die Assembly ausgeführt werden kann. Im Folgenden werden die gültigen Plattformwerte beschrieben:<br /><br /> `x86` kompiliert die Assembly für die 32-Bit-x86-kompatible CLR (Common Language Runtime).<br /><br /> `x64` kompiliert die Assembly für die 64-Bit-CLR auf einem Computer, der den AMD64- oder EM64T-Anweisungssatz unterstützt.<br /><br /> [!INCLUDE[vcpritanium](../../../../includes/vcpritanium-md.md)]kompiliert die Assembly von der 64-Bit-common Language Runtime auf einem Computer ausgeführt werden, die verfügt über eine [!INCLUDE[vcpritanium](../../../../includes/vcpritanium-md.md)] Prozessor.<br /><br /> `anycpu` kompiliert die Assembly für die Ausführung auf einer beliebigen Plattform. Dies ist die Standardeinstellung.|  
|`/out:` `assemblyName`|Gibt den Namen der Assembly an, die ausgegeben wird. Der Assemblyname entspricht standardmäßig dem Namen des Hauptstylesheets bzw. des ersten Stylesheets, falls es mehrere Stylesheets gibt.<br /><br /> Wenn das Stylesheet Skripts enthält, werden die Skripts in einer separaten Assembly gespeichert. Die Namen der Skriptassemblys werden auf der Grundlage des Namens der Hauptassembly generiert. Wenn Sie z. B. als Assemblynamen <legacyBold>CustOrders.dll</legacyBold> angegeben haben, wird die erste Skriptassembly <legacyBold>CustOrders_Script1.dll</legacyBold> genannt.|  
|`/settings:` `document+-, script+-, DTD+-,`|Gibt an, ob `document()`-Funktionen, XSLT-Skripts oder Dokumenttypdefinitionen (DTD) im Stylesheet zugelassen sind.<br /><br /> In der Standardeinstellung werden DTD, die `document()`-Funktion und Skripts nicht unterstützt.|  
|`@` `file`|Ermöglicht die Angabe einer Datei, die Compileroptionen enthält.|  
|`?`|Zeigt Befehlssyntax und Optionen für das Tool an.|  
  
## <a name="remarks"></a>Hinweise  
 XSLT-Lösungen können aus mehreren Stylesheetmodulen bestehen. Das Tool <legacyBold>xsltc.exe</legacyBold> generiert Assemblys auf der Grundlage von Stylesheets. Die Assemblys können dann direkt in die <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType>-Methode übergeben werden. Auf diese Weise lassen sich in einigen XSLT-Bereitstellungsszenarios die zu verzeichnenden Leistungseinbußen verringern.  
  
> [!NOTE]
>  Sie müssen auch die kompilierte Assembly als Verweis in die Anwendung einschließen.  
  
 Das Tool xsltc.exe überprüft nicht die Klasse (`/class:``name`) oder die Assembly (`/out:``assemblyName`) Namen. Wenn die Namen nicht gültig sind, gibt die CLR entsprechende Fehlermeldungen aus.  
  
## <a name="examples"></a>Beispiele  
 Der folgende Befehl kompiliert das Stylesheet und erstellt eine Assembly mit dem Namen <legacyBold>booksort.dll</legacyBold>.  
  
```  
xsltc booksort.xsl  
```  
  
 Der folgende Befehl kompiliert das Stylesheet und erstellt eine Assembly mit dem Namen <legacyBold>booksort.dll</legacyBold> und eine PDB-Datei mit dem Namen <legacyBold>booksort.pdb</legacyBold>.  
  
```  
xsltc booksort.xsl /debug  
```  
  
 Der folgende Befehl kompiliert ein Stylesheet, das ein <legacyBold>msxsl:script</legacyBold>-Element enthält, und erstellt zwei Assemblys namens <legacyBold>calc.dll</legacyBold> und <legacyBold>calc_Script1.dll</legacyBold>.  
  
```  
xsltc /settings:script+ calc.xsl  
```  
  
 Der folgende Befehl aktiviert die DTD-Verarbeitung und die Unterstützung für Skripts und erstellt zwei Assemblys namens <legacyBold>myTest.dll</legacyBold> und <legacyBold>myTest_Script1.dll</legacyBold>.  
  
```  
xsltc /settings:DTD+,script+ /out:myTest calc.xsl  
```  
  
 Der folgende Befehl kompiliert zwei Stylesheetmodule und eine Assembly mit dem Namen <legacyBold>booksort.dll</legacyBold>.  
  
```  
xsltc booksort.xsl output.xsl  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Xsl.XslCompiledTransform>  
 [Vorgehensweise: Ausführen eine XSLT-Transformation mittels einer Assembly](../../../../docs/standard/data/xml/how-to-perform-an-xslt-transformation-by-using-an-assembly.md)  
 [XSLT Transformations (XSLT-Transformationen)](../../../../docs/standard/data/xml/xslt-transformations.md)
