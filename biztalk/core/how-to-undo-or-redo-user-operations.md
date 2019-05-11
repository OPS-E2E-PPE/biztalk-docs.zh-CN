---
title: 如何撤消或重做用户操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1cb3708e-a9c2-4795-aba0-9c6d9635e08c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ef4122e31bae1c3bd0e107b5a5bb8a4c7405e42
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383684"
---
# <a name="how-to-undo-or-redo-user-operations"></a>如何撤消或重做用户操作
有关撤消/重做支持但另一个可用性辅助工具提供的 BizTalk 映射器。 如果您感到不满意的修改进行，或如果您错误地进行更改，可以使用撤消来逐渐回到前面"未处理"状态，并从此处继续。 重做，可重新应用已撤销的编辑操作。 本主题提供有关，您可以撤消/重做操作的信息。  
  
> [!IMPORTANT]
>  只有当您已执行至少一个编辑代码图上的操作，您可以撤消操作。 重做是不可用，除非已使用撤消命令。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
## <a name="what-can-you-undoredo"></a>什么可以你撤消/重做？  
 您可以撤消/重做所有编辑操作。 可以是撤消/重做的操作如下所示：  
  
-   剪切/复制/粘贴 functoid 和/或链接  
  
     无法撤消或重做只是选择并将其复制任意数量的项 (链接 /functoid)。 复制函数不会更改代码图上的任何内容。  
  
    > [!NOTE]
    >  有关如何剪切/复制/粘贴 functoid 的信息，请参阅[如何复制、 剪切和粘贴 Functoid](../core/how-to-copy-cut-and-paste-a-functoid.md)。 有关如何剪切/复制/粘贴 functoid 和链接的详细信息，请参阅[如何复制、 剪切和粘贴链接和 Functoid](../core/how-to-copy-cut-and-paste-links-and-functoids.md)。  
  
-   将源节点链接到目标节点或从源节点到 functoid、 functoid 到另一个 functoid 或 functoid 到目标节点  
  
-   删除 functoid 和/或链接  
  
-   将所选的链接和 functoid 移动到另一个网格页  
  
-   添加、 移动、 重新排序，或删除网格页  
  
    > [!NOTE]
    >  有关添加的信息，移动、 重新排序，或删除网格页，请参阅[如何重排网格页顺序](../core/how-to-reorder-grid-pages.md)。  
  
-   创建映射时选择源和目标架构  
  
-   替换源/目标架构  
  
    > [!NOTE]
    >  有关如何替换源/目标架构的信息，请参阅[如何替换架构](../core/how-to-replace-schemas.md)。  
  
-   配置输入的参数的 functoid  
  
    > [!NOTE]
    >  有关详细信息，请参阅[如何配置 Functoid 输入参数](../core/how-to-configure-functoid-input-parameters.md)。  
  
-   设置/编辑链接的标签  
  
    > [!NOTE]
    >  有关详细信息，请参阅[如何标记链接](../core/how-to-label-a-link.md)。  
  
-   设置/编辑标签和/或 functoid 的注释  
  
    > [!NOTE]
    >  有关详细信息，请参阅[如何标签和注释 Functoid](../core/how-to-label-and-comment-a-functoid.md)。  
  
-   忽略的映射器网格的链接和脚本类型优先级属性的命名空间。  
  
-   通过从一个节点或 functoid 对其他节点或 functoid 拖动一个链接的终结点替换链接。  
  
    > [!NOTE]
    >  有关详细信息，请参阅[如何创建链接](../core/how-to-create-links.md)。  
  
-   执行在多个修改**配置\<Functoid\> Functoid**对话框中，将被视为单个操作。  
  
-   拖动 functoid 和/或映射器网格中的链接。  
  
    > [!NOTE]
    >  有关详细信息，请参阅[如何移动网格页面之间的关系](../core/how-to-move-a-relationship-between-grid-pages.md)。  
  
## <a name="how-can-you-undoredo-any-operation"></a>如何可以你撤消/重做的任何操作？  
 您可以撤消/重做操作中的以下方法之一：  
  
-   从 Visual Studio**编辑**菜单。  
  
-   单击工具栏上的撤消和重做图标。  
  
-   按 CTRL + Z 进行撤消，CTRL + Y 进行重做。  
  
## <a name="see-also"></a>请参阅  
 [使用网格页](../core/working-with-grid-pages.md)