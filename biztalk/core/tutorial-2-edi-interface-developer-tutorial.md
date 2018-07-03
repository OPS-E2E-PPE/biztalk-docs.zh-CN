---
title: '教程 2: EDI 接口开发人员教程 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d10fb650-cbb9-41e5-a80d-06afd0513814
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f995cc21bd94ddc00ab15d78c74679eb51d939b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020426"
---
# <a name="tutorial-2-edi-interface-developer-tutorial"></a><span data-ttu-id="3aa88-102">教程 2: EDI 接口开发人员教程</span><span class="sxs-lookup"><span data-stu-id="3aa88-102">Tutorial 2: EDI Interface Developer Tutorial</span></span>
<span data-ttu-id="3aa88-103">本教程演示如何使用接口开发人员 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的 EDI 功能。</span><span class="sxs-lookup"><span data-stu-id="3aa88-103">This tutorial demonstrates how to use the EDI functionality in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in an Interface Developer scenario.</span></span>  
  
 <span data-ttu-id="3aa88-104">**教程方案**</span><span class="sxs-lookup"><span data-stu-id="3aa88-104">**Tutorial Scenario**</span></span>  
  
 <span data-ttu-id="3aa88-105">在此教程中，你的贸易合作伙伴使用 ANSI X12 版本 4010 850 事务集（一条 850 消息）将采购订单发送到你的公司。</span><span class="sxs-lookup"><span data-stu-id="3aa88-105">In this scenario, your trading partner sends Purchase Orders to your company using the ANSI X12 Version 4010 850 Transaction Set (an 850 message).</span></span> <span data-ttu-id="3aa88-106">你的公司使用名为“订单系统”的内部应用程序处理采购订单。</span><span class="sxs-lookup"><span data-stu-id="3aa88-106">Your company uses an internal application, the Order System, to process purchase orders.</span></span>  
  
 <span data-ttu-id="3aa88-107">你是一名接口开发人员，负责设计从贸易合作伙伴处收到的 850 消息与公司内部的订单系统之间的接口。</span><span class="sxs-lookup"><span data-stu-id="3aa88-107">You are an interface developer responsible for designing the interface between the 850 message you receive from your trading partner and your company’s internal Order System.</span></span> <span data-ttu-id="3aa88-108">你的贸易合作伙伴要求为发送的每条 850 消息获得一个功能确认 (997)。</span><span class="sxs-lookup"><span data-stu-id="3aa88-108">Your trading partner requires a Functional Acknowledgement (997) for each 850 message it sends.</span></span>  
  
 <span data-ttu-id="3aa88-109">为了方便地进行引用，使用了以下标识符：</span><span class="sxs-lookup"><span data-stu-id="3aa88-109">For ease of reference, the following identifiers are used:</span></span>  
  
|<span data-ttu-id="3aa88-110">实体</span><span class="sxs-lookup"><span data-stu-id="3aa88-110">Entity</span></span>|<span data-ttu-id="3aa88-111">Identifier</span><span class="sxs-lookup"><span data-stu-id="3aa88-111">Identifier</span></span>|  
|------------|----------------|  
|<span data-ttu-id="3aa88-112">你的公司</span><span class="sxs-lookup"><span data-stu-id="3aa88-112">Your company</span></span>|<span data-ttu-id="3aa88-113">OrderSystem</span><span class="sxs-lookup"><span data-stu-id="3aa88-113">OrderSystem</span></span>|  
|<span data-ttu-id="3aa88-114">你的贸易合作伙伴</span><span class="sxs-lookup"><span data-stu-id="3aa88-114">Your trading partner</span></span>|<span data-ttu-id="3aa88-115">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="3aa88-115">Fabrikam</span></span>|  
  
 <span data-ttu-id="3aa88-116">在完成的解决方案中，消息的流动过程如下所示：</span><span class="sxs-lookup"><span data-stu-id="3aa88-116">The message flow in the completed solution will be as follows:</span></span>  
  
 <span data-ttu-id="3aa88-117">![EDI 接口开发人员教程消息流](../core/media/4944352a-dc77-47f1-a324-bf71444670c5.gif "4944352a-dc77-47f1-a324-bf71444670c5")</span><span class="sxs-lookup"><span data-stu-id="3aa88-117">![EDI Interface Developer Tutorial message flow](../core/media/4944352a-dc77-47f1-a324-bf71444670c5.gif "4944352a-dc77-47f1-a324-bf71444670c5")</span></span>  
  
 <span data-ttu-id="3aa88-118">**消息流**</span><span class="sxs-lookup"><span data-stu-id="3aa88-118">**Message Flow**</span></span>  
  
 <span data-ttu-id="3aa88-119">教程中的解决方案将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3aa88-119">The solution in this tutorial will do the following:</span></span>  
  
