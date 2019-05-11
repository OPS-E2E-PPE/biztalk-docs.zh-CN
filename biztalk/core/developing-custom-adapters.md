---
title: 开发自定义适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44765fbb-b24d-43b6-a40c-d28e319b90a5
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85f0ea739e8ddfe4ee4294f3db33187fecb811b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351123"
---
# <a name="developing-custom-adapters"></a><span data-ttu-id="cc7c9-102">开发自定义适配器</span><span class="sxs-lookup"><span data-stu-id="cc7c9-102">Developing Custom Adapters</span></span>
<span data-ttu-id="cc7c9-103">若要与外部系统、 应用程序和实体交换消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用适配器的概念。</span><span class="sxs-lookup"><span data-stu-id="cc7c9-103">To exchange messages with external systems, applications, and entities, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the concept of an adapter.</span></span> <span data-ttu-id="cc7c9-104">适配器是 COM 或[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]传输业务最终消息的组件。</span><span class="sxs-lookup"><span data-stu-id="cc7c9-104">Adapters are COM or [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] components that transfer messages to and from business end.</span></span> <span data-ttu-id="cc7c9-105">点 （例如文件系统、 数据库和自定义业务应用程序），通过使用各种通信协议。</span><span class="sxs-lookup"><span data-stu-id="cc7c9-105">points (such as file systems, databases, and custom business applications) by using various communication protocols.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="cc7c9-106">提供了本机支持各种协议的适配器。</span><span class="sxs-lookup"><span data-stu-id="cc7c9-106">provides native adapters that support various protocols.</span></span> <span data-ttu-id="cc7c9-107">这些问题包括：</span><span class="sxs-lookup"><span data-stu-id="cc7c9-107">These include:</span></span>  
  
- <span data-ttu-id="cc7c9-108">支持发送和接收消息，从文件位置的文件适配器</span><span class="sxs-lookup"><span data-stu-id="cc7c9-108">A File adapter that supports sending and receiving messages from a File location</span></span>  
  
- <span data-ttu-id="cc7c9-109">EDI、 FTP、 HTTP、 MSMQ、 SMTP、 POP3 和 SOAP 协议的的适配器</span><span class="sxs-lookup"><span data-stu-id="cc7c9-109">Adapters for EDI, FTP, HTTP, MSMQ, SMTP, POP3, and SOAP protocols</span></span>  
  
