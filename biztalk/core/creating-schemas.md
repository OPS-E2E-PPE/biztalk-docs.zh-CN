---
title: 创建架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 20b88194-b400-4ebc-8882-d493fbf30e0f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4e3197dee20a222be35aa2e72dc4ac5e04208da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389876"
---
# <a name="creating-schemas"></a>创建架构
您可以使用 BizTalk 编辑器创建两种类型的架构： 消息架构和属性架构。  
  
> [!NOTE]
>  有几种类型的消息架构，包括 XML 消息架构、 平面文件消息架构和信封架构。  
  
 消息架构定义的结构和约束应发送到计算机并从贸易合作伙伴或应用程序接收的消息的内容。 消息架构是最常见的与 Microsoft 将使用的架构类型[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以创建的业务文档和用来包含它们的信封的 XML 消息架构，并通过使用平面文件扩展向 BizTalk 编辑器，它可以创建平面文件消息架构，包括头部、 正文和尾部的架构。  
  
 属性架构是架构的一种特殊类型。 属性架构字段和/或从提升实例消息中到称为消息上下文的记录数据提供了验证模板。 属性架构的用途是提供要在运行时升级的数据的正式、 强类型定义。  
  
 属性升级提供了一种用于提取关键信息的集中式的机制、 由你定义，从在实例消息并使其更轻松地访问 BizTalk Server 组件，处理消息通过 BizTalk 传递服务器。 升级的属性的一个常见用途是在匹配到订阅，从而允许消息正确路由进行处理的消息实例中。  
  
 本部分介绍了可以在其中创建不同类型的 BizTalk Server 中的架构的方式，并提供了有关对多个类型的架构的相关的主题。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [管理项目中的架构](../core/managing-schemas-within-projects.md)  
  
-   [管理架构中的节点](../core/managing-the-nodes-within-a-schema.md)  
  
-   [升级属性](../core/promoting-properties.md)