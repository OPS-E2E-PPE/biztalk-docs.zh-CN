---
title: MessageBox 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 435f6b26e2844bbf7aac8423415c83be119eea4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394120"
---
# <a name="the-messagebox-database"></a>MessageBox 数据库
Microsoft BizTalk Server 中的发布/订阅引擎的核心是 MessageBox 数据库。 MessageBox 由两个组件组成： 一个或多个 Microsoft SQL Server 数据库和消息传送代理。 SQL Server 数据库提供的许多方面，包括消息、 消息部分、 消息属性、 订阅、 业务流程状态、 跟踪数据、 用于路由的主机队列和其他持久性存储区。 BizTalk Server 组可能具有一个或多个 MessageBox 数据库在其中它将发布消息和从其对这些邮件的订阅服务器中提取消息。  
  
 数据库提供了一些与路由消息和履行订阅相关的逻辑。 消息代理，但是，是封装和提取数据库组件并且是 BizTalk Server 用于与 MessageBox 交互的接口的组件。 消息代理是为发布的消息，提供了接口的组件对象模型 (COM) 组件订阅消息、 检索消息等。 此接口是其他 BizTalk Server 组件，包括适配器框架和业务流程，用于与 MessageBox 交互的唯一机制。  
  
## <a name="the-messagebox-and-the-message"></a>MessageBox 和消息  
 MessageBox 数据库订阅是一组既定的信息和服务信息。 既定 （或谓词） 信息是一条消息必须满足的条件。 要执行的操作与消息符合条件的服务信息。 所有这些信息存储在一组调用消息传送和业务流程引擎的表。  
  
 在 BizTalk Server 接收一条消息，它处理该消息在管道中，并将该消息放在 MessageBox 数据库。 传入消息具有上下文。 消息上下文是一组与消息关联的属性。 三种类型的消息上下文属性是：  
  
- 直接编写的属性  
  
- 升级的属性  
  
- 谓词属性  
  
  升级和谓词消息属性指示订阅此消息的业务流程，该业务流程是否已接收消息所需的权限。  
  
  如果业务流程订阅该消息，MessageBox 数据库会将消息发送到业务流程。 当业务流程收到消息时，它处理上可用的主机实例的消息。 处理消息之后, 如果业务流程订阅了管道或发送端口，业务流程将发送返回消息到 MessageBox 数据库。  
  
  对于每个 BizTalk 主机，关联的 MessageBox 具有一个工作队列和一个挂起的队列。 此外，每个 MessageBox 数据库包含一组静态状态、 动态状态和实例状态表。 有关 BizTalk 主机的信息，请参阅[实体](../core/entities.md)。  
  
> [!IMPORTANT]
>  如果主机变得不可用-例如，从该主机接收消息的 MessageBox 数据库变得不可用，其他所有 MessageBox 数据库变都得不可用。  
  
 当您运行配置向导时创建的第一个 MessageBox 数据库。 配置的 MessageBox 数据库将成为主 MessageBox 数据库。 主 MessageBox 数据库的计算结果并将订阅路由到 BizTalk Server 环境中的其他所有 MessageBox 数据库。 有关提高主 MessageBox 数据库的性能信息，请参阅[管理 MessageBox 数据库](../core/managing-messagebox-databases.md)。  
  
> [!IMPORTANT]
>  必须使用 SQL Server 群集以提供对 MessageBox 数据库的故障转移保护。  
  
## <a name="suspended-messages-in-the-messagebox-database"></a>MessageBox 数据库中的挂起的消息  
 BizTalk Server 将存储与 MessageBox 数据库中的挂起管道相关联的消息。 如果管道中发生故障，BizTalk Server 将挂起的消息实例。 有两种类型的挂起的服务实例：  
  
- 可恢复的挂起的实例。  
  
- 无法恢复的挂起的实例。 例如，如果实例已损坏。  
  
  根据挂起的原因，您可能能够恢复 BizTalk Server 挂起-例如，如果业务流程遇到挂起形状，或如果传输无法传递的消息，BizTalk Server 不会自动删除挂起的服务不能恢复从 MessageBox 数据库的实例。 您可以选择将服务实例保存到磁盘，然后再从挂起队列中删除它。  
  
  有关备份 MessageBox 数据库的信息，请参阅[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server.md)。  
  
## <a name="see-also"></a>请参阅  
 [消息引擎](../core/the-messaging-engine.md)