---
title: 管理项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], artifacts
- managing [artifacts]
- artifacts, managing
- managing [artifacts], about managing artificats
ms.assetid: aa7c5e60-7c16-4bcf-b913-b1bdfc5c7543
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2327f1093658a7d6e01472e393fea40120abd6c0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380405"
---
# <a name="managing-artifacts"></a>管理项目
本部分介绍如何管理项目，包括如何添加和删除它们从 BizTalk 应用程序以及如何配置它们的属性。  
  
 项目是 BizTalk 应用程序中包含的项所需的运行。 有关如何在 BizTalk 应用程序中使用项目的背景信息，请参阅[BizTalk 应用程序是什么？](../core/what-is-a-biztalk-application.md) 有关项目的背景信息，请参阅[运行时体系结构](../core/runtime-architecture.md)。 有关如何创建和修改 BizTalk 应用程序时处理项目的信息，请参阅[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)。  

## <a name="tracking-artifacts"></a>跟踪的项目
管理你创建的项目的重要组成部分跟踪。 可以配置各种跟踪选项在运行时的业务流程、 发送端口、 接收端口和管道使用 BizTalk Server 管理控制台。 可以在任何时候，更改项的跟踪选项，而不会中断业务流程。

跟踪配置设置，可以跟踪以下类型的数据：

- 入站和/或出站事件数据。 例如，消息 ID、 开始和结束时间的项目。

- 入站和/或出站消息属性。 例如，为每个项目所处理的消息的一般和升级属性。

- 入站和/或出站消息正文和部分。 例如，正文和为每个项目所处理的消息部分。

- 业务流程。 业务流程形状的执行数据。

[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)提供了一些有用信息。 


> [!TIP]
> 如果设置管道跟踪选项，然后跟踪选项是全局设置为使用的管道的每个端口。 这会导致被跟踪不是你可能会想，并可能会影响系统性能的更多数据。 在开发期间，这可能是正常。 在生产方案中，我们建议启用任何跟踪选项上的发送端口和接收端口，而不是管道。
  
## <a name="in-this-section"></a>本节内容  
  
-   [管理业务流程](../core/managing-orchestrations.md)  
  
-   [管理角色链接](../core/managing-role-links.md)  
  
-   [管理发送端口和发送端口组](../core/managing-send-ports-and-send-port-groups.md)  
  
-   [管理接收端口](../core/managing-receive-ports.md)  
  
-   [管理接收位置](../core/managing-receive-locations.md)  
  
-   [管理策略](../core/managing-policies.md)  
  
-   [管理架构](../core/managing-schemas.md)  
  
-   [管理映射](../core/managing-maps.md)  
  
-   [管理管道](../core/managing-pipelines.md)  
  
-   [管理资源](../core/managing-resources.md)