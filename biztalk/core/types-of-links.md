---
title: 类型的链接 |Microsoft Docs
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
ms.openlocfilehash: aacaf93ce41d60d414145fbfaf19f95551da4a77
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396618"
---
# <a name="types-of-links"></a>类型的链接
以下列表汇总了各种类型的 BizTalk 映射器中提供的链接：  
  
- **弹性链接。** 术语弹性适用于链接它在创建时之前连接的链接的两端。 例如，如果在源架构中，字段中拖动一个链接，但你具有尚未将其连接到目标架构中的对应字段，是弹性链接。 完成连接后，弹性链接将变为固定链接。  
  
   可以将链接的一个终结点拖到另一个节点或 functoid。 有关链接替换的详细信息，请参阅[如何创建链接](../core/how-to-create-links.md)。  
  
- **固定链接。** 修复了术语适用于已显式构造为表示值的移动从源实例消息到目标实例消息或该移动的最少部分的链接。 固定的直接连接的链接**记录**或**字段**节点到源架构中的**记录**或**字段**目标中的节点架构表示数据的直接复制在运行时。 连接到一端或另一个 functoid 的固定链接表示的数据移动的一部分从输入的实例消息到输出实例消息在运行时。 表示数据的项的整个移动多个这些组合在一起，完成源和目标架构之间的链接。  
  
- **部分链接。** 部分术语适用于链接用于你当前无法看到的确切**记录**或**字段**它们连接到源或目标架构中的节点。 发生这种情况时**记录**或**字段**节点附加到没有显示，因为其祖先节点之一处于折叠状态中的架构的树表示形式。 有关部分链接的详细信息，请参阅[如何优化链接显示](../core/how-to-optimize-the-display-of-links.md)。  
  
- **编译器链接。** 术语编译器适用于生成 BizTalk 项目时，BizTalk 映射器会自动创建的链接。 例如，如果你配置表驱动循环，编译器链接显示关系以及记录和字段之间的链接中的源架构的记录和目标架构中的字段。 由编译器指令，可以自动生成此类型的链接，也可以是用户指导。  
  
  BizTalk 映射器中，默认情况下显示这些不同类型的链接使用不同颜色的线条，可帮助您区分映射的详细信息。 您可以更改用于这些不同种类链接的颜色**选项**命令**工具**菜单。 有关如何更改颜色呈现不同类别链接的详细信息，请参阅[如何自定义颜色和字体在 BizTalk 映射器](../core/how-to-customize-colors-and-font-in-biztalk-mapper.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用链接指定记录和字段映射](../core/using-links-to-specify-record-and-field-mappings.md)