---
title: BizTalk Server 教程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorials, getting started
- getting started, tutorials
ms.assetid: 58019f98-e91a-4705-b689-c269174d6bae
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f13a5d74d0957a208600653823e7604680296f4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232069"
---
# <a name="biztalk-server-tutorials"></a><span data-ttu-id="ae485-102">BizTalk Server 教程</span><span class="sxs-lookup"><span data-stu-id="ae485-102">BizTalk Server Tutorials</span></span>
<span data-ttu-id="ae485-103">教程以了解如何使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ae485-103">Tutorials to learn how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>

<span data-ttu-id="ae485-104">BizTalk Server 教程包含一些简单的方案，以便新用户体验如何在创建编译好的可测试集成解决方案时使用各种 BizTalk 工具。</span><span class="sxs-lookup"><span data-stu-id="ae485-104">The BizTalk Server tutorials contain simple scenarios to give new users an experience of using a variety of BizTalk tools while creating compiled, testable integration solutions.</span></span> <span data-ttu-id="ae485-105">对于更高级的用户或 BizTalk 解决方案设计的用户，请参阅[商业解决方案的方案](../core/scenarios-for-business-solutions.md)。</span><span class="sxs-lookup"><span data-stu-id="ae485-105">For more advanced users, or users who are designing BizTalk solutions, see [Scenarios for Business Solutions](../core/scenarios-for-business-solutions.md).</span></span>  
  
## <a name="enterprise-application-integration"></a><span data-ttu-id="ae485-106">企业应用程序集成</span><span class="sxs-lookup"><span data-stu-id="ae485-106">Enterprise Application Integration</span></span>
  
[<span data-ttu-id="ae485-107">教程： 企业应用程序集成</span><span class="sxs-lookup"><span data-stu-id="ae485-107">Tutorial: Enterprise Application Integration</span></span>](../core/tutorial-1-enterprise-application-integration.md) 

<span data-ttu-id="ae485-108">实现 BizTalk 解决方案，其接收来自仓库库存补货请求消息并对请求消息进行计算。</span><span class="sxs-lookup"><span data-stu-id="ae485-108">Implement a BizTalk solution that receives inventory replenishment request messages from a warehouse, and evaluates the request messages.</span></span> <span data-ttu-id="ae485-109">如果解决方案拒绝请求，然后发送拒绝消息到仓库。</span><span class="sxs-lookup"><span data-stu-id="ae485-109">If the solution denies a request, then it sends a decline message to the warehouse.</span></span> <span data-ttu-id="ae485-110">如果解决方案批准请求，然后它将消息转发到企业资源规划 (ERP) 系统。</span><span class="sxs-lookup"><span data-stu-id="ae485-110">If the solution approves a request, then it forwards the message to an Enterprise Resource Planning (ERP) system.</span></span>  

