---
title: "BizTalk ESB 工具包的内容 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e7114df-dadf-49ab-b024-44d84e47faa5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3dcfc5bbe761f70269c31294484ee37e7e79f83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="contents-of-the-biztalk-esb-toolkit"></a><span data-ttu-id="d84d7-102">BizTalk ESB 工具包的内容</span><span class="sxs-lookup"><span data-stu-id="d84d7-102">Contents of the BizTalk ESB Toolkit</span></span>
<span data-ttu-id="d84d7-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供体系结构指南、 模式和实践，以及 BizTalk Server 和.NET Framework 组件，用于简化的开发在 Microsoft 平台上的企业级解决方案的集合。</span><span class="sxs-lookup"><span data-stu-id="d84d7-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides architectural guidance, patterns and practices, and a collection of BizTalk Server and .NET Framework components to simplify the development of enterprise-scale solutions on the Microsoft platform.</span></span> <span data-ttu-id="d84d7-104">该工具包还提供功能，可帮助开发人员扩展现有消息传送和集成解决方案。</span><span class="sxs-lookup"><span data-stu-id="d84d7-104">The toolkit also provides capabilities to help developers extend existing messaging and integration solutions.</span></span> <span data-ttu-id="d84d7-105">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]支持和实现松散耦合的消息传递环境，它简化了生成动态基于消息的企业应用程序的进程的组件进行互操作的集合组成。</span><span class="sxs-lookup"><span data-stu-id="d84d7-105">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] consists of a collection of interoperating components that support and implement a loosely coupled messaging environment that simplifies the process of building dynamic message-based enterprise applications.</span></span>  
  
 <span data-ttu-id="d84d7-106">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包含以下组件：</span><span class="sxs-lookup"><span data-stu-id="d84d7-106">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contains the following components:</span></span>  
  
-   <span data-ttu-id="d84d7-107">[ESB Web 服务](../esb-toolkit/esb-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="d84d7-107">[ESB Web Services](../esb-toolkit/esb-web-services.md).</span></span> <span data-ttu-id="d84d7-108">这些公开到 ESB 使用者，如基于路线的路由、 异常管理、 动态的终结点和地图，BizTalk 操作通用、 描述、 发现和集成 (UDDI) 互操作性，解析的主要功能和消息内容的转换。</span><span class="sxs-lookup"><span data-stu-id="d84d7-108">These expose key capabilities to ESB consumers, such as itinerary-based routing, exception management, dynamic resolution of endpoints and maps, BizTalk operations, Universal Description, Discovery, and Integration (UDDI) interoperability, and transformation of message content.</span></span>  
  
-   <span data-ttu-id="d84d7-109">[ESB 管理门户](../esb-toolkit/esb-management-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="d84d7-109">[ESB Management Portal](../esb-toolkit/esb-management-portal.md).</span></span> <span data-ttu-id="d84d7-110">这提供对异常和错误跟踪，消息重新提交，警报和通知、 UDDI 集成、 报告和分析，以及配置功能的支持。</span><span class="sxs-lookup"><span data-stu-id="d84d7-110">This provides support for exception and fault tracking, message resubmission, alerts and notifications, UDDI integration, reporting and analytics, and configuration capabilities.</span></span>  
  
-   <span data-ttu-id="d84d7-111">[ESB 管道互操作组件](../esb-toolkit/esb-pipeline-interop-components.md)。</span><span class="sxs-lookup"><span data-stu-id="d84d7-111">[ESB Pipeline Interop Components](../esb-toolkit/esb-pipeline-interop-components.md).</span></span> <span data-ttu-id="d84d7-112">这些提供 BizTalk Server 管道组件，以方便与外部系统的互操作性。</span><span class="sxs-lookup"><span data-stu-id="d84d7-112">These provide BizTalk Server pipeline components that facilitate interoperability with external systems.</span></span>  
  
-   <span data-ttu-id="d84d7-113">[异常 Management Framework](../esb-toolkit/exception-management-framework.md)。</span><span class="sxs-lookup"><span data-stu-id="d84d7-113">[Exception Management Framework](../esb-toolkit/exception-management-framework.md).</span></span> <span data-ttu-id="d84d7-114">这将捕获和将合并 BizTalk 消息传送和业务流程的子系统中的异常并提供单一机制，用于处理错误消息。</span><span class="sxs-lookup"><span data-stu-id="d84d7-114">This captures and consolidates exceptions from both BizTalk Messaging and Orchestration subsystems and provides a single mechanism for handling fault messages.</span></span> <span data-ttu-id="d84d7-115">它包括异常 Web 服务、 异常管理 API 和扩充、 处理和传递给 ESB 管理门户的异常详细信息的组件。</span><span class="sxs-lookup"><span data-stu-id="d84d7-115">It includes the exception Web service, the exception management API, and components that enrich, process, and pass exception details to the ESB Management Portal.</span></span>  
  
-   <span data-ttu-id="d84d7-116">[ESB 冲突解决程序和适配器提供程序框架](../esb-toolkit/esb-resolver-and-adapter-provider-framework.md)。</span><span class="sxs-lookup"><span data-stu-id="d84d7-116">[ESB Resolver and Adapter Provider Framework](../esb-toolkit/esb-resolver-and-adapter-provider-framework.md).</span></span> <span data-ttu-id="d84d7-117">这将实现可插入和可配置体系结构来动态解析终结点和转换要求和实现路由的消息。</span><span class="sxs-lookup"><span data-stu-id="d84d7-117">This implements a pluggable and configurable architecture for dynamically resolving endpoints and transform requirements and for routing messages.</span></span>  
  
-   <span data-ttu-id="d84d7-118">[路由和处理路线基于](../esb-toolkit/itinerary-based-routing-and-processing.md)。</span><span class="sxs-lookup"><span data-stu-id="d84d7-118">[Itinerary-Based Routing and Processing](../esb-toolkit/itinerary-based-routing-and-processing.md).</span></span> <span data-ttu-id="d84d7-119">路线处理机制提供了用于动态描述、 提交，并执行多个服务调用或路由/转换请求一轻型功能。</span><span class="sxs-lookup"><span data-stu-id="d84d7-119">The Itinerary Processing mechanism provides a lightweight capability for dynamically describing, submitting, and executing multiple service invocations or routing/transformation requests.</span></span>  
  
-   <span data-ttu-id="d84d7-120">[BizTalk ESB 工具包示例应用程序](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="d84d7-120">[BizTalk ESB Toolkit Sample Applications](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md).</span></span> <span data-ttu-id="d84d7-121">包含的示例应用程序演示的可能的实现[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]以及您如何使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]自己 SOA 和 ESB 的应用程序中的功能。</span><span class="sxs-lookup"><span data-stu-id="d84d7-121">The included sample applications demonstrate possible implementations of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] and how you can use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] features in your own SOA and ESB applications.</span></span>