1. <span data-ttu-id="3aa88-120">接收来自贸易合作伙伴 Fabrikam 的平面文件交换。</span><span class="sxs-lookup"><span data-stu-id="3aa88-120">Receive a flat-file interchange from the trading partner Fabrikam.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="3aa88-121">此列表中的事件可能不会按所示顺序发生。</span><span class="sxs-lookup"><span data-stu-id="3aa88-121">The events in this list may not occur in the order shown.</span></span>  
  
2. <span data-ttu-id="3aa88-122">对照 EDI 交换的架构验证该交换，将消息拆装成 XML，并将消息 XML 放置到 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="3aa88-122">Validate the EDI interchange against its schema, disassemble the message into XML, and drop the message XML into the MessageBox.</span></span>  
  
3. <span data-ttu-id="3aa88-123">为收到的 EDI 交换生成 997 确认，并将其放置到 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="3aa88-123">Generate a 997 acknowledgment to the received EDI interchange, and drop it in the MessageBox.</span></span>  
  
4. <span data-ttu-id="3aa88-124">通过单向发送端口提取 997 XML，并组装 997 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="3aa88-124">Pick up the 997 XML by a one-way send port, and assemble the 997 EDI interchange.</span></span>  
  
5. <span data-ttu-id="3aa88-125">将 997 交换发送给 Fabrikam。</span><span class="sxs-lookup"><span data-stu-id="3aa88-125">Send the 997 interchange to Fabrikam.</span></span>  
  
6. <span data-ttu-id="3aa88-126">提取消息 XML 通过单向发送端口，并组装消息 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="3aa88-126">Pick up the Msg XML by a one-way send port, and assemble the message EDI interchange.</span></span>  
  
7. <span data-ttu-id="3aa88-127">将 EDI 交换发送给 OrderSystem。</span><span class="sxs-lookup"><span data-stu-id="3aa88-127">Send the EDI interchange to OrderSystem.</span></span>  
  
   <span data-ttu-id="3aa88-128">**Configuration**</span><span class="sxs-lookup"><span data-stu-id="3aa88-128">**Configuration**</span></span>  
  
   <span data-ttu-id="3aa88-129">在本教程中，你将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3aa88-129">In this tutorial, you will do the following:</span></span>  
  
- <span data-ttu-id="3aa88-130">配置 BizTalk 以期望从你的贸易合作伙伴处获得 850 消息并发回一个 997 确认</span><span class="sxs-lookup"><span data-stu-id="3aa88-130">Configure BizTalk to expect the 850 message from your trading partner and to send back a 997 acknowledgment</span></span>  
  
- <span data-ttu-id="3aa88-131">使用 BizTalk 映射将 850 消息数据转换为订单系统所需的格式。</span><span class="sxs-lookup"><span data-stu-id="3aa88-131">Use a BizTalk map to convert the 850 message data into the format required by the Order System.</span></span> <span data-ttu-id="3aa88-132">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK 教程文件中提供了此映射。</span><span class="sxs-lookup"><span data-stu-id="3aa88-132">This map is provided in the tutorial files in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK.</span></span>  
  
