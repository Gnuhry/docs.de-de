---
title: Option Infer-Anweisung
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.OptionInfer
- vb.Infer
helpviewer_keywords:
- variables [Visual Basic], declaring
- Option Infer statement [Visual Basic]
- Infer keyword [Visual Basic]
- declaring variables [Visual Basic], inferred
- inferred variable declaration
ms.assetid: 4ad3e6e9-8f5b-4209-a248-de22ef6e4652
caps.latest.revision: "72"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4634c198b5fc41a4834cbd3cd96f9d3f1863d09b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="option-infer-statement"></a>Option Infer-Anweisung
Ermöglicht die Verwendung des lokalen Typrückschlusses beim Deklarieren von Variablen.  
  
## <a name="syntax"></a>Syntax  
  
```  
Option Infer { On | Off }  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`On`|Dies ist optional. Ermöglicht den lokalen Typrückschluss.|  
|`Off`|Dies ist optional. Deaktiviert den lokalen Typrückschluss.|  
  
## <a name="remarks"></a>Hinweise  
 Geben Sie zum Festlegen von `Option Infer` in einer Datei am Anfang der Datei `Option Infer On` oder `Option Infer Off` ein. Wenn der in einer Datei für `Option Infer` festgelegte Wert mit dem in der IDE oder in der Befehlszeile festgelegten Wert im Konflikt steht, hat der Wert in der Datei Vorrang.  
  
 Wenn Sie für `Option Infer` `On` festlegen, können Sie lokale Variablen deklarieren, ohne explizit einen Datentyp anzugeben. Der Compiler leitet den Datentyp einer Variablen vom Typ des Initialisierungsausdrucks ab.  
  
 In der folgenden Abbildung ist `Option Infer` eingeschaltet. Die Variable in der Deklaration `Dim someVar = 2` wird als ganze Zahl durch Typrückschluss deklariert.  
  
 ![IntelliSense-Ansicht der Deklaration. ] (../../../visual-basic/language-reference/statements/media/optioninferasinteger.png "OptionInferAsInteger")  
IntelliSense, wenn die Option Infer aktiviert ist.  
  
 In der folgenden Abbildung ist `Option Infer` deaktiviert. Die Variable in der Deklaration `Dim someVar = 2` ist durch Typrückschluss als `Object` deklariert. In diesem Beispiel wird die **Option Strict** eingestellt **deaktiviert** auf die [Seite kompilieren, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).  
  
 ![IntelliSense-Ansicht der Deklaration. ] (../../../visual-basic/language-reference/statements/media/optioninferasobject.png "OptionInferAsObject")  
IntelliSense, wenn Option Infer deaktiviert ist  
  
> [!NOTE]
>  Wenn eine Variable als `Object`deklariert ist, kann sich der Laufzeittyp ändern, während das Programm ausgeführt wird. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]führt Vorgänge aufgerufen *Boxing* und *unboxing* zum Konvertieren zwischen einer `Object` und einen Werttyp, wodurch Ausführung langsamer. Informationen zu Boxing und unboxing finden Sie unter der [Visual Basic-Sprachspezifikation](../../../visual-basic/reference/language-specification/index.md).
  
 Typrückschluss findet auf Prozedurebene Anwendung und nicht außerhalb einer Prozedur in einer Klasse, Struktur, Modul oder Schnittstelle.  
  
 Weitere Informationen finden Sie unter [lokalen Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
## <a name="when-an-option-infer-statement-is-not-present"></a>Wenn eine Option Infer-Anweisung nicht vorhanden ist  
 Wenn der Quellcode nicht enthält ein `Option Infer` -Anweisung, die **Option Infer** festlegen für die [Seite kompilieren, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) verwendet wird. Wenn Sie der Befehlszeilencompiler verwendet wird, die [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) -Compileroption verwendet wird.  
  
#### <a name="to-set-option-infer-in-the-ide"></a>Festlegen der Option Infer in der IDE  
  
1.  Wählen Sie im **Projektmappen-Explorer** ein Projekt aus. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. Weitere Informationen finden Sie unter [NIB: Verwalten von Projekteigenschaften mit dem Projekt-Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).  
  
2.  Klicken Sie auf die Registerkarte **Kompilieren**.  
  
3.  Legen Sie den Wert der **Option infer** Feld.  
  
 Bei der Erstellung eines neuen Projekts die **Option Infer** festlegen, auf die **Kompilieren** auf die Registerkarte "festgelegt ist die **Option Infer** festlegen in der **VB Defaults** Das Dialogfeld. Für den Zugriff auf die **VB Defaults** Dialogfeld auf die **Tools** Menü klicken Sie auf **Optionen**. Erweitern Sie im Dialogfeld **Optionen** **Projekte und Lösungen**, und klicken Sie dann auf **VB Defaults**. Die ursprüngliche Standardeinstellung in **VB-Standard** ist `On`.  
  
#### <a name="to-set-option-infer-on-the-command-line"></a>Festlegen der Option Infer in der Befehlszeile.  
  
-   Enthalten die [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) -Compileroption in der **Vbc** Befehl.  
  
## <a name="default-data-types-and-values"></a>Standarddatentypen und -werte  
 Die folgende Tabelle beschreibt die Ergebnisse der verschiedenen Kombinationen der Spezifizierung von Datentyp und Initialisierung in einer `Dim`-Anweisung.  
  
|Datentyp angegeben?|Initialisierung angegeben?|Beispiel|Ergebnis|  
|---|---|---|---|  
|Nein|Nein|`Dim qty`|Wenn `Option Strict` deaktiviert ist (Standard), ist die Variable auf `Nothing` eingestellt.<br /><br /> Wenn `Option Strict` aktiviert ist, tritt ein Kompilierungsfehler auf.|  
|Nein|Ja|`Dim qty = 5`|Wenn `Option Infer` aktiviert ist (Standard), übernimmt die Variable den Datentyp des Initialisierers an. Finden Sie unter [lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Wenn `Option Infer` und `Option Strict` ausgeschaltet sind, nimmt die Variable den Datentyp des `Object` an.<br /><br /> Wenn `Option Infer` deaktiviert ist und `Option Strict` aktiviert ist, tritt ein Kompilierungsfehler auf.|  
|Ja|Nein|`Dim qty As Integer`|Die Variable wird auf den Standardwert für den Datentyp initialisiert. Weitere Informationen finden Sie unter [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).|  
|Ja|Ja|`Dim qty  As Integer = 5`|Wenn der Datentyp der Initialisierung nicht in den angegebenen Datentyp konvertiert werden kann, tritt ein Fehler während der Kompilierung auf.|  
  
## <a name="example"></a>Beispiel  
 Die folgenden Beispiele veranschaulichen, wie die `Option Infer`-Anweisung den lokalen Typrückschluss ermöglicht.  
  
 [!code-vb[VbVbalrTypeInference#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht, dass der Laufzeittyp abweichen kann, wenn eine Variable als ein `Object` gekennzeichnet ist.  
  
 [!code-vb[VbVbalrTypeInference#11](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [VB-Standard, Projekte, Dialogfeld „Optionen“](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)  
 [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [Boxing und Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
