---
title: "步骤 1： 配置交互存储和转发 （请求） 方案的 SWIFT 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4182021c-36c9-4c96-b2fa-e23c87862cfe
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 831a311a23e6d24f1a655d0df604032a02cb782d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="d6752-102">步骤 1： 配置 SWIFT 适配器交互应用商店应用和进 （请求） 方案</span><span class="sxs-lookup"><span data-stu-id="d6752-102">Step 1: Configure the SWIFT Adapter for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="d6752-103">在开始此步骤之前，必须完成[准备使用本教程](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)。</span><span class="sxs-lookup"><span data-stu-id="d6752-103">Before you begin this step, you must complete [Preparing to Use the Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md).</span></span>  
  
### <a name="to-configure-the-swift-adapter"></a><span data-ttu-id="d6752-104">若要配置 SWIFT 适配器</span><span class="sxs-lookup"><span data-stu-id="d6752-104">To configure the SWIFT adapter</span></span>  
  
1.  <span data-ttu-id="d6752-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="d6752-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="d6752-106">在控制台树中，依次展开 BizTalk Server 管理、 BizTalk 组及展开**平台设置**，展开**适配器**，右键单击**交互**，指向**新建**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="d6752-106">In the console tree, expand BizTalk Server Administration, expand the BizTalk group, expand **Platform Settings**, expand **Adapter**, right-click **INTERACT**, point to **New**, and then click **Send Handler**.</span></span>  
  
3.  <span data-ttu-id="d6752-107">在**交互 – 适配器处理程序属性**对话框中，在**常规**选项卡上，从**主机名**下拉列表中，选择**interacthost**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d6752-107">In the **INTERACT – Adapter Handler Properties** dialog box, on the **General** tab, from the **Host name** drop-down list, select **interacthost**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="d6752-108">在**交互传输属性**对话框中，在**属性**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d6752-108">In the **INTERACT Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="d6752-109">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="d6752-109">**Use this**</span></span>|<span data-ttu-id="d6752-110">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="d6752-110">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="d6752-111">**参数**</span><span class="sxs-lookup"><span data-stu-id="d6752-111">**Arguments**</span></span>|<span data-ttu-id="d6752-112">键入以下参数:-SagMessagePartner\<交互的客户端消息合作伙伴在压降中创建 >**注意：**自变量中的客户端是在压降中配置 MessagePartner。</span><span class="sxs-lookup"><span data-stu-id="d6752-112">Type the following argument: –SagMessagePartner \<Interact Client Message Partner created in SAG> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="d6752-113">**加密模式**</span><span class="sxs-lookup"><span data-stu-id="d6752-113">**Crypto Mode**</span></span>|<span data-ttu-id="d6752-114">从下拉列表中选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="d6752-114">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="d6752-115">**LogMessageBody**</span><span class="sxs-lookup"><span data-stu-id="d6752-115">**LogMessageBody**</span></span>|<span data-ttu-id="d6752-116">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="d6752-116">From the drop-down list, select **FALSE**.</span></span> <span data-ttu-id="d6752-117">**注意：**如果设置为 TRUE 时，它会保留 BizTalk 跟踪数据库的消息正文。</span><span class="sxs-lookup"><span data-stu-id="d6752-117">**Note:**  If you set to TRUE, it preserves the message body in the BizTalk Tracking database.</span></span> <span data-ttu-id="d6752-118">但是，出于安全原因，消息正文可以永远不会查看 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="d6752-118">However, for security reasons, the message body can never be viewed in the BAM portal.</span></span>|  
    |<span data-ttu-id="d6752-119">**日志消息**</span><span class="sxs-lookup"><span data-stu-id="d6752-119">**LogMessages**</span></span>|<span data-ttu-id="d6752-120">从下拉列表中选择**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="d6752-120">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="d6752-121">这样将捕获和 BAM 门户中跟踪消息事件。</span><span class="sxs-lookup"><span data-stu-id="d6752-121">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="d6752-122">**启用**</span><span class="sxs-lookup"><span data-stu-id="d6752-122">**Enable**</span></span>|<span data-ttu-id="d6752-123">False。</span><span class="sxs-lookup"><span data-stu-id="d6752-123">False.</span></span>|  
    |<span data-ttu-id="d6752-124">**密码**</span><span class="sxs-lookup"><span data-stu-id="d6752-124">**Password**</span></span>|<span data-ttu-id="d6752-125">键入用于连接到压降的密码。</span><span class="sxs-lookup"><span data-stu-id="d6752-125">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="d6752-126">有关详细信息，请参阅压降帮助。</span><span class="sxs-lookup"><span data-stu-id="d6752-126">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="d6752-127">**用户名**</span><span class="sxs-lookup"><span data-stu-id="d6752-127">**Username**</span></span>|<span data-ttu-id="d6752-128">键入用于连接到压降的用户名称。</span><span class="sxs-lookup"><span data-stu-id="d6752-128">Type the user name you use to connect to SAG.</span></span>|  
  
