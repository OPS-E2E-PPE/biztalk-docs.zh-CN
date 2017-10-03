---
title: "步骤 1： 配置 FileAct 应用商店应用和转发的请求方案 SWIFT 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc271544-6bc8-4d62-aba0-3fe3295f2a2a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9103caf451bb74a6ba23a7a6cf30ebe17896dfa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-configure-the-swift-adapter-for-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="c1ca8-102">步骤 1： 配置 SWIFT 适配器 FileAct 应用商店应用和转发的请求方案</span><span class="sxs-lookup"><span data-stu-id="c1ca8-102">Step 1: Configure the SWIFT Adapter for FileAct Store and Forward pull scenario</span></span>
<span data-ttu-id="c1ca8-103">完成[准备使用本教程](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)在开始此步骤之前。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-103">Complete [Preparing to Use the Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md) before you begin this step.</span></span>
  
## <a name="configure-the-swift-adapter"></a><span data-ttu-id="c1ca8-104">配置 SWIFT 适配器</span><span class="sxs-lookup"><span data-stu-id="c1ca8-104">Configure the SWIFT adapter</span></span>  
  
1.  <span data-ttu-id="c1ca8-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="c1ca8-106">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**平台设置**，展开**适配器**，右键单击**FILEACT**，指向**新建**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-106">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Platform Settings**, expand **Adapter**, right-click **FILEACT**, point to **New**, and then click **Send Handler**.</span></span>  
  
3.  <span data-ttu-id="c1ca8-107">在**FILEACT – 适配器 HandlerProperties**对话框中，在**常规**选项卡上，从**主机名**下拉列表中，选择**FileActHost**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-107">In the **FILEACT – Adapter HandlerProperties** dialog box, on the **General** tab, from the **Host name** drop-down list, select **FileActHost**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="c1ca8-108">在**FILEACT 传输属性**对话框中，在**属性**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c1ca8-108">In the **FILEACT Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="c1ca8-109">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-109">**Use this**</span></span>|<span data-ttu-id="c1ca8-110">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-110">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="c1ca8-111">**参数**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-111">**Arguments**</span></span>|<span data-ttu-id="c1ca8-112">键入以下参数:-SagMessagePartner \<Fileact 客户端消息合作伙伴创建在压降 >**注意：**自变量中的客户端是在压降中配置 MessagePartner。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-112">Type the following argument: -SagMessagePartner \<Fileact Client Message Partner created in SAG> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="c1ca8-113">**加密模式**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-113">**Crypto Mode**</span></span>|<span data-ttu-id="c1ca8-114">从下拉列表中选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-114">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="c1ca8-115">**FACryptoMode**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-115">**FACryptoMode**</span></span>|<span data-ttu-id="c1ca8-116">从下拉列表中选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-116">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="c1ca8-117">**日志消息**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-117">**LogMessages**</span></span>|<span data-ttu-id="c1ca8-118">从下拉列表中选择**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-118">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="c1ca8-119">这样将捕获和 BAM 门户中跟踪消息事件。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-119">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="c1ca8-120">**启用**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-120">**Enable**</span></span>|<span data-ttu-id="c1ca8-121">False</span><span class="sxs-lookup"><span data-stu-id="c1ca8-121">False</span></span>|  
    |<span data-ttu-id="c1ca8-122">**事件终结点**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-122">**Event end-point**</span></span>|<span data-ttu-id="c1ca8-123">键入相应压降终结点。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-123">Type the appropriate SAG end-point.</span></span>|  
    |<span data-ttu-id="c1ca8-124">**PhysicalFolderName**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-124">**PhysicalFolderName**</span></span>|<span data-ttu-id="c1ca8-125">键入服务器上的文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-125">Type the name of the folder on the server.</span></span> <span data-ttu-id="c1ca8-126">例如，C:\Fileact\ServerLocation。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-126">For example, C:\Fileact\ServerLocation.</span></span>|  
    |<span data-ttu-id="c1ca8-127">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-127">**PollingInterval**</span></span>|<span data-ttu-id="c1ca8-128">键入 PollingInterval 适当的值。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-128">Type the appropriate value for PollingInterval.</span></span> <span data-ttu-id="c1ca8-129">例如，5。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-129">For example, 5.</span></span> <span data-ttu-id="c1ca8-130">这指示的间隔 （以秒为单位） 后检查适配器的状态的文件传输。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-130">This indicates the interval (in seconds) after which the adapter checks for the status of file transfer.</span></span>|  
    |<span data-ttu-id="c1ca8-131">**密码**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-131">**Password**</span></span>|<span data-ttu-id="c1ca8-132">键入用于连接到压降的密码。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-132">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="c1ca8-133">有关详细信息，请参阅压降帮助。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-133">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="c1ca8-134">**用户名**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-134">**User Name**</span></span>|<span data-ttu-id="c1ca8-135">键入用于连接到压降的用户名称。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-135">Type the user name you use to connect to SAG.</span></span>|  
  
