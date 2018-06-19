---
title: OrderedSample （BizTalk Server 示例） |Microsoft 文档
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
ms.openlocfilehash: 1b9e93c7bb9cb59088e465dc53dd992ffd5f1c11
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974747"
---
# <a name="orderedsample-biztalk-server-sample"></a><span data-ttu-id="ca2c2-102">OrderedSample（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="ca2c2-102">OrderedSample (BizTalk Server Sample)</span></span>
<span data-ttu-id="ca2c2-103">OrderedSample 示例演示如何使用业务流程以往返过程方式接收和发送一系列有序消息。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-103">The OrderedSample sample demonstrates how to use an orchestration to receive and send an ordered series of messages in a round-trip fashion.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="ca2c2-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="ca2c2-104">What This Sample Does</span></span>  
 <span data-ttu-id="ca2c2-105">本示例假设发送消息的 MQSeries 队列中存在消息。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-105">The sample assumes there are messages in the MQSeries queue from which it receives messages.</span></span> <span data-ttu-id="ca2c2-106">当适配器读取来自 MQSeries 队列的消息时，适配器将按顺序读取消息，并将其提交给 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-106">When the adapter reads the messages from MQSeries queue, it reads them in-order and submits them to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="ca2c2-107">在业务流程，接收端口**mqreceive**，具有其**按序送达**属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-107">The receive port in the orchestration, **mqreceive**, has its **Ordered Delivery** property set to **True**.</span></span>  
  
 <span data-ttu-id="ca2c2-108">对于发送端，业务流程将发送一个消息并等待传送通知，然后再发送下一个消息。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-108">For the send side, the orchestration sends a message and then waits for a delivery notification before sending the next message.</span></span> <span data-ttu-id="ca2c2-109">发送端口**mqsend**具有其**传递通知**属性设置为**传输**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-109">The send port, **mqsend** has its **Delivery Notification** property set to **Transmitted**.</span></span> <span data-ttu-id="ca2c2-110">为了使此示例尽量简单，业务流程使用无限循环。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-110">To keep the example simple, the orchestration uses an infinite loop.</span></span>  
  
 <span data-ttu-id="ca2c2-111">业务流程可接收消息批和单个消息。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-111">The orchestration can receive batches of messages and single messages.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="ca2c2-112">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="ca2c2-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="ca2c2-113">*\<示例路径\>* \AdaptersUsage\MQSeriesAdapter\OrderedSample</span><span class="sxs-lookup"><span data-stu-id="ca2c2-113">*\<Samples Path\>* \AdaptersUsage\MQSeriesAdapter\OrderedSample</span></span>  
  
 <span data-ttu-id="ca2c2-114">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="ca2c2-114">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="ca2c2-115">文件</span><span class="sxs-lookup"><span data-stu-id="ca2c2-115">File</span></span>|<span data-ttu-id="ca2c2-116">Description</span><span class="sxs-lookup"><span data-stu-id="ca2c2-116">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="ca2c2-117">OrderedReceiveSend.btproj、</span><span class="sxs-lookup"><span data-stu-id="ca2c2-117">OrderedReceiveSend.btproj,</span></span><br /><br /> <span data-ttu-id="ca2c2-118">OrderedReceiveSend.sln</span><span class="sxs-lookup"><span data-stu-id="ca2c2-118">OrderedReceiveSend.sln</span></span>|<span data-ttu-id="ca2c2-119">应用程序的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-119">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="ca2c2-120">OrderedReceiveSendOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="ca2c2-120">OrderedReceiveSendOrchestration.odx</span></span>|<span data-ttu-id="ca2c2-121">应用程序的业务流程。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-121">The orchestration of the application.</span></span>|  
|<span data-ttu-id="ca2c2-122">OrderedSample.snk</span><span class="sxs-lookup"><span data-stu-id="ca2c2-122">OrderedSample.snk</span></span>|<span data-ttu-id="ca2c2-123">强命名密钥文件。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-123">The strong naming key file.</span></span>|  
|<span data-ttu-id="ca2c2-124">**Setup.bat**</span><span class="sxs-lookup"><span data-stu-id="ca2c2-124">**Setup.bat**</span></span>|<span data-ttu-id="ca2c2-125">生成并初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-125">Builds and initializes this sample.</span></span>|  
  
## <a name="building-and-running-the-sample"></a><span data-ttu-id="ca2c2-126">生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="ca2c2-126">Building and Running the Sample</span></span>  
  
#### <a name="to-build-and-deploy-the-sample"></a><span data-ttu-id="ca2c2-127">生成和部署示例</span><span class="sxs-lookup"><span data-stu-id="ca2c2-127">To build and deploy the sample</span></span>  
  
