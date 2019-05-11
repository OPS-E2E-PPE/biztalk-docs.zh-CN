---
title: 第 1 步：为 InterAct 存储和转发 （拉取） 方案配置 SWIFT 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4182021c-36c9-4c96-b2fa-e23c87862cfe
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a609ad94e6d8b0dcafb50d1025159b1dfcdde5af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366496"
---
# <a name="step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="4dda7-102">第 1 步：为 InterAct 存储和转发 （拉取） 方案配置 SWIFT 适配器</span><span class="sxs-lookup"><span data-stu-id="4dda7-102">Step 1: Configure the SWIFT Adapter for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="4dda7-103">在开始此步骤之前，必须完成[准备使用本教程](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)。</span><span class="sxs-lookup"><span data-stu-id="4dda7-103">Before you begin this step, you must complete [Preparing to Use the Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md).</span></span>  
  
### <a name="to-configure-the-swift-adapter"></a><span data-ttu-id="4dda7-104">若要配置 SWIFT 适配器</span><span class="sxs-lookup"><span data-stu-id="4dda7-104">To configure the SWIFT adapter</span></span>  
  
1.  <span data-ttu-id="4dda7-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="4dda7-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="4dda7-106">在控制台树中，展开 BizTalk Server 管理中，展开 BizTalk 组，展开**平台设置**，展开**适配器**，右键单击**INTERACT**，依次指向**新建**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="4dda7-106">In the console tree, expand BizTalk Server Administration, expand the BizTalk group, expand **Platform Settings**, expand **Adapter**, right-click **INTERACT**, point to **New**, and then click **Send Handler**.</span></span>  
  
3.  <span data-ttu-id="4dda7-107">在中**交互-适配器处理程序属性**对话框中，在**常规**选项卡上，从**主机名**下拉列表中，选择**interacthost**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="4dda7-107">In the **INTERACT – Adapter Handler Properties** dialog box, on the **General** tab, from the **Host name** drop-down list, select **interacthost**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="4dda7-108">在中**交互传输属性**对话框中，在**属性**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4dda7-108">In the **INTERACT Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="4dda7-109">**使用此**</span><span class="sxs-lookup"><span data-stu-id="4dda7-109">**Use this**</span></span>|<span data-ttu-id="4dda7-110">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="4dda7-110">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="4dda7-111">**参数**</span><span class="sxs-lookup"><span data-stu-id="4dda7-111">**Arguments**</span></span>|<span data-ttu-id="4dda7-112">键入以下参数:-SagMessagePartner\<进行交互的客户端消息合作伙伴创建在压降\>**注意：** 参数中的客户端是 MessagePartner 压降中配置。</span><span class="sxs-lookup"><span data-stu-id="4dda7-112">Type the following argument: –SagMessagePartner \<Interact Client Message Partner created in SAG\> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="4dda7-113">**加密模式**</span><span class="sxs-lookup"><span data-stu-id="4dda7-113">**Crypto Mode**</span></span>|<span data-ttu-id="4dda7-114">从下拉列表中，选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="4dda7-114">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="4dda7-115">**LogMessageBody**</span><span class="sxs-lookup"><span data-stu-id="4dda7-115">**LogMessageBody**</span></span>|<span data-ttu-id="4dda7-116">从下拉列表中，选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="4dda7-116">From the drop-down list, select **FALSE**.</span></span> <span data-ttu-id="4dda7-117">**注意：** 如果设置为 TRUE 时，它将保留消息正文 BizTalk 跟踪数据库中。</span><span class="sxs-lookup"><span data-stu-id="4dda7-117">**Note:**  If you set to TRUE, it preserves the message body in the BizTalk Tracking database.</span></span> <span data-ttu-id="4dda7-118">但是，出于安全原因，消息正文可以永远不会查看 BAM 门户中。</span><span class="sxs-lookup"><span data-stu-id="4dda7-118">However, for security reasons, the message body can never be viewed in the BAM portal.</span></span>|  
    |<span data-ttu-id="4dda7-119">**LogMessages**</span><span class="sxs-lookup"><span data-stu-id="4dda7-119">**LogMessages**</span></span>|<span data-ttu-id="4dda7-120">从下拉列表中，选择 **，则返回 TRUE**。</span><span class="sxs-lookup"><span data-stu-id="4dda7-120">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="4dda7-121">这样，要捕获和跟踪在 BAM 门户中的消息事件。</span><span class="sxs-lookup"><span data-stu-id="4dda7-121">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="4dda7-122">**启用**</span><span class="sxs-lookup"><span data-stu-id="4dda7-122">**Enable**</span></span>|<span data-ttu-id="4dda7-123">如果为 false。</span><span class="sxs-lookup"><span data-stu-id="4dda7-123">False.</span></span>|  
    |<span data-ttu-id="4dda7-124">**密码**</span><span class="sxs-lookup"><span data-stu-id="4dda7-124">**Password**</span></span>|<span data-ttu-id="4dda7-125">键入用于连接到压降的密码。</span><span class="sxs-lookup"><span data-stu-id="4dda7-125">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="4dda7-126">有关详细信息，请参阅压降帮助。</span><span class="sxs-lookup"><span data-stu-id="4dda7-126">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="4dda7-127">**用户名**</span><span class="sxs-lookup"><span data-stu-id="4dda7-127">**Username**</span></span>|<span data-ttu-id="4dda7-128">键入用于连接到压降的用户名。</span><span class="sxs-lookup"><span data-stu-id="4dda7-128">Type the user name you use to connect to SAG.</span></span>|  
  
