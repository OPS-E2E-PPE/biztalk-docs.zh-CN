---
title: MQSCorrelationSetOrchestrationWithSolicitResponse （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, MQSeries adapters
- orchestrations, examples
- examples, orchestrations
- examples, messages
- messages, examples
- MQSeries adapters, examples
ms.assetid: 5127d743-bb79-4e97-a2f3-446892e1bfa0
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3780aa186146d0cc1b7bca90f7934f4823882ab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014518"
---
# <a name="mqscorrelationsetorchestrationwithsolicitresponse-biztalk-server-sample"></a><span data-ttu-id="3d66a-102">MQSCorrelationSetOrchestrationWithSolicitResponse（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="3d66a-102">MQSCorrelationSetOrchestrationWithSolicitResponse (BizTalk Server Sample)</span></span>
<span data-ttu-id="3d66a-103">MQSCorrelationSetOrchestrationWithSolicitResponse 示例将演示如何使用 MQSeries Server 而非 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 生成的相关标识符。</span><span class="sxs-lookup"><span data-stu-id="3d66a-103">The MQSCorrelationSetOrchestrationWithSolicitResponse sample demonstrates how to use a correlation identifier produced by the MQSeries Server instead of by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="3d66a-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="3d66a-104">What This Sample Does</span></span>  
 <span data-ttu-id="3d66a-105">业务流程发送一条消息为空值与**MQMD_MsgID**消息标头中的属性。</span><span class="sxs-lookup"><span data-stu-id="3d66a-105">The orchestration sends a message with an empty value for the **MQMD_MsgID** property in the message header.</span></span> <span data-ttu-id="3d66a-106">MQSeries 生成 MessageID 和 CorrelationID，并返回一条消息分配给的值与**MQMD_MsgID**并**MQMD_CorrelId**要求-响应中的响应的一部分发送的适配器的端口.</span><span class="sxs-lookup"><span data-stu-id="3d66a-106">MQSeries generates the MessageID and CorrelationID and returns a message with a value assigned to **MQMD_MsgID** and **MQMD_CorrelId** as part of the response in the solicit-response send port of the adapter.</span></span> <span data-ttu-id="3d66a-107">沿用相关集在后面的通过检查接收位置和业务流程使用生成的相关标识符初始化相关集**MQMD_CorrelId**消息属性。</span><span class="sxs-lookup"><span data-stu-id="3d66a-107">The orchestration uses the generated correlation identifier to initialize the correlation set and follows the correlation set in a subsequent receive location by checking the **MQMD_CorrelId** property of the message.</span></span> <span data-ttu-id="3d66a-108">适配器还将分配到的相关标识符**BizTalk_CorrelationID**，您还可以使用它在业务流程中。</span><span class="sxs-lookup"><span data-stu-id="3d66a-108">The adapter also assigns the correlation identifier to **BizTalk_CorrelationID**, which you could also use in an orchestration.</span></span> <span data-ttu-id="3d66a-109">有关与适配器配合使用相关标识符的详细信息，请参阅[关联的消息使用请求-答复](../core/correlating-messages-using-request-reply.md)。</span><span class="sxs-lookup"><span data-stu-id="3d66a-109">For more information about using correlation identifiers with the adapter, see [Correlating Messages Using Request-Reply](../core/correlating-messages-using-request-reply.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3d66a-110">如果来自 MQSeries Server 的消息在相关标识符之前到达，则使用此方法的业务流程可能出现问题。</span><span class="sxs-lookup"><span data-stu-id="3d66a-110">Orchestrations using this technique may experience problems if the message from the MQSeries Server arrives before the correlation identifier.</span></span> <span data-ttu-id="3d66a-111">确保将您的业务流程设计为允许 MQSeries Server 具有足够的时间返回相关标识符。</span><span class="sxs-lookup"><span data-stu-id="3d66a-111">Make sure that you design your orchestrations to allow enough time for the MQSeries Server to return the correlation identifier.</span></span> <span data-ttu-id="3d66a-112">此示例未考虑可能出现争用情况。</span><span class="sxs-lookup"><span data-stu-id="3d66a-112">This example does not consider this possible race condition.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="3d66a-113">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="3d66a-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="3d66a-114">*\<示例路径\>* \AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestrationWithSolicitResponse</span><span class="sxs-lookup"><span data-stu-id="3d66a-114">*\<Samples Path\>* \AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestrationWithSolicitResponse</span></span>  
  
 <span data-ttu-id="3d66a-115">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="3d66a-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="3d66a-116">**File**</span><span class="sxs-lookup"><span data-stu-id="3d66a-116">**File**</span></span>|<span data-ttu-id="3d66a-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="3d66a-117">**Description**</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="3d66a-118">**MQSCorrelationSolicitResponse.btproj，**</span><span class="sxs-lookup"><span data-stu-id="3d66a-118">**MQSCorrelationSolicitResponse.btproj,**</span></span><br /><br /> <span data-ttu-id="3d66a-119">**MQSCorrelationSolicitResponse.sln**</span><span class="sxs-lookup"><span data-stu-id="3d66a-119">**MQSCorrelationSolicitResponse.sln**</span></span>|<span data-ttu-id="3d66a-120">应用程序的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="3d66a-120">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="3d66a-121">**MQSCorrelationSolicitResponse.odx**</span><span class="sxs-lookup"><span data-stu-id="3d66a-121">**MQSCorrelationSolicitResponse.odx**</span></span>|<span data-ttu-id="3d66a-122">应用程序的 BizTalk 业务流程文件。</span><span class="sxs-lookup"><span data-stu-id="3d66a-122">The BizTalk orchestration file for the application.</span></span>|  
|<span data-ttu-id="3d66a-123">**MQSCorrelationSolicitResponse.snk**</span><span class="sxs-lookup"><span data-stu-id="3d66a-123">**MQSCorrelationSolicitResponse.snk**</span></span>|<span data-ttu-id="3d66a-124">强命名密钥文件。</span><span class="sxs-lookup"><span data-stu-id="3d66a-124">The strong naming key file.</span></span>|  
|<span data-ttu-id="3d66a-125">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="3d66a-125">Setup.bat</span></span>|<span data-ttu-id="3d66a-126">生成并初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="3d66a-126">Builds and initializes this sample.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="3d66a-127">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="3d66a-127">How to Use This Sample</span></span>  
 <span data-ttu-id="3d66a-128">若要创建应用程序，必须完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="3d66a-128">To create the application, you must complete the following steps:</span></span>  
  
- <span data-ttu-id="3d66a-129">创建两个 MQSeries 队列。</span><span class="sxs-lookup"><span data-stu-id="3d66a-129">Create two MQSeries queues.</span></span>  
  
- <span data-ttu-id="3d66a-130">设置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的接收位置和发送端口。</span><span class="sxs-lookup"><span data-stu-id="3d66a-130">Set up a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location and send port.</span></span>  
  
- <span data-ttu-id="3d66a-131">启用接收位置。</span><span class="sxs-lookup"><span data-stu-id="3d66a-131">Enable the receive location.</span></span>  
  
- <span data-ttu-id="3d66a-132">启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="3d66a-132">Start the send port.</span></span>  
  
- <span data-ttu-id="3d66a-133">创建相应文件夹。</span><span class="sxs-lookup"><span data-stu-id="3d66a-133">Create the appropriate folders.</span></span>  
  
- <span data-ttu-id="3d66a-134">修改业务流程。</span><span class="sxs-lookup"><span data-stu-id="3d66a-134">Modify the orchestration.</span></span>  
  
- <span data-ttu-id="3d66a-135">部署、绑定并启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="3d66a-135">Deploy, bind and start the orchestration.</span></span>  
  
  <span data-ttu-id="3d66a-136">如果您具有安装 MQSeries Server for Windows 的必需权限，则可以通过适配器对话框创建 MQSeries 队列，并可以跳过下一过程。</span><span class="sxs-lookup"><span data-stu-id="3d66a-136">If you have the required permissions to the MQSeries Server for Windows installation, you can create the MQSeries queue through the adapter dialog boxes, and can skip the next procedure.</span></span> <span data-ttu-id="3d66a-137">如果您没有这样的访问权限，可以使用 IBM WebSphere MQ Explorer 来创建队列。</span><span class="sxs-lookup"><span data-stu-id="3d66a-137">If you do not have such access, you can create the queue using the IBM WebSphere MQ Explorer.</span></span> <span data-ttu-id="3d66a-138">若要通过 WebSphere MQ Explorer 创建队列，请完成下列步骤。</span><span class="sxs-lookup"><span data-stu-id="3d66a-138">To create the queues through the WebSphere MQ Explorer, complete the following steps.</span></span>  
  
## <a name="creating-the-mqseries-queues-through-the-websphere-mq-explorer"></a><span data-ttu-id="3d66a-139">创建通过 WebSphere MQ Explorer MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="3d66a-139">Creating the MQSeries Queues Through the WebSphere MQ Explorer</span></span>  
  
#### <a name="to-create-the-mqseries-queues-through-the-websphere-mq-explorer"></a><span data-ttu-id="3d66a-140">通过 WebSphere MQ Explorer 创建 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="3d66a-140">To create the MQSeries queues through the WebSphere MQ Explorer</span></span>  
  
1.  <span data-ttu-id="3d66a-141">单击**启动**，依次指向**所有程序**，指向**IBM WebSphere MQ**，然后单击**WebSphere MQ Explorer**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-141">Click **Start**, point to **All Programs**, point to **IBM WebSphere MQ**, and then click **WebSphere MQ Explorer**.</span></span>  
  
2.  <span data-ttu-id="3d66a-142">双击**队列管理器**，然后双击默认的队列管理器。</span><span class="sxs-lookup"><span data-stu-id="3d66a-142">Double-click **Queue Managers**, and then double-click the default queue manager.</span></span> <span data-ttu-id="3d66a-143">默认的队列管理器通常命名为 **QM_ * * * < m a c h >* 其中*machine_name*是您的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="3d66a-143">The default queue manager is typically named **QM_***<machine_name>* where *machine_name* is the name of your computer.</span></span>  
  
3.  <span data-ttu-id="3d66a-144">右键单击**队列**，依次指向**新建**，然后单击**本地队列**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-144">Right-click **Queues**, point to **New**, and then click **Local Queue**.</span></span>  
  
4.  <span data-ttu-id="3d66a-145">在中**创建本地队列**对话框中**队列名称**，键入"REPLYTOQ"，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-145">In **Create Local Queue** dialog box, in **Queue Name**, type "REPLYTOQ", and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="3d66a-146">右键单击**队列**，单击**新建**，然后单击**本地队列**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-146">Right-click **Queues**, click **New**, and then click **Local Queue**.</span></span>  
  
6.  <span data-ttu-id="3d66a-147">在中**创建本地队列**对话框中**队列名称**，键入"SOLICITRESPONSEQ"，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-147">In the **Create Local Queue** dialog box, in **Queue Name**, type "SOLICITRESPONSEQ", and then click **OK**.</span></span>  
  
## <a name="creating-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="3d66a-148">创建接收位置和 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="3d66a-148">Creating the Receive Location and the MQSeries Queue</span></span>  
 <span data-ttu-id="3d66a-149">此过程将创建发送端口和接收位置，以便向 MQSeries 发送消息以及接收来自 MQSeries 的相关消息。</span><span class="sxs-lookup"><span data-stu-id="3d66a-149">This procedure creates the send port and receive location to send the message to and receive the correlation message from MQSeries.</span></span> <span data-ttu-id="3d66a-150">创建接收位置时，还将创建 MQSeries 队列（如果尚未创建）。</span><span class="sxs-lookup"><span data-stu-id="3d66a-150">The MQSeries queue will also be created when you create the receive location if not already created.</span></span>  
  
#### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="3d66a-151">创建接收位置和 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="3d66a-151">To create the receive location and the MQSeries queue</span></span>  
  
1.  <span data-ttu-id="3d66a-152">打开 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="3d66a-152">Open the BizTalk Server Administration console.</span></span>  
  
2.  <span data-ttu-id="3d66a-153">展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3d66a-153">Expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the required application.</span></span>  
  
3.  <span data-ttu-id="3d66a-154">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-154">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="3d66a-155">在中**单向接收端口属性**对话框中**名称**框中，键入"MQReply"，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-155">In the **One-way Receive Port Properties** dialog box, in the **Name** box, type "MQReply", and click **OK**.</span></span>  
  
5.  <span data-ttu-id="3d66a-156">在左窗格中，单击**接收位置**选项卡，然后依次**新建**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-156">In the left pane, click **Receive Locations** tab, and then click **New**.</span></span>  
  
6.  <span data-ttu-id="3d66a-157">在中**接收位置属性**对话框中**名称**框中，键入"MQReply"。</span><span class="sxs-lookup"><span data-stu-id="3d66a-157">In the **Receive Location Properties** dialog box, in the **Name** box, type "MQReply”.</span></span>  
  
7.  <span data-ttu-id="3d66a-158">在中**传输类型**框中，选择**MQSeries**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-158">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
8.  <span data-ttu-id="3d66a-159">在中**接收处理程序**框中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-159">In the **Receive Handler** box, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="3d66a-160">在中**接收管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-160">In the **Receive pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  
  
10. <span data-ttu-id="3d66a-161">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-161">Click **Configure**.</span></span>  
  
11. <span data-ttu-id="3d66a-162">在中**MQSeries 传输属性**对话框中**轮询间隔**框中，键入"10"。</span><span class="sxs-lookup"><span data-stu-id="3d66a-162">In the **MQSeries Transport Properties** dialog box, in the **Polling Interval** box, type "10".</span></span>  
  
12. <span data-ttu-id="3d66a-163">在中**队列定义**框中，单击省略号 （...） 按钮。</span><span class="sxs-lookup"><span data-stu-id="3d66a-163">In the **Queue Definition** box, click the ellipsis (…) button.</span></span>  
  
13. <span data-ttu-id="3d66a-164">在中**队列定义**对话框中**服务器名称**框中，键入您的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="3d66a-164">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
14. <span data-ttu-id="3d66a-165">在中**队列管理器**框中，选择默认的队列管理器。</span><span class="sxs-lookup"><span data-stu-id="3d66a-165">In the **Queue Manager** box, select the default queue manager.</span></span>  
  
15. <span data-ttu-id="3d66a-166">在中**队列**框中，键入"REPLYTOQ"，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-166">In the **Queue** box, type " REPLYTOQ", and then click **Export**.</span></span>  
  
16. <span data-ttu-id="3d66a-167">在中**导出**对话框中，单击**Create Queue**，然后单击**确定**或**完成**直到您退出所有对话框为止。</span><span class="sxs-lookup"><span data-stu-id="3d66a-167">In the **Export** dialog box, click **Create Queue**, and then click**OK**or **Done** until you have exited all dialog boxes.</span></span>  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a><span data-ttu-id="3d66a-168">创建发送端口和 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="3d66a-168">Creating the Send Port and MQSeries Queue</span></span>  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a><span data-ttu-id="3d66a-169">若要创建的发送端口和 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="3d66a-169">To create the send port and MQSeries queue</span></span>  
  
1.  <span data-ttu-id="3d66a-170">右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-170">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="3d66a-171">在中**发送端口属性**对话框中**名称**框中，键入"MQSolicitResponse"。</span><span class="sxs-lookup"><span data-stu-id="3d66a-171">In the **Send Port Properties** dialog box, in the **Name** box, type "MQSolicitResponse".</span></span>  
  
3.  <span data-ttu-id="3d66a-172">在中**传输类型**框中，选择**MQSeries**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-172">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
4.  <span data-ttu-id="3d66a-173">在中**发送管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-173">In the **Send pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span></span>  
  
5.  <span data-ttu-id="3d66a-174">在中**接收管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-174">In the **Receive pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  
  
6.  <span data-ttu-id="3d66a-175">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-175">Click **Configure**.</span></span>  
  
7.  <span data-ttu-id="3d66a-176">在中**MQSeries 传输属性**对话框中**队列定义**框中，单击省略号 （...） 按钮。</span><span class="sxs-lookup"><span data-stu-id="3d66a-176">In the **MQSeries Transport Properties** dialog box, in the **Queue Definition** box, click the ellipsis (…) button.</span></span>  
  
8.  <span data-ttu-id="3d66a-177">在中**队列定义**对话框中**服务器名称**框中，键入您的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="3d66a-177">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
9. <span data-ttu-id="3d66a-178">在中**队列管理器**框中，选择默认的队列管理器。</span><span class="sxs-lookup"><span data-stu-id="3d66a-178">In the **Queue Manager** box, select the default queue manager.</span></span>  
  
10. <span data-ttu-id="3d66a-179">在中**队列**框中，键入"SOLICITRESPONSEQ"，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-179">In the **Queue** box, type " SOLICITRESPONSEQ", and then click **Export**.</span></span>  
  
11. <span data-ttu-id="3d66a-180">在导出对话框中，单击**Create Queue**，然后单击**确定**或**完成**直到您退出所有对话框为止。</span><span class="sxs-lookup"><span data-stu-id="3d66a-180">In the Export dialog box, click **Create Queue**, and then click **OK** or **Done** until you have exited all dialog boxes.</span></span>  
  
## <a name="enabling-the-receive-location-and-starting-the-send-port"></a><span data-ttu-id="3d66a-181">启用接收位置和启动发送端口</span><span class="sxs-lookup"><span data-stu-id="3d66a-181">Enabling the Receive Location and Starting the Send Port</span></span>  
 <span data-ttu-id="3d66a-182">此过程创建在业务流程中接收文件所需的文件夹，并向输出文件夹发送相关消息和响应消息。</span><span class="sxs-lookup"><span data-stu-id="3d66a-182">This procedure creates the folders required to receive the file into the orchestration and sends the correlated message and response message to the output folders.</span></span>  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="3d66a-183">若要启用接收位置并启动发送端口</span><span class="sxs-lookup"><span data-stu-id="3d66a-183">To enable the receive location and start the send port</span></span>  
  
1.  <span data-ttu-id="3d66a-184">在 BizTalk Server 管理控制台中，单击**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-184">In the BizTalk Server Administration console, click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="3d66a-185">在细节窗格中，右键单击**MQIn**接收位置，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-185">In the details pane, right-click the **MQIn** receive location and click **Enable**.</span></span>  
  
3.  <span data-ttu-id="3d66a-186">在细节窗格中，右键单击**MQOut**发送端口并单击**开始。**</span><span class="sxs-lookup"><span data-stu-id="3d66a-186">In the details pane, right-click the **MQOut** send port and click **Start.**</span></span>  
  
## <a name="creating-the-folders-used-by-the-application"></a><span data-ttu-id="3d66a-187">创建应用程序使用的文件夹</span><span class="sxs-lookup"><span data-stu-id="3d66a-187">Creating the Folders Used by the Application</span></span>  
  
#### <a name="to-create-the-folders-used-by-the-application"></a><span data-ttu-id="3d66a-188">创建应用程序使用的文件夹</span><span class="sxs-lookup"><span data-stu-id="3d66a-188">To create the folders used by the application</span></span>  
  
1.  <span data-ttu-id="3d66a-189">如果没有应用程序使用的文件夹，请在 C:\ 驱动器上创建一个名为“temp”的文件夹。</span><span class="sxs-lookup"><span data-stu-id="3d66a-189">If one does not already exist, create a folder named "temp" on your C:\ drive.</span></span>  
  
2.  <span data-ttu-id="3d66a-190">下创建文件夹**C:\temp**目录名称为"Pickup2"、"Dropit2"和"MoveIt"。</span><span class="sxs-lookup"><span data-stu-id="3d66a-190">Create folders under the **C:\temp** directory named "Pickup2", "Dropit2", and "MoveIt".</span></span>  
  
## <a name="modifying-the-orchestration-used-by-the-application"></a><span data-ttu-id="3d66a-191">修改应用程序使用的业务流程</span><span class="sxs-lookup"><span data-stu-id="3d66a-191">Modifying the Orchestration Used by the Application</span></span>  
 <span data-ttu-id="3d66a-192">此过程将修改应用程序使用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="3d66a-192">This procedure modifies the orchestration used by the application.</span></span>  
  
||  
|-|  
|<span data-ttu-id="3d66a-193">修改应用程序使用的业务流程</span><span class="sxs-lookup"><span data-stu-id="3d66a-193">To modify the Orchestration used by the application</span></span>|  
|<span data-ttu-id="3d66a-194">-在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，双击解决方案文件中， **MQSCorrelationSolicitResponse.sln**，若要打开该解决方案。</span><span class="sxs-lookup"><span data-stu-id="3d66a-194">- In Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], double-click the solution file, **MQSCorrelationSolicitResponse.sln**, to open the solution.</span></span><br /><br /> <span data-ttu-id="3d66a-195">-从解决方案资源管理器窗格中，双击业务流程**MQSCorrelationSolicitResponse.odx**查看业务流程。</span><span class="sxs-lookup"><span data-stu-id="3d66a-195">- From the Solution Explorer pane, double-click the orchestration **MQSCorrelationSolicitResponse.odx** to view the orchestration.</span></span><br /><br /> <span data-ttu-id="3d66a-196">-双击消息赋值形状**MessageAssignment_1**以启动 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="3d66a-196">- Double-click the message assignment shape **MessageAssignment_1** to launch the BizTalk Expression Editor.</span></span><br /><br /> <span data-ttu-id="3d66a-197">-输入下面的表达式的相应 MQSeries 队列管理器名称：</span><span class="sxs-lookup"><span data-stu-id="3d66a-197">- Enter the appropriate MQSeries queue manager name for the following expression:</span></span><br /><br /> `MQSeriesRequestSendMessage(MQSeries.MQMD_ReplyToQMgr) = "QM_<machine_name>";`<br /><br /> <span data-ttu-id="3d66a-198">-如果您要用于从 BizTalk 发送包含原始消息而不是仅前 100 个字节的全部内容的响应消息，修改以下行在 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="3d66a-198">- If you would like for the response message sent from BizTalk to contain the entire contents of the original message instead of only the first 100 bytes, modify the following line in the BizTalk Expression Editor.</span></span><br /><br /> <span data-ttu-id="3d66a-199">的原始行：</span><span class="sxs-lookup"><span data-stu-id="3d66a-199">- Original line:</span></span><br /><br /> `MQSeriesRequestSendMessage(MQSeries.MQMD_Report) = 768;`<br /><br /> <span data-ttu-id="3d66a-200">将更改为：</span><span class="sxs-lookup"><span data-stu-id="3d66a-200">Change to:</span></span><br /><br /> `MQSeriesRequestSendMessage(MQSeries.MQMD_Report) = 1792;`<br /><br /> <span data-ttu-id="3d66a-201">-在 BizTalk 表达式编辑器中，单击**确定**保存修改后的表达式。</span><span class="sxs-lookup"><span data-stu-id="3d66a-201">- In the BizTalk Expression Editor, click **OK** to save the modified expression.</span></span><br /><br /> <span data-ttu-id="3d66a-202">-在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，选择**文件**，然后选择**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-202">- In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], select **File**, and then select **Save All**.</span></span>|  
  
