---
title: BizTalk Server 中的 ESB 工具包概述 |Microsoft 文档
description: ESB 工具包中，以及它能做什么 BizTalk Server 中的说明
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
ms.openlocfilehash: 9ce0bbe3710530a63127701447db87b0a3135b4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22296725"
---
# <a name="what-is-the-biztalk-esb-toolkit"></a>BizTalk ESB 工具包是什么

## <a name="overview"></a>概述
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]扩展的 BizTalk Server 功能，以支持松散耦合的消息传递体系结构。 大多数开发人员熟悉面向代码，过程，或面向对象的开发范例。 但是，在开始开发 BizTalk 解决方案，开发人员往往会忽略 BizTalk Server 的面向消息的功能。  
  
 BizTalk Server 包括的功能强大发布/订阅机制，用于创建和填充订阅。 当一条新消息到达时 BizTalk 消息框数据库中时，消息代理标识订阅服务器，并将消息发送到有订阅的任何终结点。 可以在几个方面，包括绑定到接收端口，具有关联的接收等待一条消息，或创建具有筛选器条件相匹配的属性 （如类型，接收消息的发送端口业务流程创建订阅点或可路由的属性的值）。  
  
 通过提供此高效且可伸缩的方法，BizTalk Server 使开发人员创建一系列的离散的子进程、 定义触发其调用，而不用担心序列的消息的类型。 由消息的到达启动的进程执行其处理的消息;处理该消息后，它可以将这个或另一个消息传递到消息框中的数据库，而又可以激活一个或多个子进程。  
  
 Microsoft 提供了所需的构建全面的面向服务基础结构，包括 Windows Server、.NET Framework 和 BizTalk Server 中的关键构建基块。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]由于其提供的最常见的 ESB 服务，包括以下基础基于 BizTalk Server:  
  
-   消息路由  
  
-   消息验证  
  
-   消息转换  
  
-   可扩展适配器框架，用于连接  
  
-   服务业务流程  
  
-   业务规则引擎  
  
-   业务活动监视  
  
-   Web 服务和 WS-* 集成 （WCF 适配器）  

## <a name="core-capabilities"></a>核心功能  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]扩展 BizTalk Server 提供一系列上构建强大、 连接、 面向服务的应用程序的已设定焦点的新功能的功能。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] BizTalk 服务器组件将其视为单独的可连接的工作单元根据需要，以形成松散耦合解决方案。 以下是一些核心功能，[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供增强的 BizTalk Server 功能：  
  
-   **策略驱动的中介。** [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]执行下列任务：  
  
    -   它提供了基于路线的路由支持在发布消息时的轻型服务组合。 这种方法可以动态发现的服务终结点和中介邮件路由使用服务注册表或业务规则策略的要求。  
  
    -   收到了基于路线的使用服务器端路线，可动态解析并添加到消息上下文后面的消息进行路由，它会添加的策略集中的支持。 利用管理路线在一个中心位置，从完全不能识别如何路由其请求的客户端的消息的处理。  
  
    -   它使用的增强的版本[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]冲突解决程序和适配器的提供程序框架，从而使动态解析终结点以及转换要求; 这可以有效地将从服务的使用者脱耦。  
  
-   **将系统的连接。** [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]执行下列任务：  
  
    -   它提供了规范化 XML 消息命名空间的管道组件。  
  
    -   它与集成 JMS 通过 WebSphere MQ 适配器的 BizTalk Server。  
  
    -   它便于启用动态服务聚合、 消息路由、 消息验证，以及消息转换的消息交换模式。  
  
    -   它支持从注册表和使用 UDDI 3.0 的存储库集成的服务终结点发现。  
  
    -   它支持通过业务线 (LOB) 适配器路由通过 WCF 自定义 BizTalk 适配器用于 BizTalk Server 的消息。  
  
-   **管理和监视。** [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]执行下列任务：  
  
    -   它提供异常管理框架和工具。  
  
    -   它便于消息修复并重新提交使用管理门户中，作为示例应用程序。 一个特定的错误发生时，此 Web 应用程序还支持可自定义电子邮件通知。  
  
    -   它允许 BizTalk Server 终结点和注册表的集成、 管理和发布。  
  
    -   它提供了已进行版本管理的服务器端路线的集中式存储库。  
  
    -   它报告和分析 BizTalk Server 应用程序支持。  
  
    -   它包括要跟踪路线服务执行，包括开始时间、 结束时间和服务中介序列的业务活动监视的组件。  
  
-   **SOA 监管。** [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]执行下列任务：  
  
    -   它与第三方 SOA 管理解决方案，包括嵌入的管理代理从 AmberPoint 和 SOA 软件的 BizTalk Server 的集成。  

> [!TIP]
> [了解 BizTalk Server](../core/understanding-biztalk-server.md)提供了消息传送的引擎，以及更多详细信息。

## <a name="get-some-help"></a>获取帮助
获取帮助，并帮助其他人在[BizTalk ESB 工具包论坛](http://go.microsoft.com/fwlink/?LinkID=185951&clcid=0x409)。

## <a name="next-steps"></a>后续步骤
[BizTalk ESB 工具包的内容](contents-of-the-biztalk-esb-toolkit.md)  
