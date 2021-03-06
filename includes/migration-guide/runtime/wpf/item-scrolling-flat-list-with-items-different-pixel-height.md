---
ms.openlocfilehash: eb3cfdfd39444536f423b65166a3413db67a0e01
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761293"
---
### <a name="item-scrolling-a-flat-list-with-items-of-different-pixel-height"></a>Elementscrolling durch eine flache Liste mit Elementen mit unterschiedlicher Pixelhöhe

|   |   |
|---|---|
|Details|Wenn ein <xref:System.Windows.Controls.ItemsControl?displayProperty=name>-Element eine Sammlung mithilfe von Virtualisierung (<code>IsVirtualizing=true</code>) und Elementscrolling (<code>ScrollUnit=Item</code>) anzeigt, und wenn das Steuerelement gescrollt wird, um ein Element anzuzeigen, dessen Größe in Pixeln sich von dessen Nachbarn unterscheidet, durchläuft <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=name> alle Elemente in der Sammlung. Die Benutzeroberfläche reagiert während dieser Iteration nicht. Wenn die Sammlung groß ist, kann dies zu einem Absturz führen. Die Iteration tritt ebenfalls in anderen Fällen auf, auch in früheren Versionen von .NET Framework. Sie tritt z.B. beim Scrollen von Pixeln (<code>ScrollUnit=Pixel</code>) auf, nachdem ein Element mit einer anderen Pixelhöhe erkannt wurde sowie beim Elementscrolling für hierarchische Daten (wie beim <xref:System.Windows.Controls.TreeView?displayProperty=name>-Steuerelement oder einem <xref:System.Windows.Controls.ItemsControl?displayProperty=name>-Element mit aktivierter Gruppierung), nachdem bei einem Element eine andere Anzahl von Nachfolgerelementen als bei seinen Nachbarn erkannt wurde. Im Fall des Elementscrollings bei unterschiedlicher Pixelhöhe wurde die Iteration in .NET Framework 4.6.1 eingeführt, um Fehler im Layout der hierarchischen Daten zu beheben.  Dies ist für flache Datenstrukturen (ohne Hierarchie) nicht erforderlich, und .NET Framework 4.6.2 führt die Iteration in diesem Fall nicht aus.|
|Vorschlag|Wenn die Iteration in .NET Framework 4.6.1, aber nicht in früheren Releases auftritt, also wenn <xref:System.Windows.Controls.ItemsControl?displayProperty=name> das Elementscrolling in einer flachen Liste von Elementen mit unterschiedlicher Pixelhöhe durchführt, gibt es zwei Lösungen:<ol><li>.NET Framework 4.6.2 installieren</li><li>Hotfix HR 1605 für .NET Framework 4.6.1 installieren</li></ol>|
|Bereich|Gering|
|Version|4.6.1|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=nameWithType></li></ul>|

