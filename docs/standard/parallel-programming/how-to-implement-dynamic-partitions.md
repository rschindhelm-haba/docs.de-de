---
title: 'Vorgehensweise: Implementieren von dynamischen Partitionen'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 792488e53ffb7f870e21fdd1ad3ef94bf0303b1a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720235"
---
# <a name="how-to-implement-dynamic-partitions"></a>Vorgehensweise: Implementieren von dynamischen Partitionen
Im folgenden Beispiel wird das Implementieren eines benutzerdefinierten <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> gezeigt, der dynamische Partitionierung implementiert und von bestimmten <xref:System.Threading.Tasks.Parallel.ForEach%2A>-Überladungen und PLINQ verwendet werden kann.  
  
## <a name="example"></a>Beispiel  
 Jedes Mal, wenn eine Partition <xref:System.Collections.IEnumerator.MoveNext%2A> auf dem Enumerator aufruft, stellt der Enumerator die Partition mit einem Listenelement bereit. Im Fall von PLINQ und <xref:System.Threading.Tasks.Parallel.ForEach%2A> ist die Partition eine <xref:System.Threading.Tasks.Task>-Instanz. Da Anforderungen gleichzeitig in mehreren Threads auftreten, wird der Zugriff auf den aktuellen Index synchronisiert.  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 Dies ist ein Beispiel der Blockpartitionierung, wobei jeder Block aus einem Element besteht. Durch gleichzeitige Bereitstellung weiterer Elemente könnten Sie den Konflikt über die Sperre minimieren und theoretisch eine schnellere Leistung erzielen. Allerdings könnten größere Blöcke ab einem gewissen Punkt zusätzliche Lastenausgleichslogik benötigen, um alle Threads in Betrieb zu halten, bis die gesamte Arbeit abgeschlossen ist.  
  
## <a name="see-also"></a>Siehe auch

- [Benutzerdefinierte Partitionierer für PLINQ und TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
- [Vorgehensweise: Implementieren eines Partitionierers für statisches Partitionieren](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