## <a name="building-and-deploying-the-sample"></a><span data-ttu-id="3d66a-203">生成和部署示例</span><span class="sxs-lookup"><span data-stu-id="3d66a-203">Building and Deploying the Sample</span></span>  
 <span data-ttu-id="3d66a-204">此过程将生成并部署包含在此应用程序中使用的业务流程的解决方案。</span><span class="sxs-lookup"><span data-stu-id="3d66a-204">This procedure builds and deploys the solution that contains the orchestration used in this application.</span></span>  
  
#### <a name="to-build-and-deploy-the-sample"></a><span data-ttu-id="3d66a-205">生成和部署示例</span><span class="sxs-lookup"><span data-stu-id="3d66a-205">To build and deploy the sample</span></span>  
  
1.  <span data-ttu-id="3d66a-206">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="3d66a-206">In a command window, navigate to the following folder:</span></span>  
  
     `<Samples Path>\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestrationWithSolicitResponse`  
  
2.  <span data-ttu-id="3d66a-207">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3d66a-207">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    1.  <span data-ttu-id="3d66a-208">为项目创建强名称密钥。</span><span class="sxs-lookup"><span data-stu-id="3d66a-208">Creates a strong name key for the project.</span></span>  
  
    2.  <span data-ttu-id="3d66a-209">编译并部署业务流程项目。</span><span class="sxs-lookup"><span data-stu-id="3d66a-209">Compiles and deploys the orchestration project.</span></span>  
  
    3.  <span data-ttu-id="3d66a-210">使用文件适配器创建发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="3d66a-210">Creates a send port and a receive port with the File adapter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3d66a-211">由于此业务流程指定了使用文件适配器收发文件的绑定，因此，在部署业务流程时，将创建所需的发送端口、接收端口和接收位置，以便接收文件并将其放置到业务流程中，并输出相关消息和响应消息。</span><span class="sxs-lookup"><span data-stu-id="3d66a-211">Since this orchestration specifies the bindings for sending and receiving files with the file adapter, when you deploy the orchestration the necessary send ports, receive port, and receive location will be created for receiving a file into the orchestration and outputting the correlation message and the response message.</span></span>  
  
