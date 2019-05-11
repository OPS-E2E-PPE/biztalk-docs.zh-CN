---
title: 第 1 步：配置 SWIFT 适配器为 FileAct 存储和转发的请求方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc271544-6bc8-4d62-aba0-3fe3295f2a2a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b3f5d4c6698f06a49b0a5ba2bf6a862a9592a3c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366541"
---
# <a name="step-1-configure-the-swift-adapter-for-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="b5b61-102">第 1 步：配置 SWIFT 适配器为 FileAct 存储和转发的请求方案</span><span class="sxs-lookup"><span data-stu-id="b5b61-102">Step 1: Configure the SWIFT Adapter for FileAct Store and Forward pull scenario</span></span>
<span data-ttu-id="b5b61-103">完整[准备使用本教程](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)开始此步骤之前。</span><span class="sxs-lookup"><span data-stu-id="b5b61-103">Complete [Preparing to Use the Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md) before you begin this step.</span></span>
  
## <a name="configure-the-swift-adapter"></a><span data-ttu-id="b5b61-104">配置 SWIFT 适配器</span><span class="sxs-lookup"><span data-stu-id="b5b61-104">Configure the SWIFT adapter</span></span>  
  
1.  <span data-ttu-id="b5b61-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="b5b61-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="b5b61-106">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**平台设置**，展开**适配器**，右键单击**FILEACT**，依次指向**新建**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="b5b61-106">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Platform Settings**, expand **Adapter**, right-click **FILEACT**, point to **New**, and then click **Send Handler**.</span></span>  
  
