---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: 6d2717bc2d1d14e369af2b9c5a8c0affb67501d9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124227"
---
# <a name="tcptransportbindingelement"></a>TcpTransportBindingElement
TcpTransportBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Von der TcpTransportBindingElement-Klasse werden keine Methoden definiert.  
  
## <a name="properties"></a>Eigenschaften  
 Die TcpTransportBindingElement-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="connectionpoolsettings"></a>ConnectionPoolSettings  
 Datentyp: TcpConnectionPoolSettings  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Verbindungspooleinstellungen.  
  
### <a name="listenbacklog"></a>ListenBacklog  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Maximal mögliche Anzahl der ausstehenden Verbindungsanforderungen in der Warteschlange.  
  
### <a name="portsharingenabled"></a>PortSharingEnabled  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Boolescher Wert, der angibt, ob die TCP-Portfreigabe für diese Verbindung aktiviert ist.  
  
### <a name="teredoenabled"></a>TeredoEnabled  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Boolescher Wert, der angibt, ob das Teredo-Protokoll aktiviert ist, das zur Adressierung von Clients hinter einer Firewall verwendet wird.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