## <a name="binding-and-starting-the-orchestration"></a><span data-ttu-id="3d66a-212">绑定和启动业务流程</span><span class="sxs-lookup"><span data-stu-id="3d66a-212">Binding and Starting the Orchestration</span></span>  
 <span data-ttu-id="3d66a-213">此过程将业务流程绑定到主机以及相应的发送端口和接收位置。</span><span class="sxs-lookup"><span data-stu-id="3d66a-213">This procedure binds the orchestration to the host and appropriate send ports and receive locations.</span></span>  
  
#### <a name="to-bind-and-start-the-orchestration"></a><span data-ttu-id="3d66a-214">绑定和启动业务流程的步骤</span><span class="sxs-lookup"><span data-stu-id="3d66a-214">To bind and start the orchestration</span></span>  
  
1.  <span data-ttu-id="3d66a-215">在 BizTalk Server 管理控制台中，展开**业务流程**文件夹。</span><span class="sxs-lookup"><span data-stu-id="3d66a-215">In the BizTalk Server Administration console, expand the **Orchestrations** folder.</span></span>  
  
2.  <span data-ttu-id="3d66a-216">在细节窗格中，右键单击**MQSCorrelationSolicitResponse**业务流程，并单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-216">In the details pane, right-click the **MQSCorrelationSolicitResponse** orchestration and click **Bind**.</span></span>  
  
