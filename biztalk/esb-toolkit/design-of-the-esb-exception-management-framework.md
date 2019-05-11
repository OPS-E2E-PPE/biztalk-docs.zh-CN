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
ms.openlocfilehash: 14c7c7e8f6ba2632e68ed81e98a562e5ef316120
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394641"
---
# <a name="design-of-the-esb-exception-management-framework"></a><span data-ttu-id="f7a44-102">ESB 异常管理框架设计</span><span class="sxs-lookup"><span data-stu-id="f7a44-102">Design of the ESB Exception Management Framework</span></span>
<span data-ttu-id="f7a44-103">用于管理异常的一致且可重用模式是所有开发项目; 一个核心考虑因素它们有助于最大程度提高可维护性，并使其更轻松地支持在部署后的应用程序。</span><span class="sxs-lookup"><span data-stu-id="f7a44-103">Consistent and re-usable patterns for managing exceptions are a core consideration of any development project; they help to maximize maintainability and make it easier to support the application after deployment.</span></span>  
  
 <span data-ttu-id="f7a44-104">典型的 BizTalk 应用程序可能会使用 BizTalk 消息传送功能，可以选择开始处理业务流程、 调用业务规则引擎、 与多个业务 (LOB) 或企业资源规划 (ERP) 系统进行交互并返回到独立的第三方系统的响应。</span><span class="sxs-lookup"><span data-stu-id="f7a44-104">A typical BizTalk application might use the BizTalk messaging features, optionally start processing an orchestration, call the Business Rule Engine, interact with several line-of-business (LOB) or enterprise resource planning (ERP) systems, and return a response to a separate third-party system.</span></span> <span data-ttu-id="f7a44-105">此外，这些组件，包括 BizTalk 子系统的运行时的位置可能驻留在分布在当前环境的一个或多个服务器上。</span><span class="sxs-lookup"><span data-stu-id="f7a44-105">In addition, the run-time location of these components, including the BizTalk subsystems, may reside on one or more servers distributed throughout the current environment.</span></span> <span data-ttu-id="f7a44-106">这是典型的方案中，需要系统以便支持捕获和报告任何 ESB 或 BizTalk 中可能发生的异常分离子系统或各种第三方 LOB 系统，在其中每个都有其自己的异常处理约束。</span><span class="sxs-lookup"><span data-stu-id="f7a44-106">This is a typical scenario and requires the system to support catching and reporting exceptions that may occur in any of the ESB or BizTalk decoupled subsystems or in the various third-party LOB systems, each of which has its own exception handling constraints.</span></span> <span data-ttu-id="f7a44-107">例如，大型机可以拒绝正常处理周期; 从网站发送的订单网站必须补偿此错误，并通知用户。</span><span class="sxs-lookup"><span data-stu-id="f7a44-107">For example, the mainframe may reject an order sent from a Web site during a normal processing cycle; the Web site must compensate for this error and notify the user.</span></span>  
  
 <span data-ttu-id="f7a44-108">由于 ESB 应用程序的复杂性和其环境，开发一致的应用程序异常管理解决方案应体现在以下常见的设计目标：</span><span class="sxs-lookup"><span data-stu-id="f7a44-108">Because of the complexity of ESB applications and their environment, development of a consistent solution for application exception management should embody the following common design goals:</span></span>  
  
- <span data-ttu-id="f7a44-109">提供一种标准化的方法检测和处理 BizTalk Server 环境中发生的异常 (也就是说，在消息传送和业务流程的子系统中)。</span><span class="sxs-lookup"><span data-stu-id="f7a44-109">Provide a standardized approach for detecting and handling exceptions that occur in the BizTalk Server environment (that is, in the messaging and orchestration subsystems).</span></span>  
  
- <span data-ttu-id="f7a44-110">提供允许自动化的过程来响应和管理应用程序异常的常见模式。</span><span class="sxs-lookup"><span data-stu-id="f7a44-110">Provide common patterns that allow automated processes to react to and manage application exceptions.</span></span>  
  
- <span data-ttu-id="f7a44-111">提供便于重用的松散耦合的异常管理模式。</span><span class="sxs-lookup"><span data-stu-id="f7a44-111">Provide a loosely coupled exception management pattern that facilitates reuse.</span></span>  
  