1.  <span data-ttu-id="ca2c2-128">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="ca2c2-128">In a command window, navigate to the following folder:</span></span>  
  
     `<Samples Path>\AdaptersUsage\MQSeriesAdapter\OrderedSample`  
  
2.  <span data-ttu-id="ca2c2-129">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ca2c2-129">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    1.  <span data-ttu-id="ca2c2-130">为项目创建强名称密钥。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-130">Creates a strong name key for the project.</span></span>  
  
    2.  <span data-ttu-id="ca2c2-131">编译并部署业务流程项目。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-131">Compiles and deploys the orchestration project.</span></span>  
  
 <span data-ttu-id="ca2c2-132">如果您具有安装 MQSeries Server for Windows 的必需权限，则可以通过适配器对话框创建 MQSeries 队列，并可以跳过下一过程。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-132">If you have the required permissions to the MQSeries Server for Windows installation, you can create the MQSeries queue through the adapter dialog boxes, and can skip the next procedure.</span></span> <span data-ttu-id="ca2c2-133">如果您没有这样的访问权限，可以使用 IBM WebSphere MQ Explorer 来创建队列。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-133">If you do not have such access, you can create the queue using the IBM WebSphere MQ Explorer.</span></span> <span data-ttu-id="ca2c2-134">若要通过 WebSphere MQ Explorer 创建队列，请完成下列步骤。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-134">To create the queues through the WebSphere MQ Explorer, complete the following steps.</span></span>  
  
## <a name="creating-the-mqseries-queues-through-the-websphere-mq-explorer"></a><span data-ttu-id="ca2c2-135">创建通过 WebSphere MQ 资源管理器的 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="ca2c2-135">Creating the MQSeries Queues Through the WebSphere MQ Explorer</span></span>  
  
#### <a name="to-create-the-mqseries-queues-through-the-websphere-mq-explorer"></a><span data-ttu-id="ca2c2-136">若要创建 MQSeries 队列通过 WebSphere MQ 资源管理器</span><span class="sxs-lookup"><span data-stu-id="ca2c2-136">To create the MQSeries queues through the WebSphere MQ Explorer</span></span>  
  
1.  <span data-ttu-id="ca2c2-137">单击**启动**，指向**所有程序**，指向**IBM WebSphere MQ**，然后单击**WebSphere MQ 资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-137">Click **Start**, point to **All Programs**, point to **IBM WebSphere MQ**, and then click **WebSphere MQ Explorer**.</span></span>  
  
2.  <span data-ttu-id="ca2c2-138">双击**队列管理器**，然后双击**默认队列管理器**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-138">Double-click **Queue Managers**, and then double-click the **default queue manager**.</span></span> <span data-ttu-id="ca2c2-139">默认的队列管理器通常命名为的 QM_ < machine_name > machine_name 所在计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-139">The default queue manager is typically named QM_<machine_name> where machine_name is the name of your computer.</span></span>  
  
3.  <span data-ttu-id="ca2c2-140">右键单击**队列**，指向**新建**，然后单击**本地队列**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-140">Right-click **Queues**, point to **New**, and then click **Local Queue**.</span></span>  
  
4.  <span data-ttu-id="ca2c2-141">在**创建本地队列**对话框中，在**队列名称**，类型 **"queue1"**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-141">In **Create Local Queue** dialog box, in **Queue Name**, type **"queue1"**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="ca2c2-142">右键单击**队列**，单击**新建**，然后单击**本地队列**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-142">Right-click **Queues**, click **New**, and then click **Local Queue**.</span></span>  
  
6.  <span data-ttu-id="ca2c2-143">在**创建本地队列**对话框中，在**队列名称**，类型 **"queue2"**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-143">In the **Create Local Queue** dialog box, in **Queue Name**, type **"queue2"**, and then click **OK**.</span></span>  
  
## <a name="creating-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="ca2c2-144">创建接收位置和 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="ca2c2-144">Creating the Receive Location and the MQSeries Queue</span></span>  
 <span data-ttu-id="ca2c2-145">此过程将创建发送端口和接收位置，以便向 MQSeries 发送消息以及接收来自 MQSeries 的相关消息。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-145">This procedure creates the send port and receive location to send the message to and receive the correlation message from MQSeries.</span></span> <span data-ttu-id="ca2c2-146">创建接收位置时，还将创建 MQSeries 队列（如果尚未创建）。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-146">The MQSeries queue will also be created when you create the receive location if not already created.</span></span>  
  
#### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="ca2c2-147">若要创建接收位置和 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="ca2c2-147">To create the receive location and the MQSeries queue</span></span>  
  
1.  <span data-ttu-id="ca2c2-148">打开 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-148">Open the BizTalk Server Administration console.</span></span>  
  
