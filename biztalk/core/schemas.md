---
title: 架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, schema types
- deploying, schemas
- schemas
- schemas, about schemas
- property schemas
- envelope schemas
- schemas, deploying
- XML schemas
- flat file schemas
ms.assetid: aea772bd-e7ab-448e-ba82-e7c8f38087db
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4b5ecd2f4d3b7f70625a35ecbf4661f9da77146
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395569"
---
# <a name="schemas"></a>架构
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用 XML 架构定义 (XSD) 语言来定义的所有消息的处理时，它指的是这些消息结构定义称为结构*架构*。 除少数情况外，结构化消息是所有应用程序的核心。 这些结构化消息可以采用任何形式（大型或小型），并面向一系列众多的后端系统和数据存储。 创建和使用结构化消息的系统通常使用不同的格式。 结构化消息的两种最常用的格式为 XML 和平面文件。  
  
 BizTalk Server 支持以下四种类型的架构：  
  
-   XML 架构。 XML 架构定义 XML 实例消息的类的结构。 由于这种类型的架构使用 XML 架构定义 (XSD) 语言来定义 XML 实例消息的结构，这是 XSD 的预期的用途，此类架构使用 XSD 中一种简单方式。 有关 XML 架构的详细信息，请参阅[XML 架构](../core/xml-schemas.md)。  
  
-   平面文件架构。 平面文件架构将定义使用平面文件格式，分隔或位置的实例消息或它们的某种组合的类的结构。 由于 XSD 的本地语义功能不适应所有用于定义平面文件实例消息的结构要求 — 例如可能用于不同的记录和平面文件中的字段的分隔符的各种类型-BizTalk Server 使用 XSD 的批注功能来存储此 XSD 架构中的附加信息。 BizTalk Server 定义一组丰富的特定批注标记，可用于存储所有所需的其他信息。 有关平面文件架构的详细信息，请参阅[平面文件架构](../core/flat-file-schemas.md)。  
  
-   信封架构。 信封架构是一种类型的 XML 架构。 信封架构用于定义 XML 信封，用于将一个或多个 XML 业务文档包装到单个 XML 实例消息的结构。 在定义为信封架构的 XML 架构时，所需的其他属性设置，具体取决于有信封架构中定义的多个根记录。 有关信封架构的详细信息，请参阅[信封架构](../core/envelope-schemas.md)。  
  
-   属性架构。 属性架构要结合 BizTalk Server 中存在的属性升级的两个机制之一。 *属性升级*是将特定的值从实例消息的深层复制到消息上下文的过程。 从消息上下文中，更轻松地通过各种 BizTalk Server 组件访问这些值。 这些组件使用的值来执行操作，例如消息路由。 升级的属性值还可以复制另一个方向，从恢复到的实例消息中，可更轻松地访问消息上下文中的实例消息发送到其目标之前。 属性架构，这是 BizTalk 架构的简单版本，播放过程中复制的实例消息和消息上下文之间来回升级的属性的角色。 有关属性架构的详细信息，请参阅[属性架构](../core/property-schemas.md)。  
  
## <a name="schema-deployment"></a>架构部署  
 部署不同类型的架构，如消息架构、 属性架构和信封架构。 由于每个架构都不同，有中如何处理它们的部署后的细微差异。 本部分介绍什么是普遍适用于所有架构，并且还描述了与架构的类型相关的差异。  
  
 在部署架构时，管理数据库将存储架构的内容。 你可以部署多个具有相同目标命名空间的架构。 BizTalk Server 显式指向在运行时使用在管道设计器中的架构。 如果使用默认管道，或如果未指定架构在管道设计器中，并且已部署了同一架构的多个版本，BizTalk Server 来确定要使用的架构。 在这种情况下，它将是与最新版本相关联的架构，具有最高版本号 — 部署使用该架构的程序集。  
  
 删除部署架构的程序集的最新版本，请从同一程序集的最高的早期版本的架构将成为活动架构。  
  
 如果部署的架构具有重复的目标命名空间，则必须从自定义设计的用户管道引用架构。 这样，若要能够加载正确的架构的消息引擎附加信息。  
  
 例如，一种情况下，会使用重复的目标命名空间是在创建 Web 服务架构的多个版本时。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk 编辑器创建架构](../core/creating-schemas-using-biztalk-editor.md)   
 [BizTalk 架构表示法](../core/biztalk-representation-of-schemas.md)   
 [项目](../core/artifacts.md)