- <span data-ttu-id="f7a44-112">为应用程序异常，并可以将应用于任何 BizTalk 子系统及其可用的消息状态提供常见的报告机制。</span><span class="sxs-lookup"><span data-stu-id="f7a44-112">Provide a common reporting mechanism for application exceptions and their available message states that can apply to any BizTalk subsystem.</span></span>  
  
  <span data-ttu-id="f7a44-113">若要了解为什么[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供了一种自定义错误机制，即异常管理框架，和它的工作原理，有必要了解在 BizTalk Server 和为什么这些功能不完全可用的异常管理功能能够满足上述的设计目标。</span><span class="sxs-lookup"><span data-stu-id="f7a44-113">To understand why the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides a custom error mechanism, namely the Exception Management Framework, and how it works, it is necessary to understand the exception management features available in BizTalk Server and why these features are not fully capable of meeting the preceding design goals.</span></span>  
  
## <a name="biztalk-server-exception-reporting"></a><span data-ttu-id="f7a44-114">BizTalk Server 异常报告</span><span class="sxs-lookup"><span data-stu-id="f7a44-114">BizTalk Server Exception Reporting</span></span>  
 <span data-ttu-id="f7a44-115">BizTalk Server 支持以下异常处理和报告机制：</span><span class="sxs-lookup"><span data-stu-id="f7a44-115">BizTalk Server supports the following exception handling and reporting mechanisms:</span></span>  
  
- <span data-ttu-id="f7a44-116">失败的消息路由</span><span class="sxs-lookup"><span data-stu-id="f7a44-116">Failed Message Routing</span></span>  
  
- <span data-ttu-id="f7a44-117">BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="f7a44-117">BizTalk Server Administration Console</span></span>  
  
- <span data-ttu-id="f7a44-118">Microsoft 事件日志</span><span class="sxs-lookup"><span data-stu-id="f7a44-118">Microsoft Event Log</span></span>  
  
- <span data-ttu-id="f7a44-119">自定义开发选项</span><span class="sxs-lookup"><span data-stu-id="f7a44-119">Custom development options</span></span>  
  
  <span data-ttu-id="f7a44-120">默认情况下，用于处理异常的 BizTalk Server 的功能依赖于大量人员干预。</span><span class="sxs-lookup"><span data-stu-id="f7a44-120">By default, BizTalk Server's capabilities for handling exceptions rely a great deal on operator intervention.</span></span> <span data-ttu-id="f7a44-121">例如，考虑这种情况，用户将提交到 BizTalk Server 的验证阶段期间导致异常的消息。</span><span class="sxs-lookup"><span data-stu-id="f7a44-121">For example, consider the situation where a user submits a message to BizTalk Server that causes an exception during the validation stage.</span></span> <span data-ttu-id="f7a44-122">默认情况下，将消息发布到 Messagebox 数据库，它路由到挂起队列。</span><span class="sxs-lookup"><span data-stu-id="f7a44-122">By default, the message is published to the Message Box database, where it is routed to a suspended queue.</span></span> <span data-ttu-id="f7a44-123">这意味着，操作员必须以下操作：</span><span class="sxs-lookup"><span data-stu-id="f7a44-123">This means that an operator must do the following:</span></span>  
  
- <span data-ttu-id="f7a44-124">独立检测到发生了异常。</span><span class="sxs-lookup"><span data-stu-id="f7a44-124">Independently detect that an exception occurred.</span></span>  
  
- <span data-ttu-id="f7a44-125">手动将保存到磁盘使用 BizTalk Server 管理控制台在失败的消息。</span><span class="sxs-lookup"><span data-stu-id="f7a44-125">Manually save the failed message to disk using the BizTalk Server Administration Console.</span></span>  
  
- <span data-ttu-id="f7a44-126">手动编辑和更正该消息并重新将其提交给系统。</span><span class="sxs-lookup"><span data-stu-id="f7a44-126">Manually edit and correct the message and re-submit it to the system.</span></span> <span data-ttu-id="f7a44-127">在某些情况下，此过程都有可能会丢失重要的上下文信息。</span><span class="sxs-lookup"><span data-stu-id="f7a44-127">In some instances, this process has the potential for losing important context information.</span></span>  
  
  <span data-ttu-id="f7a44-128">若要解决这些问题，BizTalk Server 提供失败消息路由机制。</span><span class="sxs-lookup"><span data-stu-id="f7a44-128">To resolve these issues, BizTalk Server provides the Failed Message Routing mechanism.</span></span> <span data-ttu-id="f7a44-129">开发人员和管理员可以用于创建业务流程或消息的发送端口配置为订阅消息传送子系统中发生的任何异常。</span><span class="sxs-lookup"><span data-stu-id="f7a44-129">Developers and administrators can use this to create orchestration processes or messaging send ports configured to subscribe to any exceptions that occur in the messaging subsystem.</span></span> <span data-ttu-id="f7a44-130">这提供了一个自动化的错误检测和路由机制，可以保留原始消息状态并解决检测到异常的问题。</span><span class="sxs-lookup"><span data-stu-id="f7a44-130">This provides an automated error-detection and routing mechanism that preserves the original message state and solves the problem of detecting exceptions.</span></span>  
  
  <span data-ttu-id="f7a44-131">由于未提供的业务流程进程进行自动失败的消息路由，开发人员必须考虑错误异常处理程序块添加到业务流程作用域形状。</span><span class="sxs-lookup"><span data-stu-id="f7a44-131">Because automatic failed message routing is not provided for orchestration processes, the developer must account for errors by adding exception handler blocks to orchestration scope shapes.</span></span> <span data-ttu-id="f7a44-132">使用此解决方案，每个业务流程可以有其自己的异常处理，但没有重用异常处理功能跨多个业务流程的机制。</span><span class="sxs-lookup"><span data-stu-id="f7a44-132">With this solution, each orchestration can have its own exception handling, but there is no mechanism for reusing exception handling functionality across multiple orchestrations.</span></span>  
  
  <span data-ttu-id="f7a44-133">这意味着，现在有两个截然不同的方式处理和管理在 BizTalk Server 系统中，消息传送异常和异常处理的业务流程中的第三种方法。</span><span class="sxs-lookup"><span data-stu-id="f7a44-133">This means that there are now two very different ways in which messaging exceptions are processed and managed in a BizTalk Server system, and a third way in which orchestration exceptions are processed.</span></span> <span data-ttu-id="f7a44-134">因此，开发人员必须自定义异常处理机制，以满足其自己的要求，如果用户想要实现符合本节中前面所述要求的系统。</span><span class="sxs-lookup"><span data-stu-id="f7a44-134">Therefore, developers must customize the exception handling mechanism to suit their own requirements if they want to implement a system that matches the requirements described earlier in this section.</span></span>  
  
## <a name="biztalk-server-administration-console"></a><span data-ttu-id="f7a44-135">BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="f7a44-135">BizTalk Server Administration Console</span></span>  
 <span data-ttu-id="f7a44-136">在 BizTalk Server 管理控制台提供了一组概述页面，称为 BizTalk 组中心。</span><span class="sxs-lookup"><span data-stu-id="f7a44-136">The BizTalk Server Administration Console provides a set of Group Overview pages, referred to as the BizTalk Group Hub.</span></span> <span data-ttu-id="f7a44-137">使用这些页，管理员可以查询挂起的消息和异常按应用程序、 服务名称、 错误代码或 URI，如图 1 中所示。</span><span class="sxs-lookup"><span data-stu-id="f7a44-137">Using these pages, administrators can query for suspended messages and exceptions grouped by application, service name, error code, or URI, as shown in Figure 1.</span></span>  
  
 <span data-ttu-id="f7a44-138">![管理控制台](../esb-toolkit/media/ch4-adminconsole.gif "Ch4-AdminConsole")</span><span class="sxs-lookup"><span data-stu-id="f7a44-138">![Admin Console](../esb-toolkit/media/ch4-adminconsole.gif "Ch4-AdminConsole")</span></span>  
  
 <span data-ttu-id="f7a44-139">**图 1**</span><span class="sxs-lookup"><span data-stu-id="f7a44-139">**Figure 1**</span></span>  
  
 <span data-ttu-id="f7a44-140">**BizTalk Server 管理控制台组概述页**</span><span class="sxs-lookup"><span data-stu-id="f7a44-140">**The BizTalk Server Administration Console Group Overview pages**</span></span>  
  
 <span data-ttu-id="f7a44-141">尽管组概述功能提供了一个常见的用户界面来查看异常，但视图是局限于"实际"服务实例。</span><span class="sxs-lookup"><span data-stu-id="f7a44-141">Although the Group Overview feature provides a common user interface to view exceptions, the views are limited to "live" service instances.</span></span> <span data-ttu-id="f7a44-142">检查的状态可以是繁琐的任务，因为管理员必须向下钻取到每个项的树。</span><span class="sxs-lookup"><span data-stu-id="f7a44-142">Examining the state can be a cumbersome task because administrators must drill down through the tree to each item.</span></span> <span data-ttu-id="f7a44-143">此外，若干其他因素限制的应用程序异常报告工具的 BizTalk Server 管理控制台功能：</span><span class="sxs-lookup"><span data-stu-id="f7a44-143">In addition, several other factors limit the BizTalk Server Administration Console capabilities as an application exception-reporting tool:</span></span>  
  
- <span data-ttu-id="f7a44-144">没有对于挖掘商业智能的数据没有任何功能。</span><span class="sxs-lookup"><span data-stu-id="f7a44-144">There is no capability for mining the data for business intelligence.</span></span> <span data-ttu-id="f7a44-145">例如，不能查询按月坏的情况下有问题的应用程序，或检查每季度趋势的应用程序异常。</span><span class="sxs-lookup"><span data-stu-id="f7a44-145">For example, you cannot query for the worst offending applications on a monthly basis or examine quarterly trends for application exceptions.</span></span>  
  
- <span data-ttu-id="f7a44-146">企业可能需要某些应用程序异常发生时或当达到特定阈值时引发警报，但没有任何工具来订阅对这些类型的异常事件。</span><span class="sxs-lookup"><span data-stu-id="f7a44-146">The business may require alerts to be raised when certain application exceptions occur or when reaching specific thresholds, but there is no facility to subscribe to these types of exception events.</span></span>  
  
- <span data-ttu-id="f7a44-147">Microsoft 管理控制台 (MMC)，管理控制台使用作为其用户界面 (UI) 机制不是一个理想的接口，并会始终很不方便在生产环境中访问。</span><span class="sxs-lookup"><span data-stu-id="f7a44-147">The Microsoft Management Console (MMC) that the Administration Console uses as its user interface (UI) mechanism is not an ideal interface, and it is not always convenient to access in production environments.</span></span> <span data-ttu-id="f7a44-148">最小值，它要求用户是 BizTalk 操作员角色; 的成员和在生产环境中，向 MMC 访问通常是仅可通过终端服务器。</span><span class="sxs-lookup"><span data-stu-id="f7a44-148">At minimum, it requires users to be members of the BizTalk Operators role; and, in production environments, access to the MMC is usually only possible through Terminal Server.</span></span>  
  
- <span data-ttu-id="f7a44-149">在控制台显示仅未经处理的异常 （挂起的服务实例）。</span><span class="sxs-lookup"><span data-stu-id="f7a44-149">The console displays only unhandled exceptions (suspended service instances).</span></span> <span data-ttu-id="f7a44-150">如果开发人员处理业务流程中的异常，允许业务流程，以正常方式完成的异常信息将永远不会显示在管理控制台中。</span><span class="sxs-lookup"><span data-stu-id="f7a44-150">If the developer handles the exception in the orchestration, allowing the orchestration to complete normally, the exception information will never appear in the Administration Console.</span></span>  
  
  <span data-ttu-id="f7a44-151">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]通过 ESB 失败，业务流程异常路由机制，解决这些限制。</span><span class="sxs-lookup"><span data-stu-id="f7a44-151">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] addresses these limitations through the ESB Failed Orchestration Exception Routing mechanism.</span></span> <span data-ttu-id="f7a44-152">这非常类似于 BizTalk Server 的失败消息路由机制。</span><span class="sxs-lookup"><span data-stu-id="f7a44-152">This closely resembles the Failed Message Routing mechanism of BizTalk Server.</span></span> <span data-ttu-id="f7a44-153">此外，[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包含管道组件中订阅的 ESB 失败，业务流程异常路由机制和失败消息路由机制生成的消息的发送端口并对其进行规范化。</span><span class="sxs-lookup"><span data-stu-id="f7a44-153">In addition, the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes a pipeline component in a send port that subscribes to messages generated from both the ESB Failed Orchestration Exception Routing mechanism and the Failed Message Routing mechanism and normalizes them.</span></span>  
  
  <span data-ttu-id="f7a44-154">ESB 异常管理框架利用其他功能中的 BizTalk Server 中，如订阅模型和基于事件的业务活动监视 (BAM)。</span><span class="sxs-lookup"><span data-stu-id="f7a44-154">The ESB Exception Management Framework takes advantage of other features in BizTalk Server, such as the subscription model, and event-based Business Activity Monitoring (BAM).</span></span> <span data-ttu-id="f7a44-155">这意味着 ESB 异常管理框架可以跟踪使用 BAM，异常数据点，然后将其发布到 BizTalk BAM 门户，以便监视。</span><span class="sxs-lookup"><span data-stu-id="f7a44-155">This means that the ESB Exception Management Framework can track the exception data points with BAM, and then publish them to the BizTalk BAM Portal for monitoring.</span></span>