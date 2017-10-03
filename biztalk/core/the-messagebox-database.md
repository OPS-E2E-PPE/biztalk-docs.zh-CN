---
title: "MessageBox 数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, MessageBox database
- messages, suspended messages
- MessageBox database, messages
- MessageBox database, about MessageBox database
- MessageBox database, suspended messages
- suspended messages
- MessageBox database
- suspended messages, MessageBox database
ms.assetid: f89eb02c-1b83-4127-8a91-e78fb4a1f96e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edf1fb3a89d6e08f6a0183a3242c53c4be890e60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-messagebox-database"></a>MessageBox 数据库
Microsoft BizTalk Server 中发布/订阅引擎的核心是 MessageBox 数据库。 MessageBox 由两个组件构成：一个或多个 Microsoft SQL Server 数据库，以及消息传送代理。 SQL Server 数据库为众多对象提供持久化存储，这些对象包括消息、消息部分、消息属性、订阅、业务流程状态、跟踪数据和用于路由的主机队列等。 BizTalk Server 组可以具有一个或多个 MessageBox 数据库，该组将消息发布到此（这些）数据库中，而订阅这些消息的订户从此（这些）数据库提取消息。  
  
 数据库提供一些与路由消息和履行订阅相关的逻辑。 然而，消息代理是封装和提取数据库组件的组件，并且是 BizTalk Server 用于与 MessageBox 交互的接口。 消息代理是组件对象模型 (COM) 组件，为发布消息、订阅消息、检索消息等操作提供接口。 此接口是其他 BizTalk Server 组件（包括适配器框架和业务流程）用于与 MessageBox 交互的唯一机制。  
  
## <a name="the-messagebox-and-the-message"></a>MessageBox 和消息  
 MessageBox 数据库订阅是一组既定信息和服务信息。 既定（或谓词）信息是消息必须满足的条件。 服务信息是有关如何处理满足条件的消息的信息。 所有这些信息都存储在一组调用消息和业务流程引擎的表中。  
  
 BizTalk Server 在接收消息后，将在管道中处理该消息，然后将该消息放置在 MessageBox 数据库中。 传入消息具有上下文。 消息上下文是一组与消息关联的属性。 以下是三种类型的消息上下文属性：  
  
-   直接编写的属性  
  
-   提升的属性  
  
-   谓词属性  
  
 升级消息属性和谓词消息属性指示订阅此消息的业务流程，以及该业务流程是否具有接收该消息所需的权限。  
  
 如果有业务流程订阅消息，则 MessageBox 数据库将向该业务流程发送所订阅的消息。 当业务流程接收到消息后，将在可用的主机实例上处理该消息。 在处理消息后，如果业务流程订阅了管道或发送端口，则该业务流程将向 MessageBox 数据库发送一个返回消息。  
  
 对于每个 BizTalk 主机，关联的 MessageBox 具有一个工作队列和一个挂起队列。 此外，每个 MessageBox 数据库都包含一组静态状态、动态状态和实例状态表。 有关 BizTalk 主机的信息，请参阅[实体](../core/entities.md)。  
  
> [!IMPORTANT]
>  如果主机变得不可用（例如，从该主机接收消息的 MessageBox 数据库变得不可用），则其他所有 MessageBox 数据库也将不可用。  
  
 运行配置向导时创建第一个 MessageBox 数据库。 所配置的 MessageBox 数据库将成为主 MessageBox 数据库。 主 MessageBox 数据库将对订阅进行评估并将其路由至 BizTalk Server 环境中的其他所有 MessageBox 数据库。 有关可提高 master MessageBox 数据库性能的信息，请参阅[管理 MessageBox 数据库](../core/managing-messagebox-databases.md)。  
  
> [!IMPORTANT]
>  必须使用 SQL Server 群集以便为 MessageBox 数据库提供故障转移保护。  
  
## <a name="suspended-messages-in-the-messagebox-database"></a>MessageBox 数据库中的挂起消息  
 BizTalk Server 将与挂起管道关联的消息存储在 MessageBox 数据库中。 如果管道中发生故障，BizTalk Server 将挂起消息的实例。 挂起的服务实例分为两种类型：  
  
-   可以恢复的挂起的实例。  
  
-   无法恢复的挂起的实例。 例如，如果实例已损坏。  
  
 根据挂起的原因，您可以恢复 BizTalk Server 挂起的服务 -- 例如，如果业务流程遇到挂起形状，或者传输无法传送消息，则 BizTalk Server 不会自动删除您无法从 MessageBox 数据库恢复的已挂起实例。 您可以选择将服务实例保存到磁盘，然后再将其从挂起队列中删除。  
  
 有关备份 MessageBox 数据库的信息，请参阅[Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server.md)。  
  
## <a name="see-also"></a>另请参阅  
 [消息传送的引擎](../core/the-messaging-engine.md)