3.  <span data-ttu-id="b5b61-107">在中**FILEACT – 适配器 HandlerProperties**对话框中，在**常规**选项卡上，从**主机名**下拉列表中，选择**FileActHost**，然后依次**属性**。</span><span class="sxs-lookup"><span data-stu-id="b5b61-107">In the **FILEACT – Adapter HandlerProperties** dialog box, on the **General** tab, from the **Host name** drop-down list, select **FileActHost**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="b5b61-108">在中**FILEACT 传输属性**对话框中，在**属性**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b5b61-108">In the **FILEACT Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="b5b61-109">**使用此**</span><span class="sxs-lookup"><span data-stu-id="b5b61-109">**Use this**</span></span>|<span data-ttu-id="b5b61-110">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="b5b61-110">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="b5b61-111">**参数**</span><span class="sxs-lookup"><span data-stu-id="b5b61-111">**Arguments**</span></span>|<span data-ttu-id="b5b61-112">键入以下参数:-SagMessagePartner \<Fileact 客户端消息合作伙伴创建在压降\>**注意：** 参数中的客户端是 MessagePartner 压降中配置。</span><span class="sxs-lookup"><span data-stu-id="b5b61-112">Type the following argument: -SagMessagePartner \<Fileact Client Message Partner created in SAG\> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="b5b61-113">**加密模式**</span><span class="sxs-lookup"><span data-stu-id="b5b61-113">**Crypto Mode**</span></span>|<span data-ttu-id="b5b61-114">从下拉列表中，选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="b5b61-114">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="b5b61-115">**FACryptoMode**</span><span class="sxs-lookup"><span data-stu-id="b5b61-115">**FACryptoMode**</span></span>|<span data-ttu-id="b5b61-116">从下拉列表中，选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="b5b61-116">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="b5b61-117">**LogMessages**</span><span class="sxs-lookup"><span data-stu-id="b5b61-117">**LogMessages**</span></span>|<span data-ttu-id="b5b61-118">从下拉列表中，选择 **，则返回 TRUE**。</span><span class="sxs-lookup"><span data-stu-id="b5b61-118">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="b5b61-119">这样，要捕获和跟踪在 BAM 门户中的消息事件。</span><span class="sxs-lookup"><span data-stu-id="b5b61-119">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="b5b61-120">**启用**</span><span class="sxs-lookup"><span data-stu-id="b5b61-120">**Enable**</span></span>|<span data-ttu-id="b5b61-121">False</span><span class="sxs-lookup"><span data-stu-id="b5b61-121">False</span></span>|  
    |<span data-ttu-id="b5b61-122">**事件终结点**</span><span class="sxs-lookup"><span data-stu-id="b5b61-122">**Event end-point**</span></span>|<span data-ttu-id="b5b61-123">键入相应压降终结点。</span><span class="sxs-lookup"><span data-stu-id="b5b61-123">Type the appropriate SAG end-point.</span></span>|  
    |<span data-ttu-id="b5b61-124">**PhysicalFolderName**</span><span class="sxs-lookup"><span data-stu-id="b5b61-124">**PhysicalFolderName**</span></span>|<span data-ttu-id="b5b61-125">在服务器上键入文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="b5b61-125">Type the name of the folder on the server.</span></span> <span data-ttu-id="b5b61-126">例如，C:\Fileact\ServerLocation。</span><span class="sxs-lookup"><span data-stu-id="b5b61-126">For example, C:\Fileact\ServerLocation.</span></span>|  
    |<span data-ttu-id="b5b61-127">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="b5b61-127">**PollingInterval**</span></span>|<span data-ttu-id="b5b61-128">PollingInterval，请键入相应的值。</span><span class="sxs-lookup"><span data-stu-id="b5b61-128">Type the appropriate value for PollingInterval.</span></span> <span data-ttu-id="b5b61-129">例如，5。</span><span class="sxs-lookup"><span data-stu-id="b5b61-129">For example, 5.</span></span> <span data-ttu-id="b5b61-130">这指示的间隔 （以秒为单位） 后其检查适配器文件传输状态。</span><span class="sxs-lookup"><span data-stu-id="b5b61-130">This indicates the interval (in seconds) after which the adapter checks for the status of file transfer.</span></span>|  
    |<span data-ttu-id="b5b61-131">**密码**</span><span class="sxs-lookup"><span data-stu-id="b5b61-131">**Password**</span></span>|<span data-ttu-id="b5b61-132">键入用于连接到压降的密码。</span><span class="sxs-lookup"><span data-stu-id="b5b61-132">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="b5b61-133">有关详细信息，请参阅压降帮助。</span><span class="sxs-lookup"><span data-stu-id="b5b61-133">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="b5b61-134">**用户名**</span><span class="sxs-lookup"><span data-stu-id="b5b61-134">**User Name**</span></span>|<span data-ttu-id="b5b61-135">键入用于连接到压降的用户名。</span><span class="sxs-lookup"><span data-stu-id="b5b61-135">Type the user name you use to connect to SAG.</span></span>|  
  
5.  <span data-ttu-id="b5b61-136">单击**确定**以关闭 FILEACT 传输属性对话框。</span><span class="sxs-lookup"><span data-stu-id="b5b61-136">Click **OK** to close the FILEACT Transport Properties dialog box.</span></span>  
  
6.  <span data-ttu-id="b5b61-137">单击**确定**关闭 FILEACT – 适配器处理程序属性对话框。</span><span class="sxs-lookup"><span data-stu-id="b5b61-137">Click **OK** to close the FILEACT – Adapter Handler Properties dialog box.</span></span>  
  
7.  <span data-ttu-id="b5b61-138">在消息框中，单击**确定**，然后重新启动 FileAct 主机实例。</span><span class="sxs-lookup"><span data-stu-id="b5b61-138">In the Message box, click **OK**, and then restart the FileAct host instance.</span></span>  
  
8.  <span data-ttu-id="b5b61-139">重复步骤 1。</span><span class="sxs-lookup"><span data-stu-id="b5b61-139">Repeat step 1.</span></span>  
  
9. <span data-ttu-id="b5b61-140">在控制台树中，展开**BizTalk Server 管理**，展开**BizTalk**组中，展开**平台设置**，展开**适配器**，选择**FILEACT**，打开**BizTalkServerApplication** ，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="b5b61-140">In the console tree, expand **BizTalk Server Administration**, expand the **BizTalk** group, expand **Platform Settings**, expand **Adapter**, select **FILEACT**, open **BizTalkServerApplication** and then, click **Properties**.</span></span>  
  