## <a name="create-a-hybrid-application"></a><span data-ttu-id="ae485-111">创建混合应用程序</span><span class="sxs-lookup"><span data-stu-id="ae485-111">Create a Hybrid Application</span></span>
[<span data-ttu-id="ae485-112">教程： 创建混合应用程序使用 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ae485-112">Tutorial: Creating a Hybrid Application Using BizTalk Server</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)  

<span data-ttu-id="ae485-113">设置的端到端应用程序使用 EDI 来生成的确认，Service Bus 接收消息，然后再将数据插入到 SQL。</span><span class="sxs-lookup"><span data-stu-id="ae485-113">Set up an end-to-end application that uses EDI to generate acknowledgements, Service Bus to receive messages, and then insert data into SQL.</span></span> 

## <a name="invoke-a-rest-interface"></a><span data-ttu-id="ae485-114">调用 REST 接口</span><span class="sxs-lookup"><span data-stu-id="ae485-114">Invoke a REST Interface</span></span>
[<span data-ttu-id="ae485-115">教程： 调用 REST 接口使用 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ae485-115">Tutorial: Invoking a REST Interface Using BizTalk Server</span></span>](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)  

<span data-ttu-id="ae485-116">使用 WCF WebHttp 适配器使用 REST 的 URL，并随后发送响应消息。</span><span class="sxs-lookup"><span data-stu-id="ae485-116">Uses the WCF-WebHttp adapter to use a REST URL, and then send a response message.</span></span> 

## <a name="integrate-biztalk-with-salesforce"></a><span data-ttu-id="ae485-117">将与 Salesforce 集成 BizTalk</span><span class="sxs-lookup"><span data-stu-id="ae485-117">Integrate BizTalk with Salesforce</span></span>
[<span data-ttu-id="ae485-118">教程： 将与 Salesforce 集成 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ae485-118">Tutorial: Integrating BizTalk Server with Salesforce</span></span>](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)  

<span data-ttu-id="ae485-119">每次创建销售机会时 Salesforce 系统中，Northwind 希望其本地系统，例如 BizTalk Server 中，若要得到通知，以便其他下游系统可以选取该数据并启动其他相关的进程。</span><span class="sxs-lookup"><span data-stu-id="ae485-119">Every time a sales opportunity is created in the Salesforce system, Northwind wants its on-premise systems, such as BizTalk Server, to be notified so that other downstream systems can pick up that data and start other relevant processes.</span></span> 

## <a name="process-json-messages"></a><span data-ttu-id="ae485-120">处理 JSON 消息</span><span class="sxs-lookup"><span data-stu-id="ae485-120">Process JSON messages</span></span>
[<span data-ttu-id="ae485-121">使用 BizTalk Server 处理 JSON 消息</span><span class="sxs-lookup"><span data-stu-id="ae485-121">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)  

<span data-ttu-id="ae485-122">设置 BizTalk 应用程序接收 JSON 采购订单。</span><span class="sxs-lookup"><span data-stu-id="ae485-122">Set up a BizTalk application that receives a JSON purchase order.</span></span> <span data-ttu-id="ae485-123">在接收管道 JSON 解码器组件 JSON 消息转换为 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="ae485-123">In the receive pipeline, a JSON decoder component transforms the JSON message to XML message.</span></span> <span data-ttu-id="ae485-124">然后，使用地图将转换为 XML 发票 XML 采购订单。</span><span class="sxs-lookup"><span data-stu-id="ae485-124">Then, uses a map to transform the XML purchase order into an XML invoice.</span></span> <span data-ttu-id="ae485-125">发送管道使用 JSON 编码器可以将 XML 发票转换为 JSON 发票，然后将消息发送。</span><span class="sxs-lookup"><span data-stu-id="ae485-125">The send pipeline uses a JSON encoder to transform the XML invoice into a JSON invoice, and then sends the message.</span></span>

## <a name="edi-interface-developer"></a><span data-ttu-id="ae485-126">EDI 接口开发人员</span><span class="sxs-lookup"><span data-stu-id="ae485-126">EDI Interface Developer</span></span>
  [<span data-ttu-id="ae485-127">教程： EDI 接口开发人员教程</span><span class="sxs-lookup"><span data-stu-id="ae485-127">Tutorial: EDI Interface Developer Tutorial</span></span>](../core/tutorial-2-edi-interface-developer-tutorial.md)
  
<span data-ttu-id="ae485-128">贸易合作伙伴发送采购订单使用 ANSI X12 4010 850 事务集 （850 消息）。</span><span class="sxs-lookup"><span data-stu-id="ae485-128">A trading partner sends purchase orders using the ANSI X12 4010 850 transaction set (an 850 message).</span></span> <span data-ttu-id="ae485-129">内部顺序系统进程采购订单。</span><span class="sxs-lookup"><span data-stu-id="ae485-129">An internal order system processes purchase orders.</span></span>

<span data-ttu-id="ae485-130">作为接口开发人员负责设计 850 消息之间的接口，你收到从贸易合作伙伴和公司的内部顺序系统。</span><span class="sxs-lookup"><span data-stu-id="ae485-130">As an interface developer responsible for designing the interface between the 850 message, you receive from your trading partner and your company’s internal Order System.</span></span> <span data-ttu-id="ae485-131">你的贸易合作伙伴要求为发送的每条 850 消息获得一个功能确认 (997)。</span><span class="sxs-lookup"><span data-stu-id="ae485-131">Your trading partner requires a Functional Acknowledgement (997) for each 850 message it sends.</span></span>


## <a name="as2"></a><span data-ttu-id="ae485-132">AS2</span><span class="sxs-lookup"><span data-stu-id="ae485-132">AS2</span></span>  
[<span data-ttu-id="ae485-133">教程： AS2 教程</span><span class="sxs-lookup"><span data-stu-id="ae485-133">Tutorial: AS2 Tutorial</span></span>](../core/tutorial-3-as2-tutorial.md)

<span data-ttu-id="ae485-134">将设置为接收和发送编码 EDIINT/AS2 消息通过 HTTP 传输的解决方案。</span><span class="sxs-lookup"><span data-stu-id="ae485-134">Set up a solution that receives and sends EDIINT/AS2-encoded messages over an HTTP transport.</span></span>    


## <a name="do-more"></a><span data-ttu-id="ae485-135">执行更多操作</span><span class="sxs-lookup"><span data-stu-id="ae485-135">Do more</span></span>  
 <span data-ttu-id="ae485-136">若要了解有关 BizTalk Server 概念和体系结构的详细信息，请考虑以下：</span><span class="sxs-lookup"><span data-stu-id="ae485-136">To learn more about BizTalk Server concepts and architecture, consider the following:</span></span>  
  
[<span data-ttu-id="ae485-137">入门</span><span class="sxs-lookup"><span data-stu-id="ae485-137">Get started</span></span>](../core/getting-started-with-biztalk-server.md)
  
[<span data-ttu-id="ae485-138">规划和设计你的 BizTalk Server 解决方案</span><span class="sxs-lookup"><span data-stu-id="ae485-138">Plan and architect your BizTalk Server solution</span></span>](../core/plan-and-architect-your-biztalk-server-solution.md)