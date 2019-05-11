---
title: 不同类型的 BizTalk 架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad8847d3-6f0e-4982-b4a8-92a5f39a4b48
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cabbfc889b4a07616012dc85c6763e1444ed8f43
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351079"
---
# <a name="different-types-of-biztalk-schemas"></a>不同类型的 BizTalk 架构
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 支持以下四种类型的架构：  
  
- **XML 架构**。 XML 架构定义 XML 实例消息的类的结构。 由于这种类型的架构使用 XML 架构定义 (XSD) 语言来定义 XML 实例消息的结构，这是 XSD 的预期的用途，此类架构使用 XSD 中一种简单方式。  
  
- **平面文件架构**。 平面文件架构将定义使用平面文件格式，分隔或位置的实例消息或它们的某种组合的类的结构。 由于 XSD 的本地语义功能不适应所有用于定义平面文件实例消息的结构要求 — 例如可能用于不同的记录和平面文件中的字段的分隔符的各种类型-BizTalk Server 使用 XSD 的批注功能来存储此 XSD 架构中的附加信息。 BizTalk Server 定义一组丰富的特定批注标记，可用于存储所有所需的其他信息。  
  
- **信封架构**。 信封架构是一种特殊的 XML 架构。 信封架构用于定义 XML 信封，用于将一个或多个 XML 业务文档包装到单个 XML 实例消息的结构。 在定义为信封架构的 XML 架构时，所需的几个其他属性设置，具体取决于有信封架构中定义的多个根记录。  
  
- **属性架构**。 属性架构要结合 BizTalk Server 中存在的称为属性升级的两个机制之一。 属性升级是将特定的值从实例消息的深层复制到消息上下文的过程。 从消息上下文中，更轻松地通过各种 BizTalk Server 组件访问这些值。 这些组件使用的值来执行操作，例如消息路由。 升级的属性值还可以复制另一个方向，从恢复到的实例消息中，可更轻松地访问消息上下文中的实例消息发送到其目标之前。 属性架构是 BizTalk 架构所扮演的角色过程中复制的实例消息和消息上下文之间来回升级的属性的简单版本。  
  
  部分的其余部分提供有关 BizTalk Server 中的架构这四种类型的其他信息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [XML 架构](../core/xml-schemas.md)  
  
-   [平面文件架构](../core/flat-file-schemas.md)  
  
-   [信封架构](../core/envelope-schemas.md)  
  
-   [属性架构](../core/property-schemas.md)