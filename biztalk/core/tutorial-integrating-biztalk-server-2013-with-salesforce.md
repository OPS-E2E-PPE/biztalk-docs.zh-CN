---
title: 教程： 将与 Salesforce 集成 BizTalk Server 2013 |Microsoft 文档
description: 使用服务总线和 BIzTalk Server 与 Salesforce 集成
ms.custom: ''
ms.date: 12/07/2015
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06c9ae51-3f48-4086-883b-ab4d5b6e62e3
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8af013bc97ae9618dc19cab57d52fcb4829f0842
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287173"
---
# <a name="tutorial-integrating-biztalk-server-2013-with-salesforce"></a><span data-ttu-id="33406-103">教程： 将与 Salesforce 集成 BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="33406-103">Tutorial: Integrating BizTalk Server 2013 with Salesforce</span></span>
<span data-ttu-id="33406-104">审阅者： [Nick Hauenstein](http://social.msdn.microsoft.com/profile/nick.hauenstein/)， [Steef-jan Wiggers](http://social.msdn.microsoft.com/profile/steef-jan%20wiggers)</span><span class="sxs-lookup"><span data-stu-id="33406-104">Reviewers: [Nick Hauenstein](http://social.msdn.microsoft.com/profile/nick.hauenstein/), [Steef-Jan Wiggers](http://social.msdn.microsoft.com/profile/steef-jan%20wiggers)</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="33406-105">引入了进行大量的混合方案涉及在本地和 Azure 技术现在可能某些新适配器。</span><span class="sxs-lookup"><span data-stu-id="33406-105"> introduces some new adapters that make a lot of hybrid scenarios, involving on-premises and Azure technologies now possible.</span></span> <span data-ttu-id="33406-106">在本教程中，我们将了解纯粹的云实体（如 Salesforce）如何使用某些新适配器和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与本地 [!INCLUDE[winazure](../includes/winazure-md.md)] 集成。</span><span class="sxs-lookup"><span data-stu-id="33406-106">In this tutorial, we see how to integrate a purely cloud entity like Salesforce integrate with an on-premises [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] using some of the new adapters and [!INCLUDE[winazure](../includes/winazure-md.md)].</span></span> <span data-ttu-id="33406-107">在开始之前，我们先来了解一下我们尝试通过将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与 Salesforce 集成来实现的业务目标。</span><span class="sxs-lookup"><span data-stu-id="33406-107">Before we start, let’s understand the business objective we try to achieve by integrating [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with Salesforce.</span></span>  
  
 <span data-ttu-id="33406-108">我们还可以创建涉及 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 Salesforce 以及以前版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的混合解决方案，但是，如果涉及使用 Web 服务 (SOAP) 与 Salesforce 交互，则解决方案将会更加复杂。</span><span class="sxs-lookup"><span data-stu-id="33406-108">We could also create hybrid solutions involving [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and Salesforce with previous version of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], however the solution would be much more complex involving interaction with Salesforce by consuming a Web service (SOAP).</span></span> <span data-ttu-id="33406-109">有了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和新适配器，解决方案将容易得多。</span><span class="sxs-lookup"><span data-stu-id="33406-109">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the new adapters, the solution is that much easier.</span></span>  
  
## <a name="business-scenario"></a><span data-ttu-id="33406-110">业务方案</span><span class="sxs-lookup"><span data-stu-id="33406-110">Business Scenario</span></span>  
 <span data-ttu-id="33406-111">Northwind 使用 Salesforce 在线 CRM 系统作为其通过销售渠道跟踪客户的解决方案。</span><span class="sxs-lookup"><span data-stu-id="33406-111">Northwind uses the Salesforce online CRM system as their solution for tracking customers through the sales pipeline.</span></span> <span data-ttu-id="33406-112">每次在 Salesforce 系统中创建一个销售机会时，Northwind 就会希望其本地系统（如 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]）收到通知，以使其他下游系统可以提取该数据并启动其他相关进程。</span><span class="sxs-lookup"><span data-stu-id="33406-112">Every time a sales opportunity is created in the Salesforce system, Northwind wants its on-premise systems, such as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], to be notified so that other down-stream systems can pick up that data and start other relevant processes.</span></span> <span data-ttu-id="33406-113">Northwind 计划使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供的新适配器以及添加 [!INCLUDE[winazure](../includes/winazure-md.md)] 的某些组件来实现此解决方案。</span><span class="sxs-lookup"><span data-stu-id="33406-113">Northwind plans to implement this solution using the new adapters available with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and also by including some components of [!INCLUDE[winazure](../includes/winazure-md.md)].</span></span> <span data-ttu-id="33406-114">此解决方案的端到端数据流如下所示：</span><span class="sxs-lookup"><span data-stu-id="33406-114">This is how the end-to-end data flow looks like for the solution:</span></span>  
  