5.  <span data-ttu-id="d6752-129">单击**确定**关闭交互传输属性对话框。</span><span class="sxs-lookup"><span data-stu-id="d6752-129">Click **OK** to close the INTERACT Transport Properties dialog box.</span></span>  
  
6.  <span data-ttu-id="d6752-130">单击**确定**关闭交互 – 适配器处理程序属性对话框。</span><span class="sxs-lookup"><span data-stu-id="d6752-130">Click **OK** to close the INTERACT – Adapter Handler Properties dialog box.</span></span>  
  
7.  <span data-ttu-id="d6752-131">在消息框中，单击**确定**，然后重新启动交互主机实例。</span><span class="sxs-lookup"><span data-stu-id="d6752-131">In the message box, click **OK**, and then restart the InterAct host instance.</span></span>  
  
8.  <span data-ttu-id="d6752-132">重复步骤 1。</span><span class="sxs-lookup"><span data-stu-id="d6752-132">Repeat step 1.</span></span>  
  
9. <span data-ttu-id="d6752-133">在控制台树中，展开 BizTalk Server 管理中，展开**BizTalk**组中，展开**平台设置**，展开**适配器**，选中交互，打开**BizTalkServerApplication** ，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d6752-133">In the console tree, expand BizTalk Server Administration, expand the **BizTalk** group, expand **Platform Settings**, expand **Adapter**, select INTERACT, open **BizTalkServerApplication** and then, click **Properties**.</span></span>  
  