10. <span data-ttu-id="b5b61-141">在中**FILEACT 传输属性**对话框中，在**属性**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b5b61-141">In the **FILEACT Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="b5b61-142">**使用此**</span><span class="sxs-lookup"><span data-stu-id="b5b61-142">**Use this**</span></span>|<span data-ttu-id="b5b61-143">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="b5b61-143">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="b5b61-144">**参数**</span><span class="sxs-lookup"><span data-stu-id="b5b61-144">**Arguments**</span></span>|<span data-ttu-id="b5b61-145">键入以下参数:-SagMessagePartner \<Fileact 客户端消息合作伙伴创建在压降\>**注意：** 参数中的客户端是 MessagePartner 压降中配置。</span><span class="sxs-lookup"><span data-stu-id="b5b61-145">Type the following argument: –SagMessagePartner \<Fileact Client Message Partner created in SAG\> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="b5b61-146">**加密模式**</span><span class="sxs-lookup"><span data-stu-id="b5b61-146">**Crypto Mode**</span></span>|<span data-ttu-id="b5b61-147">从下拉列表中，选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="b5b61-147">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="b5b61-148">**LogMessageBody**</span><span class="sxs-lookup"><span data-stu-id="b5b61-148">**LogMessageBody**</span></span>|<span data-ttu-id="b5b61-149">从下拉列表中，选择 **，则返回 TRUE**。</span><span class="sxs-lookup"><span data-stu-id="b5b61-149">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="b5b61-150">这样，要捕获和跟踪在 BAM 门户中的消息事件。</span><span class="sxs-lookup"><span data-stu-id="b5b61-150">This enables the message events to be captured and tracked in the BAM portal.</span></span> <span data-ttu-id="b5b61-151">**注意：** 如果设置为 TRUE 时，它将保留消息正文 BizTalk 跟踪数据库中。</span><span class="sxs-lookup"><span data-stu-id="b5b61-151">**Note:**  If you set to TRUE, it preserves the message body in the BizTalk Tracking database.</span></span> <span data-ttu-id="b5b61-152">但是，出于安全原因，消息正文可以永远不会查看 BAM 门户中。</span><span class="sxs-lookup"><span data-stu-id="b5b61-152">However, for security reasons, the message body can never be viewed in the BAM portal.</span></span>|  
    |<span data-ttu-id="b5b61-153">**LogMessages**</span><span class="sxs-lookup"><span data-stu-id="b5b61-153">**LogMessages**</span></span>|<span data-ttu-id="b5b61-154">从下拉列表中，选择 **，则返回 TRUE**。</span><span class="sxs-lookup"><span data-stu-id="b5b61-154">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="b5b61-155">这样，要捕获和跟踪在 BAM 门户中的消息事件。</span><span class="sxs-lookup"><span data-stu-id="b5b61-155">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="b5b61-156">**启用**</span><span class="sxs-lookup"><span data-stu-id="b5b61-156">**Enable**</span></span>|<span data-ttu-id="b5b61-157">**True**</span><span class="sxs-lookup"><span data-stu-id="b5b61-157">**True**</span></span>|  
    |<span data-ttu-id="b5b61-158">**事件终结点**</span><span class="sxs-lookup"><span data-stu-id="b5b61-158">**Event end-point**</span></span>|<span data-ttu-id="b5b61-159">键入相应压降终结点。</span><span class="sxs-lookup"><span data-stu-id="b5b61-159">Type the appropriate SAG end-point.</span></span>|  
    |<span data-ttu-id="b5b61-160">**PhysicalFolderName**</span><span class="sxs-lookup"><span data-stu-id="b5b61-160">**PhysicalFolderName**</span></span>|<span data-ttu-id="b5b61-161">在服务器上键入文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="b5b61-161">Type the name of the folder on the server.</span></span> <span data-ttu-id="b5b61-162">例如，C:\Fileact\ServerLocation。</span><span class="sxs-lookup"><span data-stu-id="b5b61-162">For example, C:\Fileact\ServerLocation.</span></span>|  
    |<span data-ttu-id="b5b61-163">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="b5b61-163">**PollingInterval**</span></span>|<span data-ttu-id="b5b61-164">PollingInterval，请键入相应的值。</span><span class="sxs-lookup"><span data-stu-id="b5b61-164">Type the appropriate value for PollingInterval.</span></span> <span data-ttu-id="b5b61-165">例如，5。</span><span class="sxs-lookup"><span data-stu-id="b5b61-165">For example, 5.</span></span> <span data-ttu-id="b5b61-166">这指示的间隔 （以秒为单位） 后其检查适配器文件传输状态。</span><span class="sxs-lookup"><span data-stu-id="b5b61-166">This indicates the interval (in seconds) after which the adapter checks for the status of file transfer.</span></span>|  
    |<span data-ttu-id="b5b61-167">**密码**</span><span class="sxs-lookup"><span data-stu-id="b5b61-167">**Password**</span></span>|<span data-ttu-id="b5b61-168">键入用于连接到压降的密码。</span><span class="sxs-lookup"><span data-stu-id="b5b61-168">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="b5b61-169">有关详细信息，请参阅压降帮助。</span><span class="sxs-lookup"><span data-stu-id="b5b61-169">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="b5b61-170">**用户名**</span><span class="sxs-lookup"><span data-stu-id="b5b61-170">**Username**</span></span>|<span data-ttu-id="b5b61-171">键入用于连接到压降的用户名。</span><span class="sxs-lookup"><span data-stu-id="b5b61-171">Type the user name you use to connect to SAG.</span></span>|  
  
