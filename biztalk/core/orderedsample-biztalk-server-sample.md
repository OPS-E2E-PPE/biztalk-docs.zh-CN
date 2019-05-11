---
title: OrderedSample （BizTalk Server 示例） |Microsoft Docs
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
- MQSeries adapters, examples
ms.assetid: 7e59ff43-d425-40cd-9725-af13084f83d9
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84490c48cc4f43f226cc65d4baa90ce7bca347f1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322252"
---
# <a name="orderedsample-biztalk-server-sample"></a><span data-ttu-id="8b34c-102">OrderedSample （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="8b34c-102">OrderedSample (BizTalk Server Sample)</span></span>
<span data-ttu-id="8b34c-103">OrderedSample 示例演示如何使用业务流程接收和发送往返过程方式中的一系列有序的消息。</span><span class="sxs-lookup"><span data-stu-id="8b34c-103">The OrderedSample sample demonstrates how to use an orchestration to receive and send an ordered series of messages in a round-trip fashion.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="8b34c-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="8b34c-104">What This Sample Does</span></span>  
 <span data-ttu-id="8b34c-105">该示例假定它从中接收消息的 MQSeries 队列中有消息。</span><span class="sxs-lookup"><span data-stu-id="8b34c-105">The sample assumes there are messages in the MQSeries queue from which it receives messages.</span></span> <span data-ttu-id="8b34c-106">当适配器读取来自 MQSeries 队列的消息时，它按顺序读取消息，并将其提交给[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8b34c-106">When the adapter reads the messages from MQSeries queue, it reads them in-order and submits them to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8b34c-107">在业务流程，接收端口**mqreceive**，具有其**按序送达**属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-107">The receive port in the orchestration, **mqreceive**, has its **Ordered Delivery** property set to **True**.</span></span>  
  
 <span data-ttu-id="8b34c-108">为发送方，业务流程发送一条消息，然后等待发送下一条消息之前送达通知。</span><span class="sxs-lookup"><span data-stu-id="8b34c-108">For the send side, the orchestration sends a message and then waits for a delivery notification before sending the next message.</span></span> <span data-ttu-id="8b34c-109">发送端口**mqsend**具有其**送达通知**属性设置为**传输**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-109">The send port, **mqsend** has its **Delivery Notification** property set to **Transmitted**.</span></span> <span data-ttu-id="8b34c-110">若要简化该示例，该业务流程使用无限循环。</span><span class="sxs-lookup"><span data-stu-id="8b34c-110">To keep the example simple, the orchestration uses an infinite loop.</span></span>  
  
 <span data-ttu-id="8b34c-111">业务流程可以接收消息批和单个消息。</span><span class="sxs-lookup"><span data-stu-id="8b34c-111">The orchestration can receive batches of messages and single messages.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="8b34c-112">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="8b34c-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="8b34c-113">*\<Samples Path\>* \AdaptersUsage\MQSeriesAdapter\OrderedSample</span><span class="sxs-lookup"><span data-stu-id="8b34c-113">*\<Samples Path\>* \AdaptersUsage\MQSeriesAdapter\OrderedSample</span></span>  
  
 <span data-ttu-id="8b34c-114">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="8b34c-114">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="8b34c-115">文件</span><span class="sxs-lookup"><span data-stu-id="8b34c-115">File</span></span>|<span data-ttu-id="8b34c-116">Description</span><span class="sxs-lookup"><span data-stu-id="8b34c-116">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="8b34c-117">OrderedReceiveSend.btproj,</span><span class="sxs-lookup"><span data-stu-id="8b34c-117">OrderedReceiveSend.btproj,</span></span><br /><br /> <span data-ttu-id="8b34c-118">OrderedReceiveSend.sln</span><span class="sxs-lookup"><span data-stu-id="8b34c-118">OrderedReceiveSend.sln</span></span>|<span data-ttu-id="8b34c-119">应用程序的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="8b34c-119">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="8b34c-120">OrderedReceiveSendOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="8b34c-120">OrderedReceiveSendOrchestration.odx</span></span>|<span data-ttu-id="8b34c-121">应用程序的业务流程。</span><span class="sxs-lookup"><span data-stu-id="8b34c-121">The orchestration of the application.</span></span>|  
|<span data-ttu-id="8b34c-122">OrderedSample.snk</span><span class="sxs-lookup"><span data-stu-id="8b34c-122">OrderedSample.snk</span></span>|<span data-ttu-id="8b34c-123">强名称密钥文件。</span><span class="sxs-lookup"><span data-stu-id="8b34c-123">The strong naming key file.</span></span>|  
|<span data-ttu-id="8b34c-124">**Setup.bat**</span><span class="sxs-lookup"><span data-stu-id="8b34c-124">**Setup.bat**</span></span>|<span data-ttu-id="8b34c-125">生成并初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="8b34c-125">Builds and initializes this sample.</span></span>|  
  
## <a name="building-and-running-the-sample"></a><span data-ttu-id="8b34c-126">构建和运行示例</span><span class="sxs-lookup"><span data-stu-id="8b34c-126">Building and Running the Sample</span></span>  
  
#### <a name="to-build-and-deploy-the-sample"></a><span data-ttu-id="8b34c-127">若要生成并部署示例</span><span class="sxs-lookup"><span data-stu-id="8b34c-127">To build and deploy the sample</span></span>  
  
1. <span data-ttu-id="8b34c-128">在命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="8b34c-128">In a command window, navigate to the following folder:</span></span>  
  
    `<Samples Path>\AdaptersUsage\MQSeriesAdapter\OrderedSample`  
  
2. <span data-ttu-id="8b34c-129">运行文件 Setup.bat，以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8b34c-129">Run the file Setup.bat, which performs the following actions:</span></span>  
  
   1.  <span data-ttu-id="8b34c-130">创建项目的强名称密钥。</span><span class="sxs-lookup"><span data-stu-id="8b34c-130">Creates a strong name key for the project.</span></span>  
  
   2.  <span data-ttu-id="8b34c-131">编译并部署业务流程项目。</span><span class="sxs-lookup"><span data-stu-id="8b34c-131">Compiles and deploys the orchestration project.</span></span>  
  
   <span data-ttu-id="8b34c-132">如果必须为 MQSeries Server for Windows 安装所需的权限，您可以创建 MQSeries 队列通过适配器对话框，并可以跳过下一步的过程。</span><span class="sxs-lookup"><span data-stu-id="8b34c-132">If you have the required permissions to the MQSeries Server for Windows installation, you can create the MQSeries queue through the adapter dialog boxes, and can skip the next procedure.</span></span> <span data-ttu-id="8b34c-133">如果还没有这样的访问权限，可以创建使用 IBM WebSphere MQ Explorer 的队列。</span><span class="sxs-lookup"><span data-stu-id="8b34c-133">If you do not have such access, you can create the queue using the IBM WebSphere MQ Explorer.</span></span> <span data-ttu-id="8b34c-134">若要创建的队列通过 WebSphere MQ Explorer，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="8b34c-134">To create the queues through the WebSphere MQ Explorer, complete the following steps.</span></span>  
  
## <a name="creating-the-mqseries-queues-through-the-websphere-mq-explorer"></a><span data-ttu-id="8b34c-135">创建通过 WebSphere MQ Explorer MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="8b34c-135">Creating the MQSeries Queues Through the WebSphere MQ Explorer</span></span>  
  
#### <a name="to-create-the-mqseries-queues-through-the-websphere-mq-explorer"></a><span data-ttu-id="8b34c-136">通过 WebSphere MQ Explorer 创建 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="8b34c-136">To create the MQSeries queues through the WebSphere MQ Explorer</span></span>  
  
1.  <span data-ttu-id="8b34c-137">单击**启动**，依次指向**所有程序**，指向**IBM WebSphere MQ**，然后单击**WebSphere MQ Explorer**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-137">Click **Start**, point to **All Programs**, point to **IBM WebSphere MQ**, and then click **WebSphere MQ Explorer**.</span></span>  
  
2.  <span data-ttu-id="8b34c-138">双击**队列管理器**，然后双击**默认队列管理器**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-138">Double-click **Queue Managers**, and then double-click the **default queue manager**.</span></span> <span data-ttu-id="8b34c-139">默认的队列管理器通常命名为的 QM_ < m a c h > 其中是您的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="8b34c-139">The default queue manager is typically named QM_<machine_name> where machine_name is the name of your computer.</span></span>  
  
3.  <span data-ttu-id="8b34c-140">右键单击**队列**，依次指向**新建**，然后单击**本地队列**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-140">Right-click **Queues**, point to **New**, and then click **Local Queue**.</span></span>  
  
4.  <span data-ttu-id="8b34c-141">在中**创建本地队列**对话框中**队列名称**，类型 **"queue1"**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-141">In **Create Local Queue** dialog box, in **Queue Name**, type **"queue1"**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="8b34c-142">右键单击**队列**，单击**新建**，然后单击**本地队列**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-142">Right-click **Queues**, click **New**, and then click **Local Queue**.</span></span>  
  
6.  <span data-ttu-id="8b34c-143">在中**创建本地队列**对话框中**队列名称**，类型 **"queue2"**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-143">In the **Create Local Queue** dialog box, in **Queue Name**, type **"queue2"**, and then click **OK**.</span></span>  
  
## <a name="creating-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="8b34c-144">创建接收位置和 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="8b34c-144">Creating the Receive Location and the MQSeries Queue</span></span>  
 <span data-ttu-id="8b34c-145">此过程创建发送端口和接收位置发送到消息并接收来自 MQSeries 的相关消息。</span><span class="sxs-lookup"><span data-stu-id="8b34c-145">This procedure creates the send port and receive location to send the message to and receive the correlation message from MQSeries.</span></span> <span data-ttu-id="8b34c-146">时创建的接收位置，如果不是已创建，也可创建 MQSeries 队列。</span><span class="sxs-lookup"><span data-stu-id="8b34c-146">The MQSeries queue will also be created when you create the receive location if not already created.</span></span>  
  
#### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="8b34c-147">创建接收位置和 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="8b34c-147">To create the receive location and the MQSeries queue</span></span>  
  
1.  <span data-ttu-id="8b34c-148">打开 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="8b34c-148">Open the BizTalk Server Administration console.</span></span>  
  
2.  <span data-ttu-id="8b34c-149">展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8b34c-149">Expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the required application.</span></span>  
  
3.  <span data-ttu-id="8b34c-150">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-150">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="8b34c-151">在中**单向接收端口属性**对话框框中，键入，在**名称**框中，键入**OrderedSampleReceive**然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-151">In the **One-way Receive Port Properties** dialog box type, in the **Name** box type **OrderedSampleReceive** and click **OK**.</span></span>  
  
5.  <span data-ttu-id="8b34c-152">在左窗格中，单击**接收位置**选项卡，然后依次**新建**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-152">In the left pane, click **Receive Locations** tab, and then click **New**.</span></span>  
  
6.  <span data-ttu-id="8b34c-153">在中**接收位置属性**对话框中**名称**框中，键入"**OrderedSampleReceiveLocation**"。</span><span class="sxs-lookup"><span data-stu-id="8b34c-153">In the **Receive Location Properties** dialog box, in the **Name** box type "**OrderedSampleReceiveLocation**".</span></span>  
  
7.  <span data-ttu-id="8b34c-154">在中**传输类型**框中，选择**MQSeries**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-154">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
8.  <span data-ttu-id="8b34c-155">在中**接收处理程序**框中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-155">In the **Receive Handler** box, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="8b34c-156">在中**接收管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-156">In the **Receive pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  
  
10. <span data-ttu-id="8b34c-157">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-157">Click **Configure**.</span></span>  
  
11. <span data-ttu-id="8b34c-158">在中**MQSeries 传输属性**对话框中**轮询间隔**框中，键入 **"10"**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-158">In the **MQSeries Transport Properties** dialog box, in the **Polling Interval** box, type **"10"**.</span></span>  
  
12. <span data-ttu-id="8b34c-159">在中**队列定义**框中，单击**省略号 （...）** 按钮。</span><span class="sxs-lookup"><span data-stu-id="8b34c-159">In the **Queue Definition** box, click the **ellipsis (…)** button.</span></span>  
  
13. <span data-ttu-id="8b34c-160">在中**队列定义**对话框中**服务器名称**框中，键入您的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="8b34c-160">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
14. <span data-ttu-id="8b34c-161">在中**队列管理器**框中，选择**默认队列管理器**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-161">In the **Queue Manager** box, select the **default queue manager**.</span></span>  
  
15. <span data-ttu-id="8b34c-162">在中**队列**框中，键入" **queue1**"，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-162">In the **Queue** box, type " **queue1**", and then click **Export**.</span></span>  
  
16. <span data-ttu-id="8b34c-163">在中**导出**对话框中，单击**Create Queue**，然后单击**确定**或**完成**直到您退出所有对话框为止。</span><span class="sxs-lookup"><span data-stu-id="8b34c-163">In the **Export** dialog box, click **Create Queue**, and then click **OK** or **Done** until you have exited all dialog boxes.</span></span>  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a><span data-ttu-id="8b34c-164">创建发送端口和 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="8b34c-164">Creating the Send Port and MQSeries Queue</span></span>  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a><span data-ttu-id="8b34c-165">若要创建的发送端口和 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="8b34c-165">To create the send port and MQSeries queue</span></span>  
  
1.  <span data-ttu-id="8b34c-166">右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-166">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="8b34c-167">在中**静态端口属性**对话框框中，键入，在**名称**框中，键入"**OrderedSampleSend**"。</span><span class="sxs-lookup"><span data-stu-id="8b34c-167">In the **Static Port Properties** dialog box type, in the **Name** box, type "**OrderedSampleSend**".</span></span>  
  
3.  <span data-ttu-id="8b34c-168">在中**传输类型**框中，选择**MQSeries**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-168">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
4.  <span data-ttu-id="8b34c-169">在中**发送管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-169">In the **Send pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span></span>  
  
5.  <span data-ttu-id="8b34c-170">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-170">Click **Configure**.</span></span>  
  
6.  <span data-ttu-id="8b34c-171">在中**MQSeries 传输属性**对话框中**队列定义**框中，单击**省略号 （...）** 按钮。</span><span class="sxs-lookup"><span data-stu-id="8b34c-171">In the **MQSeries Transport Properties** dialog box, in the **Queue Definition** box, click the **ellipsis (…)** button.</span></span>  
  
7.  <span data-ttu-id="8b34c-172">在中**队列定义**对话框中**服务器名称**框中，键入您的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="8b34c-172">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
8.  <span data-ttu-id="8b34c-173">在中**队列管理器**框中，选择**默认队列管理器**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-173">In the **Queue Manager** box, select the **default queue manager**.</span></span>  
  
9. <span data-ttu-id="8b34c-174">在中**队列**框中，键入" **queue2**"，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-174">In the **Queue** box, type " **queue2**", and then click **Export**.</span></span>  
  
10. <span data-ttu-id="8b34c-175">在中**导出**对话框中，单击**Create Queue**，然后单击**确定**或**完成**直到您退出所有对话框为止。</span><span class="sxs-lookup"><span data-stu-id="8b34c-175">In the **Export** dialog box, click **Create Queue**, and then click **OK** or **Done** until you have exited all dialog boxes.</span></span>  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="8b34c-176">若要启用接收位置并启动发送端口</span><span class="sxs-lookup"><span data-stu-id="8b34c-176">To enable the receive location and start the send port</span></span>  
  
1.  <span data-ttu-id="8b34c-177">在 BizTalk Server 管理控制台中，单击**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-177">In the BizTalk Server Administration console, click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="8b34c-178">在细节窗格中，右键单击**MQIn**接收位置，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-178">In the details pane, right-click the **MQIn** receive location and click **Enable**.</span></span>  
  
3.  <span data-ttu-id="8b34c-179">在细节窗格中，右键单击**MQOut**发送端口并单击**开始。**</span><span class="sxs-lookup"><span data-stu-id="8b34c-179">In the details pane, right-click the **MQOut** send port and click **Start.**</span></span>  
  
#### <a name="to-bind-and-start-the-orchestration"></a><span data-ttu-id="8b34c-180">绑定和启动业务流程</span><span class="sxs-lookup"><span data-stu-id="8b34c-180">To bind and start the Orchestration</span></span>  
  
1.  <span data-ttu-id="8b34c-181">在 BizTalk Server 管理控制台中，展开**业务流程**文件夹。</span><span class="sxs-lookup"><span data-stu-id="8b34c-181">In the BizTalk Server Administration console, expand the **Orchestrations** folder.</span></span>  
  
2.  <span data-ttu-id="8b34c-182">双击**OrderedSampleOrchestration**业务流程，并单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-182">Double-click the **OrderedSampleOrchestration** orchestration, and then click  **Bindings**.</span></span>  
  
3.  <span data-ttu-id="8b34c-183">将业务流程端口绑定到以下发送端口和接收位置：</span><span class="sxs-lookup"><span data-stu-id="8b34c-183">Bind the orchestration ports to the following send ports and receive locations:</span></span>  
  
    |<span data-ttu-id="8b34c-184">业务流程端口</span><span class="sxs-lookup"><span data-stu-id="8b34c-184">Orchestration Port</span></span>|<span data-ttu-id="8b34c-185">消息传送端口 / 接收位置</span><span class="sxs-lookup"><span data-stu-id="8b34c-185">Messaging Port / Receive Location</span></span>|  
    |------------------------|----------------------------------------|  
    |<span data-ttu-id="8b34c-186">mqreceive</span><span class="sxs-lookup"><span data-stu-id="8b34c-186">mqreceive</span></span>|<span data-ttu-id="8b34c-187">OrderedSampleReceive</span><span class="sxs-lookup"><span data-stu-id="8b34c-187">OrderedSampleReceive</span></span>|  
    |<span data-ttu-id="8b34c-188">mqsend</span><span class="sxs-lookup"><span data-stu-id="8b34c-188">mqsend</span></span>|<span data-ttu-id="8b34c-189">OrderedSampleSend</span><span class="sxs-lookup"><span data-stu-id="8b34c-189">OrderedSampleSend</span></span>|  
  
4.  <span data-ttu-id="8b34c-190">单击**主机**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-190">Click **Host**.</span></span>  
  
5.  <span data-ttu-id="8b34c-191">在中**主机**框中，选择**BizTalkServerApplication**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-191">In the **Host** box, select **BizTalkServerApplication**, and click **OK**.</span></span>  
  
6.  <span data-ttu-id="8b34c-192">右键单击**业务流程**然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="8b34c-192">Right click the **Orchestration** and click **Start**.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="8b34c-193">若要运行示例</span><span class="sxs-lookup"><span data-stu-id="8b34c-193">To run the sample</span></span>  
  
1.  <span data-ttu-id="8b34c-194">启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="8b34c-194">Start the orchestration.</span></span>  
  
2.  <span data-ttu-id="8b34c-195">将消息放入已从其配置接收位置读取 MQSeries 队列。</span><span class="sxs-lookup"><span data-stu-id="8b34c-195">Put messages into the MQSeries queue from which you have configured the receive location to read.</span></span>  
  
3.  <span data-ttu-id="8b34c-196">已向其配置发送端口以发送消息的发送队列中在 WebSphere MQ Explorer 中查看的消息。</span><span class="sxs-lookup"><span data-stu-id="8b34c-196">View the messages in WebSphere MQ Explorer in the send queue to which you have configured the send port to send messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b34c-197">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b34c-197">See Also</span></span>  
 [<span data-ttu-id="8b34c-198">MQSeries 适配器示例</span><span class="sxs-lookup"><span data-stu-id="8b34c-198">MQSeries Adapter Samples</span></span>](../core/mqseries-adapter-samples.md)