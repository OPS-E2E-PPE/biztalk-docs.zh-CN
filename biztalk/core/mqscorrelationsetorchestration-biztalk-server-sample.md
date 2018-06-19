---
title: MQSCorrelationSetOrchestration （BizTalk Server 示例） |Microsoft 文档
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
ms.openlocfilehash: 75ac63fe0fee593f927e854ce425ff7f631f9475
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974979"
---
# <a name="mqscorrelationsetorchestration-biztalk-server-sample"></a><span data-ttu-id="d91e0-102">MQSCorrelationSetOrchestration（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="d91e0-102">MQSCorrelationSetOrchestration (BizTalk Server Sample)</span></span>
<span data-ttu-id="d91e0-103">MQSCorrelationSetOrchestration 示例演示如何使用 MQSeries 相关标识符将发送至 MQSeries 队列的消息重新与正在运行的业务流程关联。</span><span class="sxs-lookup"><span data-stu-id="d91e0-103">The MQSCorrelationSetOrchestration sample demonstrates how to use the MQSeries correlation identifier for correlating messages sent to an MQSeries queue back to a running orchestration.</span></span> <span data-ttu-id="d91e0-104">业务流程设置 MQSeries 相关标识符和消息使用的标识符值**MQMD_CorrelId**和**MQMD_MsgID**属性。</span><span class="sxs-lookup"><span data-stu-id="d91e0-104">The orchestration sets the MQSeries correlation identifier and message identifier values using the **MQMD_CorrelId** and **MQMD_MsgID** properties.</span></span> <span data-ttu-id="d91e0-105">MQSeries 队列管理器将 MessageID 值复制到消息的 CorrelationID 属性。</span><span class="sxs-lookup"><span data-stu-id="d91e0-105">The MQSeries Queue Manager copies the MessageID value to the CorrelationID property of the message.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d91e0-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="d91e0-106">Prerequisites</span></span>  
 <span data-ttu-id="d91e0-107">此示例假定已在你运行的同一服务器上安装了 IBM WebSphere MQSeries [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d91e0-107">This sample assumes that you have installed IBM WebSphere MQSeries on the same server that you are running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="d91e0-108">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="d91e0-108">What This Sample Does</span></span>  
 <span data-ttu-id="d91e0-109">本示例将演示如何在发送至 IBM WebSphere MQSeries 服务器的消息中设置消息标识符和相关标识符。</span><span class="sxs-lookup"><span data-stu-id="d91e0-109">This sample illustrates how to set a message identifier and correlation identifier in a message sent to an IBM WebSphere MQSeries Server.</span></span> <span data-ttu-id="d91e0-110">这是一种可用于将消息重新与正在运行的业务流程实例关联的方法。</span><span class="sxs-lookup"><span data-stu-id="d91e0-110">This is one method that can be used to correlate a message back to a running orchestration instance.</span></span> <span data-ttu-id="d91e0-111">当 MQSeries 队列管理器收到消息时，它会将 MessageID 值复制到消息的 CorrelationID 属性。</span><span class="sxs-lookup"><span data-stu-id="d91e0-111">When the MQSeries Queue Manager receives the message it copies the MessageID value to the CorrelationID property of the message.</span></span> <span data-ttu-id="d91e0-112">此 CorrelationID (**MQMD_CorrelId**) 然后用于在业务流程将响应消息上 MQSeries 与用来将消息发送到 MQSeries 的实例相关联。</span><span class="sxs-lookup"><span data-stu-id="d91e0-112">This CorrelationID (**MQMD_CorrelId**) is then used in the orchestration to associate the response message on MQSeries with the instance used to send messages to MQSeries.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="d91e0-113">本示例旨在如何以及为何</span><span class="sxs-lookup"><span data-stu-id="d91e0-113">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="d91e0-114">本示例将演示一个方案，在该方案中可以将业务流程正在处理的文档发送至 MQSeries 队列（可能用于其他处理），然后返回正在运行的业务流程。</span><span class="sxs-lookup"><span data-stu-id="d91e0-114">This sample illustrates a scenario in which a document that is being processed by an orchestration can be sent to an MQSeries queue (presumably for additional processing) and returned back to the running orchestration.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="d91e0-115">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="d91e0-115">Where to Find This Sample</span></span>  
 <span data-ttu-id="d91e0-116">*\<示例路径\>* \AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestration</span><span class="sxs-lookup"><span data-stu-id="d91e0-116">*\<Samples Path\>* \AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestration</span></span>  
  
 <span data-ttu-id="d91e0-117">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="d91e0-117">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="d91e0-118">**文件**</span><span class="sxs-lookup"><span data-stu-id="d91e0-118">**File**</span></span>|<span data-ttu-id="d91e0-119">**Description**</span><span class="sxs-lookup"><span data-stu-id="d91e0-119">**Description**</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="d91e0-120">**MQSCorrelationSetOrchestration.btproj，**</span><span class="sxs-lookup"><span data-stu-id="d91e0-120">**MQSCorrelationSetOrchestration.btproj,**</span></span><br /><br /> <span data-ttu-id="d91e0-121">**MQSCorrelationSetOrchestration.sln**</span><span class="sxs-lookup"><span data-stu-id="d91e0-121">**MQSCorrelationSetOrchestration.sln**</span></span>|<span data-ttu-id="d91e0-122">应用程序的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="d91e0-122">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="d91e0-123">**MQSCorrelationSetOrchestration.odx**</span><span class="sxs-lookup"><span data-stu-id="d91e0-123">**MQSCorrelationSetOrchestration.odx**</span></span>|<span data-ttu-id="d91e0-124">应用程序的业务流程。</span><span class="sxs-lookup"><span data-stu-id="d91e0-124">The orchestration of the application.</span></span>|  
|<span data-ttu-id="d91e0-125">**MQSCorrelationSetOrchestration.snk**</span><span class="sxs-lookup"><span data-stu-id="d91e0-125">**MQSCorrelationSetOrchestration.snk**</span></span>|<span data-ttu-id="d91e0-126">强命名密钥文件。</span><span class="sxs-lookup"><span data-stu-id="d91e0-126">The strong naming key file.</span></span>|  
|<span data-ttu-id="d91e0-127">**Setup.bat**</span><span class="sxs-lookup"><span data-stu-id="d91e0-127">**Setup.bat**</span></span>|<span data-ttu-id="d91e0-128">生成并初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="d91e0-128">Builds and initializes this sample.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="d91e0-129">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="d91e0-129">How to Use This Sample</span></span>  
 <span data-ttu-id="d91e0-130">如果作为整个工作流的其中一个步骤，您需要将消息发送至 MQSeries 服务器，请引入本示例中采用的逻辑。</span><span class="sxs-lookup"><span data-stu-id="d91e0-130">Incorporate the logic employed in this sample if you need to send a message to MQSeries Server as one of the steps in overall workflow.</span></span>  
  
### <a name="to-create-the-mqseries-queue-through-the-websphere-mq-explorer"></a><span data-ttu-id="d91e0-131">通过 WebSphere MQ Explorer 创建 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="d91e0-131">To create the MQSeries queue through the WebSphere MQ Explorer</span></span>  
  
1.  <span data-ttu-id="d91e0-132">单击**启动**，指向**程序**，指向**IBM WebSphere MQ**，然后单击**WebSphere MQ 资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-132">Click **Start**, point to **Programs**, point to **IBM WebSphere MQ**, and then click **WebSphere MQ Explorer**.</span></span>  
  
2.  <span data-ttu-id="d91e0-133">双击**队列管理器**，然后双击默认队列管理器。</span><span class="sxs-lookup"><span data-stu-id="d91e0-133">Double-click **Queue Managers**, and then double-click the default queue manager.</span></span> <span data-ttu-id="d91e0-134">默认的队列管理器通常命名为**QM_ < machine_name >** 其中*machine_name*是你的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="d91e0-134">The default queue manager is typically named **QM_<machine_name>** where *machine_name* is the name of your computer.</span></span>  
  
3.  <span data-ttu-id="d91e0-135">右键单击**队列**，指向**新建**，然后单击**本地队列**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-135">Right-click **Queues**, point to **New**, and then click **Local Queue**.</span></span>  
  
4.  <span data-ttu-id="d91e0-136">在**创建本地队列**对话框中，在**队列名称**，键入"MQCorrelation"，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-136">In **Create Local Queue** dialog box, in **Queue Name**, type "MQCorrelation", and then click **OK**.</span></span>  
  
### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="d91e0-137">若要创建接收位置和 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="d91e0-137">To create the receive location and the MQSeries queue</span></span>  
  
1.  <span data-ttu-id="d91e0-138">打开 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="d91e0-138">Open the BizTalk Server Administration console.</span></span>  
  
2.  <span data-ttu-id="d91e0-139">展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d91e0-139">Expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the required application.</span></span>  
  
3.  <span data-ttu-id="d91e0-140">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-140">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="d91e0-141">在**单向接收端口属性**对话框中，在**名称**框中，键入"MQIn"，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-141">In the **One-way Receive Port Properties** dialog box, in the **Name** box type "MQIn" and click **OK**.</span></span>  
  
5.  <span data-ttu-id="d91e0-142">在左窗格中，单击**接收位置**选项卡上，并依次**新建**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-142">In the left pane, click **Receive Locations** tab, and then click **New**.</span></span>  
  
6.  <span data-ttu-id="d91e0-143">在**接收位置属性**对话框中，在**名称**框中，键入"MQIn"。</span><span class="sxs-lookup"><span data-stu-id="d91e0-143">In the **Receive Location Properties** dialog box, in the **Name** box, type "MQIn".</span></span>  
  
7.  <span data-ttu-id="d91e0-144">在**传输类型**框中，选择**MQSeries**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-144">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
8.  <span data-ttu-id="d91e0-145">在**接收处理程序**框中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-145">In the **Receive Handler** box, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="d91e0-146">在**接收管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-146">In the **Receive pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  
  
10. <span data-ttu-id="d91e0-147">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-147">Click **Configure**.</span></span>  
  
11. <span data-ttu-id="d91e0-148">在**MQSeries 传输属性**对话框中，在**轮询间隔**框中，键入"10"。</span><span class="sxs-lookup"><span data-stu-id="d91e0-148">In the **MQSeries Transport Properties** dialog box, in the **Polling Interval** box, type "10".</span></span>  
  
12. <span data-ttu-id="d91e0-149">在**队列定义**框中，单击省略号 （…） 按钮。</span><span class="sxs-lookup"><span data-stu-id="d91e0-149">In the **Queue Definition** box, click the ellipsis (…) button.</span></span>  
  
13. <span data-ttu-id="d91e0-150">在**队列定义**对话框中，在**服务器名称**框中，键入你的计算机名。</span><span class="sxs-lookup"><span data-stu-id="d91e0-150">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
14. <span data-ttu-id="d91e0-151">在**队列管理器**框中，选择默认的队列管理器。</span><span class="sxs-lookup"><span data-stu-id="d91e0-151">In the **Queue Manager** box, select the default queue manager.</span></span>  
  
15. <span data-ttu-id="d91e0-152">在**队列**框中，键入"MQCorrelation"，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-152">In the **Queue** box, type "MQCorrelation", and then click **Export**.</span></span>  
  
16. <span data-ttu-id="d91e0-153">在**导出**对话框中，单击**创建队列**，然后单击**确定**或**完成**之前已退出所有对话框。</span><span class="sxs-lookup"><span data-stu-id="d91e0-153">In the **Export** dialog box, click **Create Queue**, and then click**OK**or **Done** until you have exited all dialog boxes.</span></span>  
  
### <a name="to-create-the-send-port-to-mqseries"></a><span data-ttu-id="d91e0-154">创建到 MQSeries 的发送端口</span><span class="sxs-lookup"><span data-stu-id="d91e0-154">To create the send port to MQSeries</span></span>  
  
1.  <span data-ttu-id="d91e0-155">右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-155">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="d91e0-156">在**发送端口属性**对话框中，在**名称**框中，键入"MQOut"。</span><span class="sxs-lookup"><span data-stu-id="d91e0-156">In the **Send Port Properties** dialog box, in the **Name** box, type "MQOut".</span></span>  
  
3.  <span data-ttu-id="d91e0-157">在**传输类型**框中，选择**MQSeries**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-157">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
4.  <span data-ttu-id="d91e0-158">在**发送管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-158">In the **Send pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span></span>  
  
5.  <span data-ttu-id="d91e0-159">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-159">Click **Configure**.</span></span>  
  
6.  <span data-ttu-id="d91e0-160">在**MQSeries 传输属性**对话框中，在**队列定义**框中，单击省略号 （…） 按钮。</span><span class="sxs-lookup"><span data-stu-id="d91e0-160">In the **MQSeries Transport Properties** dialog box, in the **Queue Definition** box, click the ellipsis (…) button.</span></span>  
  
7.  <span data-ttu-id="d91e0-161">在**队列定义**对话框中，在**服务器名称**框中，键入你的计算机名。</span><span class="sxs-lookup"><span data-stu-id="d91e0-161">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
8.  <span data-ttu-id="d91e0-162">在**队列管理器**框中，选择默认的队列管理器。</span><span class="sxs-lookup"><span data-stu-id="d91e0-162">In the **Queue Manager** box, select the default queue manager.</span></span>  
  
9. <span data-ttu-id="d91e0-163">在**队列**框中，键入"MQCorrelation"，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-163">In the **Queue** box, type "MQCorrelation", and then click **OK**.</span></span>  
  
10. <span data-ttu-id="d91e0-164">单击**确定**之前已退出所有对话框。</span><span class="sxs-lookup"><span data-stu-id="d91e0-164">Click **OK** until you have exited all dialog boxes.</span></span>  
  
### <a name="to-enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="d91e0-165">若要启用接收位置和启动发送端口</span><span class="sxs-lookup"><span data-stu-id="d91e0-165">To enable the receive location and start the send port</span></span>  
  
1.  <span data-ttu-id="d91e0-166">在 BizTalk Server 管理控制台中，单击**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-166">In the BizTalk Server Administration console, click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="d91e0-167">在细节窗格中，右键单击**MQIn**接收位置，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-167">In the details pane, right-click the **MQIn** receive location and click **Enable**.</span></span>  
  
3.  <span data-ttu-id="d91e0-168">在细节窗格中，右键单击**MQOut**发送端口和单击**启动。**</span><span class="sxs-lookup"><span data-stu-id="d91e0-168">In the details pane, right-click the **MQOut** send port and click **Start.**</span></span>  
  
### <a name="to-create-the-folders-used-by-the-application"></a><span data-ttu-id="d91e0-169">创建应用程序使用的文件夹</span><span class="sxs-lookup"><span data-stu-id="d91e0-169">To create the folders used by the application</span></span>  
  
1.  <span data-ttu-id="d91e0-170">在你**c:\\** 驱动器中，创建名为"temp"如果不存在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d91e0-170">On your **C:\\** drive, create a folder named "temp" if it does not already exist.</span></span>  
  
2.  <span data-ttu-id="d91e0-171">下**C:\temp**目录中，创建名为"选取"和"Dropit"的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d91e0-171">Under the **C:\temp** directory, create folders named "Pickup" and "Dropit".</span></span>  
  
### <a name="building-and-deploying-this-sample"></a><span data-ttu-id="d91e0-172">生成和部署此示例</span><span class="sxs-lookup"><span data-stu-id="d91e0-172">Building and deploying this sample</span></span>  
  
1.  <span data-ttu-id="d91e0-173">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="d91e0-173">In a command window, navigate to the following folder:</span></span>  
  
     `<Samples Path>\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestration`  
  
2.  <span data-ttu-id="d91e0-174">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d91e0-174">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    1.  <span data-ttu-id="d91e0-175">为项目创建强名称密钥。</span><span class="sxs-lookup"><span data-stu-id="d91e0-175">Creates a strong name key for the project.</span></span>  
  
    2.  <span data-ttu-id="d91e0-176">编译并部署业务流程项目。</span><span class="sxs-lookup"><span data-stu-id="d91e0-176">Compiles and deploys the orchestration project.</span></span>  
  
    3.  <span data-ttu-id="d91e0-177">使用文件适配器创建发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="d91e0-177">Creates a send port and a receive port with the File adapter.</span></span>  
  
### <a name="bind-and-start-the-orchestration"></a><span data-ttu-id="d91e0-178">将绑定和启动业务流程</span><span class="sxs-lookup"><span data-stu-id="d91e0-178">Bind and start the Orchestration</span></span>  
  
1.  <span data-ttu-id="d91e0-179">在 BizTalk Server 管理控制台中，展开**业务流程**文件夹。</span><span class="sxs-lookup"><span data-stu-id="d91e0-179">In the BizTalk Server Administration console, expand the **Orchestrations** folder.</span></span>  
  
2.  <span data-ttu-id="d91e0-180">在细节窗格中，右键单击**MQSCorrelationSetOrchestration**业务流程，，然后单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-180">In the details pane, right-click the **MQSCorrelationSetOrchestration** orchestration, and then click **Bind**.</span></span>  
  
3.  <span data-ttu-id="d91e0-181">将业务流程端口绑定到下列发送端口和接收位置：</span><span class="sxs-lookup"><span data-stu-id="d91e0-181">Bind the orchestration ports to the following send ports and receive locations:</span></span>  
  
    |<span data-ttu-id="d91e0-182">**业务流程端口**</span><span class="sxs-lookup"><span data-stu-id="d91e0-182">**Orchestration Port**</span></span>|<span data-ttu-id="d91e0-183">**消息端口 / 接收位置**</span><span class="sxs-lookup"><span data-stu-id="d91e0-183">**Messaging Port / Receive Location**</span></span>|  
    |----------------------------|--------------------------------------------|  
    |<span data-ttu-id="d91e0-184">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="d91e0-184">FileReceivePort</span></span>|<span data-ttu-id="d91e0-185">MQSCorrelationSetOrchestration.FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="d91e0-185">MQSCorrelationSetOrchestration.FileReceivePort</span></span>|  
    |<span data-ttu-id="d91e0-186">MQSeriesResponseReceivePort</span><span class="sxs-lookup"><span data-stu-id="d91e0-186">MQSeriesResponseReceivePort</span></span>|<span data-ttu-id="d91e0-187">MQIn</span><span class="sxs-lookup"><span data-stu-id="d91e0-187">MQIn</span></span>|  
    |<span data-ttu-id="d91e0-188">MQSeriesRequestSendPort</span><span class="sxs-lookup"><span data-stu-id="d91e0-188">MQSeriesRequestSendPort</span></span>|<span data-ttu-id="d91e0-189">MQOut</span><span class="sxs-lookup"><span data-stu-id="d91e0-189">MQOut</span></span>|  
    |<span data-ttu-id="d91e0-190">FileSendPort</span><span class="sxs-lookup"><span data-stu-id="d91e0-190">FileSendPort</span></span>|<span data-ttu-id="d91e0-191">MQSCorrelationSetOrchestration.FileSendPort</span><span class="sxs-lookup"><span data-stu-id="d91e0-191">MQSCorrelationSetOrchestration.FileSendPort</span></span>|  
  
4.  <span data-ttu-id="d91e0-192">单击**主机**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-192">Click **Host**.</span></span>  
  
5.  <span data-ttu-id="d91e0-193">在**主机**框中，选择**BizTalkServerApplication**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-193">In the **Host** box, select **BizTalkServerApplication**, and click **OK**.</span></span>  
  
6.  <span data-ttu-id="d91e0-194">在**发送端口**，右键单击**MQSCorrelationSetOrchestration.FileSendPort**，然后选择**启动**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-194">In **Send Ports**, right-click **MQSCorrelationSetOrchestration.FileSendPort**, and then select **Start**.</span></span>  
  
7.  <span data-ttu-id="d91e0-195">在**接收位置**，右键单击**MQSCorrelationSetOrchestration.FileReceivePort** ，然后选择**启用**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-195">In **Receive Locations**, right-click **MQSCorrelationSetOrchestration.FileReceivePort** and then select **Enable**.</span></span>  
  
8.  <span data-ttu-id="d91e0-196">右键单击业务流程和单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-196">Right-click the orchestration and click **Start**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d91e0-197">启动业务流程还将自动登记该业务流程。</span><span class="sxs-lookup"><span data-stu-id="d91e0-197">Starting the orchestration also automatically enlists the orchestration.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="d91e0-198">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="d91e0-198">To test the application</span></span>  
  
1.  <span data-ttu-id="d91e0-199">放置到一个文件**C:\Temp\Pickup**文件夹。</span><span class="sxs-lookup"><span data-stu-id="d91e0-199">Put a file into the **C:\Temp\Pickup** folder.</span></span>  
  
2.  <span data-ttu-id="d91e0-200">查看中的文件**C:\Temp\Dropit**文件夹。</span><span class="sxs-lookup"><span data-stu-id="d91e0-200">Examine the file in the **C:\Temp\Dropit** folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d91e0-201">如果禁用**MQIn**接收位置，你可以检查 WebSphere MQ 资源管理器中的消息，并查看是否设置的消息和关联的标识符。</span><span class="sxs-lookup"><span data-stu-id="d91e0-201">If you disable the **MQIn** receive location, you can examine the message in WebSphere MQ Explorer and see that the message and correlation identifiers are set.</span></span> <span data-ttu-id="d91e0-202">若要执行此操作，启动**WebSphere MQ 资源管理器**和检查消息放入**MQCorrelation**队列。</span><span class="sxs-lookup"><span data-stu-id="d91e0-202">To do this, launch the **WebSphere MQ Explorer** and examine the message placed in the **MQCorrelation** queue.</span></span> <span data-ttu-id="d91e0-203">上显示的消息和相关标识符**标识符**选项卡**消息属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="d91e0-203">The message and correlation identifiers are displayed on the **Identifiers** tab of the **Message properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d91e0-204">在生产方案中，您将希望为发送到 MQSeries 队列的每个消息分配一个唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="d91e0-204">In a production scenario, you will want to assign a unique ID for each message that is sent to the MQSeries queue.</span></span> <span data-ttu-id="d91e0-205">可以通过修改业务流程中的表达式形状完成该操作。</span><span class="sxs-lookup"><span data-stu-id="d91e0-205">This can be done by modifying the expression shape in the orchestration.</span></span> <span data-ttu-id="d91e0-206">更改以下行以将这些属性设置为唯一的 24 字节 ID：</span><span class="sxs-lookup"><span data-stu-id="d91e0-206">Change the following lines to set these properties to a unique 24 byte ID:</span></span>  
    >   
    >  <span data-ttu-id="d91e0-207">MQSeriesRequestSendMessageModified(MQSeries.MQMD_MsgId) = "111213141516171819202122232425262728293031323334";</span><span class="sxs-lookup"><span data-stu-id="d91e0-207">MQSeriesRequestSendMessageModified(MQSeries.MQMD_MsgId) = "111213141516171819202122232425262728293031323334";</span></span>  
    >   
    >  <span data-ttu-id="d91e0-208">MQSeriesRequestSendMessageModified(MQSeries.MQMD_CorrelId) = "111213141516171819202122232425262728293031323334";</span><span class="sxs-lookup"><span data-stu-id="d91e0-208">MQSeriesRequestSendMessageModified(MQSeries.MQMD_CorrelId) = "111213141516171819202122232425262728293031323334";</span></span>  
    >   
    >  <span data-ttu-id="d91e0-209">如果你想要设置的唯一 24 字节 ID，有关这些属性，请参阅明**创建唯一 24 字节 ID 的消息发送到 MQSeries**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-209">If you want to set a unique 24 byte ID for these properties see the section **To create a unique 24 byte ID for messages sent to MQSeries**.</span></span>  
  
### <a name="to-create-a-unique-24-byte-id-for-messages-sent-to-mqseries"></a><span data-ttu-id="d91e0-210">为发送到 MQSeries 的消息创建唯一的 24 字节 ID</span><span class="sxs-lookup"><span data-stu-id="d91e0-210">To create a unique 24 byte ID for messages sent to MQSeries</span></span>  
  
1.  <span data-ttu-id="d91e0-211">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中新建一个 C# 类库项目。</span><span class="sxs-lookup"><span data-stu-id="d91e0-211">Create a new C# class library project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="d91e0-212">将以下代码粘贴到该类的 .cs 文件中：</span><span class="sxs-lookup"><span data-stu-id="d91e0-212">Paste the following code into the .cs file for the class:</span></span>  
  
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
  
3.  <span data-ttu-id="d91e0-213">指定**默认命名空间**的**MQId**和**程序集名称**的**GetId**的项目属性**应用程序**页。</span><span class="sxs-lookup"><span data-stu-id="d91e0-213">Specify a **Default namespace** of **MQId** and an **Assembly name** of **GetId** on the project properties **Application** page.</span></span>  
  
4.  <span data-ttu-id="d91e0-214">指定要在项目属性对程序集签名的强名称密钥文件**签名**页上，然后生成项目。</span><span class="sxs-lookup"><span data-stu-id="d91e0-214">Specify a strong name key file to sign the assembly on the project properties **Signing** page and then build the project.</span></span>  
  
5.  <span data-ttu-id="d91e0-215">使用全局程序集缓存工具 (gacutil.exe) 编译的程序集加载到 GAC (gacutil /i \<*编译的 dll 文件的名称*\>)。</span><span class="sxs-lookup"><span data-stu-id="d91e0-215">Use the global assembly cache tool (gacutil.exe) to load the compiled assembly into the GAC (gacutil /i \<*name of compiled dll file*\>).</span></span>  
  
6.  <span data-ttu-id="d91e0-216">对于本示例，在 BizTalk 项目中添加对 GetId 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="d91e0-216">Add a reference to the GetId assembly in the BizTalk project for this sample.</span></span>  
  
7.  <span data-ttu-id="d91e0-217">向本示例中使用的业务流程中添加两个变量：</span><span class="sxs-lookup"><span data-stu-id="d91e0-217">Add two variables to the orchestration used in this sample:</span></span>  
  
    |<span data-ttu-id="d91e0-218">变量名（标识符）</span><span class="sxs-lookup"><span data-stu-id="d91e0-218">Variable name (Identifier)</span></span>|<span data-ttu-id="d91e0-219">类型</span><span class="sxs-lookup"><span data-stu-id="d91e0-219">Type</span></span>|  
    |----------------------------------|----------|  
    |<span data-ttu-id="d91e0-220">GetId</span><span class="sxs-lookup"><span data-stu-id="d91e0-220">GetId</span></span>|<span data-ttu-id="d91e0-221">MQId.GetId</span><span class="sxs-lookup"><span data-stu-id="d91e0-221">MQId.GetId</span></span>|  
    |<span data-ttu-id="d91e0-222">strGuid</span><span class="sxs-lookup"><span data-stu-id="d91e0-222">strGuid</span></span>|<span data-ttu-id="d91e0-223">System.String</span><span class="sxs-lookup"><span data-stu-id="d91e0-223">System.String</span></span>|  
  
8.  <span data-ttu-id="d91e0-224">将以下代码粘贴到本示例的业务流程中使用的表达式形状，该代码应该覆盖现有代码：</span><span class="sxs-lookup"><span data-stu-id="d91e0-224">Paste the following code into the expression shape used in the orchestration for this sample, this code should overwrite the existing code:</span></span>  
  
    ```  
    GetId = new MQId.GetId();  
    strGuid = GetId.getGuidstr();  
    MQSeriesRequestSendMessageModified = MQSeriesRequestSendMessage;  
    MQSeriesRequestSendMessageModified(MQSeries.MQMD_MsgId) = strGuid;  
    MQSeriesRequestSendMessageModified(MQSeries.MQMD_CorrelId) = strGuid;  
    ```  
  
9. <span data-ttu-id="d91e0-225">停止并移动到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中的业务流程（如果已部署该业务流程）。</span><span class="sxs-lookup"><span data-stu-id="d91e0-225">Stop and remove the orchestration in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console if it is already deployed.</span></span> <span data-ttu-id="d91e0-226">然后按照部分中的步骤**生成和部署此示例**，**绑定和开始业务流程**和**测试应用程序**。</span><span class="sxs-lookup"><span data-stu-id="d91e0-226">Then follow the steps in the sections **Building and deploying this sample**, **Bind and start the Orchestration** and **To test the application**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d91e0-227">使用此方法为发送到 MQSeries 的消息创建唯一的 24 字节 ID 并不能够百分百保证所有发送的消息的 ID 唯一，但出现重复消息 ID 的可能性非常低。</span><span class="sxs-lookup"><span data-stu-id="d91e0-227">Use of this method to create a unique 24 byte ID for messages sent to MQSeries does not 100% guarantee unique IDs for all messages sent but the probability of duplicate message IDs is very low.</span></span> <span data-ttu-id="d91e0-228">如果业务需要百分百保证消息 ID 不重复，则您将需要使用另一个自定义代码来确保此功能。</span><span class="sxs-lookup"><span data-stu-id="d91e0-228">If business needs require a 100% guarantee that no message IDs are duplicated then you will need to employ different custom code to ensure this functionality.</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="d91e0-229">本示例中使用的类或方法</span><span class="sxs-lookup"><span data-stu-id="d91e0-229">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="d91e0-230">本示例不显式使用任何类或方法。</span><span class="sxs-lookup"><span data-stu-id="d91e0-230">This sample does not make explicit use of any classes or methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d91e0-231">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d91e0-231">See Also</span></span>  
 <span data-ttu-id="d91e0-232">[使消息使用请求-答复关联](../core/correlating-messages-using-request-reply.md) </span><span class="sxs-lookup"><span data-stu-id="d91e0-232">[Correlating Messages Using Request-Reply](../core/correlating-messages-using-request-reply.md) </span></span>  
 [<span data-ttu-id="d91e0-233">MQSeries 适配器示例</span><span class="sxs-lookup"><span data-stu-id="d91e0-233">MQSeries Adapter Samples</span></span>](../core/mqseries-adapter-samples.md)