5.  <span data-ttu-id="4dda7-129">单击**确定**以关闭交互传输属性对话框。</span><span class="sxs-lookup"><span data-stu-id="4dda7-129">Click **OK** to close the INTERACT Transport Properties dialog box.</span></span>  
  
6.  <span data-ttu-id="4dda7-130">单击**确定**关闭交互 – 适配器处理程序属性对话框。</span><span class="sxs-lookup"><span data-stu-id="4dda7-130">Click **OK** to close the INTERACT – Adapter Handler Properties dialog box.</span></span>  
  
7.  <span data-ttu-id="4dda7-131">在消息框中，单击**确定**，然后重新启动交互主机实例。</span><span class="sxs-lookup"><span data-stu-id="4dda7-131">In the message box, click **OK**, and then restart the InterAct host instance.</span></span>  
  
8.  <span data-ttu-id="4dda7-132">重复步骤 1。</span><span class="sxs-lookup"><span data-stu-id="4dda7-132">Repeat step 1.</span></span>  
  
9. <span data-ttu-id="4dda7-133">在控制台树中，展开 BizTalk Server 管理，展开**BizTalk**组中，展开**平台设置**，展开**适配器**中，选择交互，打开**BizTalkServerApplication** ，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="4dda7-133">In the console tree, expand BizTalk Server Administration, expand the **BizTalk** group, expand **Platform Settings**, expand **Adapter**, select INTERACT, open **BizTalkServerApplication** and then, click **Properties**.</span></span>  
  
