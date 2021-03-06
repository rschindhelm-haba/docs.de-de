---
title: Peerkanalsicherheit
ms.date: 03/30/2017
ms.assetid: 2c59b164-3729-44f0-a967-f247c42de662
ms.openlocfilehash: bc17c35bf088472cfbf36b2c6d7c868c8cc85f20
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129453"
---
# <a name="peer-channel-security"></a>Peerkanalsicherheit
Der Peerkanal ermöglicht die Verwendung einer Vielzahl von verteilten Anwendungstypen, die von Mehrparteienmessaging abhängen. Beispielsweise gehört hierzu eine Inhaltsverteilung auf Internetebene, wobei eine vertrauenswürdige Quelle Inhalte (wie beispielsweise Medien- oder Softwareupdates) verteilt, eine Gruppe von Freunden Musik oder Fotos austauscht oder ein Team von Kollegen zusammen ein Dokument bearbeitet. Jedes dieser Szenarien erfordert ein individuelles Sicherheitsmodell. Das Peerkanal-Sicherheitsmodell ist auf die Adressierung dieser Szenarien ausgelegt und bietet ein umfangreiches Sicherheitsmodell für die entsprechenden Anforderungen an unterschiedliche Identitäten, Authentifizierung und Autorisierungsmodelle.  
  
## <a name="security-scenarios"></a>Sicherheitsszenarios  
 Ein Inhaltsverteilungsszenario erfordert, dass jeder Inhaltsempfänger die Inhaltsquelle identifiziert. Aufgrund der Verteilungseigenschaft des Szenarios ist es nicht immer möglich, die Vermittler, die Nachrichten verarbeiten und abfangen, zu kennen. Um die Bedrohung durch einen nicht vertrauenswürdigen Vermittler, der die Nachrichten manipulieren könnte, zu mindern, können Anwendungen die Nachricht beim Absender sichern, sodass alle Manipulationsversuche leicht zu erkennen sind. In diesem Fall kann, abhängig von der Vertraulichkeit des Inhalts, Verschlüsselung notwendig sein.  
  
 Zusammenarbeitsszenarien wie die Zusammenarbeit an einem gemeinsamen Dokument erfordern oft, dass jedes Mitglied, das an der Sitzung teilnimmt, individuell identifiziert und authentifiziert wird. Dies bedeutet, dass ein Mechanismus für die Definition von Benutzergruppen und die Authentifizierung gegenüber diesen Gruppen notwendig ist, um diese Sitzung zu sichern. Darüber hinaus könnten Anwendungen das Aufzeichnen jeder Nachricht durch die Authentifizierung auf Nachrichtenebene erfordern. Bei diesen Typen von Anwendungen kann die Leistung für ein stärkeres Sicherheitsschema geopfert werden.  
  
 Für eine Kommunikationssitzung zwischen einer Gruppe von Gelegenheitsbenutzern können formlose Sicherheitsmodelle erforderlich sein. Hierzu gehört beispielsweise das Wissen über einen gemeinsamen geheimen Schlüssel innerhalb dieser Gruppe. Bei diesen Anwendungsarten hat die komfortable Einrichtung und Konfiguration des Sicherheitsmodells Vorrang vor der sichersten Art der Authentifizierung oder der Bereitstellung von Nichtabstreitbarkeitsmaßnahmen. Bei diesen Szenarien hilft ein kennwortbasierter Authentifizierungsmechanismus bei der Sicherung der Kommunikationsebene, während gleichzeitig Nachrichtenauthentifizierung ermöglicht wird. Kennwortbasierte Sicherheit ist die Standardeinstellung für den Peerkanal.  
  
## <a name="token-types"></a>Tokentypen  
 Der Peerkanal akzeptiert einen einzelnen Tokentyp für eine starke Identifizierung: X.509-Zertifikate. Diese Zertifikate stellen ein starkes Identifikationsmodell bereit, das auf dem Typ der Authentifizierung und der Autorisierung basiert, der implementiert werden kann. Vertraulichkeit und Integrität stehen über Zertifikate auf einfache Art und Weise zur Verfügung. Verwendung und Bereitstellung von X.509-Zertifikaten können allerdings schwierig sein.  
  
 Der Peerkanal unterstützt darüber hinaus einfache Anwendungen durch die Verwendung von Kennwörtern. Anwendungen können wählen, ob schnelle und einfache Peergruppen auf Grundlage eines angegebenen Kennworts eingerichtet werden sollen. In diesem Fall entscheidet sich ein Gruppenbesitzer für ein Kennwort und gibt es an die Mitglieder weiter. Jedes Mitglied muss sich mit diesem Kennwort anmelden, damit es an der Sitzung teilnehmen kann. Kennwörter können nur verwendet werden, um Zugang zu einer Sitzung zu erhalten. Die Durchführung von Nachrichtenauthentifizierung über Kennwörter ist nicht möglich. Grund hierfür ist, dass ein symmetrischer Token, den sich eine Peergruppe teilt, für die Quellenauthentifizierung schwierig und ungeeignet ist.  
  
## <a name="security-model"></a>Sicherheitsmodell  
 Der Peerkanal bietet die Möglichkeit, die einzelnen Links zwischen Peers zu sichern. Dies bedeutet, dass eine Nachricht nie auf einem ungesicherten Link (aus Anwendungssicht) fließt. Intern wird jeder Link (ein Transportkanal zwischen zwei Peers) mit Transport Layer Security (TLS) gesichert. Wenn also ein Absender eine Nachricht aufstellt und sendet, wird diese über einen sicheren Transport zu allen unmittelbaren Peers gesendet, die auf die Nachricht zugreifen und sie wiederum über sichere Verbindungen an ihre unmittelbaren Peers senden. Diese Sicherheit funktioniert nur auf Transportebene und ist von den Nachrichtensicherheitsmodellen unabhängig.  
  
 Der Peerkanal bietet auch eine Möglichkeit, Nachrichten unabhängig von der verwendeten Transportsicherheit zu sichern. In diesem Modell wird die Nachricht mithilfe des Sicherheitstoken der Quelle an der Quelle gesichert, obwohl aktuell nur X.509-Zertifikate unterstützt werden. Die gesicherte Nachricht wird dann über das Peernetzwerk gesendet. Jeder empfangende Peer kann die Echtheit der Quelle bestätigen. Beachten Sie, dass die Nachricht gesichert wird, damit Vermittler diese nicht manipulieren können.  
  
 Um Vertraulichkeit zu erreichen, können Anwendungen Transportsicherheit mit starken Gruppenmitgliedschaftsschemas anwenden, um einen nicht berechtigten Zugriff auf die Nachricht zu unterbinden.  
  
 Der Peerkanal erfordert kein spezifisches Identifikationsmodell, solange die Anwendung einen der unterstützten Tokentypen auswählt. Anwendungen besitzen den Lebenszyklus dieser Identitäten und die Authentifizierungsenscheidungen vollständig.  
  
## <a name="see-also"></a>Siehe auch

- [Sichern von Peerkanalanwendungen](../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
- [Peerkanalbegriffe](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md)
- [Erstellen einer Peerkanalanwendung](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