- <span data-ttu-id="3aa88-133">配置用于接收 850 消息的接收端口。</span><span class="sxs-lookup"><span data-stu-id="3aa88-133">Configure a receive port for receiving the 850 message.</span></span>  
  
- <span data-ttu-id="3aa88-134">配置发送端口以正确格式发送 OrderSystem 850 消息到 OrderSystem。</span><span class="sxs-lookup"><span data-stu-id="3aa88-134">Configure a send port to send the 850 message to OrderSystem in the correct format.</span></span>  
  
- <span data-ttu-id="3aa88-135">配置发送端口以订阅 BizTalk 生成的 997 确认并将其路由回贸易合作伙伴，Fabrikam。</span><span class="sxs-lookup"><span data-stu-id="3aa88-135">Configure a send port to subscribe to the BizTalk-generated 997 acknowledgment for routing back to the trading partner, Fabrikam.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3aa88-136">本节内容</span><span class="sxs-lookup"><span data-stu-id="3aa88-136">In This Section</span></span>  
  
-   [<span data-ttu-id="3aa88-137">步骤 1：EDI 接口开发人员教程的准备工作</span><span class="sxs-lookup"><span data-stu-id="3aa88-137">Step 1: Prepare for the EDI Interface Developer Tutorial</span></span>](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)  
  
-   [<span data-ttu-id="3aa88-138"> 2：更新和部署教程解决方案</span><span class="sxs-lookup"><span data-stu-id="3aa88-138">Step 2: Update and Deploy the Tutorial Solution</span></span>](../core/step-2-update-and-deploy-the-tutorial-solution.md)  
  
-   [<span data-ttu-id="3aa88-139">步骤 3：配置组织的参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="3aa88-139">Step 3: Configure a Party and Business Profile for Your Organization</span></span>](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)  
  
-   [<span data-ttu-id="3aa88-140">步骤 4：为贸易合作伙伴配置参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="3aa88-140">Step 4: Configure a Party and Business Profile for Your Trading Partner</span></span>](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md)  
  
-   [<span data-ttu-id="3aa88-141">步骤 5：配置接收端口和接收位置</span><span class="sxs-lookup"><span data-stu-id="3aa88-141">Step 5: Configure a Receive Port and Receive Location</span></span>](../core/step-5-configure-a-receive-port-and-receive-location.md)  
  
-   [<span data-ttu-id="3aa88-142">步骤 6：将发送端口配置为将数据发给你的组织</span><span class="sxs-lookup"><span data-stu-id="3aa88-142">Step 6: Configure a Send Port to Send Data to Your Organization</span></span>](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md)  
  
-   [<span data-ttu-id="3aa88-143">步骤 7：配置发送端口向贸易合作伙伴发送确认</span><span class="sxs-lookup"><span data-stu-id="3aa88-143">Step 7: Configure a Send Port to Send the Acknowledgment to Your Trading Partner</span></span>](../core/step-7-configure-a-send-port-to-send-the-acknowledgment-to-trading-partner.md)  
  
-   [<span data-ttu-id="3aa88-144">步骤 8：配置参与方间的贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="3aa88-144">Step 8: Configure the Trading Partner Agreement between the Parties</span></span>](../core/step-8-configure-the-trading-partner-agreement-between-the-parties.md)  
  
-   [<span data-ttu-id="3aa88-145">步骤 9：测试 EDI 解决方案</span><span class="sxs-lookup"><span data-stu-id="3aa88-145">Step 9: Test the EDI Solution</span></span>](../core/step-9-test-the-edi-solution.md)  
  
## <a name="see-also"></a><span data-ttu-id="3aa88-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="3aa88-146">See Also</span></span>  
 [<span data-ttu-id="3aa88-147">BizTalk Server 教程</span><span class="sxs-lookup"><span data-stu-id="3aa88-147">BizTalk Server Tutorials</span></span>](../core/biztalk-server-tutorials.md)