---
title: 服务组件面向解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, pipelines
- pipelines, service solutions
- service solution tutorial, assemblies
- service solution tutorial, components [BizTalk Server]
- service solution tutorial, client applications
- assemblies, service solutions
- orchestrations, service solutions
- client applications, service solutions
- back-end systems
- service solution tutorial, orchestrations
- service solution tutorial, back-end applications
ms.assetid: 97b7b754-abfb-48f9-87bf-7fe171121166
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a50743b178f9394c74b137e265532542af2b579c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234253"
---
# <a name="components-of-the-service-oriented-solution"></a><span data-ttu-id="df125-102">服务组件面向解决方案</span><span class="sxs-lookup"><span data-stu-id="df125-102">Components of the Service Oriented Solution</span></span>
<span data-ttu-id="df125-103">本部分对面向服务的解决方案的主要 BizTalk Server 组件进行了说明。</span><span class="sxs-lookup"><span data-stu-id="df125-103">This section describes the major BizTalk Server components of the Service Oriented Solution.</span></span> <span data-ttu-id="df125-104">下图显示了该解决方案的主要组件：</span><span class="sxs-lookup"><span data-stu-id="df125-104">The following diagram shows the major components of the solution:</span></span>  
  
 <span data-ttu-id="df125-105">![面向服务的解决方案流关系图](../core/media/service-oriented-flow-diagram.gif "Service_Oriented_Flow_Diagram")</span><span class="sxs-lookup"><span data-stu-id="df125-105">![Service Oriented Solution Flow Diagram](../core/media/service-oriented-flow-diagram.gif "Service_Oriented_Flow_Diagram")</span></span>  
  
 <span data-ttu-id="df125-106">面向服务的解决方案具有以下三个业务流程版本：</span><span class="sxs-lookup"><span data-stu-id="df125-106">The Service Oriented solution has three versions of the orchestrations:</span></span>  
  
-   <span data-ttu-id="df125-107">一个版本中对所有三个后端应用程序进行了存根</span><span class="sxs-lookup"><span data-stu-id="df125-107">A version in which all three of the back-end applications are stubbed out</span></span>  
  
-   <span data-ttu-id="df125-108">一个版本中将内联调用所有三个后端应用程序</span><span class="sxs-lookup"><span data-stu-id="df125-108">One in which all three back-end applications are invoked inline</span></span>  
  