5.  <span data-ttu-id="c1ca8-136">单击**确定**以关闭 FILEACT 传输属性对话框。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-136">Click **OK** to close the FILEACT Transport Properties dialog box.</span></span>  
  
6.  <span data-ttu-id="c1ca8-137">单击**确定**关闭 FILEACT – 适配器处理程序属性对话框。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-137">Click **OK** to close the FILEACT – Adapter Handler Properties dialog box.</span></span>  
  
7.  <span data-ttu-id="c1ca8-138">在消息框中，单击**确定**，然后重新启动 FileAct 主机实例。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-138">In the Message box, click **OK**, and then restart the FileAct host instance.</span></span>  
  
8.  <span data-ttu-id="c1ca8-139">重复步骤 1。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-139">Repeat step 1.</span></span>  
  
9. <span data-ttu-id="c1ca8-140">在控制台树中，展开**BizTalk Server 管理**，展开**BizTalk**组中，展开**平台设置**，展开**适配器**，选择**FILEACT**，打开**BizTalkServerApplication** ，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-140">In the console tree, expand **BizTalk Server Administration**, expand the **BizTalk** group, expand **Platform Settings**, expand **Adapter**, select **FILEACT**, open **BizTalkServerApplication** and then, click **Properties**.</span></span>  
  
