---
title: Datenmember-Reihenfolge
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], ordering members
ms.assetid: 0658a47d-b6e5-4ae0-ba72-ababc3c6ff33
ms.openlocfilehash: c78cc682c0776bfb0ce09dec7ba1ff8cab504285
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198568"
---
# <a name="data-member-order"></a>Datenmember-Reihenfolge
Bei einigen Anwendungen ist es hilfreich, die Reihenfolge zu kennen, in der die Daten aus verschiedenen Datenmembern gesendet oder erwartet werden (wie z.&amp;#160;B. die Reihenfolge, in der die Daten im serialisierten XML angezeigt werden). Manchmal kann es auch notwendig sein, diese Reihenfolge zu ändern. In diesem Thema werden die Sortierungsregeln beschrieben.  
  
## <a name="basic-rules"></a>Grundregeln  
 Zu den grundlegenden Regeln für die Sortierung von Daten gehören u.&amp;#160;a.:  
  
-   Wenn ein Datenvertragstyp Teil einer Vererbungshierarchie ist, stehen die Datenmember der Basistypen immer am Anfang der Reihenfolge.  
  
-   Danach folgen die Datenmember des aktuellen Typs, für die die <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>-Eigenschaft des Attributs <xref:System.Runtime.Serialization.DataMemberAttribute> nicht festgelegt ist, in alphabetischer Reihenfolge.  
  
-   Dann folgen die Datenmember mit der <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>-Eigenschaft der <xref:System.Runtime.Serialization.DataMemberAttribute>Attributgruppe. Diese sind zunächst nach dem Wert der `Order`-Eigenschaft geordnet und dann alphabetisch, falls mehr als ein Member eines bestimmten `Order`-Werts vorhanden ist. Die Reihenfolgenwerte können übersprungen werden.  
  
 Die alphabetische Reihenfolge wird erstellt, indem die <xref:System.String.CompareOrdinal%2A>-Methode aufgerufen wird.  
  
## <a name="examples"></a>Beispiele  
 Betrachten Sie folgenden Code.  
  
 [!code-csharp[C_DataContractNames#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#4)]
 [!code-vb[C_DataContractNames#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#4)]  
  
 Das generierte XML sieht ähnlich aus wie das folgende.  
  
```xml  
<DerivedType>  
    <!-- Zebra is a base data member, and appears first. -->  
    <zebra/>   
  
    <!-- Cat has no Order, appears alphabetically first. -->  
    <cat/>  
  
   <!-- Dog has no Order, appears alphabetically last. -->  
    <dog/>   
  
    <!-- Bird is the member with the smallest Order value -->  
    <bird/>  
  
    <!-- Albatross has the next Order value, alphabetically first. -->  
    <albatross/>  
  
    <!-- Parrot, with the next Order value, alphabetically last. -->  
     <parrot/>  
  
    <!-- Antelope is the member with the highest Order value. Note that   
    Order=2 is skipped -->  
     <antelope/>   
</DerivedType>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Serialization.DataContractAttribute>
- [Datenvertragsäquivalenz](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)
- [Verwenden von Datenverträgen](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