-   <span data-ttu-id="df125-109">一个版本使用适配器连接到应用程序。</span><span class="sxs-lookup"><span data-stu-id="df125-109">A version that uses adapters to connect to the applications.</span></span>  
  
 <span data-ttu-id="df125-110">在 SDK\Senarios\SO\BTSSoln\Orchestrations 目录中将显示所有这些业务流程版本。</span><span class="sxs-lookup"><span data-stu-id="df125-110">All versions of the orchestrations appear in the SDK\Senarios\SO\BTSSoln\Orchestrations directory.</span></span>  
  
 <span data-ttu-id="df125-111">业务流程的内联版本提供了业务流程内请求与响应之间最低的延迟时间。</span><span class="sxs-lookup"><span data-stu-id="df125-111">The inline version of the orchestrations provides the lowest latency time within the solution between requests and responses.</span></span>  
  
 <span data-ttu-id="df125-112">有关源文件的信息，请参阅[服务面向解决方案的文件清单](../core/file-inventory-for-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="df125-112">For information about the source files, see [File Inventory for the Service Oriented Solution](../core/file-inventory-for-the-service-oriented-solution.md).</span></span>  
  
## <a name="orchestrations-in-the-service-oriented-solution"></a><span data-ttu-id="df125-113">面向服务的解决方案中的业务流程</span><span class="sxs-lookup"><span data-stu-id="df125-113">Orchestrations in the Service Oriented Solution</span></span>  
 <span data-ttu-id="df125-114">三个业务流程， **CustomerServiceReceiveSend**， **CustomerServiceNativeRequestResponse**，和**CustomerService**编写解决方案的大容量。</span><span class="sxs-lookup"><span data-stu-id="df125-114">Three orchestrations, **CustomerServiceReceiveSend**, **CustomerServiceNativeRequestResponse**, and **CustomerService** compose the bulk of the solution.</span></span> <span data-ttu-id="df125-115">**CustomerServiceReceiveSend**和**CustomerServiceNativeRequestResponse**业务流程充当前端调用**CustomerService**业务流程。</span><span class="sxs-lookup"><span data-stu-id="df125-115">The **CustomerServiceReceiveSend** and **CustomerServiceNativeRequestResponse** orchestrations act as front-ends that call the **CustomerService** orchestration.</span></span> <span data-ttu-id="df125-116">**CustomerService**业务流程完成大部分工作-将请求发送到后端应用程序、 收集答复、 将答复合并为单个消息，并将其发送到相应前端业务流程。</span><span class="sxs-lookup"><span data-stu-id="df125-116">The **CustomerService** orchestration does most of the work—sending requests to the back-end applications, gathering the replies, combining the replies into a single message, and sending the message to the appropriate front-end orchestration.</span></span> <span data-ttu-id="df125-117">因为前端业务流程调用**CustomerService**业务流程，将一直等到前端业务流程**CustomerService**业务流程完成。</span><span class="sxs-lookup"><span data-stu-id="df125-117">Because the front-end orchestrations call the **CustomerService** orchestration, the front-end orchestrations wait until the **CustomerService** orchestration finishes.</span></span>  
  
 <span data-ttu-id="df125-118">解决方案公开**CustomerServiceNativeRequestResponse**作为 Web 服务的业务流程。</span><span class="sxs-lookup"><span data-stu-id="df125-118">The solution exposes the **CustomerServiceNativeRequestResponse** orchestration as a Web service.</span></span> <span data-ttu-id="df125-119">**CustomerServiceReceiveSend** orchestration 采用 MQSeries 队列中的消息。</span><span class="sxs-lookup"><span data-stu-id="df125-119">The **CustomerServiceReceiveSend** orchestration takes messages from an MQSeries queue.</span></span>  
  
## <a name="back-end-applications"></a><span data-ttu-id="df125-120">后端应用程序</span><span class="sxs-lookup"><span data-stu-id="df125-120">Back-end Applications</span></span>  
 <span data-ttu-id="df125-121">面向服务的解决方案与三个后端应用程序进行通信：</span><span class="sxs-lookup"><span data-stu-id="df125-121">The Service Oriented solution communicates with three back-end applications:</span></span>  
  
-   <span data-ttu-id="df125-122">**PaymentTracker**应用程序返回的最近的付款模拟的列表。</span><span class="sxs-lookup"><span data-stu-id="df125-122">The **PaymentTracker** application returns a simulated list of recent payments.</span></span> <span data-ttu-id="df125-123">**PaymentTracker**从 MQSeries 队列读取请求并发送到另一个 MQSeries 队列响应。</span><span class="sxs-lookup"><span data-stu-id="df125-123">**PaymentTracker** reads the request from an MQSeries queue and sends the response to another MQSeries queue.</span></span>  
  
-   <span data-ttu-id="df125-124">**PendingTransaction**应用程序报告挂起针对的是客户帐户的事务的总数。</span><span class="sxs-lookup"><span data-stu-id="df125-124">The **PendingTransaction** application reports the sum of transactions pending against the customer account.</span></span> <span data-ttu-id="df125-125">而该应用程序是使用 Microsoft Host Integration Server (HIS) 与大型机上的 CICS/COBOL 程序进行通信的 Web Services。</span><span class="sxs-lookup"><span data-stu-id="df125-125">The application is a Web service that, in turn, uses Microsoft Host Integration Server (HIS) to communicate with a CICS/COBOL program on a mainframe computer.</span></span>  
  
-   <span data-ttu-id="df125-126">SAP 应用程序提供有关客户的信用总限额的信息。</span><span class="sxs-lookup"><span data-stu-id="df125-126">The SAP application provides information about the customer's overall credit limit.</span></span> <span data-ttu-id="df125-127">该解决方案将连接到作为 Web Services 的 SAP 应用程序。</span><span class="sxs-lookup"><span data-stu-id="df125-127">The solution connects to the SAP application as a Web service.</span></span> <span data-ttu-id="df125-128">应用程序使用 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] 中的 SAP 适配器与 SAP 系统进行通信。</span><span class="sxs-lookup"><span data-stu-id="df125-128">The application uses the SAP adapter in [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] to communicate with a SAP system.</span></span>  
  
## <a name="pipelines"></a><span data-ttu-id="df125-129">管道</span><span class="sxs-lookup"><span data-stu-id="df125-129">Pipelines</span></span>  
 <span data-ttu-id="df125-130">面向服务的解决方案在两个位置使用除默认管道： 用于接收管道**CustomerServiceReceiveSend**业务流程，和**CustomerService**业务流程的发送到管道**PaymentTracker**。</span><span class="sxs-lookup"><span data-stu-id="df125-130">The Service Oriented solution uses default pipelines except in two places: the receive pipeline for the **CustomerServiceReceiveSend** orchestration, and the **CustomerService** orchestration's send pipeline to the **PaymentTracker**.</span></span> <span data-ttu-id="df125-131">这两个管道都使用自定义组件。</span><span class="sxs-lookup"><span data-stu-id="df125-131">Both pipelines use custom components.</span></span>  
  
 <span data-ttu-id="df125-132">接收管道**CustomerServiceReceiveSend**包括自定义方解析组件， **SSO 票证颁发者管道组件**。</span><span class="sxs-lookup"><span data-stu-id="df125-132">The receive pipeline for **CustomerServiceReceiveSend** includes a custom party resolution component, **SSO Ticket Issuer Pipeline Component**.</span></span> <span data-ttu-id="df125-133">消息的**CustomerServiceReceiveSend** orchestration 接收没有凭据。</span><span class="sxs-lookup"><span data-stu-id="df125-133">The messages that the **CustomerServiceReceiveSend** orchestration receives do not have credentials.</span></span> <span data-ttu-id="df125-134">这样可以模拟在消息来自交互式语音应答系统的情况下所发生的情况。</span><span class="sxs-lookup"><span data-stu-id="df125-134">This simulates what would happen if the messages came from an Interactive Voice Response system.</span></span> <span data-ttu-id="df125-135">自定义管道组件将使用 BizTalk 接收主机的服务帐户来添加凭据。</span><span class="sxs-lookup"><span data-stu-id="df125-135">The custom pipeline component adds credentials using the service account of the BizTalk receive host.</span></span>  
  
 <span data-ttu-id="df125-136">相反，消息**CustomerSericeNativeRequestResponse**业务流程已接收具有凭据。</span><span class="sxs-lookup"><span data-stu-id="df125-136">In contrast, the messages the **CustomerSericeNativeRequestResponse** orchestration receives already have credentials.</span></span> <span data-ttu-id="df125-137">由于为集成安全性配置了 Web Services 的虚拟文件夹，并且配置了 SOAP 接收位置以集成企业单一登录 (SSO)，因此 SOAP 适配器将为该消息生成票证。</span><span class="sxs-lookup"><span data-stu-id="df125-137">Because the virtual folder for the Web service is configured for integrated security and the SOAP receive location is configured to integrate Enterprise Single Sign-On (SSO), the SOAP adapter generates a ticket for the message.</span></span>  
  
 <span data-ttu-id="df125-138">其他自定义管道将出现在**CustomerService**到发送管道**PaymentTracker**应用程序。</span><span class="sxs-lookup"><span data-stu-id="df125-138">The other custom pipeline appears in the **CustomerService** send pipeline to the **PaymentTracker** application.</span></span> <span data-ttu-id="df125-139">MQSeries 标头 Setter 管道组件将设置两个 MQSeries 消息头属性的值。</span><span class="sxs-lookup"><span data-stu-id="df125-139">The component, MQSeries Header Setter Pipeline Component, sets values for two MQSeries message header properties.</span></span> <span data-ttu-id="df125-140">该组件设置的第一个，消息数据格式 (**MQMD_Format**)，以指示消息位于形式**MQCIH**结构时，通常使用与 CICS 程序进行通信的结构。</span><span class="sxs-lookup"><span data-stu-id="df125-140">The component sets the first, the Message Data Format (**MQMD_Format**), to indicate the message is in the form of an **MQCIH** structure, a structure commonly used to communicate with CICS programs.</span></span> <span data-ttu-id="df125-141">第二个、 数据本身的格式中**MQCIH**结构 (**MQCIH_Format**)，设置为显示该消息是一个字符串。</span><span class="sxs-lookup"><span data-stu-id="df125-141">The second, the format of the data itself within the **MQCIH** structure (**MQCIH_Format**),is set to show the message is a string.</span></span>  
  
 <span data-ttu-id="df125-142">使用**MQCIH**格式可用于传递用户 ID 和密码在**MQCIH**结构。</span><span class="sxs-lookup"><span data-stu-id="df125-142">Using the **MQCIH** format enables you to pass the user ID and password in the **MQCIH** structure.</span></span> <span data-ttu-id="df125-143">SSO 关联应用程序将 BizTalk 应用程序的 Windows 用户 ID 映射到支付跟踪系统的用户 Id 传入**MQCIH**结构。</span><span class="sxs-lookup"><span data-stu-id="df125-143">SSO affiliate applications map the BizTalk application's Windows user ID to the Payment Tracking System's user IDs passed in the **MQCIH** structure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df125-144">该解决方案的内联版本使用相同管道，方法是从业务流程中调用这些管道。</span><span class="sxs-lookup"><span data-stu-id="df125-144">The inline version of the solution uses the same pipelines by calling them from the orchestration.</span></span> <span data-ttu-id="df125-145">这样允许重用管道代码。</span><span class="sxs-lookup"><span data-stu-id="df125-145">This enables re-use of the pipeline code.</span></span>  
  
## <a name="client-application"></a><span data-ttu-id="df125-146">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="df125-146">Client Application</span></span>  
 <span data-ttu-id="df125-147">该解决方案包括使用 C# 编写的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="df125-147">The solution includes a client application written in C#.</span></span> <span data-ttu-id="df125-148">可以使用该应用程序将请求作为 SOAP 或 MQSeries 消息进行发送并检查结果。</span><span class="sxs-lookup"><span data-stu-id="df125-148">You can use the application to send requests as SOAP or MQSeries messages, and examine the results.</span></span>  
  
## <a name="other-assemblies"></a><span data-ttu-id="df125-149">其他程序集</span><span class="sxs-lookup"><span data-stu-id="df125-149">Other Assemblies</span></span>  
 <span data-ttu-id="df125-150">应用程序包括几个未显示在以上摘要图中的辅助程序集。</span><span class="sxs-lookup"><span data-stu-id="df125-150">The application includes several auxiliary assemblies not shown in the summary diagram above.</span></span> <span data-ttu-id="df125-151">**实用工具**解决方案的程序集实用工具函数。</span><span class="sxs-lookup"><span data-stu-id="df125-151">The **Utilities** assembly utility functions for the solution.</span></span>  
  
 <span data-ttu-id="df125-152">**ErrorHelper**程序集包含将错误代码转换消息，并将错误消息转换为错误代码的类。</span><span class="sxs-lookup"><span data-stu-id="df125-152">The **ErrorHelper** assembly contains classes to translate error codes into messages, and to convert error messages to error codes.</span></span>  
  
 <span data-ttu-id="df125-153">**ServiceLevelTracking**程序集包括使用业务活动监视 (BAM) API 跟踪服务级别协议的数据的帮助器方法。</span><span class="sxs-lookup"><span data-stu-id="df125-153">The **ServiceLevelTracking** assembly includes helper methods using the Business Activity Monitoring (BAM) API to track service-level agreement data.</span></span>  
  
 <span data-ttu-id="df125-154">**ConfigHelper**程序集包含帮助器方法来检索从解决方案的配置值**SSOConfigStore**应用程序。</span><span class="sxs-lookup"><span data-stu-id="df125-154">The **ConfigHelper** assembly contains helper methods to retrieve configuration values for the solution from the **SSOConfigStore** application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df125-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df125-155">See Also</span></span>  
 <span data-ttu-id="df125-156">[面向开发的服务解决方案](../core/developing-a-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="df125-156">[Developing a Service Oriented Solution](../core/developing-a-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="df125-157">服务文件清单面向解决方案</span><span class="sxs-lookup"><span data-stu-id="df125-157">File Inventory for the Service Oriented Solution</span></span>](../core/file-inventory-for-the-service-oriented-solution.md)