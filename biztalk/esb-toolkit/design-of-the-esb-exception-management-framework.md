---
title: ESB 异常管理框架设计 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfc2688c-c01c-4244-9e35-3d482135d8b7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f25bec37d7ee6ec02db5db28e32ce8ed5b62f724
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996574"
---
# <a name="design-of-the-esb-exception-management-framework"></a>ESB 异常管理框架设计
用于管理异常的一致且可重用模式是所有开发项目; 一个核心考虑因素它们有助于最大程度提高可维护性，并使其更轻松地支持在部署后的应用程序。  
  
 典型的 BizTalk 应用程序可能会使用 BizTalk 消息传送功能，可以选择开始处理业务流程、 调用业务规则引擎、 与多个业务 (LOB) 或企业资源规划 (ERP) 系统进行交互并返回到独立的第三方系统的响应。 此外，这些组件，包括 BizTalk 子系统的运行时的位置可能驻留在分布在当前环境的一个或多个服务器上。 这是典型的方案中，需要系统以便支持捕获和报告任何 ESB 或 BizTalk 中可能发生的异常分离子系统或各种第三方 LOB 系统，在其中每个都有其自己的异常处理约束。 例如，大型机可以拒绝正常处理周期; 从网站发送的订单网站必须补偿此错误，并通知用户。  
  
 由于 ESB 应用程序的复杂性和其环境，开发一致的应用程序异常管理解决方案应体现在以下常见的设计目标：  
  
- 提供一种标准化的方法检测和处理 BizTalk Server 环境中发生的异常 (也就是说，在消息传送和业务流程的子系统中)。  
  
- 提供允许自动化的过程来响应和管理应用程序异常的常见模式。  
  
- 提供便于重用的松散耦合的异常管理模式。  
  
- 为应用程序异常，并可以将应用于任何 BizTalk 子系统及其可用的消息状态提供常见的报告机制。  
  
  若要了解为什么[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供了一种自定义错误机制，即异常管理框架，和它的工作原理，有必要了解在 BizTalk Server 和为什么这些功能不完全可用的异常管理功能能够满足上述的设计目标。  
  
## <a name="biztalk-server-exception-reporting"></a>BizTalk Server 异常报告  
 BizTalk Server 支持以下异常处理和报告机制：  
  
- 失败的消息路由  
  
- BizTalk Server 管理控制台  
  
- Microsoft 事件日志  
  
- 自定义开发选项  
  
  默认情况下，用于处理异常的 BizTalk Server 的功能依赖于大量人员干预。 例如，考虑这种情况，用户将提交到 BizTalk Server 的验证阶段期间导致异常的消息。 默认情况下，将消息发布到 Messagebox 数据库，它路由到挂起队列。 这意味着，操作员必须以下操作：  
  
- 独立检测到发生了异常。  
  
- 手动将保存到磁盘使用 BizTalk Server 管理控制台在失败的消息。  
  
- 手动编辑和更正该消息并重新将其提交给系统。 在某些情况下，此过程都有可能会丢失重要的上下文信息。  
  
  若要解决这些问题，BizTalk Server 提供失败消息路由机制。 开发人员和管理员可以用于创建业务流程或消息的发送端口配置为订阅消息传送子系统中发生的任何异常。 这提供了一个自动化的错误检测和路由机制，可以保留原始消息状态并解决检测到异常的问题。  
  
  由于未提供的业务流程进程进行自动失败的消息路由，开发人员必须考虑错误异常处理程序块添加到业务流程作用域形状。 使用此解决方案，每个业务流程可以有其自己的异常处理，但没有重用异常处理功能跨多个业务流程的机制。  
  
  这意味着，现在有两个截然不同的方式处理和管理在 BizTalk Server 系统中，消息传送异常和异常处理的业务流程中的第三种方法。 因此，开发人员必须自定义异常处理机制，以满足其自己的要求，如果用户想要实现符合本节中前面所述要求的系统。  
  
## <a name="biztalk-server-administration-console"></a>BizTalk Server 管理控制台  
 在 BizTalk Server 管理控制台提供了一组概述页面，称为 BizTalk 组中心。 使用这些页，管理员可以查询挂起的消息和异常按应用程序、 服务名称、 错误代码或 URI，如图 1 中所示。  
  
 ![管理控制台](../esb-toolkit/media/ch4-adminconsole.gif "Ch4-AdminConsole")  
  
 **图 1**  
  
 **BizTalk Server 管理控制台组概述页**  
  
 尽管组概述功能提供了一个常见的用户界面来查看异常，但视图是局限于"实际"服务实例。 检查的状态可以是繁琐的任务，因为管理员必须向下钻取到每个项的树。 此外，若干其他因素限制的应用程序异常报告工具的 BizTalk Server 管理控制台功能：  
  
- 没有对于挖掘商业智能的数据没有任何功能。 例如，不能查询按月坏的情况下有问题的应用程序，或检查每季度趋势的应用程序异常。  
  
- 企业可能需要某些应用程序异常发生时或当达到特定阈值时引发警报，但没有任何工具来订阅对这些类型的异常事件。  
  
- Microsoft 管理控制台 (MMC)，管理控制台使用作为其用户界面 (UI) 机制不是一个理想的接口，并会始终很不方便在生产环境中访问。 最小值，它要求用户是 BizTalk 操作员角色; 的成员和在生产环境中，向 MMC 访问通常是仅可通过终端服务器。  
  
- 在控制台显示仅未经处理的异常 （挂起的服务实例）。 如果开发人员处理业务流程中的异常，允许业务流程，以正常方式完成的异常信息将永远不会显示在管理控制台中。  
  
  [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]通过 ESB 失败，业务流程异常路由机制，解决这些限制。 这非常类似于 BizTalk Server 的失败消息路由机制。 此外，[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包含管道组件中订阅的 ESB 失败，业务流程异常路由机制和失败消息路由机制生成的消息的发送端口并对其进行规范化。  
  
  ESB 异常管理框架利用其他功能中的 BizTalk Server 中，如订阅模型和基于事件的业务活动监视 (BAM)。 这意味着 ESB 异常管理框架可以跟踪使用 BAM，异常数据点，然后将其发布到 BizTalk BAM 门户，以便监视。