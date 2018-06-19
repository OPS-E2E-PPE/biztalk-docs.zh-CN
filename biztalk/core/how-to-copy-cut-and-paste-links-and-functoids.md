---
title: 如何复制、 剪切和粘贴链接和 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80b4792a-5ff6-4603-96cd-b3d3d530c12f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5eec0ddc164af936e1c3739e4da167753a6e58c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250365"
---
# <a name="how-to-copy-cut-and-paste-links-and-functoids"></a>如何复制、剪切和粘贴链接和 Functoid
BizTalk 映射器中的复制/剪切/粘贴功能使关系可重复使用。 本主题提供了在映射中复制、剪切和粘贴 functoid 和/或链接的分步说明。  
  
 如果希望重复使用一组 functoid 和/或链接，可以使用复制/粘贴功能。 如果希望从现有位置删除所选内容并将其移动到新位置，也可以使用剪切/粘贴功能。  
  
> [!IMPORTANT]
>  您是否觉得剪切/粘贴功能和移动功能很相似？ 这两者之间只有一点区别。 如果选择剪切，则所选内容中只有 functoid 和/或链接会从源网格页面中删除。 但如果选择移动，则关系（无论是否为所选内容）中的所有 functoid 和链接都会以递归方式从源网格页面中删除。 有关移动关系的详细信息，请参阅[如何移动关系网格页面之间](../core/how-to-move-a-relationship-between-grid-pages.md)。  
  
 当你复制/剪切 functoid 和/或链接的一组时、 functoid、 标签、 注释和常量值 （连同正确的占位符） 与关联组将保留。  
  
 您只能复制/剪切以下映射项：  
  
-   从源到目标架构的链接。  
  
-   从 functoid 到架构节点的链接（仅在同时选择了“functoid”及链接的情况下）。  
  
-   从 functoid 到 functoid 的链接（仅在同时选择了这两个 functoid 及链接的情况下）。  
  
 您可以从以下位置复制/剪切 functoid 和/或链接：  
  
-   在映射的同一网格页面中  
  
-   在同一映射中一个网格页面到另一个网格页面  
  
-   在同一 Visual Studio 实例中一个映射到另一个映射  
  
-   在 Visual Studio 的不同实例之间  
  
 可以撤消或重做剪切和粘贴操作。 有关详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。  
  
 此外，在粘贴链接时，您还必须考虑以下几点：  
  
-   仅当以下情况下才能粘贴源架构和目标架构之间的链接：正在粘贴链接的当前映射包含源节点和目标节点，其 XPath 与正在粘贴的链接的源节点和目标节点的 XPath 相同。  
  
-   仅当上述源节点和目标节点之间没有链接的情况下，才能粘贴源架构和目标架构之间的链接。  
  
-   仅当以下情况下才能将链接从 functoid 粘贴到目标架构：存在一个目标节点，其 XPath 与正在粘贴的链接的目标节点的 XPath 相同。  
  
-   仅当以下情况下才能将链接从源架构粘贴到 functoid：存在一个源节点，其 XPath 与正在粘贴的链接的源节点的 XPath 相同。  
  
> [!NOTE]
>  选择多个项目（链接和/或 functoid）时，如果其中某些项目无法剪切/复制，则在执行剪切/复制命令时，Visual Studio 中的状态栏将显示一条警告消息：“某些所选项目无法剪切/复制”。 消息还将显示相关详细信息。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
### <a name="to-copy-and-paste-a-relationship"></a>复制和粘贴关系  
  
1.  在解决方案资源管理器中，打开 BizTalk 项目，然后双击映射，将其在 BizTalk 映射器中打开。  
  
2.  选择您要复制的 functoid 和/或链接。  
  
    > [!TIP]
    >  可以通过以下方式进行选择：按下 Ctrl 键，然后选择所需的 functoid 和/或链接，或者拖放鼠标框住链接以形成一个矩形选区。  
  
    > [!NOTE]
    >  可以使用“功能区选择”操作选择多个链接和/或 functoid。 有关详细信息，请参阅[如何选择多个链接和 Functoid](../core/how-to-select-multiple-links-and-functoids.md)。  
  
3.  右键单击所选内容。 然后单击**复制**。 也可以在键盘上按 Ctrl+C。  
  
    > [!NOTE]
    >  键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
4.  将光标放在要粘贴所选内容的地方。  
  
5.  在网格页上，右键单击，然后单击**粘贴**。 也可以选择并按键盘上的 Ctrl+V。 所选内容的副本会显示在新位置。  
  
### <a name="to-cut-and-paste-a-relationship"></a>剪切和粘贴关系  
  
1.  在解决方案资源管理器中，打开 BizTalk 项目，然后双击映射，将其在 BizTalk 映射器中打开。  
  
2.  选择您要剪切的 functoid 和/或链接。  
  
    > [!TIP]
    >  可以通过以下方式进行选择：按下 Ctrl 键，然后选择所需的 functoid 和/或链接，或者拖放鼠标框住链接以形成一个矩形选区。  
  
    > [!NOTE]
    >  可以使用“功能区选择”操作选择多个链接和/或 functoid。 有关详细信息，请参阅[如何选择多个链接和 Functoid](../core/how-to-select-multiple-links-and-functoids.md)。  
  
3.  右键单击所选内容，并依次**剪切**。 也可以在键盘上按 Ctrl+X。  
  
    > [!NOTE]
    >  键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
4.  将光标放在要粘贴所选内容的地方。  
  
5.  在网格页上，右键单击，然后单击**粘贴**。 也可以选择并按键盘上的 Ctrl+V。 所选内容将从现有位置中删除，并显示在新位置中。