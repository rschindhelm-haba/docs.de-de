---
title: Konvertieren von Datentypen (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
ms.openlocfilehash: ad9594cabe0e2382ae4e19f2541eec4aa74ccd75
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58837051"
---
# <a name="converting-data-types-visual-basic"></a>Konvertieren von Datentypen (Visual Basic)
Konvertierungsmethoden ändern den Typ von Eingabeobjekten.  
  
 Konvertierungsvorgänge in LINQ-Abfragen sind in vielen Anwendungen nützlich. Nachstehend sind einige Beispiele aufgeführt:  
  
-   Die <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>-Methode kann zum Ausblenden einer benutzerdefinierten Implementierung eines Standardabfrageoperators eines Typs verwendet werden.  
  
-   Die <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType>-Methode kann verwendet werden, um nicht parametrisierte Auflistungen für LINQ-Abfragen zu ermöglichen.  
  
-   Die Methoden <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> und <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> können verwendet werden, um die sofortige Ausführung einer Abfrage zu erzwingen, statt sie zu verzögern, bis die Abfrage enumeriert wurde.  
  
## <a name="methods"></a>Methoden  
 Die folgende Tabelle enthält die Standardabfrageoperator-Methoden, die Datentypumwandlungen ausführen.  
  
 Die Konvertierungsmethoden in dieser Tabelle, deren Namen mit „As“ beginnen, ändern den statischen Typ der Quellauflistung, listen ihn jedoch nicht auf. Die Methoden, deren Namen mit „To“ anfangen, listen die Quellauflistung auf und verschieben die Elemente in den entsprechenden Auflistungstyp.  
  
|Methodenname|Beschreibung|Visual Basic-Abfrageausdruckssyntax|Weitere Informationen|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|AsEnumerable|Gibt die Eingabe als <xref:System.Collections.Generic.IEnumerable%601> typisiert zurück|Nicht zutreffend.|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|  
|AsQueryable|Konvertiert ein (generisches) <xref:System.Collections.IEnumerable>-Element in ein (generisches) <xref:System.Linq.IQueryable>-Element|Nicht zutreffend.|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|  
|Typumwandlung|Kopiert die Elemente einer Auflistung in einen bestimmten Typ.|`From … As …`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|  
|OfType|Filtert Werte, je nach ihrer Fähigkeit, die in einen angegebenen Typ umgewandelt werden sollen.|Nicht zutreffend.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|ToArray|Konvertiert eine Auflistung in ein Array. Diese Methode erzwingt die Ausführung der Abfrage.|Nicht zutreffend.|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|  
|ToDictionary|Platziert Elemente in ein <xref:System.Collections.Generic.Dictionary%602> auf Grundlage einer Schlüsselauswahlfunktion. Diese Methode erzwingt die Ausführung der Abfrage.|Nicht zutreffend.|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|  
|ToList|Konvertiert eine Auflistung in eine <xref:System.Collections.Generic.List%601>. Diese Methode erzwingt die Ausführung der Abfrage.|Nicht zutreffend.|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|  
|ToLookup|Platziert Elemente, basierend auf einer Schlüsselauswahlfunktion, in ein <xref:System.Linq.Lookup%602> (one-to-many-Wörterbuch) ein. Diese Methode erzwingt die Ausführung der Abfrage.|Nicht zutreffend.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a>Beispiel für die Abfrageausdruckssyntax  
 Im folgenden Codebeispiel wird die `From As` -Klausel, um einen Typ in einen Untertyp umzuwandeln, vor dem Zugriff auf ein Element, das nur im Untertyp verfügbar ist.  
  
```vb  
Class Plant  
    Public Property Name As String  
End Class  
  
Class CarnivorousPlant  
    Inherits Plant  
    Public Property TrapType As String  
End Class  
  
Sub Cast()  
  
    Dim plants() As Plant = {   
        New CarnivorousPlant With {.Name = "Venus Fly Trap", .TrapType = "Snap Trap"},   
        New CarnivorousPlant With {.Name = "Pitcher Plant", .TrapType = "Pitfall Trap"},   
        New CarnivorousPlant With {.Name = "Sundew", .TrapType = "Flypaper Trap"},   
        New CarnivorousPlant With {.Name = "Waterwheel Plant", .TrapType = "Snap Trap"}}  
  
    Dim query = From plant As CarnivorousPlant In plants   
                Where plant.TrapType = "Snap Trap"   
                Select plant  
  
    Dim sb As New System.Text.StringBuilder()  
    For Each plant In query  
        sb.AppendLine(plant.Name)  
    Next  
  
    ' Display the results.  
    MsgBox(sb.ToString())  
  
    ' This code produces the following output:  
  
    ' Venus Fly Trap  
    ' Waterwheel Plant  
  
End Sub  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Linq>
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [From-Klausel](../../../../visual-basic/language-reference/queries/from-clause.md)
- [Vorgehensweise: Abfragen von ArrayList mit LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)
