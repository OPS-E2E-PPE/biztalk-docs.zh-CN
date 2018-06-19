---
title: 类型的链接 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- compiler directives, links
- elastic links [maps]
- maps, links
- BizTalk Mapper, links
- partial links [maps]
- fixed links [maps]
ms.assetid: 348fae77-2e25-4b79-93bb-d42f3d18a3f7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64d6f1039e65989a2de0243a1a9a09f30165e603
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286821"
---
# <a name="types-of-links"></a>类型的链接
以下列表概括列出了 BizTalk 映射器中各种类型的可用链接：  
  
-   **弹性的链接。** 术语“弹性”适用于在连接链接的两端之前所创建的链接。 例如，如果从源架构内的字段中拖动一个链接，但尚未将其连接到目标架构中的对应字段，则该链接为弹性链接。 当你完成连接时，弹性的链接将变为固定的链接。  
  
     可以将每个端点的链接拖动到另一个节点或 functoid。 有关链接替换的详细信息，请参阅[如何创建链接](../core/how-to-create-links.md)。  
  
-   **固定的链接。** 术语“固定”适用于已显式构造为表示值从源实例消息到目标实例消息的移动，或至少为该移动的一部分的链接。 固定直接连接的链接**记录**或**字段**到源架构中的节点**记录**或**字段**目标中的节点架构表示直接复制的数据在运行时。 一端或另一端连接到 functoid 的固定链接，表示在运行时数据从输入实例消息到输出实例消息的移动的一部分。 以上这几个链接组合在一起，可完成源架构与目标架构之间的链接，并表示数据项的整个移动。  
  
-   **部分的链接。** 部分术语适用于为其你当前无法看到准确的链接**记录**或**字段**它们连接到源或目标架构中的节点。 发生这种情况时**记录**或**字段**它们所连接的节点未显示，因为其上级节点之一处于折叠状态中的树表示形式的架构。 有关部分的链接的详细信息，请参阅[如何优化链接显示](../core/how-to-optimize-the-display-of-links.md)。  
  
-   **编译器提供的链接。** 术语“编译器”适用于在生成 BizTalk 项目时 BizTalk 映射器自动创建的链接。 例如，如果配置表驱动循环，则编译器链接将显示源架构中的记录和字段与目标架构中的记录和字段之间的关系和链接。 此类型的链接可由编译器指令自动生成，也可由用户指定。  
  
 默认情况下，BizTalk 映射器将使用不同颜色的线条来显示这些不同类型的链接，以便帮助您区分映射的详细信息。 您可以更改用于这些不同类型的链接的颜色**选项**命令**工具**菜单。 有关如何更改颜色呈现的链接的不同类别的详细信息，请参阅[如何自定义颜色和字体在 BizTalk 映射程序](../core/how-to-customize-colors-and-font-in-biztalk-mapper.md)。  
  
## <a name="see-also"></a>另请参阅  
 [使用链接以指定记录和字段映射](../core/using-links-to-specify-record-and-field-mappings.md)