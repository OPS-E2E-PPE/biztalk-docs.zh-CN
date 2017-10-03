---
title: "管理项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [applications], artifacts
- managing [artifacts]
- artifacts, managing
- managing [artifacts], about managing artificats
ms.assetid: aa7c5e60-7c16-4bcf-b913-b1bdfc5c7543
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ccca48682f009a24f538015b055c45dd79a9587
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="managing-artifacts"></a>管理项目
本部分介绍如何管理项目，包括如何在 BizTalk 应用程序中添加和删除项目，以及如何配置项目的属性。  
  
 项目是 BizTalk 应用程序中包含的项，BizTalk 应用程序运行时需要它们。 有关如何在 BizTalk 应用程序中使用的项目的背景信息，请参阅[BizTalk 应用程序是什么？](../core/what-is-a-biztalk-application.md) 有关项目的背景信息，请参阅[运行时体系结构](../core/runtime-architecture.md)。 有关如何创建和修改 BizTalk 应用程序时操作项目的信息，请参阅[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)。  

## <a name="tracking-artifacts"></a>跟踪的项目
管理你创建的项目的重要部分跟踪。 您可以使用 BizTalk Server 管理控制台为业务流程、发送端口、接收端口和管道配置不同的运行时跟踪选项。 您随时可以在不中断业务流程的情况下更改某项的跟踪选项。

使用跟踪配置设置，可以跟踪以下类型的数据：

- 入站和/或出站事件数据。 例如，消息 ID、项目的开始和结束时间。

- 入站和/或出站消息属性。 例如，项目所处理的各消息的一般和升级的属性。

- 入站和/或出站消息正文和部分。 例如，项目所处理的各消息的正文和部分。

- 业务流程。 业务流程形状的执行数据。

[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)提供了一些良好的信息。 


> [!TIP]
> 如果你设置跟踪选项卡上的管道，然后跟踪选项设置全局使用管道的每个端口。 这会导致不是你可能想，并可能会影响系统性能被跟踪的更多数据。 在开发期间，这可能是正常的内容。 在生产方案中，我们建议你启用发送端口上的任何跟踪选项并接收端口，而不是管道。
  
## <a name="in-this-section"></a>在本节中  
  
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