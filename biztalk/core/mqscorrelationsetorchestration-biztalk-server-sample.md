---
title: MQSCorrelationSetOrchestration （BizTalk Server 示例） |Microsoft Docs
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
ms.assetid: fcda65d0-e3ec-4ead-978d-3904903b8762
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d0057e9a9276de5eb3724f1af298822b03065a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011774"
---
# <a name="mqscorrelationsetorchestration-biztalk-server-sample"></a><span data-ttu-id="fb0e2-102">MQSCorrelationSetOrchestration（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="fb0e2-102">MQSCorrelationSetOrchestration (BizTalk Server Sample)</span></span>
<span data-ttu-id="fb0e2-103">MQSCorrelationSetOrchestration 示例演示如何使用 MQSeries 相关标识符将发送至 MQSeries 队列的消息重新与正在运行的业务流程关联。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-103">The MQSCorrelationSetOrchestration sample demonstrates how to use the MQSeries correlation identifier for correlating messages sent to an MQSeries queue back to a running orchestration.</span></span> <span data-ttu-id="fb0e2-104">业务流程设置 MQSeries 相关标识符和消息使用的标识符值**MQMD_CorrelId**并**MQMD_MsgID**属性。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-104">The orchestration sets the MQSeries correlation identifier and message identifier values using the **MQMD_CorrelId** and **MQMD_MsgID** properties.</span></span> <span data-ttu-id="fb0e2-105">MQSeries 队列管理器将 MessageID 值复制到消息的 CorrelationID 属性。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-105">The MQSeries Queue Manager copies the MessageID value to the CorrelationID property of the message.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="fb0e2-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="fb0e2-106">Prerequisites</span></span>  
 <span data-ttu-id="fb0e2-107">此示例假定已在正在运行的同一服务器上安装 IBM WebSphere MQSeries [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-107">This sample assumes that you have installed IBM WebSphere MQSeries on the same server that you are running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="fb0e2-108">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="fb0e2-108">What This Sample Does</span></span>  
 <span data-ttu-id="fb0e2-109">本示例将演示如何在发送至 IBM WebSphere MQSeries 服务器的消息中设置消息标识符和相关标识符。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-109">This sample illustrates how to set a message identifier and correlation identifier in a message sent to an IBM WebSphere MQSeries Server.</span></span> <span data-ttu-id="fb0e2-110">这是一种可用于将消息重新与正在运行的业务流程实例关联的方法。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-110">This is one method that can be used to correlate a message back to a running orchestration instance.</span></span> <span data-ttu-id="fb0e2-111">当 MQSeries 队列管理器收到消息时，它会将 MessageID 值复制到消息的 CorrelationID 属性。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-111">When the MQSeries Queue Manager receives the message it copies the MessageID value to the CorrelationID property of the message.</span></span> <span data-ttu-id="fb0e2-112">此 CorrelationID (**MQMD_CorrelId**) 然后使用在业务流程中将 MQSeries 上的响应消息与用来将消息发送到 MQSeries 的实例相关联。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-112">This CorrelationID (**MQMD_CorrelId**) is then used in the orchestration to associate the response message on MQSeries with the instance used to send messages to MQSeries.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="fb0e2-113">此示例设计方式和原因</span><span class="sxs-lookup"><span data-stu-id="fb0e2-113">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="fb0e2-114">本示例将演示一个方案，在该方案中可以将业务流程正在处理的文档发送至 MQSeries 队列（可能用于其他处理），然后返回正在运行的业务流程。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-114">This sample illustrates a scenario in which a document that is being processed by an orchestration can be sent to an MQSeries queue (presumably for additional processing) and returned back to the running orchestration.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="fb0e2-115">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="fb0e2-115">Where to Find This Sample</span></span>  
 <span data-ttu-id="fb0e2-116">*\<示例路径\>* \AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestration</span><span class="sxs-lookup"><span data-stu-id="fb0e2-116">*\<Samples Path\>* \AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestration</span></span>  

 <span data-ttu-id="fb0e2-117">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="fb0e2-117">The following table shows the files in this sample and describes their purpose.</span></span>  

|<span data-ttu-id="fb0e2-118">**File**</span><span class="sxs-lookup"><span data-stu-id="fb0e2-118">**File**</span></span>|<span data-ttu-id="fb0e2-119">**Description**</span><span class="sxs-lookup"><span data-stu-id="fb0e2-119">**Description**</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="fb0e2-120">**MQSCorrelationSetOrchestration.btproj，**</span><span class="sxs-lookup"><span data-stu-id="fb0e2-120">**MQSCorrelationSetOrchestration.btproj,**</span></span><br /><br /> <span data-ttu-id="fb0e2-121">**MQSCorrelationSetOrchestration.sln**</span><span class="sxs-lookup"><span data-stu-id="fb0e2-121">**MQSCorrelationSetOrchestration.sln**</span></span>|<span data-ttu-id="fb0e2-122">应用程序的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-122">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="fb0e2-123">**MQSCorrelationSetOrchestration.odx**</span><span class="sxs-lookup"><span data-stu-id="fb0e2-123">**MQSCorrelationSetOrchestration.odx**</span></span>|<span data-ttu-id="fb0e2-124">应用程序的业务流程。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-124">The orchestration of the application.</span></span>|  
|<span data-ttu-id="fb0e2-125">**MQSCorrelationSetOrchestration.snk**</span><span class="sxs-lookup"><span data-stu-id="fb0e2-125">**MQSCorrelationSetOrchestration.snk**</span></span>|<span data-ttu-id="fb0e2-126">强命名密钥文件。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-126">The strong naming key file.</span></span>|  
|<span data-ttu-id="fb0e2-127">**Setup.bat**</span><span class="sxs-lookup"><span data-stu-id="fb0e2-127">**Setup.bat**</span></span>|<span data-ttu-id="fb0e2-128">生成并初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-128">Builds and initializes this sample.</span></span>|  

## <a name="how-to-use-this-sample"></a><span data-ttu-id="fb0e2-129">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="fb0e2-129">How to Use This Sample</span></span>  
 <span data-ttu-id="fb0e2-130">如果作为整个工作流的其中一个步骤，您需要将消息发送至 MQSeries 服务器，请引入本示例中采用的逻辑。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-130">Incorporate the logic employed in this sample if you need to send a message to MQSeries Server as one of the steps in overall workflow.</span></span>  

### <a name="to-create-the-mqseries-queue-through-the-websphere-mq-explorer"></a><span data-ttu-id="fb0e2-131">通过 WebSphere MQ Explorer 创建 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="fb0e2-131">To create the MQSeries queue through the WebSphere MQ Explorer</span></span>  

1.  <span data-ttu-id="fb0e2-132">单击**启动**，依次指向**程序**，指向**IBM WebSphere MQ**，然后单击**WebSphere MQ Explorer**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-132">Click **Start**, point to **Programs**, point to **IBM WebSphere MQ**, and then click **WebSphere MQ Explorer**.</span></span>  

2.  <span data-ttu-id="fb0e2-133">双击**队列管理器**，然后双击默认的队列管理器。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-133">Double-click **Queue Managers**, and then double-click the default queue manager.</span></span> <span data-ttu-id="fb0e2-134">默认的队列管理器通常命名为**QM_ < m a c h >** 其中*machine_name*是您的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-134">The default queue manager is typically named **QM_<machine_name>** where *machine_name* is the name of your computer.</span></span>  

3.  <span data-ttu-id="fb0e2-135">右键单击**队列**，依次指向**新建**，然后单击**本地队列**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-135">Right-click **Queues**, point to **New**, and then click **Local Queue**.</span></span>  

4.  <span data-ttu-id="fb0e2-136">在中**创建本地队列**对话框中**队列名称**，键入"MQCorrelation"，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-136">In **Create Local Queue** dialog box, in **Queue Name**, type "MQCorrelation", and then click **OK**.</span></span>  

### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="fb0e2-137">创建接收位置和 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="fb0e2-137">To create the receive location and the MQSeries queue</span></span>  

1.  <span data-ttu-id="fb0e2-138">打开 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-138">Open the BizTalk Server Administration console.</span></span>  

2.  <span data-ttu-id="fb0e2-139">展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需的应用程序。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-139">Expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the required application.</span></span>  

3.  <span data-ttu-id="fb0e2-140">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-140">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  

4.  <span data-ttu-id="fb0e2-141">在中**单向接收端口属性**对话框中**名称**框中，键入"MQIn"，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-141">In the **One-way Receive Port Properties** dialog box, in the **Name** box type "MQIn" and click **OK**.</span></span>  

5.  <span data-ttu-id="fb0e2-142">在左窗格中，单击**接收位置**选项卡，然后依次**新建**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-142">In the left pane, click **Receive Locations** tab, and then click **New**.</span></span>  

6.  <span data-ttu-id="fb0e2-143">在中**接收位置属性**对话框中**名称**框中，键入"MQIn"。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-143">In the **Receive Location Properties** dialog box, in the **Name** box, type "MQIn".</span></span>  

7.  <span data-ttu-id="fb0e2-144">在中**传输类型**框中，选择**MQSeries**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-144">In the **Transport Type** box, select **MQSeries**.</span></span>  

8.  <span data-ttu-id="fb0e2-145">在中**接收处理程序**框中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-145">In the **Receive Handler** box, select **BizTalkServerApplication**.</span></span>  

9. <span data-ttu-id="fb0e2-146">在中**接收管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-146">In the **Receive pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  

10. <span data-ttu-id="fb0e2-147">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-147">Click **Configure**.</span></span>  

11. <span data-ttu-id="fb0e2-148">在中**MQSeries 传输属性**对话框中**轮询间隔**框中，键入"10"。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-148">In the **MQSeries Transport Properties** dialog box, in the **Polling Interval** box, type "10".</span></span>  

12. <span data-ttu-id="fb0e2-149">在中**队列定义**框中，单击省略号 （...） 按钮。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-149">In the **Queue Definition** box, click the ellipsis (…) button.</span></span>  

13. <span data-ttu-id="fb0e2-150">在中**队列定义**对话框中**服务器名称**框中，键入您的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-150">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  

14. <span data-ttu-id="fb0e2-151">在中**队列管理器**框中，选择默认的队列管理器。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-151">In the **Queue Manager** box, select the default queue manager.</span></span>  

15. <span data-ttu-id="fb0e2-152">在中**队列**框中，键入"MQCorrelation"，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-152">In the **Queue** box, type "MQCorrelation", and then click **Export**.</span></span>  

16. <span data-ttu-id="fb0e2-153">在中**导出**对话框中，单击**Create Queue**，然后单击**确定**或**完成**直到您退出所有对话框为止。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-153">In the **Export** dialog box, click **Create Queue**, and then click**OK**or **Done** until you have exited all dialog boxes.</span></span>  

### <a name="to-create-the-send-port-to-mqseries"></a><span data-ttu-id="fb0e2-154">创建到 MQSeries 的发送端口</span><span class="sxs-lookup"><span data-stu-id="fb0e2-154">To create the send port to MQSeries</span></span>  

1.  <span data-ttu-id="fb0e2-155">右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-155">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

2.  <span data-ttu-id="fb0e2-156">在中**发送端口属性**对话框中**名称**框中，键入"MQOut"。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-156">In the **Send Port Properties** dialog box, in the **Name** box, type "MQOut".</span></span>  

3.  <span data-ttu-id="fb0e2-157">在中**传输类型**框中，选择**MQSeries**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-157">In the **Transport Type** box, select **MQSeries**.</span></span>  

4.  <span data-ttu-id="fb0e2-158">在中**发送管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-158">In the **Send pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span></span>  

5.  <span data-ttu-id="fb0e2-159">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-159">Click **Configure**.</span></span>  

6.  <span data-ttu-id="fb0e2-160">在中**MQSeries 传输属性**对话框中**队列定义**框中，单击省略号 （...） 按钮。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-160">In the **MQSeries Transport Properties** dialog box, in the **Queue Definition** box, click the ellipsis (…) button.</span></span>  

7.  <span data-ttu-id="fb0e2-161">在中**队列定义**对话框中**服务器名称**框中，键入您的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-161">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  

8.  <span data-ttu-id="fb0e2-162">在中**队列管理器**框中，选择默认的队列管理器。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-162">In the **Queue Manager** box, select the default queue manager.</span></span>  

9. <span data-ttu-id="fb0e2-163">在中**队列**框中，键入"MQCorrelation"，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-163">In the **Queue** box, type "MQCorrelation", and then click **OK**.</span></span>  

10. <span data-ttu-id="fb0e2-164">单击**确定**直到您退出所有对话框为止。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-164">Click **OK** until you have exited all dialog boxes.</span></span>  

### <a name="to-enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="fb0e2-165">若要启用接收位置并启动发送端口</span><span class="sxs-lookup"><span data-stu-id="fb0e2-165">To enable the receive location and start the send port</span></span>  

1.  <span data-ttu-id="fb0e2-166">在 BizTalk Server 管理控制台中，单击**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-166">In the BizTalk Server Administration console, click **Receive Ports**.</span></span>  

2.  <span data-ttu-id="fb0e2-167">在细节窗格中，右键单击**MQIn**接收位置，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-167">In the details pane, right-click the **MQIn** receive location and click **Enable**.</span></span>  

3.  <span data-ttu-id="fb0e2-168">在细节窗格中，右键单击**MQOut**发送端口并单击**开始。**</span><span class="sxs-lookup"><span data-stu-id="fb0e2-168">In the details pane, right-click the **MQOut** send port and click **Start.**</span></span>  

### <a name="to-create-the-folders-used-by-the-application"></a><span data-ttu-id="fb0e2-169">创建应用程序使用的文件夹</span><span class="sxs-lookup"><span data-stu-id="fb0e2-169">To create the folders used by the application</span></span>  

1.  <span data-ttu-id="fb0e2-170">在你**c:\\** 驱动器中，创建名为"temp"如果尚不存在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-170">On your **C:\\** drive, create a folder named "temp" if it does not already exist.</span></span>  

2.  <span data-ttu-id="fb0e2-171">下**C:\temp**目录中，创建名为"Pickup"和"dropit 的文件夹"的文件夹。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-171">Under the **C:\temp** directory, create folders named "Pickup" and "Dropit".</span></span>  

### <a name="building-and-deploying-this-sample"></a><span data-ttu-id="fb0e2-172">生成和部署此示例</span><span class="sxs-lookup"><span data-stu-id="fb0e2-172">Building and deploying this sample</span></span>  

1.  <span data-ttu-id="fb0e2-173">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="fb0e2-173">In a command window, navigate to the following folder:</span></span>  

     `<Samples Path>\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestration`  

2.  <span data-ttu-id="fb0e2-174">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fb0e2-174">Run the file Setup.bat, which performs the following actions:</span></span>  

    1.  <span data-ttu-id="fb0e2-175">为项目创建强名称密钥。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-175">Creates a strong name key for the project.</span></span>  

    2.  <span data-ttu-id="fb0e2-176">编译并部署业务流程项目。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-176">Compiles and deploys the orchestration project.</span></span>  

    3.  <span data-ttu-id="fb0e2-177">使用文件适配器创建发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-177">Creates a send port and a receive port with the File adapter.</span></span>  

### <a name="bind-and-start-the-orchestration"></a><span data-ttu-id="fb0e2-178">绑定和启动业务流程</span><span class="sxs-lookup"><span data-stu-id="fb0e2-178">Bind and start the Orchestration</span></span>  

1.  <span data-ttu-id="fb0e2-179">在 BizTalk Server 管理控制台中，展开**业务流程**文件夹。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-179">In the BizTalk Server Administration console, expand the **Orchestrations** folder.</span></span>  

2.  <span data-ttu-id="fb0e2-180">在细节窗格中，右键单击**MQSCorrelationSetOrchestration**业务流程，并单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-180">In the details pane, right-click the **MQSCorrelationSetOrchestration** orchestration, and then click **Bind**.</span></span>  

3.  <span data-ttu-id="fb0e2-181">将业务流程端口绑定到下列发送端口和接收位置：</span><span class="sxs-lookup"><span data-stu-id="fb0e2-181">Bind the orchestration ports to the following send ports and receive locations:</span></span>  

    |<span data-ttu-id="fb0e2-182">**业务流程端口**</span><span class="sxs-lookup"><span data-stu-id="fb0e2-182">**Orchestration Port**</span></span>|<span data-ttu-id="fb0e2-183">**消息传送端口 / 接收位置**</span><span class="sxs-lookup"><span data-stu-id="fb0e2-183">**Messaging Port / Receive Location**</span></span>|  
    |----------------------------|--------------------------------------------|  
    |<span data-ttu-id="fb0e2-184">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="fb0e2-184">FileReceivePort</span></span>|<span data-ttu-id="fb0e2-185">MQSCorrelationSetOrchestration.FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="fb0e2-185">MQSCorrelationSetOrchestration.FileReceivePort</span></span>|  
    |<span data-ttu-id="fb0e2-186">MQSeriesResponseReceivePort</span><span class="sxs-lookup"><span data-stu-id="fb0e2-186">MQSeriesResponseReceivePort</span></span>|<span data-ttu-id="fb0e2-187">MQIn</span><span class="sxs-lookup"><span data-stu-id="fb0e2-187">MQIn</span></span>|  
    |<span data-ttu-id="fb0e2-188">MQSeriesRequestSendPort</span><span class="sxs-lookup"><span data-stu-id="fb0e2-188">MQSeriesRequestSendPort</span></span>|<span data-ttu-id="fb0e2-189">MQOut</span><span class="sxs-lookup"><span data-stu-id="fb0e2-189">MQOut</span></span>|  
    |<span data-ttu-id="fb0e2-190">FileSendPort</span><span class="sxs-lookup"><span data-stu-id="fb0e2-190">FileSendPort</span></span>|<span data-ttu-id="fb0e2-191">MQSCorrelationSetOrchestration.FileSendPort</span><span class="sxs-lookup"><span data-stu-id="fb0e2-191">MQSCorrelationSetOrchestration.FileSendPort</span></span>|  

4.  <span data-ttu-id="fb0e2-192">单击**主机**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-192">Click **Host**.</span></span>  

5.  <span data-ttu-id="fb0e2-193">在中**主机**框中，选择**BizTalkServerApplication**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-193">In the **Host** box, select **BizTalkServerApplication**, and click **OK**.</span></span>  

6.  <span data-ttu-id="fb0e2-194">在中**发送端口**，右键单击**MQSCorrelationSetOrchestration.FileSendPort**，然后选择**启动**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-194">In **Send Ports**, right-click **MQSCorrelationSetOrchestration.FileSendPort**, and then select **Start**.</span></span>  

7.  <span data-ttu-id="fb0e2-195">在中**接收位置**，右键单击**MQSCorrelationSetOrchestration.FileReceivePort** ，然后选择**启用**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-195">In **Receive Locations**, right-click **MQSCorrelationSetOrchestration.FileReceivePort** and then select **Enable**.</span></span>  

8.  <span data-ttu-id="fb0e2-196">右键单击该业务流程，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-196">Right-click the orchestration and click **Start**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="fb0e2-197">启动业务流程还将自动登记该业务流程。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-197">Starting the orchestration also automatically enlists the orchestration.</span></span>  

### <a name="to-test-the-application"></a><span data-ttu-id="fb0e2-198">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="fb0e2-198">To test the application</span></span>  

1.  <span data-ttu-id="fb0e2-199">Put 将文件放**C:\Temp\Pickup**文件夹。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-199">Put a file into the **C:\Temp\Pickup** folder.</span></span>  

2.  <span data-ttu-id="fb0e2-200">查看中的文件**C:\Temp\Dropit**文件夹。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-200">Examine the file in the **C:\Temp\Dropit** folder.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="fb0e2-201">如果禁用**MQIn**接收位置，您可以检查在 WebSphere MQ Explorer 中的消息，请参阅设置消息和相关标识符。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-201">If you disable the **MQIn** receive location, you can examine the message in WebSphere MQ Explorer and see that the message and correlation identifiers are set.</span></span> <span data-ttu-id="fb0e2-202">若要执行此操作，启动**WebSphere MQ Explorer**并查看放置在消息**MQCorrelation**队列。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-202">To do this, launch the **WebSphere MQ Explorer** and examine the message placed in the **MQCorrelation** queue.</span></span> <span data-ttu-id="fb0e2-203">消息和相关标识符显示在**标识符**选项卡**消息属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-203">The message and correlation identifiers are displayed on the **Identifiers** tab of the **Message properties** dialog box.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="fb0e2-204">在生产方案中，您将希望为发送到 MQSeries 队列的每个消息分配一个唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-204">In a production scenario, you will want to assign a unique ID for each message that is sent to the MQSeries queue.</span></span> <span data-ttu-id="fb0e2-205">可以通过修改业务流程中的表达式形状完成该操作。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-205">This can be done by modifying the expression shape in the orchestration.</span></span> <span data-ttu-id="fb0e2-206">更改以下行以将这些属性设置为唯一的 24 字节 ID：</span><span class="sxs-lookup"><span data-stu-id="fb0e2-206">Change the following lines to set these properties to a unique 24 byte ID:</span></span>  
    >   
    >  <span data-ttu-id="fb0e2-207">MQSeriesRequestSendMessageModified(MQSeries.MQMD_MsgId) = "111213141516171819202122232425262728293031323334";</span><span class="sxs-lookup"><span data-stu-id="fb0e2-207">MQSeriesRequestSendMessageModified(MQSeries.MQMD_MsgId) = "111213141516171819202122232425262728293031323334";</span></span>  
    >   
    >  <span data-ttu-id="fb0e2-208">MQSeriesRequestSendMessageModified(MQSeries.MQMD_CorrelId) = "111213141516171819202122232425262728293031323334";</span><span class="sxs-lookup"><span data-stu-id="fb0e2-208">MQSeriesRequestSendMessageModified(MQSeries.MQMD_CorrelId) = "111213141516171819202122232425262728293031323334";</span></span>  
    >   
    >  <span data-ttu-id="fb0e2-209">如果你想要设置唯一的 24 字节 ID，有关这些属性，请参阅明**创建唯一的 24 字节 ID 发送到 MQSeries 的消息**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-209">If you want to set a unique 24 byte ID for these properties see the section **To create a unique 24 byte ID for messages sent to MQSeries**.</span></span>  

### <a name="to-create-a-unique-24-byte-id-for-messages-sent-to-mqseries"></a><span data-ttu-id="fb0e2-210">为发送到 MQSeries 的消息创建唯一的 24 字节 ID</span><span class="sxs-lookup"><span data-stu-id="fb0e2-210">To create a unique 24 byte ID for messages sent to MQSeries</span></span>  

1. <span data-ttu-id="fb0e2-211">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中新建一个 C# 类库项目。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-211">Create a new C# class library project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  

2. <span data-ttu-id="fb0e2-212">将以下代码粘贴到该类的 .cs 文件中：</span><span class="sxs-lookup"><span data-stu-id="fb0e2-212">Paste the following code into the .cs file for the class:</span></span>  

   ```  
   using System;  
   using System.Collections.Generic;  
   using System.Text;  
   using System.Security.Cryptography;  

   namespace MQId  
   {[Serializable]  
       public class GetId  
       {  
           RNGCryptoServiceProvider randomCryptoString = new RNGCryptoServiceProvider();  

           public string getGuidstr()  
           {  
               byte[] newGuid = GetRandomData(24);  
               return ConvertToHex(newGuid);  
           }  

           private byte[] GetRandomData(int keySize)  
           {  
               byte[] randomData = new byte[keySize];  
               randomCryptoString.GetBytes(randomData);  
               return randomData;  
           }  

           private string ConvertToHex(byte[] key)  
           {  
               StringBuilder hexString = new StringBuilder();  
               for (int i = 0; i < key.Length; ++i)  
               {  
                   hexString.Append(String.Format("{0:X2}", key[i]));  
               }  
               return hexString.ToString();  
           }  
       }  
   }  
   ```  

3. <span data-ttu-id="fb0e2-213">指定**默认命名空间**的**MQId**和一个**程序集名称**的**GetId**的项目属性**应用程序**页。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-213">Specify a **Default namespace** of **MQId** and an **Assembly name** of **GetId** on the project properties **Application** page.</span></span>  

4. <span data-ttu-id="fb0e2-214">指定一个强名称密钥文件的项目属性为程序集签名**签名**页上，然后生成项目。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-214">Specify a strong name key file to sign the assembly on the project properties **Signing** page and then build the project.</span></span>  

5. <span data-ttu-id="fb0e2-215">使用全局程序集缓存工具 (gacutil.exe) 已编译的程序集加载到 GAC (gacutil /i \<*已编译的 dll 文件的名称*\>)。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-215">Use the global assembly cache tool (gacutil.exe) to load the compiled assembly into the GAC (gacutil /i \<*name of compiled dll file*\>).</span></span>  

6. <span data-ttu-id="fb0e2-216">对于本示例，在 BizTalk 项目中添加对 GetId 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-216">Add a reference to the GetId assembly in the BizTalk project for this sample.</span></span>  

7. <span data-ttu-id="fb0e2-217">向本示例中使用的业务流程中添加两个变量：</span><span class="sxs-lookup"><span data-stu-id="fb0e2-217">Add two variables to the orchestration used in this sample:</span></span>  


   | <span data-ttu-id="fb0e2-218">变量名（标识符）</span><span class="sxs-lookup"><span data-stu-id="fb0e2-218">Variable name (Identifier)</span></span> |     <span data-ttu-id="fb0e2-219">类型</span><span class="sxs-lookup"><span data-stu-id="fb0e2-219">Type</span></span>      |
   |----------------------------|---------------|
   |           <span data-ttu-id="fb0e2-220">GetId</span><span class="sxs-lookup"><span data-stu-id="fb0e2-220">GetId</span></span>            |  <span data-ttu-id="fb0e2-221">MQId.GetId</span><span class="sxs-lookup"><span data-stu-id="fb0e2-221">MQId.GetId</span></span>   |
   |          <span data-ttu-id="fb0e2-222">strGuid</span><span class="sxs-lookup"><span data-stu-id="fb0e2-222">strGuid</span></span>           | <span data-ttu-id="fb0e2-223">System.String</span><span class="sxs-lookup"><span data-stu-id="fb0e2-223">System.String</span></span> |


8. <span data-ttu-id="fb0e2-224">将以下代码粘贴到本示例的业务流程中使用的表达式形状，该代码应该覆盖现有代码：</span><span class="sxs-lookup"><span data-stu-id="fb0e2-224">Paste the following code into the expression shape used in the orchestration for this sample, this code should overwrite the existing code:</span></span>  

   ```  
   GetId = new MQId.GetId();  
   strGuid = GetId.getGuidstr();  
   MQSeriesRequestSendMessageModified = MQSeriesRequestSendMessage;  
   MQSeriesRequestSendMessageModified(MQSeries.MQMD_MsgId) = strGuid;  
   MQSeriesRequestSendMessageModified(MQSeries.MQMD_CorrelId) = strGuid;  
   ```  

9. <span data-ttu-id="fb0e2-225">停止并移动到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中的业务流程（如果已部署该业务流程）。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-225">Stop and remove the orchestration in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console if it is already deployed.</span></span> <span data-ttu-id="fb0e2-226">然后按照部分中的步骤**构建和部署此示例**，**绑定和启动业务流程**并**测试应用程序**。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-226">Then follow the steps in the sections **Building and deploying this sample**, **Bind and start the Orchestration** and **To test the application**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="fb0e2-227">使用此方法为发送到 MQSeries 的消息创建唯一的 24 字节 ID 并不能够百分百保证所有发送的消息的 ID 唯一，但出现重复消息 ID 的可能性非常低。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-227">Use of this method to create a unique 24 byte ID for messages sent to MQSeries does not 100% guarantee unique IDs for all messages sent but the probability of duplicate message IDs is very low.</span></span> <span data-ttu-id="fb0e2-228">如果业务需要百分百保证消息 ID 不重复，则您将需要使用另一个自定义代码来确保此功能。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-228">If business needs require a 100% guarantee that no message IDs are duplicated then you will need to employ different custom code to ensure this functionality.</span></span>  

## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="fb0e2-229">本示例中使用的类或方法</span><span class="sxs-lookup"><span data-stu-id="fb0e2-229">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="fb0e2-230">本示例不显式使用任何类或方法。</span><span class="sxs-lookup"><span data-stu-id="fb0e2-230">This sample does not make explicit use of any classes or methods.</span></span>  

## <a name="see-also"></a><span data-ttu-id="fb0e2-231">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb0e2-231">See Also</span></span>  
 <span data-ttu-id="fb0e2-232">[使用请求-答复相关消息](../core/correlating-messages-using-request-reply.md) </span><span class="sxs-lookup"><span data-stu-id="fb0e2-232">[Correlating Messages Using Request-Reply](../core/correlating-messages-using-request-reply.md) </span></span>  
 [<span data-ttu-id="fb0e2-233">MQSeries 适配器示例</span><span class="sxs-lookup"><span data-stu-id="fb0e2-233">MQSeries Adapter Samples</span></span>](../core/mqseries-adapter-samples.md)