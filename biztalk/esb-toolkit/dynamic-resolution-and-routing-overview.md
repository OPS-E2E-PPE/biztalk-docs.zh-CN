---
title: 动态解析和路由概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a9a32491-132b-4b25-ac8c-4a927052f0be
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab7ea6f4ddd37be8d8c2c6629d2449c2d9df5f81
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018763"
---
# <a name="dynamic-resolution-and-routing-overview"></a><span data-ttu-id="b13c0-102">动态解析和路由概述</span><span class="sxs-lookup"><span data-stu-id="b13c0-102">Dynamic Resolution and Routing Overview</span></span>
<span data-ttu-id="b13c0-103">ESB 解析程序类支持以下运行时解析：</span><span class="sxs-lookup"><span data-stu-id="b13c0-103">The ESB Resolver classes support run-time resolution of the following:</span></span>  

- <span data-ttu-id="b13c0-104">消息传递终结点</span><span class="sxs-lookup"><span data-stu-id="b13c0-104">Message delivery endpoints</span></span>  

- <span data-ttu-id="b13c0-105">用于转换的映射</span><span class="sxs-lookup"><span data-stu-id="b13c0-105">Maps for transformation</span></span>  

- <span data-ttu-id="b13c0-106">终结点配置</span><span class="sxs-lookup"><span data-stu-id="b13c0-106">Endpoint configuration</span></span>  

- <span data-ttu-id="b13c0-107">自定义服务元数据</span><span class="sxs-lookup"><span data-stu-id="b13c0-107">Custom service metadata</span></span>  

- <span data-ttu-id="b13c0-108">服务器端的路线</span><span class="sxs-lookup"><span data-stu-id="b13c0-108">Server-side itineraries</span></span>  

  <span data-ttu-id="b13c0-109">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]冲突解决程序的连接字符串用于在消息到达时尝试的映射和终结点解析。</span><span class="sxs-lookup"><span data-stu-id="b13c0-109">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] uses resolver connection strings to attempt resolution of maps and endpoints when messages arrive.</span></span> <span data-ttu-id="b13c0-110">这些连接字符串中可能存在路线的 SOAP 标头的消息到达时，或可能会设置它们的自定义管道使用以下管道组件之一时： ESB 路线选择器、 ESB 调度程序或 ESB 调度程序反汇编。</span><span class="sxs-lookup"><span data-stu-id="b13c0-110">These connections strings may exist in the itinerary SOAP header of messages when they arrive, or they may be set in a custom pipeline using one of the following pipeline components: ESB Itinerary Selector, ESB Dispatcher, or ESB Dispatcher Disassemble.</span></span> <span data-ttu-id="b13c0-111">使用 ESB 解析程序和适配器提供程序框架组件的"实时"(JIT) 解析功能在处理生命周期中稍后发生解析。</span><span class="sxs-lookup"><span data-stu-id="b13c0-111">Resolution occurs later in the processing life cycle using the "just-in-time" (JIT) resolution capabilities of the ESB Resolver and Adapter Provider Framework components.</span></span>  

  <span data-ttu-id="b13c0-112">例如，如果动态转换代理收到一条消息必须映射，但尚未确定映射名称，它将尝试使用关联的冲突解决程序来执行解析。</span><span class="sxs-lookup"><span data-stu-id="b13c0-112">For example, if the dynamic transformation agent receives a message that it must map, but the map name has not yet been determined, it will attempt to use the associated resolver to perform the resolution.</span></span> <span data-ttu-id="b13c0-113">如果 JIT 解析失败，这被归类为错误，则系统可以生成一条异常消息。</span><span class="sxs-lookup"><span data-stu-id="b13c0-113">If JIT resolution fails, which is classed as an error, the system generates an exception message.</span></span>  

  <span data-ttu-id="b13c0-114">冲突解决程序和适配器提供程序框架可以查询以下数据存储或解决机制：</span><span class="sxs-lookup"><span data-stu-id="b13c0-114">The Resolver and Adapter Provider Framework can query the following data stores or resolution mechanisms:</span></span>  

- <span data-ttu-id="b13c0-115">硬编码映射或终结点，在其中写动态解析不会发生</span><span class="sxs-lookup"><span data-stu-id="b13c0-115">Hard-coded maps or endpoints, in which case dynamic resolution does not occur</span></span>  

- <span data-ttu-id="b13c0-116">业务规则引擎 (BRE) 策略</span><span class="sxs-lookup"><span data-stu-id="b13c0-116">A Business Rules Engine (BRE) policy</span></span>  

- <span data-ttu-id="b13c0-117">实现自定义程序集**IResolveProvider**接口</span><span class="sxs-lookup"><span data-stu-id="b13c0-117">A custom assembly implementing the **IResolveProvider** interface</span></span>  

- <span data-ttu-id="b13c0-118">XPath 查询到消息</span><span class="sxs-lookup"><span data-stu-id="b13c0-118">An XPath query over the message</span></span>  

- <span data-ttu-id="b13c0-119">通用描述、 发现和集成 (UDDI) 查找</span><span class="sxs-lookup"><span data-stu-id="b13c0-119">A Universal Description, Discovery, and Integration (UDDI) lookup</span></span>
