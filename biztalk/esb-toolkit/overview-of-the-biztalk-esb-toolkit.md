---
title: 在 BizTalk Server 中的 ESB 工具包概述 |Microsoft Docs
description: ESB 工具包，和它的作用在 BizTalk Server 中的说明
caps.latest.revision: 6
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e190b34-40bc-4f27-9b4f-56e98591e1d4
ms.author: mandia
ms.openlocfilehash: 404e93739d45cbca0235990dc7d2014bf38e0a84
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008782"
---
# <a name="what-is-the-biztalk-esb-toolkit"></a>什么是 BizTalk ESB 工具包

## <a name="overview"></a>概述
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]扩展了 BizTalk Server 的功能来支持松散耦合的消息传递体系结构。 大多数开发人员都熟悉代码面向、 过程、 或面向对象开发范例。 但是，在开发 BizTalk 解决方案开始，开发人员往往会忽视面向消息的 BizTalk Server 的功能。  
  
 BizTalk Server 包含的强大发布/订阅机制通过创建和填充订阅。 当新消息到达 BizTalk Messagebox 数据库中时，消息代理标识订阅服务器，并将消息发送到具有订阅的任何终结点。 可以在几个方面，包括业务流程绑定到接收端口，让等待的消息，或与筛选条件相匹配 （如类型、 接收消息的属性创建发送端口的相关的接收创建订阅点或可路由的属性的值）。  
  
 通过提供高效、 可缩放这种方法，BizTalk Server 开发人员可以创建一系列离散的子进程、 定义触发其调用，而不必担心序列的消息的类型。 消息的到达由启动的进程执行其处理消息;处理该消息后，它可以将这个或另一个邮件传递到 Messagebox 数据库，这又可以激活一个或多个的子进程。  
  
 Microsoft 提供了所需的构建全面的面向服务基础结构，包括 Windows Server、.NET Framework 和 BizTalk Server 的主要构建基块。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]基于 BizTalk Server，因为它为最常见的 ESB 服务，包括以下提供了基础：  
  
-   消息路由  
  
-   消息验证  
  
-   消息转换  
  
-   用于连接的可扩展适配器框架  
  
-   服务业务流程  
  
-   业务规则引擎  
  
-   业务活动监视  
  
-   Web 服务和 WS-* 集成 （WCF 适配器）  

## <a name="core-capabilities"></a>核心功能  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]扩展了 BizTalk Server 能够提供各种新功能，专注于构建强大、 连接、 面向服务的应用程序的功能。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] BizTalk Server 组件视为单独的可连接的工作单元根据需要，以形成松散耦合的解决方案。 以下是一些核心功能的[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供增强的 BizTalk Server 功能：  
  
- **策略驱动的中介。** [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]执行以下操作：  
  
  - 它提供了基于路线的路由支持在发布消息时的轻型服务组合。 这种方法可以动态发现服务终结点和中介的消息路由使用服务注册表或业务规则策略的要求。  
  
  - 收到了基于路线的路由使用服务器端路线的动态解析并添加到消息上下文消息后，它会添加对策略集中管理的支持。 管理在一个中心位置的路线可让来自客户端的完全不知道如何路由其请求的消息的处理。  
  
  - 它使用的增强的版本[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]冲突解决程序和适配器提供程序框架，这样的终结点和转换需求动态解析; 这会有效地使使用者与服务。  
  
- **连接系统。** [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]执行以下操作：  
  
  -   它提供了标准化 XML 消息命名空间的管道组件。  
  
  -   它与集成 JMS 通过 WebSphere MQ 适配器的 BizTalk Server。  
  
  -   它便于启用动态服务聚合、 消息路由、 消息验证和消息转换的消息交换模式。  
  
  -   它支持从注册表和使用 UDDI 3.0 的存储库集成的服务终结点发现。  
  
  -   它支持通过业务线 (LOB) 适配器路由通过 WCF 自定义 BizTalk 适配器用于 BizTalk Server 的消息。  
  
- **管理和监视。** [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]执行以下操作：  
  
  -   它提供异常管理框架和工具。  
  
  -   它便于消息修复和重新提交使用管理门户中，作为示例应用程序。 出现特定错误时，此 Web 应用程序还支持可自定义电子邮件通知。  
  
  -   它允许 BizTalk Server 终结点和注册表集成、 管理和发布。  
  
  -   它提供了集中式存储库的版本控制的服务器端的路线。  
  
  -   它为 BizTalk Server 应用程序中支持报告和分析。  
  
  -   它包括要跟踪路线服务执行，包括开始时间、 结束时间和服务中介序列中的业务活动监视组件。  
  
- **SOA 管理。** [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]执行以下操作：  
  
  -   它与第三方 SOA 监管解决方案，包括嵌入的管理代理从 AmberPoint 和 SOA 软件的 BizTalk Server 的集成。  

> [!TIP]
> [了解 BizTalk Server](../core/understanding-biztalk-server.md)消息引擎和的详细信息中提供更多详细信息。

## <a name="get-some-help"></a>获取帮助
获取一些帮助，并可帮助在其他人[BizTalk ESB 工具包论坛](http://go.microsoft.com/fwlink/?LinkID=185951&clcid=0x409)。

## <a name="next-steps"></a>后续步骤
[BizTalk ESB 工具包内容](contents-of-the-biztalk-esb-toolkit.md)  