- <span data-ttu-id="cc7c9-110">用于适配器 [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc7c9-110">An adapter for [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]</span></span>  
  
  <span data-ttu-id="cc7c9-111">在某些情况下[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可能需要消息传输到特定的自定义应用程序或使用为其本机适配器不存在的协议。</span><span class="sxs-lookup"><span data-stu-id="cc7c9-111">In some cases [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] may need to transport messages to a specific custom application or use a protocol for which a native adapter does not exist.</span></span> <span data-ttu-id="cc7c9-112">第三方公司编写了适配器，以支持其他协议。</span><span class="sxs-lookup"><span data-stu-id="cc7c9-112">Third-party companies have written adapters to support additional protocols.</span></span> <span data-ttu-id="cc7c9-113">您可能想要确定是否有您的协议的适配器在决定编写自定义适配器之前。</span><span class="sxs-lookup"><span data-stu-id="cc7c9-113">You may want to determine if there is an adapter for your protocol before deciding to write a custom adapter.</span></span> <span data-ttu-id="cc7c9-114">有关适配器和关联供应商的列表，请参阅[ http://go.microsoft.com/fwlink/?LinkId=47140 ](http://go.microsoft.com/fwlink/?LinkId=47140)。</span><span class="sxs-lookup"><span data-stu-id="cc7c9-114">For a list of adapters and associated vendors see [http://go.microsoft.com/fwlink/?LinkId=47140](http://go.microsoft.com/fwlink/?LinkId=47140).</span></span> <span data-ttu-id="cc7c9-115">如果您找不到适配器以支持您的通信要求，可以开发自定义适配器。</span><span class="sxs-lookup"><span data-stu-id="cc7c9-115">If you are unable to locate an adapter to support your communication requirements, you can develop your own custom adapter.</span></span>  
  
  <span data-ttu-id="cc7c9-116">编写自定义适配器很有挑战性的工作。</span><span class="sxs-lookup"><span data-stu-id="cc7c9-116">Writing a custom adapter can be a challenging exercise.</span></span> <span data-ttu-id="cc7c9-117">若要简化此过程，Microsoft 已开发了称作适配器框架的基础。</span><span class="sxs-lookup"><span data-stu-id="cc7c9-117">To simplify this process Microsoft has developed a foundation called the Adapter Framework.</span></span> <span data-ttu-id="cc7c9-118">您可以将此框架作为基础进行开发以及在示例适配器源代码[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SDK。</span><span class="sxs-lookup"><span data-stu-id="cc7c9-118">You can use this framework as a basis for your development along with sample adapter source code in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK.</span></span>  
  
  <span data-ttu-id="cc7c9-119">在本部分中的主题提供自定义适配器的开发技巧和建议。</span><span class="sxs-lookup"><span data-stu-id="cc7c9-119">The topics in this section present custom adapter development tips and recommendations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cc7c9-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="cc7c9-120">In This Section</span></span>  
  
-   [<span data-ttu-id="cc7c9-121">适配器框架概述</span><span class="sxs-lookup"><span data-stu-id="cc7c9-121">What Is the Adapter Framework?</span></span>](../core/what-is-the-adapter-framework.md)  
  
-   [<span data-ttu-id="cc7c9-122">BizTalk Server 如何实例化适配器</span><span class="sxs-lookup"><span data-stu-id="cc7c9-122">How BizTalk Server Instantiates an Adapter</span></span>](../core/how-biztalk-server-instantiates-an-adapter.md)  
  
-   [<span data-ttu-id="cc7c9-123">消息批</span><span class="sxs-lookup"><span data-stu-id="cc7c9-123">Message Batches</span></span>](../core/message-batches.md)  
  
-   [<span data-ttu-id="cc7c9-124">事务性消息批</span><span class="sxs-lookup"><span data-stu-id="cc7c9-124">Transactional Message Batches</span></span>](../core/transactional-message-batches.md)  
  
-   [<span data-ttu-id="cc7c9-125">开发接收适配器</span><span class="sxs-lookup"><span data-stu-id="cc7c9-125">Developing a Receive Adapter</span></span>](../core/developing-a-receive-adapter.md)  
  
-   [<span data-ttu-id="cc7c9-126">开发发送适配器</span><span class="sxs-lookup"><span data-stu-id="cc7c9-126">Developing a Send Adapter</span></span>](../core/developing-a-send-adapter.md)  
  
-   [<span data-ttu-id="cc7c9-127">实例化独立适配器</span><span class="sxs-lookup"><span data-stu-id="cc7c9-127">Instantiating Isolated Adapters</span></span>](../core/instantiating-isolated-adapters.md)  
  
-   [<span data-ttu-id="cc7c9-128">适配器设计问题</span><span class="sxs-lookup"><span data-stu-id="cc7c9-128">Adapter Design Issues</span></span>](../core/adapter-design-issues.md)  
  
-   [<span data-ttu-id="cc7c9-129">适配器如何处理大消息</span><span class="sxs-lookup"><span data-stu-id="cc7c9-129">How Adapters Handle Large Messages</span></span>](../core/how-adapters-handle-large-messages.md)  
  
-   [<span data-ttu-id="cc7c9-130">如何处理适配器故障</span><span class="sxs-lookup"><span data-stu-id="cc7c9-130">How to Handle Adapter Failures</span></span>](../core/how-to-handle-adapter-failures.md)  
  
-   [<span data-ttu-id="cc7c9-131">如何终止适配器</span><span class="sxs-lookup"><span data-stu-id="cc7c9-131">How to Terminate an Adapter</span></span>](../core/how-to-terminate-an-adapter.md)  
  
-   [<span data-ttu-id="cc7c9-132">如何设计优异的适配器</span><span class="sxs-lookup"><span data-stu-id="cc7c9-132">How to Design a Performant Adapter</span></span>](../core/how-to-design-a-performant-adapter.md)  
  
-   [<span data-ttu-id="cc7c9-133">如何部署自定义适配器</span><span class="sxs-lookup"><span data-stu-id="cc7c9-133">How to Deploy a Custom Adapter</span></span>](../core/how-to-deploy-a-custom-adapter.md)  
  
-   [<span data-ttu-id="cc7c9-134">如何测试和调试适配器</span><span class="sxs-lookup"><span data-stu-id="cc7c9-134">How to Test and Debug an Adapter</span></span>](../core/how-to-test-and-debug-an-adapter.md)  
  
-   [<span data-ttu-id="cc7c9-135">如何向 BizTalk 项目添加适配器元数据</span><span class="sxs-lookup"><span data-stu-id="cc7c9-135">How to Add Adapter Metadata to a BizTalk Project</span></span>](../core/how-to-add-adapter-metadata-to-a-biztalk-project.md)  
  
-   [<span data-ttu-id="cc7c9-136">适配器本地化问题</span><span class="sxs-lookup"><span data-stu-id="cc7c9-136">Adapter Localization Issues</span></span>](../core/adapter-localization-issues.md)  
  
-   [<span data-ttu-id="cc7c9-137">设计适配器的提示</span><span class="sxs-lookup"><span data-stu-id="cc7c9-137">Tips for Designing Your Adapter</span></span>](../core/tips-for-designing-your-adapter.md)  
  
-   [<span data-ttu-id="cc7c9-138">适配器设计时配置</span><span class="sxs-lookup"><span data-stu-id="cc7c9-138">Adapter Design-Time Configuration</span></span>](../core/adapter-design-time-configuration.md)  
  
## <a name="see-also"></a><span data-ttu-id="cc7c9-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc7c9-139">See Also</span></span>  
 [<span data-ttu-id="cc7c9-140">开发自定义组件</span><span class="sxs-lookup"><span data-stu-id="cc7c9-140">Developing Custom Components</span></span>](../core/developing-custom-components.md)