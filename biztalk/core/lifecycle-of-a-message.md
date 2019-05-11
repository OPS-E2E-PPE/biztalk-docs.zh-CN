---
title: 一条消息的生命周期 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 305dc48db684a1e0f0ba37232b672e6ffb63406a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329668"
---
# <a name="lifecycle-of-a-message"></a>一条消息的生命周期
下图提供了从消息传送的角度来看的 BizTalk Server 体系结构的高级概述。  
  
 ![BizTalk Server 消息传送体系结构](../core/media/arch-messaging-01.gif "arch_messaging_01")  
  
 在此简化视图中，通过在给定的接收端口中定义的接收位置收到消息。 此消息是由接收位置处理，然后发布到 MessageBox 数据库、 主要持久化和路由机制为 BizTalk Server。 MessageBox 评估活动的订阅并将该消息路由到这些业务流程和发送端口使用匹配的订阅。 业务流程可能处理该消息并将通过 MessageBox 的消息发布到其中它推送到其最终目标的发送端口。  
  
 以下是 BizTalk Server 消息处理过程中涉及的关键组件。  
  
## <a name="receive-ports-and-receive-locations"></a>接收端口和接收位置  
 一个*接收端口*是一系列一个或多个接收到 BizTalk Server 定义的特定入口点的位置。 一个*接收位置*是单个终结点 (URL) 的配置以接收消息。 位置包含一个接收适配器和接收管道的配置信息。 *适配器*负责接收消息的传输和通信部分。 示例包括文件适配器和 SOAP 适配器，其中每个接收来自不同类型的源的消息。 接收管道负责准备发布到 MessageBox 的消息。 一个*管道*是一系列序列，每个都提供一条消息，例如解密/加密到特定的处理、 分析过程中，或验证中执行的组件。 有关管道的详细信息，接收端口和接收位置，请参阅[项目](../core/artifacts.md)。  
  
## <a name="send-ports-and-send-port-groups"></a>发送端口和发送端口组  
 一个*发送端口*是发送管道和发送适配器的组合。 发送端口组是发送端口的集合，作用很像电子邮件通讯组列表。 发送到发送端口组的消息将发送到该组中的所有发送端口。 发送管道用于准备即将从 BizTalk Server 传输到另一个服务的消息。 发送适配器负责使用特定的协议，例如 SOAP 或 FTP 将消息实际上发送。 发送端口和发送端口组的详细信息，请参阅[项目](../core/artifacts.md)。  
  
## <a name="orchestrations"></a>业务流程  
 业务流程可以订阅 （接收） 和发布 （发送） 消息通过 MessageBox。 此外，业务流程可以构造新消息。 使用的订阅和路由机制已经讨论过接收消息。 订阅的业务流程在填充后激活新的实例传递消息，或对于实例订阅，该实例解除冻结，如有必要，然后传递消息。 当从业务流程发送消息时，它们是相同的方式发布到 MessageBox，消息到达接收位置的相应属性插入到在路由中使用的数据库。 有关业务流程的详细信息，请参阅[项目](../core/artifacts.md)。  
  
## <a name="messagebox-database"></a>MessageBox 数据库  
 在 BizTalk Server 中的发布/订阅引擎的核心是 MessageBox 数据库。 MessageBox 由两个组件组成： 一个或多个 Microsoft SQL Server 数据库和消息代理。 SQL Server 数据库提供的许多事情，包括消息、 消息属性、 订阅、 业务流程状态、 跟踪数据和用于路由的主机队列的持久性存储区。 有关 MessageBox 数据库的详细信息，请参阅[MessageBox 数据库](../core/the-messagebox-database.md)。  
  
## <a name="hosts-and-host-instances"></a>主机和主机实例  
 一个*主机*是如执行 BizTalk Server 项目的 Microsoft Windows 进程的逻辑表示发送端口和业务流程。 一个*主机实例*特定服务器上的主机的物理表示形式。 主机可以是为在进程内主机，这意味着它是由拥有和管理 BizTalk Server 或独立的主机，这意味着，不受 BizTalk Server 进程中运行的 BizTalk Server 代码。 独立主机的一个很好示例是 Internet 信息服务 (IIS) 承载的 HTTP 和 SOAP 适配器的接收功能。 为整个 BizTalk Server 组; 定义主机共享配置、 Messagebox、 端口和等等的 BizTalk 服务器的集合。 有关主机和主机实例的详细信息，请参阅[实体](../core/entities.md)。  
  
## <a name="saving-a-message-body"></a>保存消息正文  
 有三种方法来保存消息正文。  
  
### <a name="from-the-admin-mmc-group-hub-page-queries"></a>从管理 MMC 组中心页查询  
 此方法适用于只在 MessageBox 数据库中的消息。  
  
-   查看服务实例。  
  
-   打开**服务实例详细信息**对话框。  
  
-   单击**消息选项卡**若要查看与此实例关联的消息列表。  
  
-   右键单击该消息，然后单击**保存**。  
  
     -或-  
  
-   双击要打开该文件的消息**消息查看器**，然后单击**保存**。  
  
### <a name="from-the-operations-om"></a>从操作 OM  
  
-   使用**GetInstance**检索服务实例对象。  
  
-   使用**Instance.Messages []** 来枚举服务实例当前引用的所有消息。  
  
-   如使用消息对象上的方法**Message.BodyPart []** 并**Message.Context []** 访问并将其保存。  
  
### <a name="from-the-dta"></a>从 DTA  
  
-   从 DTA 使用检索的消息**GetTrackedInstance**并**GetTrackedmessage** API 调用。  
  
## <a name="see-also"></a>请参阅  
 [运行时体系结构](../core/runtime-architecture.md)