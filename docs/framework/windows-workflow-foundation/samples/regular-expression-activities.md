---
title: "Aktivitäten mit regulären Ausdrücken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8f24694-49db-4339-92ec-014e3d4ae63b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 77968872d878f7b4d6b0eb3f27516a75abb54919
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="regular-expression-activities"></a>Aktivitäten mit regulären Ausdrücken
In diesem Beispiel wird veranschaulicht, wie ein Satz von Aktivitäten erstellt wird, der die reguläre Ausdrucksfunktionalität des <xref:System.Text.RegularExpressions>-Namespaces verfügbar macht. Diese benutzerdefinierten Aktivitäten können innerhalb einer Workflowanwendung verwendet werden. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]reguläre Ausdrücke finden Sie unter [System.Text.RegularExpressions](http://go.microsoft.com/fwlink/?LinkId=150434) Namespace.  
  
 In der folgenden Tabelle sind die benutzerdefinierten Aktivitäten in diesem Beispiel aufgeführt.  
  
|Aktivität|Beschreibung|  
|--------------|-----------------|  
|IsMatch|Gibt an, ob der reguläre Ausdruck eine Übereinstimmung in der Eingabezeichenfolge gefunden hat.|  
|Entsprechungen|Sucht in einer Eingabezeichenfolge nach allen Vorkommnissen eines regulären Ausdrucks und gibt alle erfolgreichen Übereinstimmungen zurück.|  
|Ersetzen|Ersetzt innerhalb einer angegebenen Eingabezeichenfolge Zeichenfolgen, die ein Muster eines regulären Ausdrucks mit einer angegebenen Ersatzzeichenfolge vergleichen.|  
  
## <a name="ismatch"></a>IsMatch  
 Die benutzerdefinierte `IsMatch`-Aktivität gibt `true` zurück, wenn die `Input`-Zeichenfolge eine Übereinstimmung im regulären Ausdruck findet, der in der `Pattern`-Eigenschaft angegeben ist. Wenn die Aktivität von <xref:System.Activities.CodeActivity%601> abgeleitet wird, ruft die <xref:System.Activities.CodeActivity%601.Execute%2A>-Methode die <xref:System.Text.RegularExpressions.Regex.IsMatch%2A>-Methode auf.  
  
 In der folgenden Tabelle sind die Eigenschaften und der Rückgabewert für die benutzeraktivierte `IsMatch` Aktivität beschrieben.  
  
|Eigenschaft oder Rückgabewert|Beschreibung|  
|------------------------------|-----------------|  
|Muster (erforderlich)|Der für die Suche zu verwendende reguläre Ausdruck.|  
|Eingabe (erforderlich)|Die zu suchende Eingabezeichenfolge.|  
|RegexOptions|Bitweise OR-Kombination von [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) Enumerationswerte.|  
|Rückgabewert|`true`, wenn die Eingabe eine Übereinstimmung im bereitgestellten Muster findet; andernfalls `false`.|  
  
 Das folgende Codebeispiel zeigt, wie Sie die benutzerdefinierte `IsMatch`-Aktivität verwenden.  
  
```  
new IsMatch  
{  
    Pattern = new InArgument<string>( @"^-?\d+(\.\d{2})?$"),  
    Input = "20.00",  
};  
```  
  
## <a name="matches"></a>Entsprechungen  
 Die benutzerdefinierte `Matches`-Aktivität sucht in einer Eingabezeichenfolge nach allen Vorkommnissen eines regulären Ausdrucks und gibt alle erfolgreichen Übereinstimmungen zurück. Wenn die Aktivität von <xref:System.Activities.CodeActivity%601> abgeleitet wird, ruft die <xref:System.Activities.CodeActivity%601.Execute%2A>-Methode die <xref:System.Text.RegularExpressions.Regex.Matches%2A>-Methode auf.  
  
 In der folgenden Tabelle sind die Eigenschaften und der Rückgabewert für die benutzeraktivierte `IsMatch` Aktivität beschrieben.  
  
|Eigenschaft oder Rückgabewert|Beschreibung|  
|------------------------------|-----------------|  
|Muster (erforderlich)|Der für die Suche zu verwendende reguläre Ausdruck.|  
|Eingabe (erforderlich)|Die zu suchende Eingabezeichenfolge.|  
|RegexOptions|Bitweise OR-Kombination von [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) Enumerationswerte.|  
|Rückgabewert|Eine <xref:System.Text.RegularExpressions.MatchCollection>, die die Auflistung erfolgreicher Übereinstimmungen enthält.|  
  
 Das folgende Codebeispiel zeigt, wie Sie die benutzerdefinierte `Matches`-Aktivität verwenden.  
  
```  
new Matches  
{  
    Pattern = @"\b(?<word>\w+)\s+(\k<word>)\b",  
    Input = "The quick brown fox  fox jumped over over the lazy dog dog.",  
};  
```  
  
## <a name="replace"></a>Ersetzen  
 Die benutzerdefinierte `Replace`-Aktivität sucht eine Eingabezeichenfolge und ersetzt alle Zeichenfolgen, die einen angegebenen regulären Ausdruck mit einer Zeichenfolge vergleichen. Wenn die Aktivität von <xref:System.Activities.CodeActivity%601> abgeleitet wird, ruft die <xref:System.Activities.CodeActivity%601.Execute%2A>-Methode die <xref:System.Text.RegularExpressions.Regex.Replace%2A>-Methode auf.  
  
 In der folgenden Tabelle sind die Eigenschaften und der Rückgabewert für die benutzeraktivierte `Replace` Aktivität beschrieben.  
  
|Eigenschaft oder Rückgabewert|Beschreibung|  
|------------------------------|-----------------|  
|Muster (erforderlich)|Der für die Suche zu verwendende reguläre Ausdruck.|  
|Eingabe (erforderlich)|Die zu suchende Eingabezeichenfolge.|  
|Ersetzung|Die Ersatzzeichenfolge.<br /><br /> Wenn eine `Replacement` angegeben wurde, wird die `MatchEvaluator`-Eigenschaft ignoriert. Es muss entweder die `Replacement`-Eigenschaft oder die `MatchEvaluator`-Eigenschaft angegeben werden.|  
|MatchEvaluator|Eine benutzerdefinierte Methode, die jede Übereinstimmung überprüft und entweder die ursprüngliche entsprechende Zeichenfolge oder eine Ersatzzeichenfolge zurückgibt.<br /><br /> Wenn eine `Replacement` angegeben wurde, wird die `MatchEvaluator`-Eigenschaft ignoriert. Es muss entweder die `Replacement`-Eigenschaft oder die `MatchEvaluator`-Eigenschaft angegeben werden.|  
|RegexOptions|Bitweise OR-Kombination von [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) Enumerationswerte.|  
|Rückgabewert|Eine <xref:System.Text.RegularExpressions.MatchCollection>, die die Auflistung erfolgreicher Übereinstimmungen enthält.|  
  
 Das folgende Codebeispiel zeigt, wie Sie die benutzerdefinierte `Replace`-Aktivität verwenden.  
  
```  
// Using the replacement string.  
new Replace  
{  
    Pattern = @"\bWorld\b",  
    Input = "Hello World! This is a wonderful World",  
    Replacement = "Universe"  
};  
  
// Using a match evaluator.  
new Replace  
{  
    Pattern = new InArgument<string>(pattern),  
    Input = new InArgument<string>(input),  
    MatchEvaluator = new MatchEvaluator(CapText)                  
};  
```  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei RegexActivities.sln.  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Regex`