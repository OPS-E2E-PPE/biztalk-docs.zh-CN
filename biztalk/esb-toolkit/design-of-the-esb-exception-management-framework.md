---
title: "设计 ESB 异常管理框架 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cfc2688c-c01c-4244-9e35-3d482135d8b7
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 089942c8b531575c157c0037777e85fe6d8608a7
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="design-of-the-esb-exception-management-framework"></a>ESB 异常管理框架的设计
用于管理异常的一致且可重用的模式是任何开发项目; 一个核心考虑因素它们可帮助最大化可维护性并使其更轻松地支持后部署的应用程序。  
  
 典型的 BizTalk 应用程序可能使用消息传送功能 BizTalk，（可选） 开始处理业务流程、 调用业务规则引擎，与多个-的业务线 (LOB) 或企业资源规划 (ERP) 系统进行交互并返回对单独的第三方系统的响应。 此外，这些组件，其中包括 BizTalk 子系统的运行时的位置可能驻留在分布在当前环境的一个或多个服务器上。 这是典型的方案中，要求系统上以便支持捕捉和报表中的任何 ESB 或 BizTalk 可能会发生的异常分离子系统或在各种第三方 LOB 系统，其中每个都有其自己的异常处理约束。 例如，主机可以拒绝在正常处理周期; 从网站发送顺序网站必须补偿此错误，并通知用户。  
  
 由于 ESB 应用程序的复杂性和其环境，开发的应用程序异常管理的一致解决方案应体现了以下常见的设计目标：  
  
-   提供一种标准化的方法检测和处理在 BizTalk Server 环境中发生的异常 (也就是说，在消息传递和业务流程子系统中)。  
  
-   提供允许自动化的过程来响应操作和管理应用程序异常的常见模式。  
  
-   提供一个松散耦合的异常管理模式，它方便了重复使用。  
  
-   为应用程序异常和其可用的消息状态，可以将应用于任何 BizTalk 子系统状态提供常见报表机制。  
  
 若要了解为什么[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供的自定义错误机制，即异常管理框架，以及它如何工作，它有必要了解在 BizTalk Server 和为什么这些功能不是完全中可用的异常管理功能能够满足前面的设计目标。  
  
## <a name="biztalk-server-exception-reporting"></a>BizTalk Server 异常报告  
 BizTalk Server 支持以下异常处理和报告机制：  
  
-   失败的邮件路由  
  
-   BizTalk Server 管理控制台  
  
-   Microsoft 事件日志  
  
-   自定义开发选项  
  
 默认情况下，处理异常的 BizTalk Server 功能依赖大量操作员干预。 例如，考虑这种情况，其中用户将消息提交至在验证阶段期间导致异常的 BizTalk Server。 默认情况下，消息发布到消息框数据库，它将路由到挂起队列。 这意味着，操作员必须以下操作：  
  
-   独立检测发生了异常。  
  
-   手动将保存到磁盘使用 BizTalk Server 管理控制台在失败的消息。  
  
-   手动编辑和更正消息并重新将其提交至系统。 在某些情况下，此过程都有可能会丢失重要的上下文信息。  
  
 若要解决这些问题，BizTalk Server 提供的失败消息路由的机制。 开发人员和管理员可以用于创建业务流程或配置为订阅消息传送的子系统中发生的任何异常的消息发送端口。 这将提供自动的错误检测和路由机制，可以保留原始消息状态并解决了检测异常的问题。  
  
 为业务流程不提供自动失败的邮件路由，因为开发人员必须考虑错误通过将异常处理程序块添加到业务流程作用域形状。 通过此解决方案，每个业务流程可以有其自己的异常处理，但没有任何机制可重复使用异常处理跨多个业务流程的功能。  
  
 这意味着，现在有两个非常不同的方式处理和管理在 BizTalk Server 系统中，消息传送异常和异常处理的业务流程中的第三个方法。 因此，开发人员必须自定义异常处理机制根据其自己的需求，如果他们想要实现匹配在本部分前面所述的要求的系统。  
  
## <a name="biztalk-server-administration-console"></a>BizTalk Server 管理控制台  
 BizTalk Server 管理控制台提供了一套称为 BizTalk 组中心数据库的组概述页。 使用这些页面，管理员可以查询有关挂起的消息和按应用程序、 服务名称、 错误代码或 URI，分组的异常中图 1 所示。  
  
 ![管理员控制台](../esb-toolkit/media/ch4-adminconsole.gif "第四章第 4 AdminConsole")  
  
 **图 1**  
  
 **BizTalk Server 管理控制台组概述页面**  
  
 虽然组概述功能提供了用于查看异常的常见用户界面，但仅限于"实时"服务实例视图。 检查状态可以是繁琐的任务，因为向下钻取的管理员必须通过为每个项的树。 此外，若干其他因素将 BizTalk Server 管理控制台功能限制是为了用作应用程序异常报告工具：  
  
-   没有对于挖掘商业智能的数据没有任何功能。 例如，你不能按月坏的情况下有问题的应用程序的查询，或检查应用程序异常的每季度趋势。  
  
-   业务可能需要某些应用程序异常发生时或在达到特定阈值时引发的警报，但没有任何工具来订阅这些类型的异常事件。  
  
-   Microsoft 管理控制台 (MMC)，管理控制台使用作为其用户界面 (UI) 机制不是一个理想的接口，并会始终很不方便访问的生产环境中。 最小，它要求用户是 BizTalk 操作员角色中; 的成员并且，在生产环境中，访问 MMC 受到通常仅可通过终端服务器。  
  
-   控制台显示仅未经处理的异常 （挂起的服务实例）。 如果开发人员处理业务流程中的异常，允许以正常方式完成的业务流程的异常信息将永远不会显示在管理控制台。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]通过 ESB 失败业务流程异常路由机制解决这些限制。 这十分类似于 BizTalk Server 的失败消息路由机制。 此外，[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括订阅 ESB 失败业务流程异常路由机制和失败消息路由机制生成的消息的发送端口中的管道组件并对它们进行规范化。  
  
 ESB 异常 Management Framework 利用其他功能中的 BizTalk Server 中，如订阅模型和基于事件的业务活动监视 (BAM)。 也就是说 ESB 异常管理框架，可以跟踪与 BAM，异常数据点，然后将其发布到 BizTalk BAM 门户，以便监视。