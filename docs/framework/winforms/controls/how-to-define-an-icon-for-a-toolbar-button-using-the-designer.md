---
title: 'Vorgehensweise: Definieren eines Symbols für eine Symbolleistenschaltfläche mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: 6657a9bbb850a24ae47be11854d6affd2a02f9b7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118273"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a>Vorgehensweise: Definieren eines Symbols für eine Symbolleistenschaltfläche mithilfe des Designers
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.ToolStrip>-Steuerelement das <xref:System.Windows.Forms.ToolBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ToolBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 <xref:System.Windows.Forms.ToolBar> Schaltflächen sind Symbole, die darin enthaltenen zur leichteren Identifizierung von Benutzern anzeigen. Erfolgt dies durch das Hinzufügen von Bildern, um die <xref:System.Windows.Forms.ImageList> -Komponente und ordnet ihm dabei die <xref:System.Windows.Forms.ToolBar> Steuerelement.  
  
 Erfordert das folgende Verfahren eine **Windows-Anwendung** Projekt ein Formular mit einer <xref:System.Windows.Forms.ToolBar> Steuerelement und ein <xref:System.Windows.Forms.ImageList> Komponente. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a>Ein Symbol für eine Symbolleisten-Schaltfläche zur Entwurfszeit festlegen  
  
1.  Hinzufügen von Bildern, um die <xref:System.Windows.Forms.ImageList> Komponente. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen oder Entfernen von ImageList-Bildern mithilfe des Designers](how-to-add-or-remove-imagelist-images-with-the-designer.md).  
  
2.  Wählen Sie die <xref:System.Windows.Forms.ToolBar> Steuerelement auf Ihrem Formular.  
  
3.  In der **Eigenschaften** legen die <xref:System.Windows.Forms.ToolBar> des Steuerelements <xref:System.Windows.Forms.ToolBar.ImageList%2A> Eigenschaft, um die <xref:System.Windows.Forms.ImageList> Komponente.  
  
4.  Klicken Sie auf die <xref:System.Windows.Forms.ToolBar> des Steuerelements <xref:System.Windows.Forms.ToolBar.Buttons%2A> Eigenschaft, um auszuwählen, und klicken Sie auf die Auslassungspunkte (![VisualStudioEllipsesButton-bildschirmabbildung](../media/vbellipsesbutton.png "VbEllipsesButton")) die Schaltfläche, um die **ToolBarButton Auflistungs-Editor**.  
  
5.  Verwenden der **hinzufügen** Schaltfläche zum Hinzufügen von Schaltflächen der <xref:System.Windows.Forms.ToolBar> Steuerelement.  
  
6.  In der **Eigenschaften** im Bereich auf der rechten Seite des angezeigten Fenster die **ToolBarButton Auflistungs-Editor**legen die <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> Eigenschaft jedes Symbolleisten-Schaltfläche, um einen der Werte in der Liste der gezeichnet wird, von den Images, die Sie hinzugefügt, um haben die <xref:System.Windows.Forms.ImageList> Komponente.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolBar>
- [Vorgehensweise: Auslösen von Menüereignissen für Symbolleistenschaltflächen](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [ToolBar-Steuerelement](toolbar-control-windows-forms.md)
- [ImageList-Komponente](imagelist-component-windows-forms.md)
