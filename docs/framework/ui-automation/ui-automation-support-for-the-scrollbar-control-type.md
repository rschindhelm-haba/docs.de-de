---
title: Benutzeroberflächenautomatisierungs-Unterstützung für den ScrollBar-Steuerelementtyp
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Scroll Bar control type
- control types, Scroll Bar
- Scroll Bar control type
ms.assetid: 329891d7-b609-49e6-920a-09ea8a627d07
ms.openlocfilehash: b9716cd33a3d030121f738fc896d90186791ca2b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081878"
---
# <a name="ui-automation-support-for-the-scrollbar-control-type"></a>Benutzeroberflächenautomatisierungs-Unterstützung für den ScrollBar-Steuerelementtyp
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Unterstützung für den Steuerelementtyp „ScrollBar“. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]umfasst ein Steuerelementtyp eine Reihe von Bedingungen, die ein Steuerelement erfüllen muss, damit die <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> -Eigenschaft verwendet werden kann. Die Bedingungen schließen bestimmte Richtlinien für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaftswerte und Steuerelementmuster ein.  
  
 Mit ScrollBar-Steuerelementen können Sie einen Bildlauf für den Inhalt eines Fenster- oder Elementcontainers ausführen. Das Steuerelement besteht aus einer Gruppe von Schaltflächen und einem Thumb-Steuerelement.  
  
 In den folgenden Abschnitten werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, -Eigenschaften, -Steuerelementmuster und -Ereignisse definiert, die für den Steuerelementtyp „ScrollBar“ erforderlich sind. Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Anforderungen gelten für alle Listensteuerelemente in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]oder [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Erforderliche Benutzeroberflächenautomatisierungs-Struktur  
 In der folgenden Tabelle werden die Steuerelementansicht und die Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur für ScrollBar-Steuerelemente sowie die möglichen Inhalte der Ansichten beschrieben. Weitere Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur finden Sie unter [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).  
  
|Steuerelementansicht|Inhaltsansicht|  
|------------------|------------------|  
|ScrollBar<br /><br /> -Button (2 oder 4)<br />-Thumb (0 oder 1)|Nicht zutreffend. Das Bildlaufleisten-Steuerelement enthält keinen Inhalt.|  
  
 Das Bildlaufleisten-Steuerelement umfasst immer drei bis fünf untergeordnete Elemente. Da die Teilstruktur mehrere Schaltflächen enthält, müssen Sie einen bestimmten <xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty> -Wert für jedes Element festlegen, sodass diese von Testautomatisierungstools erkannt werden können.  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Erforderliche Benutzeroberflächenautomatisierungs-Eigenschaften  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaften, deren Werte oder Definitionen für Bildlaufleisten-Steuerelemente besonders relevant sind. Beachten Sie, dass ein Bildlaufleisten-Steuerelement keinen Inhalt enthält. Seine Funktionalität wird über das von dem Container unterstützte Scroll-Steuerelementmuster verfügbar gemacht, für den der Bildlauf ausgeführt wird.  
  
 Weitere Informationen zu Eigenschaften [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -finden Sie unter [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Eigenschaft|Wert|Hinweise|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Siehe Hinweise.|Der Wert dieser Eigenschaft muss für alle Steuerelemente in einer Anwendung eindeutig sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Siehe Hinweise.|Das äußere Rechteck, das das gesamte Steuerelement enthält.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Siehe Hinweise.|Wenn das Steuerelement den Tastaturfokus erhalten kann, muss es diese Eigenschaft unterstützen.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|`Null`|Das Bildlaufleisten-Steuerelement enthält keine Inhaltselemente, und die `NameProperty` muss nicht festgelegt werden.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Keine Zahl.|Das Bildlaufleisten-Steuerelement enthält keine durch Klicken aktivierbaren Punkte.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|Bildlaufleisten weisen keine Bezeichnungen auf.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|ScrollBar|Dieser Wert ist für alle Frameworks gleich. Von Bildlaufleisten, die wie Schieberegler funktionieren, muss der Slider-Steuerelementtyp verwendet werden.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|„Bildlaufleiste“|Lokalisierte Zeichenfolge, die dem Button-Steuerelementtyp entspricht.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|False|Das Bildlaufleisten-Steuerelement ist nie ein Inhaltselement. Wenn es sich bei der Bildlaufleiste um ein eigenständiges Steuerelement handelt, muss es dem Slider-Steuerelementtyp entsprechen und `ControlType.Slider` für die `ControlType` -Eigenschaft zurückgeben.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Die Bildlaufleiste muss immer ein Steuerelement sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.OrientationProperty>|True|Die horizontale oder vertikale Ausrichtung muss vom Bildlaufleisten-Steuerelement immer verfügbar gemacht werden.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Erforderliche Benutzeroberflächenautomatisierungs-Steuerelementmuster  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Steuerelementmuster, die von Bildlaufleisten-Steuerelementen unterstützt werden müssen. Weitere Informationen zu Steuerelementmustern finden Sie unter [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md). Beachten Sie, dass Steuerelementmuster nicht unterstützt werden, wenn eine Bildlaufleiste nur über eine Maus als Steuerelement verwendet wird. Wenn es in einer Anwendung als Schieberegler-Steuerelement verwendet wird, muss ihm der Slider-Steuerelementtyp zugewiesen werden.  
  
|Steuerelementmuster|Unterstützung|Hinweise|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollProvider>|Nie|Das Scroll-Steuerelementmuster wird auf der Bildlaufleiste nie direkt unterstützt.|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider>|Variabel|Diese Funktionalität muss nur unterstützt werden, wenn das Scroll-Steuerelementmuster von dem Container, der die Bildlaufleiste enthält, nicht unterstützt wird.|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Erforderliche Benutzeroberflächenautomatisierungs-Ereignisse  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignisse, die von allen Bildlaufleisten-Steuerelementen unterstützt werden müssen. Weitere Informationen zu Ereignissen finden Sie unter [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] event|Unterstützung/Wert|Hinweise|  
|---------------------------------------------------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> Durch geänderte Eigenschaften ausgelöste Ereignis.|Erforderlich|Keiner|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> Durch geänderte Eigenschaften ausgelöste Ereignis.|Erforderlich|Keiner|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> Durch geänderte Eigenschaften ausgelöste Ereignis.|Erforderlich|Keiner|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> Durch geänderte Eigenschaften ausgelöste Ereignis.|Nie|Keiner|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> Durch geänderte Eigenschaften ausgelöste Ereignis.|Nie|Keiner|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> Durch geänderte Eigenschaften ausgelöste Ereignis.|Nie|Keiner|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> Durch geänderte Eigenschaften ausgelöste Ereignis.|Nie|Keiner|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> Durch geänderte Eigenschaften ausgelöste Ereignis.|Nie|Keiner|  
|<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> Durch geänderte Eigenschaften ausgelöste Ereignis.|Nie|Keiner|  
|<xref:System.Windows.Automation.RangeValuePatternIdentifiers.ValueProperty> Durch geänderte Eigenschaften ausgelöste Ereignis.|Variabel|Keiner|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Erforderlich|Keiner|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Erforderlich|Keiner|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Automation.ControlType.ScrollBar>
- [Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)
- [Übersicht über die Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-overview.md)