3.  <span data-ttu-id="3d66a-217">将业务流程端口绑定到下列发送端口和接收位置：</span><span class="sxs-lookup"><span data-stu-id="3d66a-217">Bind the orchestration ports to the following send ports and receive locations:</span></span>  
  
    |<span data-ttu-id="3d66a-218">**业务流程端口**</span><span class="sxs-lookup"><span data-stu-id="3d66a-218">**Orchestration Port**</span></span>|<span data-ttu-id="3d66a-219">**消息传送端口 / 接收位置**</span><span class="sxs-lookup"><span data-stu-id="3d66a-219">**Messaging Port / Receive Location**</span></span>|  
    |----------------------------|--------------------------------------------|  
    |<span data-ttu-id="3d66a-220">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="3d66a-220">FileReceivePort</span></span>|<span data-ttu-id="3d66a-221">MQSCorrelationSolicitResponse.Orchestration.FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="3d66a-221">MQSCorrelationSolicitResponse.Orchestration.FileReceivePort</span></span>|  
    |<span data-ttu-id="3d66a-222">MQSeriesResponseReceivePort</span><span class="sxs-lookup"><span data-stu-id="3d66a-222">MQSeriesResponseReceivePort</span></span>|<span data-ttu-id="3d66a-223">MQReply</span><span class="sxs-lookup"><span data-stu-id="3d66a-223">MQReply</span></span>|  
    |<span data-ttu-id="3d66a-224">SolicitResponsePort</span><span class="sxs-lookup"><span data-stu-id="3d66a-224">SolicitResponsePort</span></span>|<span data-ttu-id="3d66a-225">MQSolicitResponse</span><span class="sxs-lookup"><span data-stu-id="3d66a-225">MQSolicitResponse</span></span>|  
    |<span data-ttu-id="3d66a-226">TempPort</span><span class="sxs-lookup"><span data-stu-id="3d66a-226">TempPort</span></span>|<span data-ttu-id="3d66a-227">MQSCorrelationSolicitResponse.Orchestration.TempPort</span><span class="sxs-lookup"><span data-stu-id="3d66a-227">MQSCorrelationSolicitResponse.Orchestration.TempPort</span></span>|  
    |<span data-ttu-id="3d66a-228">FileSendPort</span><span class="sxs-lookup"><span data-stu-id="3d66a-228">FileSendPort</span></span>|<span data-ttu-id="3d66a-229">MQSCorrelationSolicitResponse.Orchestration.FileSendPort</span><span class="sxs-lookup"><span data-stu-id="3d66a-229">MQSCorrelationSolicitResponse.Orchestration.FileSendPort</span></span>|  
  
