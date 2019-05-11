---
title: 使用动态路由 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: caa3a35f-cafa-4524-8b96-f8a333b7ff87
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e30d13458e9c020f66984f42d3a472364bc8b425
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396451"
---
# <a name="using-dynamic-routing"></a><span data-ttu-id="4cbec-102">使用动态路由</span><span class="sxs-lookup"><span data-stu-id="4cbec-102">Using Dynamic Routing</span></span>
<span data-ttu-id="4cbec-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]支持动态路由的消息使用内置过程和泛型传递代理; 它还支持动态路由的消息在消息传送层使用 ESB 调度程序或 ESB 调度程序反汇编管道组件。</span><span class="sxs-lookup"><span data-stu-id="4cbec-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports dynamic routing of messages using a built-in process and a generic delivery agent; it also supports dynamic routing of messages at the messaging layer using the ESB Dispatcher or ESB Dispatcher Disassemble pipeline components.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="4cbec-104">概述</span><span class="sxs-lookup"><span data-stu-id="4cbec-104">Overview</span></span>  
 <span data-ttu-id="4cbec-105">中的动态解析机制[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]在消息到达时，或将消息传递之前立即启用的终结点的发现。</span><span class="sxs-lookup"><span data-stu-id="4cbec-105">The dynamic resolution mechanism in [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] enables discovery of endpoints when a message arrives or immediately before a message is delivered.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="4cbec-106">其工作原理</span><span class="sxs-lookup"><span data-stu-id="4cbec-106">How It Works</span></span>  
 <span data-ttu-id="4cbec-107">使用提供的泛型传递代理[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]是一个示例和开发以及动态路由技术的使用情况的指南。</span><span class="sxs-lookup"><span data-stu-id="4cbec-107">The generic delivery agent provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is both a sample and a guide to the development and usage of dynamic routing techniques.</span></span> <span data-ttu-id="4cbec-108">可以轻松地创建更多的传递代理或实现包含的只是一个发送端口 （这不会实现业务流程） 的传递代理。</span><span class="sxs-lookup"><span data-stu-id="4cbec-108">You can easily create additional delivery agents or implement delivery agents consisting of just a send port (which do not implement an orchestration).</span></span> <span data-ttu-id="4cbec-109">默认情况下，ESB 调度和 ESB 调度拆装器管道组件提供更多优化动态路由功能。</span><span class="sxs-lookup"><span data-stu-id="4cbec-109">By default, the ESB Dispatch and ESB Dispatch Disassembler pipeline components offer a much more optimized dynamic routing capability.</span></span>  
  
 <span data-ttu-id="4cbec-110">泛型传递代理本身实现业务流程订阅消息的位置**名称**属性的当前**ServiceInstance**路线中的元素是**Microsoft.Practices.ESB.Services.Routing**。</span><span class="sxs-lookup"><span data-stu-id="4cbec-110">The generic delivery agent itself implements an orchestration that subscribes to messages where the **Name** attribute of the current **ServiceInstance** element in the itinerary is **Microsoft.Practices.ESB.Services.Routing**.</span></span> <span data-ttu-id="4cbec-111">代理将执行以下一系列操作：</span><span class="sxs-lookup"><span data-stu-id="4cbec-111">The agent performs the following sequence of operations:</span></span>  
  
1.  <span data-ttu-id="4cbec-112">收到非类型化的消息 (System.Xml.XmlDocument)。</span><span class="sxs-lookup"><span data-stu-id="4cbec-112">It receives an un-typed message (System.Xml.XmlDocument).</span></span>  
  
2.  <span data-ttu-id="4cbec-113">尝试解析 n 使用的冲突解决程序管理器终结点的数目。</span><span class="sxs-lookup"><span data-stu-id="4cbec-113">It attempts to resolve n number of endpoints using the resolver manager.</span></span>  
  
3.  <span data-ttu-id="4cbec-114">它使用适配器管理器来设置消息上下文和逻辑的动态端口的终结点属性。</span><span class="sxs-lookup"><span data-stu-id="4cbec-114">It uses the adapter manager to set the endpoint properties of the message context and the logical dynamic port.</span></span>  
  
4.  <span data-ttu-id="4cbec-115">它将发布通过直接绑定的发送端口，这会触发 BizTalk Server 订阅服务器上的更多消息路由的动态发送端口的消息。</span><span class="sxs-lookup"><span data-stu-id="4cbec-115">It publishes the message through the direct-bound send port, which triggers the BizTalk Server subscription on the dynamic send port for further message routing.</span></span>  
  
## <a name="how-to-configure-dynamic-routing"></a><span data-ttu-id="4cbec-116">如何配置动态路由</span><span class="sxs-lookup"><span data-stu-id="4cbec-116">How to Configure Dynamic Routing</span></span>  
 <span data-ttu-id="4cbec-117">有关如何配置动态路由使用路线设计器的详细信息，请参阅创建路线使用路线设计器。</span><span class="sxs-lookup"><span data-stu-id="4cbec-117">For more information about how to configure dynamic routing using the Itinerary Designer, see Creating Itineraries Using Itinerary Designer.</span></span>  
  
## <a name="dynamic-routing-errors"></a><span data-ttu-id="4cbec-118">动态路由错误</span><span class="sxs-lookup"><span data-stu-id="4cbec-118">Dynamic Routing Errors</span></span>  
 <span data-ttu-id="4cbec-119">动态路由机制将创建并发布[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]在以下情况下的错误消息：</span><span class="sxs-lookup"><span data-stu-id="4cbec-119">The dynamic routing mechanism will create and publish an [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Fault message in the following cases:</span></span>  
  
-   <span data-ttu-id="4cbec-120">发送代理不能在实时 (JIT) 解析期间确定的终结点。</span><span class="sxs-lookup"><span data-stu-id="4cbec-120">The delivery agent cannot determine the endpoint during just-in-time (JIT) resolution.</span></span>  
  
-   <span data-ttu-id="4cbec-121">传送失败时发生。</span><span class="sxs-lookup"><span data-stu-id="4cbec-121">A delivery failure occurs.</span></span>  
  
-   <span data-ttu-id="4cbec-122">没有订阅服务器上存在的输出消息。</span><span class="sxs-lookup"><span data-stu-id="4cbec-122">No subscriber exists for the output message.</span></span>  
  
-   <span data-ttu-id="4cbec-123">会发生任何系统异常。</span><span class="sxs-lookup"><span data-stu-id="4cbec-123">Any system exception occurs.</span></span>