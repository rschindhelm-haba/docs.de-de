---
title: Verteilte Oracle-Transaktionen
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: 4af1c98818f1929850c5ae78892c64993a93d4d2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116216"
---
# <a name="oracle-distributed-transactions"></a>Verteilte Oracle-Transaktionen
Das <xref:System.Data.OracleClient.OracleConnection>-Objekt wird automatisch in einer vorhandenen verteilten Transaktion aufgelistet, wenn es ermittelt, dass eine Transaktion aktiv ist. Die automatische Eintragung von Transaktionen wird vorgenommen, wenn die Verbindung aus dem Verbindungspool geöffnet oder abgerufen wird. Die automatische Eintragung kann in vorhandenen Transaktionen deaktiviert werden, indem  
  
```  
Enlist=false  
```  
  
 als Verbindungszeichenfolgenparameter für die <xref:System.Data.OracleClient.OracleConnection> angegeben wird.  
  
## <a name="see-also"></a>Siehe auch

- [Oracle und ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