-   <span data-ttu-id="33406-115">销售代表在 Salesforce 系统中创建了一个“机会”。</span><span class="sxs-lookup"><span data-stu-id="33406-115">A sales representative creates an “opportunity” in the Salesforce system.</span></span>  
  
-   <span data-ttu-id="33406-116">当该机会的状态设置为“已结束 - 赢得”时，将向 [!INCLUDE[winazure](../includes/winazure-md.md)] 上托管的中继终结点发送通知。</span><span class="sxs-lookup"><span data-stu-id="33406-116">When the status of the opportunity is set to “Closed Won”, a notification is sent to a relay endpoint hosted on [!INCLUDE[winazure](../includes/winazure-md.md)].</span></span>  
  
-   <span data-ttu-id="33406-117">使用新的 WCF-BasicHttpRelay 适配器，通知信息将传递到本地安置的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 系统。</span><span class="sxs-lookup"><span data-stu-id="33406-117">Using the new WCF-BasicHttpRelay adapter, the notification information is passed on to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system housed on-premise.</span></span>  
  
-   <span data-ttu-id="33406-118">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用作为通知的一部分收到的信息，通过新的 WCF-WebHttp 适配器调用 Salesforce 中的 REST 终结点，以获取有关机会的详细信息。</span><span class="sxs-lookup"><span data-stu-id="33406-118">Using the information received as part of the notification, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] invokes a REST endpoint in Salesforce, using the new WCF-WebHttp adapter, to get more information about the opportunity.</span></span>  
  
-   <span data-ttu-id="33406-119">最终，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用从 Salesforce 收到的信息在内部 SQL Server 数据库表中创建一个采购订单条目。</span><span class="sxs-lookup"><span data-stu-id="33406-119">Finally, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the information received from Salesforce to create a purchase order entry in an in-house SQL Server database table.</span></span>  
  
 <span data-ttu-id="33406-120">以下是为实现此解决方案中所述的集成目标必须执行的一组步骤。</span><span class="sxs-lookup"><span data-stu-id="33406-120">These are the set of steps that you must perform to achieve the integration objective outlined in this solution.</span></span> <span data-ttu-id="33406-121">其中每个步骤均涉及在继续创建解决方案时要了解的一组广泛活动。</span><span class="sxs-lookup"><span data-stu-id="33406-121">Each of these steps involves broad set of activities that we’ll look at as we proceed with creating the solution.</span></span>  
  
 <span data-ttu-id="33406-122">以下是描述端到端集成解决方案的插图：</span><span class="sxs-lookup"><span data-stu-id="33406-122">Here’s an illustration that describes the end-to-end integration solution:</span></span>  
  
 <span data-ttu-id="33406-123">![BizTalk Server 与 Salesforce 集成方案](../core/media/bts-sf-scenario.gif "BTS_SF_Scenario")</span><span class="sxs-lookup"><span data-stu-id="33406-123">![BizTalk Server and Salesforce integration scenario](../core/media/bts-sf-scenario.gif "BTS_SF_Scenario")</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="33406-124">先决条件</span><span class="sxs-lookup"><span data-stu-id="33406-124">Prerequisites</span></span>  
 <span data-ttu-id="33406-125">你必须已在要设置此解决方案的计算机上安装了以下软件：</span><span class="sxs-lookup"><span data-stu-id="33406-125">You must have the following software installed on the computer where you set up this solution:</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]  
  