11. <span data-ttu-id="b5b61-172">单击确定关闭 FILEACT 传输属性对话框。</span><span class="sxs-lookup"><span data-stu-id="b5b61-172">Click OK to close the FILEACT Transport Properties dialog box.</span></span>  
  
12. <span data-ttu-id="b5b61-173">选择将此默认处理程序选项。</span><span class="sxs-lookup"><span data-stu-id="b5b61-173">Select make this the default handler option.</span></span>  
  
13. <span data-ttu-id="b5b61-174">单击确定以关闭 FILEACT – 适配器处理程序属性对话框。</span><span class="sxs-lookup"><span data-stu-id="b5b61-174">Click OK to close the FILEACT – Adapter Handler Properties dialog box.</span></span>  
  
14. <span data-ttu-id="b5b61-175">在消息框中，单击确定，然后重新启动 BizTalkServerApplication 主机实例。</span><span class="sxs-lookup"><span data-stu-id="b5b61-175">In the Message box, click OK, and then restart the BizTalkServerApplication host instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5b61-176">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5b61-176">See Also</span></span>  
 <span data-ttu-id="b5b61-177">[步骤 2：创建发送端口和接收端口为 FileAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-2-create-send-and-receive-ports-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="b5b61-177">[Step 2: Create Send Ports and Receive Ports for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2-create-send-and-receive-ports-for-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="b5b61-178">[步骤 3：创建并将替换为 Fileact 存储和转发 （拉取） 方案的动态发送端口业务流程绑定](../../adapters-and-accelerators/fileact-interact/step-3-create-and-bind-an-orchestration-with-dynamic-send-port-for-file-act.md) </span><span class="sxs-lookup"><span data-stu-id="b5b61-178">[Step 3: Create and bind an orchestration with dynamic send port  for the File Act Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-and-bind-an-orchestration-with-dynamic-send-port-for-file-act.md) </span></span>  
 [<span data-ttu-id="b5b61-179">步骤 4：测试 FileAct 存储和转发 （拉取） 端到端方案</span><span class="sxs-lookup"><span data-stu-id="b5b61-179">Step 4: Test FileAct Store and Forward (Pull) End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-pull-end-to-end-scenario.md)