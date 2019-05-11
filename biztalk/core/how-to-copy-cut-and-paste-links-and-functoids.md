---
title: 如何复制、 剪切和粘贴链接和 Functoid |Microsoft Docs
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
ms.openlocfilehash: b7af51d8bf1f2e7686647ccdf286402179d19a0b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385651"
---
# <a name="how-to-copy-cut-and-paste-links-and-functoids"></a>如何复制、 剪切和粘贴链接和 Functoid
在 BizTalk 映射器中的复制/剪切/粘贴功能使关系的可重用性。 本主题提供复制、 剪切和粘贴 functoid 和/或链接在映射中的分步说明。  
  
 当你想要重复使用一组 functoid 和/或链接时，可以使用复制/粘贴功能。 并且，当你想要从现有位置删除所选内容并将其移到新位置，可以使用剪切/粘贴功能。  
  
> [!IMPORTANT]
>  您是否觉得剪切/粘贴功能和移动功能很相似？ 没有区别。 如果选择剪切，只有 functoid 和/或所选内容中的链接是从从源网格页面中删除。 但是，当你选择移动，所有 functoid 和链接中的关系 （无论所选内容的），以递归方式，从从源网格页面中删除。 有关移动关系的详细信息，请参阅[如何移动网格页面之间的关系](../core/how-to-move-a-relationship-between-grid-pages.md)。  
  
 当你复制/剪切一组 functoid 和/或链接时，functoid、 标签、 注释和常数值 （以及正确的占位符） 与关联组会保留。  
  
 您可以复制/剪切以下映射项：  
  
- 将链接从源到目标架构。  
  
- 链接从 functoid 到架构节点，当且仅当及链接还选择了"functoid"。  
  
- 链接从 functoid 到 functoid，当且仅当选择这两个 functoid 及链接。  
  
  您可以复制/剪切 functoid 和/或中的链接：  
  
- 映射的同一网格页中  
  
- 到相同的映射中另一个网格页  
  
- 一个映射到其他 Visual Studio 的同一实例中  
  
- Visual Studio 的不同实例中  
  
  可以撤消或重做剪切和粘贴操作。 有关详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。  
  
  除此之外，粘贴链接时必须考虑以下几点：  
  
- 当且仅当当前映射，其中正在粘贴链接，包含源节点，以及其 XPath 与正在粘贴的链接的源和目标节点的 XPath 相同的目标节点才能粘贴源和目标架构之间的链接。  
  
- 当且仅当上述源和目标节点之间没有现有链接，才能粘贴源和目标架构之间的链接。  
  
- 可以粘贴链接从 functoid 到目标架构，当且仅当存在目标节点，其 XPath 与正在粘贴的链接的目标节点的 XPath 相同。  
  
- 可以粘贴 functoid 的链接源架构中，当且仅当存在源节点，其 XPath 与正在粘贴的链接的源节点的 XPath 相同。  
  
> [!NOTE]
>  时，其中一些无法剪切/复制选择多个项 （链接和/或 functoid），然后在执行剪切/复制命令中，Visual Studio 中的状态栏显示一条警告消息"某些所选项目无法剪切/复制。" 消息还将显示相关详细信息。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
### <a name="to-copy-and-paste-a-relationship"></a>若要复制和粘贴关系  
  
1.  在解决方案资源管理器，打开 BizTalk 项目中，，然后双击要打开 BizTalk 映射器中的映射。  
  
2.  选择 functoid 和/或你想要复制的链接。  
  
    > [!TIP]
    >  您可以选择通过按住 CTRL 键，然后选择所需的 functoid 和/或链接或通过拖放鼠标链接以形成一个矩形选区。  
  
    > [!NOTE]
    >  "功能区选择"操作可用于选择多个链接和/或 functoid。 有关详细信息，请参阅[如何选择多个链接和 Functoid](../core/how-to-select-multiple-links-and-functoids.md)。  
  
3.  右键单击所选内容。 然后单击**复制**。 或者，也可以在键盘上按 CTRL + C。  
  
    > [!NOTE]
    >  键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
4.  将光标置于想要粘贴所选内容。  
  
5.  在网格页上，右键单击，然后单击**粘贴**。 或者，可以选择，并在键盘上按 CTRL + V。 所选内容的副本会显示在新位置。  
  
### <a name="to-cut-and-paste-a-relationship"></a>若要剪切和粘贴关系  
  
1.  在解决方案资源管理器，打开 BizTalk 项目中，，然后双击要打开 BizTalk 映射器中的映射。  
  
2.  选择 functoid 和/或你想要剪切的链接。  
  
    > [!TIP]
    >  您可以选择通过按住 CTRL 键，然后选择所需的 functoid 和/或链接或通过拖放鼠标链接以形成一个矩形选区。  
  
    > [!NOTE]
    >  "功能区选择"操作可用于选择多个链接和/或 functoid。 有关详细信息，请参阅[如何选择多个链接和 Functoid](../core/how-to-select-multiple-links-and-functoids.md)。  
  
3.  右键单击所选内容，然后依次**剪切**。 此外，您可以在键盘上按 CTRL + X。  
  
    > [!NOTE]
    >  键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
4.  将光标置于想要粘贴所选内容。  
  
5.  在网格页上，右键单击，然后单击**粘贴**。 或者，可以选择，并在键盘上按 CTRL + V。 所选内容从现有位置删除并显示在新位置。