-   [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]  
  
-   [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]  
  
 <span data-ttu-id="33406-126">你必须拥有以下服务订阅：</span><span class="sxs-lookup"><span data-stu-id="33406-126">You must have the following service subscriptions:</span></span>  
  
-   <span data-ttu-id="33406-127">[!INCLUDE[winazure](../includes/winazure-md.md)] 订阅</span><span class="sxs-lookup"><span data-stu-id="33406-127">A [!INCLUDE[winazure](../includes/winazure-md.md)] subscription</span></span>  
  
-   <span data-ttu-id="33406-128">Salesforce 开发人员版帐户</span><span class="sxs-lookup"><span data-stu-id="33406-128">Salesforce Developer Edition account</span></span>  
  
## <a name="more-resources"></a><span data-ttu-id="33406-129">更多资源</span><span class="sxs-lookup"><span data-stu-id="33406-129">More Resources</span></span>  
 <span data-ttu-id="33406-130">除了本教程中，你还可以查看以下资源来了解有关集成的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与 Salesforce 使用中引入的新适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="33406-130">In addition to this tutorial, you can also look at the following resources to understand more about integrating [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with Salesforce using the new adapters introduced in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="33406-131">虚拟实验室演示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 Salesforce 集成位于[http://go.microsoft.com/fwlink/?LinkId=290930](http://go.microsoft.com/fwlink/?LinkId=290930)。</span><span class="sxs-lookup"><span data-stu-id="33406-131">A virtual lab demonstrating [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and Salesforce integration is available at [http://go.microsoft.com/fwlink/?LinkId=290930](http://go.microsoft.com/fwlink/?LinkId=290930).</span></span>  
  
-   <span data-ttu-id="33406-132">基于本教程的示例是下载[http://go.microsoft.com/fwlink/?LinkId=290932](http://go.microsoft.com/fwlink/?LinkId=290932)。</span><span class="sxs-lookup"><span data-stu-id="33406-132">A sample based on this tutorial is available for download at [http://go.microsoft.com/fwlink/?LinkId=290932](http://go.microsoft.com/fwlink/?LinkId=290932).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="33406-133">后续步骤</span><span class="sxs-lookup"><span data-stu-id="33406-133">Next steps</span></span>
  
-   [<span data-ttu-id="33406-134">步骤 1： 创建服务总线 Namespace</span><span class="sxs-lookup"><span data-stu-id="33406-134">Step 1: Create a Service Bus Namespace</span></span>](../core/step-1-create-a-service-bus-namespace.md)  
  
-   [<span data-ttu-id="33406-135">步骤 2： 设置 Salesforce 系统</span><span class="sxs-lookup"><span data-stu-id="33406-135">Step 2: Set up the Salesforce System</span></span>](../core/step-2-set-up-the-salesforce-system.md)  
  
-   [<span data-ttu-id="33406-136">步骤 3： 在 Visual Studio 中创建 BizTalk 服务器解决方案</span><span class="sxs-lookup"><span data-stu-id="33406-136">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)  
  
-   [<span data-ttu-id="33406-137">步骤 4： 配置 BizTalk Server 解决方案</span><span class="sxs-lookup"><span data-stu-id="33406-137">Step 4: Configure the BizTalk Server Solution</span></span>](../core/step-4-configure-the-biztalk-server-solution.md)  
  
-   [<span data-ttu-id="33406-138">步骤 5： 测试解决方案</span><span class="sxs-lookup"><span data-stu-id="33406-138">Step 5: Test the Solution</span></span>](../core/step-5-test-the-solution.md)  
  
## <a name="see-also"></a><span data-ttu-id="33406-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33406-139">See Also</span></span>  
 [<span data-ttu-id="33406-140">BizTalk Server 教程</span><span class="sxs-lookup"><span data-stu-id="33406-140">BizTalk Server Tutorials</span></span>](../core/biztalk-server-tutorials.md)