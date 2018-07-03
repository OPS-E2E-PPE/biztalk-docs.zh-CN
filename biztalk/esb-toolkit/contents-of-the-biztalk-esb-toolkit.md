---
title: BizTalk ESB 工具包的内容 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e7114df-dadf-49ab-b024-44d84e47faa5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af25a536152544f26d55eebab1d11ee76493187c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009430"
---
# <a name="contents-of-the-biztalk-esb-toolkit"></a><span data-ttu-id="86715-102">BizTalk ESB 工具包的内容</span><span class="sxs-lookup"><span data-stu-id="86715-102">Contents of the BizTalk ESB Toolkit</span></span>
<span data-ttu-id="86715-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供的体系结构指南、 模式和实践和简化 Microsoft 平台上的企业级解决方案的开发的 BizTalk Server 和.NET Framework 组件的集合。</span><span class="sxs-lookup"><span data-stu-id="86715-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides architectural guidance, patterns and practices, and a collection of BizTalk Server and .NET Framework components to simplify the development of enterprise-scale solutions on the Microsoft platform.</span></span> <span data-ttu-id="86715-104">该工具包还提供功能，可帮助开发人员扩展现有消息传送和集成解决方案。</span><span class="sxs-lookup"><span data-stu-id="86715-104">The toolkit also provides capabilities to help developers extend existing messaging and integration solutions.</span></span> <span data-ttu-id="86715-105">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]进行互操作支持和实现松散耦合的消息传送环境，简化了构建动态的基于消息的企业应用程序的过程组件的集合组成。</span><span class="sxs-lookup"><span data-stu-id="86715-105">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] consists of a collection of interoperating components that support and implement a loosely coupled messaging environment that simplifies the process of building dynamic message-based enterprise applications.</span></span>  

 <span data-ttu-id="86715-106">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包含以下组件：</span><span class="sxs-lookup"><span data-stu-id="86715-106">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contains the following components:</span></span>  

- <span data-ttu-id="86715-107">[ESB Web 服务](../esb-toolkit/esb-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="86715-107">[ESB Web Services](../esb-toolkit/esb-web-services.md).</span></span> <span data-ttu-id="86715-108">这些公开到 ESB 的使用者，如基于路线的路由、 异常管理、 动态解析的终结点和映射，BizTalk 操作通用描述、 发现和集成 (UDDI) 互操作性的主要功能和消息内容的转换。</span><span class="sxs-lookup"><span data-stu-id="86715-108">These expose key capabilities to ESB consumers, such as itinerary-based routing, exception management, dynamic resolution of endpoints and maps, BizTalk operations, Universal Description, Discovery, and Integration (UDDI) interoperability, and transformation of message content.</span></span>  

- <span data-ttu-id="86715-109">[ESB 管理门户](../esb-toolkit/esb-management-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="86715-109">[ESB Management Portal](../esb-toolkit/esb-management-portal.md).</span></span> <span data-ttu-id="86715-110">这提供对异常和错误跟踪，消息重新提交，警报和通知、 UDDI 集成、 报告和分析，以及配置功能的支持。</span><span class="sxs-lookup"><span data-stu-id="86715-110">This provides support for exception and fault tracking, message resubmission, alerts and notifications, UDDI integration, reporting and analytics, and configuration capabilities.</span></span>  

- <span data-ttu-id="86715-111">[ESB 管道互操作组件](../esb-toolkit/esb-pipeline-interop-components.md)。</span><span class="sxs-lookup"><span data-stu-id="86715-111">[ESB Pipeline Interop Components](../esb-toolkit/esb-pipeline-interop-components.md).</span></span> <span data-ttu-id="86715-112">它们提供 BizTalk Server 简化与外部系统的互操作性的管道组件。</span><span class="sxs-lookup"><span data-stu-id="86715-112">These provide BizTalk Server pipeline components that facilitate interoperability with external systems.</span></span>  

- <span data-ttu-id="86715-113">[异常管理框架](../esb-toolkit/exception-management-framework.md)。</span><span class="sxs-lookup"><span data-stu-id="86715-113">[Exception Management Framework](../esb-toolkit/exception-management-framework.md).</span></span> <span data-ttu-id="86715-114">此捕获并整合了 BizTalk 消息传送和业务流程的子系统中的异常并提供一个机制，用于处理错误消息。</span><span class="sxs-lookup"><span data-stu-id="86715-114">This captures and consolidates exceptions from both BizTalk Messaging and Orchestration subsystems and provides a single mechanism for handling fault messages.</span></span> <span data-ttu-id="86715-115">它包括异常 Web 服务、 异常管理 API，以及组件的丰富、 处理，并将异常详细信息传递到 ESB 管理门户。</span><span class="sxs-lookup"><span data-stu-id="86715-115">It includes the exception Web service, the exception management API, and components that enrich, process, and pass exception details to the ESB Management Portal.</span></span>  

- <span data-ttu-id="86715-116">[ESB 解析程序和适配器提供程序框架](../esb-toolkit/esb-resolver-and-adapter-provider-framework.md)。</span><span class="sxs-lookup"><span data-stu-id="86715-116">[ESB Resolver and Adapter Provider Framework](../esb-toolkit/esb-resolver-and-adapter-provider-framework.md).</span></span> <span data-ttu-id="86715-117">这会实现可插入、 可配置和体系结构用于动态解析终结点和转换要求来路由消息。</span><span class="sxs-lookup"><span data-stu-id="86715-117">This implements a pluggable and configurable architecture for dynamically resolving endpoints and transform requirements and for routing messages.</span></span>  

- <span data-ttu-id="86715-118">[基于路线的路由和处理](../esb-toolkit/itinerary-based-routing-and-processing.md)。</span><span class="sxs-lookup"><span data-stu-id="86715-118">[Itinerary-Based Routing and Processing](../esb-toolkit/itinerary-based-routing-and-processing.md).</span></span> <span data-ttu-id="86715-119">路线处理机制提供轻量动态描述、 提交和执行多个服务调用或路由/转换请求的功能。</span><span class="sxs-lookup"><span data-stu-id="86715-119">The Itinerary Processing mechanism provides a lightweight capability for dynamically describing, submitting, and executing multiple service invocations or routing/transformation requests.</span></span>  

- <span data-ttu-id="86715-120">[BizTalk ESB 工具包示例应用程序](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="86715-120">[BizTalk ESB Toolkit Sample Applications](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md).</span></span> <span data-ttu-id="86715-121">包含的示例应用程序演示了可能的实现方式[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]以及如何使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]自己 SOA 和 ESB 的应用程序中的功能。</span><span class="sxs-lookup"><span data-stu-id="86715-121">The included sample applications demonstrate possible implementations of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] and how you can use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] features in your own SOA and ESB applications.</span></span>