10. <span data-ttu-id="4dda7-134">在中**交互传输属性**对话框中，在**属性**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4dda7-134">In the **INTERACT Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="4dda7-135">**使用此**</span><span class="sxs-lookup"><span data-stu-id="4dda7-135">**Use this**</span></span>|<span data-ttu-id="4dda7-136">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="4dda7-136">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="4dda7-137">**参数**</span><span class="sxs-lookup"><span data-stu-id="4dda7-137">**Arguments**</span></span>|<span data-ttu-id="4dda7-138">键入以下参数:-SagMessagePartner\<进行交互的客户端消息合作伙伴创建在压降\>**注意：** 参数中的客户端是 MessagePartner 压降中配置。</span><span class="sxs-lookup"><span data-stu-id="4dda7-138">Type the following argument: –SagMessagePartner \<Interact Client Message Partner created in SAG\> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="4dda7-139">**加密模式**</span><span class="sxs-lookup"><span data-stu-id="4dda7-139">**Crypto Mode**</span></span>|<span data-ttu-id="4dda7-140">从下拉列表中，选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="4dda7-140">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="4dda7-141">**LogMessageBody**</span><span class="sxs-lookup"><span data-stu-id="4dda7-141">**LogMessageBody**</span></span>|<span data-ttu-id="4dda7-142">从下拉列表中，选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="4dda7-142">From the drop-down list, select **FALSE**.</span></span> <span data-ttu-id="4dda7-143">**注意：** 如果设置为 TRUE 时，它将保留消息正文 BizTalk 跟踪数据库中。</span><span class="sxs-lookup"><span data-stu-id="4dda7-143">**Note:**  If you set to TRUE, it preserves the message body in the BizTalk Tracking database.</span></span> <span data-ttu-id="4dda7-144">但是，出于安全原因，消息正文可以永远不会查看 BAM 门户中。</span><span class="sxs-lookup"><span data-stu-id="4dda7-144">However, for security reasons, the message body can never be viewed in the BAM portal.</span></span>|  
    |<span data-ttu-id="4dda7-145">**LogMessages**</span><span class="sxs-lookup"><span data-stu-id="4dda7-145">**LogMessages**</span></span>|<span data-ttu-id="4dda7-146">从下拉列表中，选择 **，则返回 TRUE**。</span><span class="sxs-lookup"><span data-stu-id="4dda7-146">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="4dda7-147">这样，要捕获和跟踪在 BAM 门户中的消息事件。</span><span class="sxs-lookup"><span data-stu-id="4dda7-147">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="4dda7-148">**启用**</span><span class="sxs-lookup"><span data-stu-id="4dda7-148">**Enable**</span></span>|<span data-ttu-id="4dda7-149">True</span><span class="sxs-lookup"><span data-stu-id="4dda7-149">True</span></span>|  
    |<span data-ttu-id="4dda7-150">**密码**</span><span class="sxs-lookup"><span data-stu-id="4dda7-150">**Password**</span></span>|<span data-ttu-id="4dda7-151">键入用于连接到压降的密码。</span><span class="sxs-lookup"><span data-stu-id="4dda7-151">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="4dda7-152">有关详细信息，请参阅压降帮助。</span><span class="sxs-lookup"><span data-stu-id="4dda7-152">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="4dda7-153">**用户名**</span><span class="sxs-lookup"><span data-stu-id="4dda7-153">**Username**</span></span>|<span data-ttu-id="4dda7-154">键入用于连接到压降的用户名。</span><span class="sxs-lookup"><span data-stu-id="4dda7-154">Type the user name you use to connect to SAG.</span></span>|  
  
11. <span data-ttu-id="4dda7-155">单击**确定**以关闭交互传输属性对话框。</span><span class="sxs-lookup"><span data-stu-id="4dda7-155">Click **OK** to close the INTERACT Transport Properties dialog box.</span></span>  
  
12. <span data-ttu-id="4dda7-156">选择**将此项的默认处理程序**选项。</span><span class="sxs-lookup"><span data-stu-id="4dda7-156">Select **make this the default handler** option.</span></span>  
  
13. <span data-ttu-id="4dda7-157">单击**确定**以关闭交互-适配器处理程序属性对话框。</span><span class="sxs-lookup"><span data-stu-id="4dda7-157">Click **OK** to close the INTERACT– Adapter Handler Properties dialog box.</span></span>  
  
14. <span data-ttu-id="4dda7-158">在消息框中，单击**确定**，然后重新启动**BizTalkServerApplication**主机实例。</span><span class="sxs-lookup"><span data-stu-id="4dda7-158">In the Message box, click **OK**, and then restart the **BizTalkServerApplication** host instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dda7-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="4dda7-159">See Also</span></span>  
 <span data-ttu-id="4dda7-160">[步骤 2:创建发送端口和接收端口为 InterAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-2-create-send-ports-and-receive-ports-for-the-interact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="4dda7-160">[Step2: Create Send Ports and Receive Ports for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2-create-send-ports-and-receive-ports-for-the-interact-store-and-forward.md) </span></span>  
 <span data-ttu-id="4dda7-161">[步骤 3:与动态发送端口为 InterAct 存储和转发 （拉取） 方案创建一个业务流程](../../adapters-and-accelerators/fileact-interact/step-3-create-orchestration-with-dynamic-send-for-interact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="4dda7-161">[Step3: Create an orchestration with  dynamic send port for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-orchestration-with-dynamic-send-for-interact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="4dda7-162">步骤 4：测试 InterAct 存储和转发 （拉取） 端到端方案</span><span class="sxs-lookup"><span data-stu-id="4dda7-162">Step 4: Test the InterAct Store and Forward (Pull) End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-pull-end-to-end-scenario.md)