4.  <span data-ttu-id="3d66a-230">单击**主机**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-230">Click **Host**.</span></span>  
  
5.  <span data-ttu-id="3d66a-231">在中**主机**框中，选择**BizTalkServerApplication**然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-231">In the **Host** box, select **BizTalkServerApplication** and click **OK**.</span></span>  
  
6.  <span data-ttu-id="3d66a-232">在中**发送端口**，右键单击**MQSCorrelationSolicitResponse.Orchestration.TempPort**，然后选择**启动**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-232">In **Send Ports**, right-click **MQSCorrelationSolicitResponse.Orchestration.TempPort**, and then select **Start**.</span></span>  
  
7.  <span data-ttu-id="3d66a-233">在中**发送端口**，右键单击**MQSCorrelationSolicitResponse.Orchestration.FileSendPort**，然后选择**启动**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-233">In **Send Ports**, right-click **MQSCorrelationSolicitResponse.Orchestration.FileSendPort**, and then select **Start**.</span></span>  
  
8.  <span data-ttu-id="3d66a-234">在中**接收位置**，右键单击**MQSCorrelationSolicitResponse.Orchestration.FileReceivePort**，然后选择**启用**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-234">In **Receive Locations**, right-click **MQSCorrelationSolicitResponse.Orchestration.FileReceivePort**, and then select **Enable**.</span></span>  
  
