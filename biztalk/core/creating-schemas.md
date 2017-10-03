---
title: "创建架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20b88194-b400-4ebc-8882-d493fbf30e0f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac019276923467fe2d95f5a0a0b4a7b53513e9c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-schemas"></a>创建架构
你可以使用 BizTalk 编辑器创建两种类型的架构： 消息架构和属性的架构。  
  
> [!NOTE]
>  消息架构包括以下几种类型：XML 消息架构、平面文件消息架构和信封架构。  
  
 消息架构可定义要向贸易合作伙伴或应用程序发送或从其接收的消息的结构，并约束这些消息的内容。 消息架构是架构将与 Microsoft 使用的最常见类型[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以创建业务文档和用于包含，包络线的 XML 消息架构，并通过使用平面文件扩展到 BizTalk 编辑器，它可以创建平面文件消息架构，包括有关标头、 正文和拖车的架构。  
  
 属性架构是特殊类型的架构。 对于从实例消息中升级为消息上下文的字段和/或记录数据，属性架构为其提供了验证模板。 属性架构的用途是要在运行时升级的数据提供正式的强类型定义。  
  
 属性提升提供用于提取关键信息的集中式的机制、 由你定义、 从内实例消息并使其更轻松地访问 BizTalk Server 组件，正在处理该消息通过 BizTalk 传递服务器。 升级属性常用于将消息实例与订阅相匹配，从而允许正确地路由消息以进行处理。  
  
 本部分介绍了在 BizTalk Server 中创建不同类型架构的几种方式，并且提供了与多种架构类型有关的相关主题。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [管理架构在项目中](../core/managing-schemas-within-projects.md)  
  
-   [管理在架构中的节点](../core/managing-the-nodes-within-a-schema.md)  
  
-   [提升属性](../core/promoting-properties.md)