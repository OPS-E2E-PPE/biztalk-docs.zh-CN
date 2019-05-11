---
title: 第 1 步：为 InterAct 存储和转发方案配置 SWIFT 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03b81599-bd26-44dc-9cf3-73868248764c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e10c320f82d66d4bc78059d0e9bf078efae5e638
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366447"
---
# <a name="step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="36cc1-102">第 1 步：为 InterAct 存储和转发方案配置 SWIFT 适配器</span><span class="sxs-lookup"><span data-stu-id="36cc1-102">Step 1: Configure the SWIFT Adapter for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="36cc1-103">在开始此步骤之前，必须完成[准备使用本教程](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)。</span><span class="sxs-lookup"><span data-stu-id="36cc1-103">Before you begin this step, you must complete [Preparing to Use the Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md).</span></span>  
  
### <a name="to-configure-the-swift-adapter"></a><span data-ttu-id="36cc1-104">若要配置 SWIFT 适配器</span><span class="sxs-lookup"><span data-stu-id="36cc1-104">To configure the SWIFT adapter</span></span>  
  
1.  <span data-ttu-id="36cc1-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="36cc1-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="36cc1-106">在控制台树中，展开 BizTalk Server 管理中，展开 BizTalk 组，展开**平台设置**，展开**适配器**，右键单击**INTERACT**，依次指向**新建**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="36cc1-106">In the console tree, expand BizTalk Server Administration, expand the BizTalk group, expand **Platform Settings**, expand **Adapter**, right-click **INTERACT**, point to **New**, and then click **Send Handler**.</span></span>  
  
3.  <span data-ttu-id="36cc1-107">在中**交互-适配器处理程序属性**对话框中，在**常规**选项卡上，从**主机名**下拉列表中，选择**interacthost**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="36cc1-107">In the **INTERACT – Adapter Handler Properties** dialog box, on the **General** tab, from the **Host name** drop-down list, select **interacthost**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="36cc1-108">在中**交互传输属性**对话框中，在**属性**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="36cc1-108">In the **INTERACT Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="36cc1-109">**使用此**</span><span class="sxs-lookup"><span data-stu-id="36cc1-109">**Use this**</span></span>|<span data-ttu-id="36cc1-110">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="36cc1-110">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="36cc1-111">**参数**</span><span class="sxs-lookup"><span data-stu-id="36cc1-111">**Arguments**</span></span>|<span data-ttu-id="36cc1-112">键入以下参数:-SagMessagePartner\<进行交互的客户端消息合作伙伴创建在压降\>**注意：** 参数中的客户端是 MessagePartner 压降中配置。</span><span class="sxs-lookup"><span data-stu-id="36cc1-112">Type the following argument: –SagMessagePartner \<Interact Client Message Partner created in SAG\> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="36cc1-113">**加密模式**</span><span class="sxs-lookup"><span data-stu-id="36cc1-113">**Crypto Mode**</span></span>|<span data-ttu-id="36cc1-114">从下拉列表中，选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="36cc1-114">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="36cc1-115">**LogMessageBody**</span><span class="sxs-lookup"><span data-stu-id="36cc1-115">**LogMessageBody**</span></span>|<span data-ttu-id="36cc1-116">从下拉列表中，选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="36cc1-116">From the drop-down list, select **FALSE**.</span></span> <span data-ttu-id="36cc1-117">**注意：** 如果设置为 TRUE 时，它将保留消息正文 BizTalk 跟踪数据库中。</span><span class="sxs-lookup"><span data-stu-id="36cc1-117">**Note:**  If you set to TRUE, it preserves the message body in the BizTalk Tracking database.</span></span> <span data-ttu-id="36cc1-118">但是，出于安全原因，消息正文可以永远不会查看 BAM 门户中。</span><span class="sxs-lookup"><span data-stu-id="36cc1-118">However, for security reasons, the message body can never be viewed in the BAM portal.</span></span>|  
    |<span data-ttu-id="36cc1-119">**LogMessages**</span><span class="sxs-lookup"><span data-stu-id="36cc1-119">**LogMessages**</span></span>|<span data-ttu-id="36cc1-120">从下拉列表中，选择 **，则返回 TRUE**。</span><span class="sxs-lookup"><span data-stu-id="36cc1-120">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="36cc1-121">这样，要捕获和跟踪在 BAM 门户中的消息事件。</span><span class="sxs-lookup"><span data-stu-id="36cc1-121">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="36cc1-122">**启用**</span><span class="sxs-lookup"><span data-stu-id="36cc1-122">**Enable**</span></span>|<span data-ttu-id="36cc1-123">如果为 false。</span><span class="sxs-lookup"><span data-stu-id="36cc1-123">False.</span></span>|  
    |<span data-ttu-id="36cc1-124">**密码**</span><span class="sxs-lookup"><span data-stu-id="36cc1-124">**Password**</span></span>|<span data-ttu-id="36cc1-125">键入用于连接到压降的密码。</span><span class="sxs-lookup"><span data-stu-id="36cc1-125">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="36cc1-126">有关详细信息，请参阅压降帮助。</span><span class="sxs-lookup"><span data-stu-id="36cc1-126">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="36cc1-127">**用户名**</span><span class="sxs-lookup"><span data-stu-id="36cc1-127">**Username**</span></span>|<span data-ttu-id="36cc1-128">键入用于连接到压降的用户名。</span><span class="sxs-lookup"><span data-stu-id="36cc1-128">Type the user name you use to connect to SAG.</span></span>|  
  
5.  <span data-ttu-id="36cc1-129">单击**确定**以关闭交互传输属性对话框。</span><span class="sxs-lookup"><span data-stu-id="36cc1-129">Click **OK** to close the INTERACT Transport Properties dialog box.</span></span>  
  
6.  <span data-ttu-id="36cc1-130">单击**确定**关闭交互 – 适配器处理程序属性对话框。</span><span class="sxs-lookup"><span data-stu-id="36cc1-130">Click **OK** to close the INTERACT – Adapter Handler Properties dialog box.</span></span>  
  
7.  <span data-ttu-id="36cc1-131">在消息框中，单击**确定**，然后重新启动交互主机实例。</span><span class="sxs-lookup"><span data-stu-id="36cc1-131">In the message box, click **OK**, and then restart the InterAct host instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36cc1-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="36cc1-132">See Also</span></span>  
 <span data-ttu-id="36cc1-133">[InterAct 存储和转发 （推送） 方案](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="36cc1-133">[InterAct Store and Forward (Push) Scenario](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span></span>  
 <span data-ttu-id="36cc1-134">[步骤 2：为 InterAct 存储和转发方案向 Paramfile 添加 SWIFTNet 配置](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="36cc1-134">[Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md) </span></span>  
 <span data-ttu-id="36cc1-135">[步骤 3：创建发送端口和接收端口为 InterAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="36cc1-135">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="36cc1-136">步骤 4：测试 InterAct 存储和转发端到端方案</span><span class="sxs-lookup"><span data-stu-id="36cc1-136">Step 4: Test the InterAct Store and Forward End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)