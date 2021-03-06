---
title: Verwalten von Docker-produktionsumgebungen
description: Lernen Sie wichtige Punkte für die Verwaltung einer produktionsumgebung containerbasierte kennen.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: f3cf9bc281e94f342cecb1083d886daba03c019d
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2019
ms.locfileid: "56836616"
---
# <a name="manage-production-docker-environments"></a>Verwalten von Docker-produktionsumgebungen

Clusterverwaltung und Orchestrierung ist der Prozess, eine Gruppe von Hosts zu steuern. Dies kann beinhalten, hinzufügen und Entfernen von Hosts in einem Cluster, das Abrufen von Informationen zu den aktuellen Zustand des Hosts und Containern, und starten und Beenden von Prozessen. Clusterverwaltung und Orchestrierung sind eng mit planen, da der Scheduler den Zugriff auf jedem Host im Cluster benötigen, um Dienste zu planen. Aus diesem Grund wird das gleiche Tool häufig für beide Zwecke verwendet.

## <a name="container-service-and-management-tools"></a>Container Service und Verwaltungstools

Container Service bietet eine schnelle Bereitstellung von Lösungen für beliebte Open-Source-Container clustering und die Orchestrierung. Docker-Images verwendet, um sicherzustellen, dass Ihre Anwendungscontainer vollständig portierbar sind. Mithilfe von Container Service können Sie DC/OS (unterstützt von Mesosphere und Apache Mesos) bereitstellen und Docker Swarm-Clustern mit Azure Resource Manager-Vorlagen oder im Azure-Portal um sicherzustellen, dass Sie diese Anwendungen auf Tausende skalieren können – sogar Tausende – von Container.

Sie diesen Clustern mit Azure Virtual Machine Scale Sets bereitstellen, und die Cluster profitieren Sie von Azure-Netzwerk und Speicher-Angebote. Für den Zugriff auf Container Service benötigen Sie ein Azure-Abonnement. Mit Container Service können Sie professionelle Funktionen von Azure nutzen und gleichzeitig die Anwendungsportabilität, einschließlich der auf den orchestrierungsebenen.

Tabelle 6 – 1 listet allgemeiner Verwaltungstools, die im Zusammenhang mit ihrer orchestratoren, Planer und clustering-Plattform.

**Tabelle 6 – 1**. Docker-Verwaltungstools

| Verwaltungstools | Beschreibung | Verwandte orchestratoren |
|------------------|-------------|-----------------------|
| [Azure Monitor für Container](https://docs.microsoft.com/azure/monitoring/monitoring-container-insights-overview) | Azure reserviert die Kubernetes-Verwaltungstool | Azure Kubernetes-Dienste (AKS) |
| [Kubernetes Web UI (dashboard)](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) | Kubernetes-Verwaltungstool, können überwachen und Verwalten von lokalen Kubernetes-cluster | Azure Kubernetes Service (AKS)<br/>Lokale Kubernetes |
| [Azure-Portal für Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal)<br/>[Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) | Online und desktop-Version für die Verwaltung von Service Fabric-Cluster in Azure, lokal, lokalen Entwicklungs-und andere clouds | Azure Service Fabric |
| [Containerüberwachung (Log Analytics)](https://docs.microsoft.com/azure/azure-monitor/insights/containers) | Allgemeine Container Management y-Lösung zur Überwachung. Kubernetes-Cluster über verwalten [Azure Monitor für Container](https://docs.microsoft.com/azure/monitoring/monitoring-container-insights-overview). | Azure Service Fabric<br/>Azure Kubernetes Service (AKS)<br/>Mesosphere DC/OS und andere. |

## <a name="azure-service-fabric"></a>Azure Service Fabric

Eine weitere Option für die Cluster-Bereitstellung und Verwaltung ist Azure Service Fabric. [Service Fabric](https://azure.microsoft.com/services/service-fabric/) ist eine Microservices-Plattform von Microsoft, die containerorchestrierung als auch für Entwickler enthält Programmiermodelle nutzen, um hochgradig skalierbare microserviceanwendungen erstellen. Service Fabric unterstützt Docker in Linux und Windows-Container und können in Windows und Linux-Servern ausgeführt.

Service Fabric-Management-Tools für folgen:

- [Azure-Portal für Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal) clusterbezogenen Vorgänge (erstellen/aktualisieren/löschen) einen Cluster oder konfigurieren die Infrastruktur (virtuelle Computer, Load Balancer, Netzwerke usw.)

- [Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) ist ein spezielles-Webbenutzeroberfläche als auch Multi-Plattform-Desktoptool, die Einblicke und bestimmte Vorgänge auf dem Service Fabric-Cluster, aus der Sicht der Knoten/VMs und aus der Sicht Anwendungen und Dienste bereitstellt.

>[!div class="step-by-step"]
>[Zurück](run-microservices-based-applications-in-production.md)
>[Weiter](monitor-containerized-application-services.md)
