---
title: "如何撤消或重做用户操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1cb3708e-a9c2-4795-aba0-9c6d9635e08c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6f47071ee003a896b66120c0fd81a121ab73230
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-undo-or-redo-user-operations"></a>如何撤消或重做用户操作
撤消/重做的支持，而另一个可用性帮助提供通过 BizTalk 映射程序。 如果您对所做的更改不满意或者执行了误操作，可以使用撤消功能来返回到之前的“未处理”状态，并从此处继续。 重做，可重新应用已撤消的编辑操作。 本主题提供有关操作的您可以撤消/重做的信息。  
  
> [!IMPORTANT]
>  只有当您执行完至少一个编辑代码图上的操作，则可以撤消操作。 重做是不可用，除非你已使用撤消命令。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
## <a name="what-can-you-undoredo"></a>新增功能可以你撤消/重做？  
 你可以撤消/重做所有的编辑操作。 可以撤消/重做的操作如下所示：  
  
-   剪切/复制/粘贴 functoid 和/或链接  
  
     您无法撤消操作或重做通过简单地选择并将其复制的任意数量的项 (链接/functoid)。 复制功能不会更改在地图上的任何内容。  
  
    > [!NOTE]
    >  有关如何对剪切/复制/粘贴 functoid 的信息，请参阅[如何复制、 剪切和粘贴 Functoid](../core/how-to-copy-cut-and-paste-a-functoid.md)。 有关如何剪切/复制/粘贴 functoid 和链接的详细信息，请参阅[如何复制、 剪切、 粘贴链接和 Functoid](../core/how-to-copy-cut-and-paste-links-and-functoids.md)。  
  
-   将源节点链接到目标节点上或到 functoid、 与另一个 functoid functoid 或到目标节点 functoid 源节点  
  
-   删除 functoid 和/或链接  
  
-   将所选的链接和 functoid 移动到另一个网格页  
  
-   添加、 移动、 重新排序，或删除网格页  
  
    > [!NOTE]
    >  移动、 重新排序，或删除网格页将添加的信息，请参阅[如何重新排序网格页](../core/how-to-reorder-grid-pages.md)。  
  
-   在创建地图时选择源和目标架构  
  
-   替换源/目标架构  
  
    > [!NOTE]
    >  有关如何替换源/目标架构的信息，请参阅[如何替换架构](../core/how-to-replace-schemas.md)。  
  
-   配置 functoid 的输入的参数  
  
    > [!NOTE]
    >  有关详细信息，请参阅[如何配置 Functoid 输入参数](../core/how-to-configure-functoid-input-parameters.md)。  
  
-   链接的/编辑设置的标签  
  
    > [!NOTE]
    >  有关详细信息，请参阅[如何标记链接](../core/how-to-label-a-link.md)。  
  
-   设置/编辑 functoid 的标签和/或注释  
  
    > [!NOTE]
    >  有关详细信息，请参阅[如何标记和注释 Functoid](../core/how-to-label-and-comment-a-functoid.md)。  
  
-   忽略链接和脚本类型优先级映射器网格的属性的命名空间。  
  
-   通过将链接的一个终结点中的节点或 functoid 到另一种节点或 functoid 替换链接。  
  
    > [!NOTE]
    >  有关详细信息，请参阅[如何创建链接](../core/how-to-create-links.md)。  
  
-   执行中的多个修改**配置\<Functoid > Functoid**对话框中，将被视为单个操作。  
  
-   拖动 functoid(s) 和/或映射器网格中的链接。  
  
    > [!NOTE]
    >  有关详细信息，请参阅[如何移动关系网格页面之间](../core/how-to-move-a-relationship-between-grid-pages.md)。  
  
## <a name="how-can-you-undoredo-any-operation"></a>如何可以你撤消/重做的任何操作？  
 你可以撤消/重做操作通过以下方式之一：  
  
-   从 Visual Studio**编辑**菜单。  
  
-   单击工具栏上的撤消和重做图标。  
  
-   按 CTRL + Z 表示撤消和 CTRL + Y 重做的。  
  
## <a name="see-also"></a>另请参阅  
 [使用网格页](../core/working-with-grid-pages.md)