2.  <span data-ttu-id="ca2c2-149">展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-149">Expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the required application.</span></span>  
  
3.  <span data-ttu-id="ca2c2-150">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-150">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="ca2c2-151">在**单向接收端口属性**对话框框中，键入，在**名称**框中，键入**OrderedSampleReceive**单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-151">In the **One-way Receive Port Properties** dialog box type, in the **Name** box type **OrderedSampleReceive** and click **OK**.</span></span>  
  
5.  <span data-ttu-id="ca2c2-152">在左窗格中，单击**接收位置**选项卡上，并依次**新建**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-152">In the left pane, click **Receive Locations** tab, and then click **New**.</span></span>  
  
6.  <span data-ttu-id="ca2c2-153">在**接收位置属性**对话框中，在**名称**框中，键入"**OrderedSampleReceiveLocation**"。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-153">In the **Receive Location Properties** dialog box, in the **Name** box type "**OrderedSampleReceiveLocation**".</span></span>  
  
7.  <span data-ttu-id="ca2c2-154">在**传输类型**框中，选择**MQSeries**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-154">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
8.  <span data-ttu-id="ca2c2-155">在**接收处理程序**框中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-155">In the **Receive Handler** box, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="ca2c2-156">在**接收管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-156">In the **Receive pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  
  
10. <span data-ttu-id="ca2c2-157">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-157">Click **Configure**.</span></span>  
  
11. <span data-ttu-id="ca2c2-158">在**MQSeries 传输属性**对话框中，在**轮询间隔**框中，键入 **"10"**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-158">In the **MQSeries Transport Properties** dialog box, in the **Polling Interval** box, type **"10"**.</span></span>  
  
12. <span data-ttu-id="ca2c2-159">在**队列定义**框中，单击**省略号 （...）** 按钮。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-159">In the **Queue Definition** box, click the **ellipsis (…)** button.</span></span>  
  
13. <span data-ttu-id="ca2c2-160">在**队列定义**对话框中，在**服务器名称**框中，键入你的计算机名。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-160">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
14. <span data-ttu-id="ca2c2-161">在**队列管理器**框中，选择**默认队列管理器**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-161">In the **Queue Manager** box, select the **default queue manager**.</span></span>  
  
15. <span data-ttu-id="ca2c2-162">在**队列**框中，键入" **queue1**"，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-162">In the **Queue** box, type " **queue1**", and then click **Export**.</span></span>  
  
16. <span data-ttu-id="ca2c2-163">在**导出**对话框中，单击**创建队列**，然后单击**确定**或**完成**之前已退出所有对话框。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-163">In the **Export** dialog box, click **Create Queue**, and then click **OK** or **Done** until you have exited all dialog boxes.</span></span>  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a><span data-ttu-id="ca2c2-164">创建发送端口和 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="ca2c2-164">Creating the Send Port and MQSeries Queue</span></span>  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a><span data-ttu-id="ca2c2-165">若要创建的发送端口和 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="ca2c2-165">To create the send port and MQSeries queue</span></span>  
  
1.  <span data-ttu-id="ca2c2-166">右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-166">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="ca2c2-167">在**静态端口属性**对话框框中，键入，在**名称**框中，键入"**OrderedSampleSend**"。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-167">In the **Static Port Properties** dialog box type, in the **Name** box, type "**OrderedSampleSend**".</span></span>  
  
3.  <span data-ttu-id="ca2c2-168">在**传输类型**框中，选择**MQSeries**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-168">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
4.  <span data-ttu-id="ca2c2-169">在**发送管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-169">In the **Send pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span></span>  
  
5.  <span data-ttu-id="ca2c2-170">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-170">Click **Configure**.</span></span>  
  
6.  <span data-ttu-id="ca2c2-171">在**MQSeries 传输属性**对话框中，在**队列定义**框中，单击**省略号 （...）** 按钮。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-171">In the **MQSeries Transport Properties** dialog box, in the **Queue Definition** box, click the **ellipsis (…)** button.</span></span>  
  
7.  <span data-ttu-id="ca2c2-172">在**队列定义**对话框中，在**服务器名称**框中，键入你的计算机名。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-172">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
8.  <span data-ttu-id="ca2c2-173">在**队列管理器**框中，选择**默认队列管理器**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-173">In the **Queue Manager** box, select the **default queue manager**.</span></span>  
  
9. <span data-ttu-id="ca2c2-174">在**队列**框中，键入" **queue2**"，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-174">In the **Queue** box, type " **queue2**", and then click **Export**.</span></span>  
  
