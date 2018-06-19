---
title: 使用动态路由 |Microsoft 文档
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
ms.openlocfilehash: 38b668f53ba87a461441b0dbb498ae0677fa5956
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295693"
---
# <a name="using-dynamic-routing"></a><span data-ttu-id="8db3f-102">使用动态路由</span><span class="sxs-lookup"><span data-stu-id="8db3f-102">Using Dynamic Routing</span></span>
<span data-ttu-id="8db3f-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]支持动态路由的消息使用内置的过程和泛型传递代理; 它还支持动态路由的消息传递层使用 ESB 调度程序或 ESB 调度程序反汇编管道组件上的消息。</span><span class="sxs-lookup"><span data-stu-id="8db3f-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports dynamic routing of messages using a built-in process and a generic delivery agent; it also supports dynamic routing of messages at the messaging layer using the ESB Dispatcher or ESB Dispatcher Disassemble pipeline components.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="8db3f-104">概述</span><span class="sxs-lookup"><span data-stu-id="8db3f-104">Overview</span></span>  
 <span data-ttu-id="8db3f-105">中的动态解析机制[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]当消息到达时立即之前将消息传递，或者启用的终结点的发现。</span><span class="sxs-lookup"><span data-stu-id="8db3f-105">The dynamic resolution mechanism in [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] enables discovery of endpoints when a message arrives or immediately before a message is delivered.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="8db3f-106">它是如何工作</span><span class="sxs-lookup"><span data-stu-id="8db3f-106">How It Works</span></span>  
 <span data-ttu-id="8db3f-107">使用提供的泛型传递代理[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]是示例，开发和动态路由技术的使用情况的指南。</span><span class="sxs-lookup"><span data-stu-id="8db3f-107">The generic delivery agent provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is both a sample and a guide to the development and usage of dynamic routing techniques.</span></span> <span data-ttu-id="8db3f-108">可轻松创建其他传递代理或实现传递代理包含只发送端口 （从而未实现业务流程）。</span><span class="sxs-lookup"><span data-stu-id="8db3f-108">You can easily create additional delivery agents or implement delivery agents consisting of just a send port (which do not implement an orchestration).</span></span> <span data-ttu-id="8db3f-109">默认情况下，ESB 调度和 ESB 调度反汇编程序管道组件提供更多优化动态路由功能。</span><span class="sxs-lookup"><span data-stu-id="8db3f-109">By default, the ESB Dispatch and ESB Dispatch Disassembler pipeline components offer a much more optimized dynamic routing capability.</span></span>  
  
 <span data-ttu-id="8db3f-110">泛型传递代理本身实现业务流程中订阅了消息其中**名称**属性的当前**服务实例**路线中的元素是**Microsoft.Practices.ESB.Services.Routing**。</span><span class="sxs-lookup"><span data-stu-id="8db3f-110">The generic delivery agent itself implements an orchestration that subscribes to messages where the **Name** attribute of the current **ServiceInstance** element in the itinerary is **Microsoft.Practices.ESB.Services.Routing**.</span></span> <span data-ttu-id="8db3f-111">代理可执行以下操作序列：</span><span class="sxs-lookup"><span data-stu-id="8db3f-111">The agent performs the following sequence of operations:</span></span>  
  
1.  <span data-ttu-id="8db3f-112">接收非类型化的消息 (System.Xml.XmlDocument)。</span><span class="sxs-lookup"><span data-stu-id="8db3f-112">It receives an un-typed message (System.Xml.XmlDocument).</span></span>  
  
2.  <span data-ttu-id="8db3f-113">它尝试解析 n 数量的终结点使用的解析程序管理器。</span><span class="sxs-lookup"><span data-stu-id="8db3f-113">It attempts to resolve n number of endpoints using the resolver manager.</span></span>  
  
3.  <span data-ttu-id="8db3f-114">它使用的适配器管理器来设置消息上下文和逻辑的动态端口的终结点属性。</span><span class="sxs-lookup"><span data-stu-id="8db3f-114">It uses the adapter manager to set the endpoint properties of the message context and the logical dynamic port.</span></span>  
  
4.  <span data-ttu-id="8db3f-115">它将发布通过直接绑定发送端口，随即将会触发 BizTalk Server 订阅服务器上的动态发送端口获得进一步的消息路由消息。</span><span class="sxs-lookup"><span data-stu-id="8db3f-115">It publishes the message through the direct-bound send port, which triggers the BizTalk Server subscription on the dynamic send port for further message routing.</span></span>  
  
## <a name="how-to-configure-dynamic-routing"></a><span data-ttu-id="8db3f-116">如何配置动态路由</span><span class="sxs-lookup"><span data-stu-id="8db3f-116">How to Configure Dynamic Routing</span></span>  
 <span data-ttu-id="8db3f-117">有关如何配置动态路由使用路线设计器的详细信息，请参阅创建路线使用路线设计器。</span><span class="sxs-lookup"><span data-stu-id="8db3f-117">For more information about how to configure dynamic routing using the Itinerary Designer, see Creating Itineraries Using Itinerary Designer.</span></span>  
  
## <a name="dynamic-routing-errors"></a><span data-ttu-id="8db3f-118">动态路由错误</span><span class="sxs-lookup"><span data-stu-id="8db3f-118">Dynamic Routing Errors</span></span>  
 <span data-ttu-id="8db3f-119">动态路由机制将创建并发布[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]在以下情况下的错误消息：</span><span class="sxs-lookup"><span data-stu-id="8db3f-119">The dynamic routing mechanism will create and publish an [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Fault message in the following cases:</span></span>  
  
-   <span data-ttu-id="8db3f-120">传递代理不能在实时 (JIT) 解析期间确定的终结点。</span><span class="sxs-lookup"><span data-stu-id="8db3f-120">The delivery agent cannot determine the endpoint during just-in-time (JIT) resolution.</span></span>  
  
-   <span data-ttu-id="8db3f-121">传送失败时发生。</span><span class="sxs-lookup"><span data-stu-id="8db3f-121">A delivery failure occurs.</span></span>  
  
-   <span data-ttu-id="8db3f-122">没有任何订户存在输出消息。</span><span class="sxs-lookup"><span data-stu-id="8db3f-122">No subscriber exists for the output message.</span></span>  
  
-   <span data-ttu-id="8db3f-123">会发生任何系统异常。</span><span class="sxs-lookup"><span data-stu-id="8db3f-123">Any system exception occurs.</span></span>