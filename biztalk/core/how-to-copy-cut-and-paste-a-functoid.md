---
title: "如何复制、 剪切和粘贴 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 825847e4-87db-4b40-8e5d-5b5b1c79c6de
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9af3662fb866eb09c1dcb2516279ca097cc998f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-copy-cut-and-paste-a-functoid"></a>如何复制、 剪切和粘贴 Functoid
BizTalk 映射器中的复制/剪切/粘贴功能使 functoid 可重复使用。 在映射中，您可以将一个或多个 functoid 从一个网格页复制、剪切和粘贴到另一个网格页。 本主题提供了执行这些操作的分步说明。  
  
 当您希望能够重复使用 functoid 时，可以使用复制/粘贴功能。 如果希望从现有位置删除 functoid 并将其移动到新位置，则可以使用剪切/粘贴功能。  
  
> [!IMPORTANT]
>  当您选择复制 functoid 时，该 functoid、其标签、注释和输入的常数，以及占位符索引都会被复制。 同样，当您选择剪切 functoid 时，该 functoid、其标签、注释和输入的常数，以及占位符索引也都会被剪切。 但是，当您粘贴（在选择剪切之后）所选内容时，只会保留 functoid，会删除孤立的链接。 标签、注释、输入的常数和占位符索引都不会被保留。  
  
 如果您只选择 functoid（链接到另一个 functoid 或架构节点），则只有该 functoid 会被剪切或复制（不包括这些链接）。 如果您剪切的 functoid 链接到映射中的其他 functoid 或链接到架构节点，则会删除指向这个剪切的 functoid 的链接。  
  
 您可以复制/剪切以下位置中的 functoid：  
  
-   在映射的同一网格页面中  
  
-   在同一映射中一个网格页面到另一个网格页面  
  
-   Visual Studio 的一个实例到另一个实例  
  
 可以撤消或重做剪切和粘贴操作。 有关详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
### <a name="to-copy-and-paste-a-functoid"></a>复制并粘贴 functoid  
  
1.  在解决方案资源管理器中，打开 BizTalk 项目，然后双击映射，将其在 BizTalk 映射器中打开。  
  
2.  选择要复制的 functoid。 若要选择多个 functoid，请单击一个 functoid，按下 Ctrl 键，然后单击其他 functoid。  
  
    > [!NOTE]
    >  可以使用“功能区选择”操作选择多个链接和/或 functoid。 有关详细信息，请参阅[如何选择多个链接和 Functoid](../core/how-to-select-multiple-links-and-functoids.md)。  
  
3.  右键单击所选内容，并依次**复制**。 或者，你可以单击**复制**从 Visual Studio**编辑**菜单或键盘上的按 CTRL + C。  
  
    > [!NOTE]
    >  键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
4.  将光标放在要粘贴 functoid 的地方。  
  
5.  在网格页上，右键单击，然后单击**粘贴**。 或者，你可以单击**粘贴**从 Visual Studio**编辑**菜单或键盘上的按 CTRL + V。 选定的 functoid 或 functoid 组的副本会显示在新位置。  
  
### <a name="to-cut-and-paste-a-functoid"></a>剪切并粘贴 functoid  
  
1.  在解决方案资源管理器中，打开 BizTalk 项目，然后双击映射，将其在 BizTalk 映射器中打开。  
  
2.  选择要剪切的 functoid。 若要选择多个 functoid，请单击一个 functoid，按下 Ctrl 键，然后单击其他 functoid。  
  
3.  右键单击所选内容，并依次**剪切**。 或者，你可以单击**剪切**从 Visual Studio**编辑**菜单或键盘上的按 CTRL + X。  
  
    > [!NOTE]
    >  键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
4.  将光标放在要粘贴 functoid 的地方。  
  
5.  在网格页上，右键单击，然后单击**粘贴**。 或者，你可以单击**粘贴**从 Visual Studio**编辑**菜单或键盘上的按 CTRL + V。 选定的 functoid 或 functoid 组会从现有位置删除并显示在新位置中。  
  
## <a name="see-also"></a>另请参阅  
 [使用 Functoid 创建更复杂的映射](../core/using-functoids-to-create-more-complex-mappings.md)