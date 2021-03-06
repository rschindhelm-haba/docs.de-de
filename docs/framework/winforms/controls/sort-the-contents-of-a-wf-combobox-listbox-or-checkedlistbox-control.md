---
title: 'Vorgehensweise: Sortieren des Inhalts eines ComboBox-, ListBox- oder CheckedListBox-Steuerelements in Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
ms.openlocfilehash: 4db1c133aabe39232a891183356e9c1b712f5cc8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150604"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Vorgehensweise: Sortieren des Inhalts eines ComboBox-, ListBox- oder CheckedListBox-Steuerelements in Windows Forms
Windows Forms-Steuerelemente werden nicht sortiert werden, wenn sie die Daten gebunden werden. Um sortierte Daten anzuzeigen, verwenden Sie eine Datenquelle, die das Sortieren unterstützt, und lassen Sie dann die Datenquelle sortiert das System. Datenquellen, die das Sortieren unterstützt, sind Ansichten, Data Manager anzuzeigen, und sortiert Sie Arrays.  
  
 Wenn das Steuerelement nicht datengebunden ist, können Sie sie sortieren.  
  
### <a name="to-sort-the-list"></a>Um die Liste sortieren  
  
1.  Legen Sie die `Sorted` -Eigenschaft auf `true`fest.  
  
     Diese Einstellung automatisch neu positioniert und alle vorhandenen Auflisten von Elementen in sortierter Reihenfolge.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [Datenbindung in Web Forms](../windows-forms-data-binding.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms](add-and-remove-items-from-a-wf-combobox.md)
- [Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [Steuerelemente in Windows Forms zum Auflisten von Optionen](windows-forms-controls-used-to-list-options.md)