9. <span data-ttu-id="3d66a-235">右键单击该业务流程，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="3d66a-235">Right-click the orchestration and click **Start**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3d66a-236">启动业务流程还将自动登记该业务流程。</span><span class="sxs-lookup"><span data-stu-id="3d66a-236">Starting the orchestration also automatically enlists the orchestration.</span></span>  
  
## <a name="testing-the-application"></a><span data-ttu-id="3d66a-237">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="3d66a-237">Testing the Application</span></span>  
 <span data-ttu-id="3d66a-238">此过程将测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="3d66a-238">This procedure tests the application.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="3d66a-239">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="3d66a-239">To test the application</span></span>  
  
1. <span data-ttu-id="3d66a-240">将文件放入**C:\Temp\Pickup2**文件夹。</span><span class="sxs-lookup"><span data-stu-id="3d66a-240">Put a file in the **C:\Temp\Pickup2** folder.</span></span>  
  
2. <span data-ttu-id="3d66a-241">检查中的文件**C:\Temp\Dropit2**文件夹并**C:\Temp\Moveit**文件夹。</span><span class="sxs-lookup"><span data-stu-id="3d66a-241">Examine the files in the **C:\Temp\Dropit2** folder and the **C:\Temp\Moveit**folder.</span></span>  
  
   - <span data-ttu-id="3d66a-242">**C:\Temp\Dropit2**文件夹应包含最初所提取的消息的副本[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3d66a-242">The **C:\Temp\Dropit2** folder should contain a copy of the message that was originally picked up by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
   - <span data-ttu-id="3d66a-243">**C:\Temp\Moveit**文件夹应包含带有消息标识符 (MQMD_MsgId) 和相关标识符 (MQMD_CorrelId) 的响应文档。</span><span class="sxs-lookup"><span data-stu-id="3d66a-243">The **C:\Temp\Moveit**folder should contain a response document with the message identifier (MQMD_MsgId) and the correlation identifier (MQMD_CorrelId).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="3d66a-244">如果禁用**MQReply**接收位置，您可以检查在 WebSphere MQ Explorer 中的消息，请参阅设置消息和相关标识符。</span><span class="sxs-lookup"><span data-stu-id="3d66a-244">If you disable the **MQReply** receive location, you can examine the message in WebSphere MQ Explorer and see that the message and correlation identifiers are set.</span></span> <span data-ttu-id="3d66a-245">若要执行此操作，启动**WebSphere MQ Explorer**并查看放置在消息**REPLYTOQ**队列。</span><span class="sxs-lookup"><span data-stu-id="3d66a-245">To do this, launch the **WebSphere MQ Explorer** and examine the message placed in the **REPLYTOQ** queue.</span></span> <span data-ttu-id="3d66a-246">消息和相关标识符显示在**标识符**选项卡**Messageproperties**对话框。</span><span class="sxs-lookup"><span data-stu-id="3d66a-246">The message and correlation identifiers are displayed on the **Identifiers** tab of the **Messageproperties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d66a-247">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d66a-247">See Also</span></span>  
 <span data-ttu-id="3d66a-248">[使用请求-答复相关消息](../core/correlating-messages-using-request-reply.md) </span><span class="sxs-lookup"><span data-stu-id="3d66a-248">[Correlating Messages Using Request-Reply](../core/correlating-messages-using-request-reply.md) </span></span>  
 [<span data-ttu-id="3d66a-249">MQSeries 适配器示例</span><span class="sxs-lookup"><span data-stu-id="3d66a-249">MQSeries Adapter Samples</span></span>](../core/mqseries-adapter-samples.md)