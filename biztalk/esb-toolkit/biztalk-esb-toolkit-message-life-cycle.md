---
title: BizTalk ESB 工具包消息生命周期 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c72fdbda-b9ef-431a-8322-56dba98e9eab
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2cb15a4c87a497a5595327b65019ca95b3201664
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290349"
---
# <a name="biztalk-esb-toolkit-message-life-cycle"></a><span data-ttu-id="4d013-102">BizTalk ESB 工具包消息生命周期</span><span class="sxs-lookup"><span data-stu-id="4d013-102">BizTalk ESB Toolkit Message Life Cycle</span></span>
<span data-ttu-id="4d013-103">下面是一条消息，来自外部系统，并通过 ESB 到达其最终目的地遍历生命周期：</span><span class="sxs-lookup"><span data-stu-id="4d013-103">The following is the life cycle of a message that originates from an external system and traverses through the ESB to reach its final destination:</span></span>  
  
1.  <span data-ttu-id="4d013-104">入口接收的消息。</span><span class="sxs-lookup"><span data-stu-id="4d013-104">An on-ramp receives the message.</span></span> <span data-ttu-id="4d013-105">具体取决于正在提交方或客户端，消息可能会也可能不包含定义消息的处理说明路线。</span><span class="sxs-lookup"><span data-stu-id="4d013-105">Depending on the submitting party or client, the message may or may not contain an itinerary that defines the processing instructions for the message.</span></span>  
  
2.  <span data-ttu-id="4d013-106">ESB 管道组件将复制路线 （如果 SOAP 标头中存在） 到消息的上下文为提升的属性。</span><span class="sxs-lookup"><span data-stu-id="4d013-106">ESB pipeline components copy the itinerary (if present in the SOAP header) into the context of the message as promoted properties.</span></span> <span data-ttu-id="4d013-107">如果没有路线的情况下接收消息，则可以配置特定管道组件从一个数据库，具体取决于消息内容或上下文中，选择适当的路线，然后将路线复制到消息的上下文。</span><span class="sxs-lookup"><span data-stu-id="4d013-107">If the message is received without an itinerary, a specific pipeline component can be configured to select the appropriate itinerary from a database, depending on message content or context, and then copy the itinerary into the context of the message.</span></span> <span data-ttu-id="4d013-108">消息的有效期限的持续时间内，路线将保留在消息上下文中。</span><span class="sxs-lookup"><span data-stu-id="4d013-108">For the duration of the lifetime of the message, the itinerary is maintained within the message context.</span></span>  
  
3.  <span data-ttu-id="4d013-109">虽然路线计算仍在管道中，并且基于消息的路线服务能够处理该消息。</span><span class="sxs-lookup"><span data-stu-id="4d013-109">While still in the pipeline, the itinerary is evaluated and message-based itinerary services can process the message.</span></span> <span data-ttu-id="4d013-110">这些路线服务可能会转换消息，或配置路由的终结点。</span><span class="sxs-lookup"><span data-stu-id="4d013-110">These itinerary services may transform the message or configure routing endpoints.</span></span>  
  
4.  <span data-ttu-id="4d013-111">消息发布到 Microsoft BizTalk Server 消息框数据库。</span><span class="sxs-lookup"><span data-stu-id="4d013-111">The message is published to the Microsoft BizTalk Server Message Box database.</span></span>  
  
5.  <span data-ttu-id="4d013-112">BizTalk Server 用于一个或多个订阅服务器，评估提升的属性的消息和队列的消息。</span><span class="sxs-lookup"><span data-stu-id="4d013-112">BizTalk Server evaluates the promoted properties of the message and queues the message for one or more subscribers.</span></span>  
  
6.  <span data-ttu-id="4d013-113">订阅服务器上处理使用典型的 BizTalk Server 机制的消息。</span><span class="sxs-lookup"><span data-stu-id="4d013-113">The subscriber(s) process the message using typical BizTalk Server mechanisms.</span></span> <span data-ttu-id="4d013-114">订阅服务器可以是以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="4d013-114">A subscriber can be either of the following:</span></span>  
  
    -   <span data-ttu-id="4d013-115">使用筛选器直接绑定上配置 BizTalk Server 业务流程接收端口</span><span class="sxs-lookup"><span data-stu-id="4d013-115">A BizTalk Server orchestration with a filter configured on a direct-bound receive port</span></span>  
  
    -   <span data-ttu-id="4d013-116">动态的 BizTalk Server 发送端口，也称为 ESB 出口。</span><span class="sxs-lookup"><span data-stu-id="4d013-116">A dynamic BizTalk Server send port, which is also referred to as an ESB off-ramp.</span></span> <span data-ttu-id="4d013-117">路线确定如何将配置端口以便继续处理消息。</span><span class="sxs-lookup"><span data-stu-id="4d013-117">The itinerary determines how the port will be configured to continue processing the message.</span></span>  
  
 <span data-ttu-id="4d013-118">作为消息到达通过路线入口的替代方法，BizTalk Server 业务流程可以还将消息发布到 ESB 处理此消息框：</span><span class="sxs-lookup"><span data-stu-id="4d013-118">As an alternative to a message arriving through an itinerary on-ramp, BizTalk Server orchestrations can also publish messages to the Message Box for ESB processing:</span></span>  
  
1.  <span data-ttu-id="4d013-119">在 BizTalk Server 业务流程中会创建消息。</span><span class="sxs-lookup"><span data-stu-id="4d013-119">A message is created within a BizTalk Server orchestration.</span></span>  
  
2.  <span data-ttu-id="4d013-120">消息的上下文被填充 ESB 路线。</span><span class="sxs-lookup"><span data-stu-id="4d013-120">The message's context is populated with the ESB itinerary.</span></span>  
  
3.  <span data-ttu-id="4d013-121">通过直接绑定到消息框数据库端口发布消息。</span><span class="sxs-lookup"><span data-stu-id="4d013-121">The message is published through a direct-bound port to the Message Box database.</span></span>