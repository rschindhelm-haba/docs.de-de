---
title: 'Vorgehensweise: Ausrichten und Strecken eines Steuerelements in einem TableLayoutPanel-Steuerelement'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
ms.openlocfilehash: c0bcf91d358d233b5b1d2e300d63112303e87a09
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59095400"
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a>Vorgehensweise: Ausrichten und Strecken eines Steuerelements in einem TableLayoutPanel-Steuerelement
Sie können das Ausrichten und Dehnen von Steuerelementen in einem <xref:System.Windows.Forms.TableLayoutPanel> mit der <xref:System.Windows.Forms.Control.Anchor%2A> und <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaften.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-align-and-stretch-a-control"></a>Ausrichten und Strecken eines Steuerelements  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** in die linke obere Zelle des der <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement. Die <xref:System.Windows.Forms.Button> Steuerelement in der Zelle zentriert ist.  
  
3.  Legen Sie den Wert, der die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft `Left,Right`. Die <xref:System.Windows.Forms.Button> -Steuerelement wird an die Breite der Zelle angepasst.  
  
4.  Legen Sie den Wert, der die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft `Top,Bottom`. Die <xref:System.Windows.Forms.Button> -Steuerelement wird an die Höhe der Zelle angepasst.  
  
5.  Legen Sie den Wert, der die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Fill>. Die <xref:System.Windows.Forms.Button> Steuerelement wird erweitert, um die gesamte Zelle ausfüllt.  
  
6.  Legen Sie den Wert, der die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.None>. Die <xref:System.Windows.Forms.Button> Steuerelement gibt Sie zurück auf seine ursprüngliche Größe und wird in der oberen linken Ecke der Zelle verschoben. Die **Windows Forms-Designer** hat die <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft `Top, Left`.  
  
7.  Legen Sie den Wert, der die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft `Bottom,Right`. Die <xref:System.Windows.Forms.Button> -Steuerelement wird in der unteren rechten Ecke der Zelle.  
  
8.  Legen Sie den Wert, der die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft <xref:System.Windows.Forms.AnchorStyles.None>. Die <xref:System.Windows.Forms.Button> Steuerelement verschoben wird, in die Mitte der Zelle.  
  
## <a name="see-also"></a>Siehe auch

- [TableLayoutPanel-Steuerelement](tablelayoutpanel-control-windows-forms.md)
