---
title: Das Objekt oder die Klasse unterstützt diese Gruppe von Ereignissen nicht.
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: 2e00bdd624b54e19f19b6dabf6681bbf89709e60
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822582"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>Das Objekt oder die Klasse unterstützt diese Gruppe von Ereignissen nicht.
Sie haben versucht, Sie verwenden eine `WithEvents` Variable mit dem eine Komponente, die als Ereignisquelle für den angegebenen Satz von Ereignissen nicht funktioniert. Beispielsweise die Senke Ereignisse eines Objekts, und klicken Sie dann ein anderes Objekt zu erstellen, möchten `Implements` das erste Objekt. Obwohl Sie denken, dass Sie Ereignisse aus dem implementierte Objekt auffangen können vielleicht, ist dies nicht immer der Fall. `Implements` nur implementiert eine Schnittstelle für Methoden und Eigenschaften. `WithEvents` wird nicht unterstützt, für die Private `UserControls`, da die Typinformationen zum Auslösen der `ObjectEvent` zur Laufzeit nicht verfügbar ist.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Sie können nicht für eine Komponente Auffangen von Ereignissen, die keine Ereignisse.  
  
## <a name="see-also"></a>Siehe auch

- [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)
- [Implements-Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md)