10. <span data-ttu-id="ca2c2-175">在**导出**对话框中，单击**创建队列**，然后单击**确定**或**完成**之前已退出所有对话框。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-175">In the **Export** dialog box, click **Create Queue**, and then click **OK** or **Done** until you have exited all dialog boxes.</span></span>  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="ca2c2-176">若要启用接收位置和启动发送端口</span><span class="sxs-lookup"><span data-stu-id="ca2c2-176">To enable the receive location and start the send port</span></span>  
  
1.  <span data-ttu-id="ca2c2-177">在 BizTalk Server 管理控制台中，单击**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-177">In the BizTalk Server Administration console, click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="ca2c2-178">在细节窗格中，右键单击**MQIn**接收位置，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-178">In the details pane, right-click the **MQIn** receive location and click **Enable**.</span></span>  
  
3.  <span data-ttu-id="ca2c2-179">在细节窗格中，右键单击**MQOut**发送端口和单击**启动。**</span><span class="sxs-lookup"><span data-stu-id="ca2c2-179">In the details pane, right-click the **MQOut** send port and click **Start.**</span></span>  
  
#### <a name="to-bind-and-start-the-orchestration"></a><span data-ttu-id="ca2c2-180">若要将绑定和启动业务流程</span><span class="sxs-lookup"><span data-stu-id="ca2c2-180">To bind and start the Orchestration</span></span>  
  
1.  <span data-ttu-id="ca2c2-181">在 BizTalk Server 管理控制台中，展开**业务流程**文件夹。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-181">In the BizTalk Server Administration console, expand the **Orchestrations** folder.</span></span>  
  
2.  <span data-ttu-id="ca2c2-182">双击**OrderedSampleOrchestration**业务流程，，然后单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-182">Double-click the **OrderedSampleOrchestration** orchestration, and then click  **Bindings**.</span></span>  
  
3.  <span data-ttu-id="ca2c2-183">将业务流程端口绑定到下列发送端口和接收位置：</span><span class="sxs-lookup"><span data-stu-id="ca2c2-183">Bind the orchestration ports to the following send ports and receive locations:</span></span>  
  
    |<span data-ttu-id="ca2c2-184">业务流程端口</span><span class="sxs-lookup"><span data-stu-id="ca2c2-184">Orchestration Port</span></span>|<span data-ttu-id="ca2c2-185">消息传送端口/接收位置</span><span class="sxs-lookup"><span data-stu-id="ca2c2-185">Messaging Port / Receive Location</span></span>|  
    |------------------------|----------------------------------------|  
    |<span data-ttu-id="ca2c2-186">mqreceive</span><span class="sxs-lookup"><span data-stu-id="ca2c2-186">mqreceive</span></span>|<span data-ttu-id="ca2c2-187">OrderedSampleReceive</span><span class="sxs-lookup"><span data-stu-id="ca2c2-187">OrderedSampleReceive</span></span>|  
    |<span data-ttu-id="ca2c2-188">mqsend</span><span class="sxs-lookup"><span data-stu-id="ca2c2-188">mqsend</span></span>|<span data-ttu-id="ca2c2-189">OrderedSampleSend</span><span class="sxs-lookup"><span data-stu-id="ca2c2-189">OrderedSampleSend</span></span>|  
  
4.  <span data-ttu-id="ca2c2-190">单击**主机**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-190">Click **Host**.</span></span>  
  
5.  <span data-ttu-id="ca2c2-191">在**主机**框中，选择**BizTalkServerApplication**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-191">In the **Host** box, select **BizTalkServerApplication**, and click **OK**.</span></span>  
  
6.  <span data-ttu-id="ca2c2-192">右键单击**Orchestration**单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-192">Right click the **Orchestration** and click **Start**.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="ca2c2-193">运行示例</span><span class="sxs-lookup"><span data-stu-id="ca2c2-193">To run the sample</span></span>  
  
1.  <span data-ttu-id="ca2c2-194">启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-194">Start the orchestration.</span></span>  
  
2.  <span data-ttu-id="ca2c2-195">将消息放置到 MQSeries 队列中，已将接收位置配置为从此队列进行读取。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-195">Put messages into the MQSeries queue from which you have configured the receive location to read.</span></span>  
  
3.  <span data-ttu-id="ca2c2-196">在 WebSphere MQ Explorer 中查看发送队列中的消息，已将发送端口配置为向此队列发送消息。</span><span class="sxs-lookup"><span data-stu-id="ca2c2-196">View the messages in WebSphere MQ Explorer in the send queue to which you have configured the send port to send messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca2c2-197">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca2c2-197">See Also</span></span>  
 [<span data-ttu-id="ca2c2-198">MQSeries 适配器示例</span><span class="sxs-lookup"><span data-stu-id="ca2c2-198">MQSeries Adapter Samples</span></span>](../core/mqseries-adapter-samples.md)