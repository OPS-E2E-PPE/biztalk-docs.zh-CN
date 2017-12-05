---
title: "步骤 1： 配置的 SWIFT 适配器交互实时方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f4d3e08-611a-4af1-a3e3-957ace3b74e6
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab603f12e1f2c431f83af00dc79b57a9e416c251
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario"></a><span data-ttu-id="5a518-102">步骤 1： 配置的 SWIFT 适配器交互实时方案</span><span class="sxs-lookup"><span data-stu-id="5a518-102">Step 1: Configure the SWIFT Adapter for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="5a518-103">下列步骤说明如何配置交互适配器发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="5a518-103">The following steps explain how to configure the send handler for the Interact adapter.</span></span> <span data-ttu-id="5a518-104">在开始该过程之前，必须完成中列出的要求[准备使用本教程](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)。</span><span class="sxs-lookup"><span data-stu-id="5a518-104">Before you begin the procedure, you must complete the requirements listed in [Preparing to Use the Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md).</span></span>  
  
### <a name="to-configure-the-swift-adapter"></a><span data-ttu-id="5a518-105">若要配置 SWIFT 适配器</span><span class="sxs-lookup"><span data-stu-id="5a518-105">To configure the SWIFT adapter</span></span>  
  
1.  <span data-ttu-id="5a518-106">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="5a518-106">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="5a518-107">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**平台设置**，展开**适配器**，右键单击**交互**，指向**新建**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="5a518-107">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Platform Settings**, expand **Adapter**, right-click **INTERACT**, point to **New**, and then click **Send Handler**.</span></span>  
  
3.  <span data-ttu-id="5a518-108">在**交互 – 适配器处理程序属性**对话框中，在**常规**选项卡上，从**主机名**下拉列表中，选择**interacthost**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="5a518-108">In the **INTERACT – Adapter Handler Properties** dialog box, on the **General** tab, from the **Host name** drop-down list, select **interacthost**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="5a518-109">在**INTERACTTransport 属性**对话框中，在**属性**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5a518-109">In the **INTERACTTransport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="5a518-110">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="5a518-110">**Use this**</span></span>|<span data-ttu-id="5a518-111">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="5a518-111">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="5a518-112">**参数**</span><span class="sxs-lookup"><span data-stu-id="5a518-112">**Arguments**</span></span>|<span data-ttu-id="5a518-113">键入以下参数： **SagMessagePartner**\<交互的客户端消息合作伙伴创建在压降\>**注意：**自变量中的客户端是 MessagePartner 你在压降中配置。</span><span class="sxs-lookup"><span data-stu-id="5a518-113">Type the following argument: **SagMessagePartner**\<Interact Client Message Partner created in SAG\> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="5a518-114">**加密模式**</span><span class="sxs-lookup"><span data-stu-id="5a518-114">**Crypto Mode**</span></span>|<span data-ttu-id="5a518-115">从下拉列表中选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="5a518-115">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="5a518-116">**LogMessageBody**</span><span class="sxs-lookup"><span data-stu-id="5a518-116">**LogMessageBody**</span></span>|<span data-ttu-id="5a518-117">从下拉列表中选择`FALSE`。</span><span class="sxs-lookup"><span data-stu-id="5a518-117">From the drop-down list, select `FALSE`.</span></span> <span data-ttu-id="5a518-118">**注意：**如果设置为`TRUE`，它将保留跟踪数据库的消息正文。</span><span class="sxs-lookup"><span data-stu-id="5a518-118">**Note:**  If you set to `TRUE`, it preserves the message body in the tracking database.</span></span> <span data-ttu-id="5a518-119">但是，出于安全原因，消息正文可以永远不会查看 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="5a518-119">However, for security reasons, the message body can never be viewed in the BAM portal.</span></span>|  
    |<span data-ttu-id="5a518-120">**日志消息**</span><span class="sxs-lookup"><span data-stu-id="5a518-120">**LogMessages**</span></span>|<span data-ttu-id="5a518-121">从下拉列表中选择`TRUE`。</span><span class="sxs-lookup"><span data-stu-id="5a518-121">From the drop-down list, select `TRUE`.</span></span> <span data-ttu-id="5a518-122">这样将捕获和 BAM 门户中跟踪消息事件。</span><span class="sxs-lookup"><span data-stu-id="5a518-122">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="5a518-123">**启用**</span><span class="sxs-lookup"><span data-stu-id="5a518-123">**Enable**</span></span>|<span data-ttu-id="5a518-124">False</span><span class="sxs-lookup"><span data-stu-id="5a518-124">False</span></span>|  
    |<span data-ttu-id="5a518-125">**密码**</span><span class="sxs-lookup"><span data-stu-id="5a518-125">**Password**</span></span>|<span data-ttu-id="5a518-126">键入用于连接到压降的密码。</span><span class="sxs-lookup"><span data-stu-id="5a518-126">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="5a518-127">有关详细信息，请参阅压降帮助。</span><span class="sxs-lookup"><span data-stu-id="5a518-127">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="5a518-128">**用户名**</span><span class="sxs-lookup"><span data-stu-id="5a518-128">**User Name**</span></span>|<span data-ttu-id="5a518-129">键入用于连接到压降的用户名称。</span><span class="sxs-lookup"><span data-stu-id="5a518-129">Type the user name you use to connect to SAG.</span></span>|  
  
5.  <span data-ttu-id="5a518-130">单击**确定**关闭交互传输属性对话框。</span><span class="sxs-lookup"><span data-stu-id="5a518-130">Click **OK** to close the INTERACT Transport Properties dialog box.</span></span>  
  
6.  <span data-ttu-id="5a518-131">单击**确定**关闭交互 – 适配器处理程序属性对话框。</span><span class="sxs-lookup"><span data-stu-id="5a518-131">Click **OK** to close the INTERACT – Adapter Handler Properties dialog box.</span></span>  
  
7.  <span data-ttu-id="5a518-132">在消息框中，单击**确定**，然后重新启动交互主机实例。</span><span class="sxs-lookup"><span data-stu-id="5a518-132">In the message box, click **OK**, and then restart the Interact host instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a518-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a518-133">See Also</span></span>  
 <span data-ttu-id="5a518-134">[交互实时方案](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5a518-134">[InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="5a518-135">[步骤 1： 配置的 SWIFT 适配器交互实时方案](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5a518-135">[Step 1: Configure the SWIFT Adapter for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="5a518-136">[步骤 2： 将 SWIFTNet 配置添加到为 Paramfile 交互实时方案](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5a518-136">[Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="5a518-137">[步骤 3： 创建发送和接收端口交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5a518-137">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="5a518-138">步骤 4：测试 InterAct 实时端到端方案</span><span class="sxs-lookup"><span data-stu-id="5a518-138">Step 4: Test the InterAct Real-Time End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)