10. <span data-ttu-id="d6752-134">在**交互传输属性**对话框中，在**属性**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d6752-134">In the **INTERACT Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="d6752-135">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="d6752-135">**Use this**</span></span>|<span data-ttu-id="d6752-136">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="d6752-136">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="d6752-137">**参数**</span><span class="sxs-lookup"><span data-stu-id="d6752-137">**Arguments**</span></span>|<span data-ttu-id="d6752-138">键入以下参数:-SagMessagePartner\<交互的客户端消息合作伙伴在压降中创建 >**注意：**自变量中的客户端是在压降中配置 MessagePartner。</span><span class="sxs-lookup"><span data-stu-id="d6752-138">Type the following argument: –SagMessagePartner \<Interact Client Message Partner created in SAG> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="d6752-139">**加密模式**</span><span class="sxs-lookup"><span data-stu-id="d6752-139">**Crypto Mode**</span></span>|<span data-ttu-id="d6752-140">从下拉列表中选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="d6752-140">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="d6752-141">**LogMessageBody**</span><span class="sxs-lookup"><span data-stu-id="d6752-141">**LogMessageBody**</span></span>|<span data-ttu-id="d6752-142">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="d6752-142">From the drop-down list, select **FALSE**.</span></span> <span data-ttu-id="d6752-143">**注意：**如果设置为 TRUE 时，它会保留 BizTalk 跟踪数据库的消息正文。</span><span class="sxs-lookup"><span data-stu-id="d6752-143">**Note:**  If you set to TRUE, it preserves the message body in the BizTalk Tracking database.</span></span> <span data-ttu-id="d6752-144">但是，出于安全原因，消息正文可以永远不会查看 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="d6752-144">However, for security reasons, the message body can never be viewed in the BAM portal.</span></span>|  
    |<span data-ttu-id="d6752-145">**日志消息**</span><span class="sxs-lookup"><span data-stu-id="d6752-145">**LogMessages**</span></span>|<span data-ttu-id="d6752-146">从下拉列表中选择**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="d6752-146">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="d6752-147">这样将捕获和 BAM 门户中跟踪消息事件。</span><span class="sxs-lookup"><span data-stu-id="d6752-147">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="d6752-148">**启用**</span><span class="sxs-lookup"><span data-stu-id="d6752-148">**Enable**</span></span>|<span data-ttu-id="d6752-149">True</span><span class="sxs-lookup"><span data-stu-id="d6752-149">True</span></span>|  
    |<span data-ttu-id="d6752-150">**密码**</span><span class="sxs-lookup"><span data-stu-id="d6752-150">**Password**</span></span>|<span data-ttu-id="d6752-151">键入用于连接到压降的密码。</span><span class="sxs-lookup"><span data-stu-id="d6752-151">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="d6752-152">有关详细信息，请参阅压降帮助。</span><span class="sxs-lookup"><span data-stu-id="d6752-152">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="d6752-153">**用户名**</span><span class="sxs-lookup"><span data-stu-id="d6752-153">**Username**</span></span>|<span data-ttu-id="d6752-154">键入用于连接到压降的用户名称。</span><span class="sxs-lookup"><span data-stu-id="d6752-154">Type the user name you use to connect to SAG.</span></span>|  
  
11. <span data-ttu-id="d6752-155">单击**确定**关闭交互传输属性对话框。</span><span class="sxs-lookup"><span data-stu-id="d6752-155">Click **OK** to close the INTERACT Transport Properties dialog box.</span></span>  
  
12. <span data-ttu-id="d6752-156">选择**将此项的默认处理**选项。</span><span class="sxs-lookup"><span data-stu-id="d6752-156">Select **make this the default handler** option.</span></span>  
  
13. <span data-ttu-id="d6752-157">单击**确定**以关闭交互 – 适配器处理程序属性对话框。</span><span class="sxs-lookup"><span data-stu-id="d6752-157">Click **OK** to close the INTERACT– Adapter Handler Properties dialog box.</span></span>  
  
14. <span data-ttu-id="d6752-158">在消息框中，单击**确定**，然后重新启动**BizTalkServerApplication**主机实例。</span><span class="sxs-lookup"><span data-stu-id="d6752-158">In the Message box, click **OK**, and then restart the **BizTalkServerApplication** host instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6752-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6752-159">See Also</span></span>  
 <span data-ttu-id="d6752-160">[步骤 2： 创建发送端口和接收交互应用商店应用和进 （请求） 方案的端口](../../adapters-and-accelerators/fileact-interact/step-2-create-send-ports-and-receive-ports-for-the-interact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="d6752-160">[Step2: Create Send Ports and Receive Ports for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2-create-send-ports-and-receive-ports-for-the-interact-store-and-forward.md) </span></span>  
 <span data-ttu-id="d6752-161">[步骤 3： 创建与交互应用商店应用和向前 （请求） 方案的动态发送端口业务流程](../../adapters-and-accelerators/fileact-interact/step-3-create-orchestration-with-dynamic-send-for-interact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="d6752-161">[Step3: Create an orchestration with  dynamic send port for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-orchestration-with-dynamic-send-for-interact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="d6752-162">步骤 4： 测试的交互，存储和转发 （请求） 端到端方案</span><span class="sxs-lookup"><span data-stu-id="d6752-162">Step 4: Test the InterAct Store and Forward (Pull) End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-pull-end-to-end-scenario.md)