10. <span data-ttu-id="c1ca8-141">在**FILEACT 传输属性**对话框中，在**属性**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c1ca8-141">In the **FILEACT Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="c1ca8-142">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-142">**Use this**</span></span>|<span data-ttu-id="c1ca8-143">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-143">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="c1ca8-144">**参数**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-144">**Arguments**</span></span>|<span data-ttu-id="c1ca8-145">键入以下参数:-SagMessagePartner \<Fileact 客户端消息合作伙伴创建在压降 >**注意：**自变量中的客户端是在压降中配置 MessagePartner。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-145">Type the following argument: –SagMessagePartner \<Fileact Client Message Partner created in SAG> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="c1ca8-146">**加密模式**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-146">**Crypto Mode**</span></span>|<span data-ttu-id="c1ca8-147">从下拉列表中选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-147">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="c1ca8-148">**LogMessageBody**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-148">**LogMessageBody**</span></span>|<span data-ttu-id="c1ca8-149">从下拉列表中选择**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-149">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="c1ca8-150">这样将捕获和 BAM 门户中跟踪消息事件。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-150">This enables the message events to be captured and tracked in the BAM portal.</span></span> <span data-ttu-id="c1ca8-151">**注意：**如果设置为 TRUE 时，它会保留 BizTalk 跟踪数据库的消息正文。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-151">**Note:**  If you set to TRUE, it preserves the message body in the BizTalk Tracking database.</span></span> <span data-ttu-id="c1ca8-152">但是，出于安全原因，消息正文可以永远不会查看 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-152">However, for security reasons, the message body can never be viewed in the BAM portal.</span></span>|  
    |<span data-ttu-id="c1ca8-153">**日志消息**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-153">**LogMessages**</span></span>|<span data-ttu-id="c1ca8-154">从下拉列表中选择**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-154">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="c1ca8-155">这样将捕获和 BAM 门户中跟踪消息事件。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-155">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="c1ca8-156">**启用**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-156">**Enable**</span></span>|<span data-ttu-id="c1ca8-157">**True**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-157">**True**</span></span>|  
    |<span data-ttu-id="c1ca8-158">**事件终结点**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-158">**Event end-point**</span></span>|<span data-ttu-id="c1ca8-159">键入相应压降终结点。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-159">Type the appropriate SAG end-point.</span></span>|  
    |<span data-ttu-id="c1ca8-160">**PhysicalFolderName**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-160">**PhysicalFolderName**</span></span>|<span data-ttu-id="c1ca8-161">键入服务器上的文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-161">Type the name of the folder on the server.</span></span> <span data-ttu-id="c1ca8-162">例如，C:\Fileact\ServerLocation。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-162">For example, C:\Fileact\ServerLocation.</span></span>|  
    |<span data-ttu-id="c1ca8-163">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-163">**PollingInterval**</span></span>|<span data-ttu-id="c1ca8-164">键入 PollingInterval 适当的值。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-164">Type the appropriate value for PollingInterval.</span></span> <span data-ttu-id="c1ca8-165">例如，5。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-165">For example, 5.</span></span> <span data-ttu-id="c1ca8-166">这指示的间隔 （以秒为单位） 后检查适配器的状态的文件传输。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-166">This indicates the interval (in seconds) after which the adapter checks for the status of file transfer.</span></span>|  
    |<span data-ttu-id="c1ca8-167">**密码**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-167">**Password**</span></span>|<span data-ttu-id="c1ca8-168">键入用于连接到压降的密码。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-168">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="c1ca8-169">有关详细信息，请参阅压降帮助。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-169">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="c1ca8-170">**用户名**</span><span class="sxs-lookup"><span data-stu-id="c1ca8-170">**Username**</span></span>|<span data-ttu-id="c1ca8-171">键入用于连接到压降的用户名称。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-171">Type the user name you use to connect to SAG.</span></span>|  
  
11. <span data-ttu-id="c1ca8-172">单击确定以关闭 FILEACT 传输属性对话框。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-172">Click OK to close the FILEACT Transport Properties dialog box.</span></span>  
  
12. <span data-ttu-id="c1ca8-173">选择将此默认处理程序选项。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-173">Select make this the default handler option.</span></span>  
  
13. <span data-ttu-id="c1ca8-174">单击确定以关闭 FILEACT – 适配器处理程序属性对话框。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-174">Click OK to close the FILEACT – Adapter Handler Properties dialog box.</span></span>  
  
14. <span data-ttu-id="c1ca8-175">在消息框中，单击确定，，然后重新启动 BizTalkServerApplication 主机实例。</span><span class="sxs-lookup"><span data-stu-id="c1ca8-175">In the Message box, click OK, and then restart the BizTalkServerApplication host instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ca8-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1ca8-176">See Also</span></span>  
 <span data-ttu-id="c1ca8-177">[步骤 2： 创建发送端口和接收 FileAct 应用商店应用和进 （请求） 方案的端口](../../adapters-and-accelerators/fileact-interact/step-2-create-send-and-receive-ports-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="c1ca8-177">[Step 2: Create Send Ports and Receive Ports for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2-create-send-and-receive-ports-for-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="c1ca8-178">[步骤 3： 创建和绑定与文件 Act 存储和转发 （请求） 方案的动态发送端口业务流程](../../adapters-and-accelerators/fileact-interact/step-3-create-and-bind-an-orchestration-with-dynamic-send-port-for-file-act.md) </span><span class="sxs-lookup"><span data-stu-id="c1ca8-178">[Step 3: Create and bind an orchestration with dynamic send port  for the File Act Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-and-bind-an-orchestration-with-dynamic-send-port-for-file-act.md) </span></span>  
 [<span data-ttu-id="c1ca8-179">步骤 4： 测试 FileAct 存储区和进 （请求） 端到端方案</span><span class="sxs-lookup"><span data-stu-id="c1ca8-179">Step 4: Test FileAct Store and Forward (Pull) End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-pull-end-to-end-scenario.md)