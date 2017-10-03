---
title: "消息的生命周期 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, MessageBox database
- messages, orchestrations
- messages, host instances
- messages, receive locations
- send ports, about send ports
- processing, messages
- messages, processing
- host instances, about host instances
- receive locations, about receive locations
- hosts, about hosts
- messages, lifecycle
- MessageBox database, about MessageBox database
- receive ports, about receive ports
- send port groups, about send port groups
- messages, hosts
- messages, send port groups
- messages, receive ports
- orchestrations, about orchestrations
- messages, send ports
ms.assetid: d2374f86-9b5f-404f-ba7b-9cab69873fa8
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e05aca3ec819fb8615552c5ed57114032d7ea60b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="lifecycle-of-a-message"></a>消息的生命周期
下图从消息传送方面对 BizTalk Server 结构进行了高度概括：  
  
 ![消息传递体系结构的 BizTalk Server](../core/media/arch-messaging-01.gif "arch_messaging_01")  
  
 在此简化视图中，通过在给定接收端口中定义的接收位置接收消息。 此消息由接收位置处理，然后被发布到 MessageBox 数据库，这是 BizTalk Server 的主要持久化和路由机制。 MessageBox 评估活动的订阅，并将消息路由到具有匹配订阅的业务流程和发送端口。 业务流程可以处理消息，并通过 MessageBox 将消息发布到发送端口，从发送端口将消息推送到最终目标。  
  
 以下是 BizTalk Server 消息处理中涉及的关键组件：  
  
## <a name="receive-ports-and-receive-locations"></a>接收端口和接收位置  
 A*接收端口*是集合的一个或多个接收到 BizTalk Server 中定义特定入口点的位置。 A*接收位置*是单个终结点 (URL) 的配置接收消息。 该位置包含接收适配器和接收管道的配置信息。 *适配器*负责接收消息的传输和通信的部分。 示例包括 FILE 适配器和 SOAP 适配器，这两种适配器都从不同类型的源接收消息。 接收管道负责准备消息以便将消息发布到 MessageBox 中。 A*管道*是一系列序列，每个提供对解密/加密的消息的特定处理、 分析过程中，或验证中执行的组件。 接收端口，有关管道的详细信息，以及接收位置，请参阅[项目](../core/artifacts.md)。  
  
## <a name="send-ports-and-send-port-groups"></a>发送端口和发送端口组  
 A*发送端口*是发送管道和发送适配器的组合。 发送端口组是发送端口的集合，作用很像电子邮件分发列表。 发送到发送端口组的消息将被发送到该组中的所有发送端口。 发送管道用于准备来自 BizTalk Server 的消息以将其传输到其他服务。 发送适配器负责使用特定协议（如 SOAP 或 FTP）实际发送消息。 发送端口和发送端口组的详细信息，请参阅[项目](../core/artifacts.md)。  
  
## <a name="orchestrations"></a>业务流程  
 业务流程可以通过 MessageBox 订阅（接收）和发布（发送）消息。 此外，业务流程可以构造新的消息。 使用已讨论过的订阅和路由机制接收消息。 在填入业务流程的订阅后，将激活新的实例并传送消息；对于实例订阅，如有必要，将解除对该实例的冻结，然后传送消息。 当消息发送从业务流程时，它们发布到 MessageBox 在相同的方式如到达具有适当的属性的接收位置的消息插入到在路由中使用的数据库。 有关业务流程的详细信息，请参阅[项目](../core/artifacts.md)。  
  
## <a name="messagebox-database"></a>MessageBox 数据库  
 BizTalk Server 中发布/订阅引擎的核心是 MessageBox 数据库。 MessageBox 由两个组件构成：一个或多个 Microsoft SQL Server 数据库和消息代理。 SQL Server 数据库为许多对象（包括消息、消息属性、订阅、业务流程状态、跟踪数据和用于路由的主机队列）提供持久化存储。 MessageBox 数据库有关的详细信息，请参阅[MessageBox 数据库](../core/the-messagebox-database.md)。  
  
## <a name="hosts-and-host-instances"></a>主机和主机实例  
 A*主机*是 Microsoft Windows 进程，如执行 BizTalk 服务器项目的逻辑表示发送端口和业务流程。 A*主机实例*是特定服务器上的主机的物理表示。 主机可以是进程内主机（意味着它由 BizTalk Server 所拥有和管理），也可以是独立的主机（意味着 BizTalk Server 代码运行在不由 BizTalk Server 所控制的进程中）。 独立主机的一个典型示例为 Internet 信息服务 (IIS)，它承载了 HTTP 和 SOAP 适配器的接收功能。 主机是为整个 BizTalk Server 组（即共享配置、MessageBox 和端口等的 BizTalk Server 集合）定义的。 有关主机和主机实例的详细信息，请参阅[实体](../core/entities.md)。  
  
## <a name="saving-a-message-body"></a>保存消息正文  
 保存消息正文有三种方式。  
  
### <a name="from-the-admin-mmc-group-hub-page-queries"></a>从管理 MMC 组中心页查询  
 此方法仅针对 MessageBox 数据库中的消息。  
  
-   查看服务实例。  
  
-   打开**服务实例详细信息**对话框。  
  
-   单击**消息选项卡**若要查看与此实例关联的消息的列表。  
  
-   可以右键单击该消息，然后单击**保存**。  
  
     - 或 -  
  
-   双击该消息以中将其打开**消息查看器**，然后单击**保存**。  
  
### <a name="from-the-operations-om"></a>从操作 OM  
  
-   使用**GetInstance**检索服务实例对象。  
  
-   使用**Instance.Messages []**枚举所有消息都当前引用服务实例。  
  
-   使用方法对 message 对象例如**Message.BodyPart []**和**Message.Context []**访问并将其保存。  
  
### <a name="from-the-dta"></a>从 DTA  
  
-   从 DTA 使用检索消息**GetTrackedInstance**和**GetTrackedmessage** API 调用。  
  
## <a name="see-also"></a>另请参阅  
 [运行时体系结构](../core/runtime-architecture.md)