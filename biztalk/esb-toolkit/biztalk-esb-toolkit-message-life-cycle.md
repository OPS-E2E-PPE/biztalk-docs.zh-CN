---
title: BizTalk ESB 工具包消息生命周期 |Microsoft Docs
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
ms.openlocfilehash: 8f93a4ee2024fcb9cfaf65e7cf33922784a47030
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979134"
---
# <a name="biztalk-esb-toolkit-message-life-cycle"></a><span data-ttu-id="14b12-102">BizTalk ESB 工具包消息生命周期</span><span class="sxs-lookup"><span data-stu-id="14b12-102">BizTalk ESB Toolkit Message Life Cycle</span></span>
<span data-ttu-id="14b12-103">下面是消息的来自外部系统开始并遍历 ESB 到达其最终目标的生命周期：</span><span class="sxs-lookup"><span data-stu-id="14b12-103">The following is the life cycle of a message that originates from an external system and traverses through the ESB to reach its final destination:</span></span>  

1. <span data-ttu-id="14b12-104">入口接收消息。</span><span class="sxs-lookup"><span data-stu-id="14b12-104">An on-ramp receives the message.</span></span> <span data-ttu-id="14b12-105">根据提交的参与方或客户端中，消息可能会也可能不包含定义该消息的处理指令的路线。</span><span class="sxs-lookup"><span data-stu-id="14b12-105">Depending on the submitting party or client, the message may or may not contain an itinerary that defines the processing instructions for the message.</span></span>  

2. <span data-ttu-id="14b12-106">ESB 管道组件将复制路线 （如果存在 SOAP 标头中） 到消息的上下文作为升级的属性。</span><span class="sxs-lookup"><span data-stu-id="14b12-106">ESB pipeline components copy the itinerary (if present in the SOAP header) into the context of the message as promoted properties.</span></span> <span data-ttu-id="14b12-107">如果没有路线的情况下收到消息时，可以配置特定的管道组件从一个数据库，具体取决于消息内容或上下文中，选择相应的路线，然后将路线复制到的消息上下文。</span><span class="sxs-lookup"><span data-stu-id="14b12-107">If the message is received without an itinerary, a specific pipeline component can be configured to select the appropriate itinerary from a database, depending on message content or context, and then copy the itinerary into the context of the message.</span></span> <span data-ttu-id="14b12-108">消息的生命周期的持续时间内，路线被保留在消息上下文中。</span><span class="sxs-lookup"><span data-stu-id="14b12-108">For the duration of the lifetime of the message, the itinerary is maintained within the message context.</span></span>  

3. <span data-ttu-id="14b12-109">虽然仍在管道中，计算路线，并基于消息的路线服务能够处理该消息。</span><span class="sxs-lookup"><span data-stu-id="14b12-109">While still in the pipeline, the itinerary is evaluated and message-based itinerary services can process the message.</span></span> <span data-ttu-id="14b12-110">这些路线服务可能会转换该消息，或配置路由终结点。</span><span class="sxs-lookup"><span data-stu-id="14b12-110">These itinerary services may transform the message or configure routing endpoints.</span></span>  

4. <span data-ttu-id="14b12-111">将消息发布到 Microsoft BizTalk Server Messagebox 数据库。</span><span class="sxs-lookup"><span data-stu-id="14b12-111">The message is published to the Microsoft BizTalk Server Message Box database.</span></span>  

5. <span data-ttu-id="14b12-112">BizTalk Server 评估的升级的属性的消息和队列消息的一个或多个订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="14b12-112">BizTalk Server evaluates the promoted properties of the message and queues the message for one or more subscribers.</span></span>  

6. <span data-ttu-id="14b12-113">订阅者处理的消息使用典型的 BizTalk Server 机制。</span><span class="sxs-lookup"><span data-stu-id="14b12-113">The subscriber(s) process the message using typical BizTalk Server mechanisms.</span></span> <span data-ttu-id="14b12-114">订阅服务器可以是以下之一：</span><span class="sxs-lookup"><span data-stu-id="14b12-114">A subscriber can be either of the following:</span></span>  

   -   <span data-ttu-id="14b12-115">与直接绑定上配置的筛选器的 BizTalk Server 业务流程接收端口</span><span class="sxs-lookup"><span data-stu-id="14b12-115">A BizTalk Server orchestration with a filter configured on a direct-bound receive port</span></span>  

   -   <span data-ttu-id="14b12-116">动态的 BizTalk Server 发送端口，也称为 ESB 关闭接入点。</span><span class="sxs-lookup"><span data-stu-id="14b12-116">A dynamic BizTalk Server send port, which is also referred to as an ESB off-ramp.</span></span> <span data-ttu-id="14b12-117">路线确定如何将配置端口以继续处理该消息。</span><span class="sxs-lookup"><span data-stu-id="14b12-117">The itinerary determines how the port will be configured to continue processing the message.</span></span>  

   <span data-ttu-id="14b12-118">作为通过路线接入点到达的消息的替代方法，BizTalk Server 业务流程还可以发布消息到 ESB 处理消息框：</span><span class="sxs-lookup"><span data-stu-id="14b12-118">As an alternative to a message arriving through an itinerary on-ramp, BizTalk Server orchestrations can also publish messages to the Message Box for ESB processing:</span></span>  

7. <span data-ttu-id="14b12-119">BizTalk Server 业务流程中创建一条消息。</span><span class="sxs-lookup"><span data-stu-id="14b12-119">A message is created within a BizTalk Server orchestration.</span></span>  

8. <span data-ttu-id="14b12-120">ESB 路线被填充消息的上下文。</span><span class="sxs-lookup"><span data-stu-id="14b12-120">The message's context is populated with the ESB itinerary.</span></span>  

9. <span data-ttu-id="14b12-121">通过直接绑定端口到 Messagebox 数据库中发布消息。</span><span class="sxs-lookup"><span data-stu-id="14b12-121">The message is published through a direct-bound port to the Message Box database.</span></span>
