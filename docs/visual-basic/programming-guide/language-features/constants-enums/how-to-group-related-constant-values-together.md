---
title: 'Vorgehensweise: Gruppieren Sie verwandter konstanter Werte zusammen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 9174bcd2385103cf7fa1daf3133e388f9b4998a4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843760"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a>Vorgehensweise: Gruppieren Sie verwandter konstanter Werte zusammen (Visual Basic)
Eine Enumeration ist die beste Methode zum Gruppieren verwandter Konstanten. Sie erstellen eine Enumeration mit den `Enum` Anweisung im Abschnitt zu Deklarationen einer Klasse oder ein Modul. Weitere Informationen finden Sie unter [Vorgehensweise: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).  
  
### <a name="to-group-related-constant-values"></a>Gruppe verwandter konstanter Werte  
  
1.  Schreiben Sie eine Deklaration, die eine Ebene, enthält die `Enum` -Schlüsselwort und einen gültigen Namen. In diesem Beispiel wird die `Private` Enumeration `temperatureValues`.  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2.  Definieren der Konstanten in der Enumeration. In diesem Beispiel wird die `Public` Enumeration `temperatureValues` und ihre Werte zuordnet.  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Vorgehensweise: Finden Sie in einen Enumerationsmember](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Situationen für die Verwendung von Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Übersicht über Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Konstanten und literale Datentypen](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)
