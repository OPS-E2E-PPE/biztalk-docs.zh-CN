---
title: 演练： 创建 BizTalk 应用程序使用 MQSeries 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBM WebSphere MQ queues
- MQSeries adapters, tutorial
- MQSeries adapters, testing
- tutorials, MQSeries adapters
- MQSeries adapters, IBM WebSphere MQ queues
- testing, MQSeries adapters
- MQSeries adapters, queues
- configuring [MQSeries adapters], tutorial
ms.assetid: e9e169e4-d41c-4e5d-b165-7bd36b481f24
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8c086c69dee4318b9ab15f8746291594a815870
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024523"
---
# <a name="walkthrough-creating-a-biztalk-application-that-uses-the-mqseries-adapter"></a><span data-ttu-id="1fd4e-102">演练： 创建使用 MQSeries 适配器的 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="1fd4e-102">Walkthrough: Creating a BizTalk Application That Uses the MQSeries Adapter</span></span>
<span data-ttu-id="1fd4e-103">本部分将指导您创建使用 MQSeries 适配器的简单 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-103">This section takes you through creating a simple Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application that uses the MQSeries adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1fd4e-104">该应用程序假定您已在安装 BizTalk Server 的计算机上安装了 IBM WebSphere MQ（面向 Windows 平台的服务器组件）。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-104">The application assumes that you have installed the IBM WebSphere MQ, server component for Windows platforms on the same computer as BizTalk Server.</span></span> <span data-ttu-id="1fd4e-105">并假定您尚未创建任何发送端口或接收位置。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-105">It also assumes that you have not yet created any send ports or receive locations.</span></span> <span data-ttu-id="1fd4e-106">如果已存在发送端口或接收位置，请在执行以下步骤时替换相应的名称。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-106">If you have existing send ports or receive locations, substitute appropriate names when you work through the steps.</span></span>  
  
 <span data-ttu-id="1fd4e-107">该应用程序是一个简单的基于内容的路由应用程序，仅使用一个接收位置和一个发送端口。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-107">The application is a simple content-based routing application using only a receive location and a send port.</span></span> <span data-ttu-id="1fd4e-108">接收位置从 IBM WebSphere MQ 队列读取消息。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-108">The receive location reads from an IBM WebSphere MQ queue.</span></span> <span data-ttu-id="1fd4e-109">发送端口从接收位置获取消息，然后将其发送到其他 IBM WebSphere MQ 队列。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-109">The send port takes the message from the receive location and sends it to a different IBM WebSphere MQ queue.</span></span>  
  
 <span data-ttu-id="1fd4e-110">若要创建该应用程序，必须创建 IBM WebSphere MQ 队列，设置 BizTalk Server 接收位置和发送端口，启动发送端口并启用接收位置，并在队列中放入测试消息。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-110">To create the application, you have to create the IBM WebSphere MQ queues, set up the BizTalk Server receive location and send port, start the send port and enable the receive location, and put a test message in the queue.</span></span>  
  
 <span data-ttu-id="1fd4e-111">如果您具有安装 IBM WebSphere MQ 所需的权限，可以通过适配器对话框创建 IBM WebSphere MQ 队列，并可以跳过下一过程。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-111">If you have the required permissions to the IBM WebSphere MQ installation, you can create the IBM WebSphere MQ queues through the adapter dialog boxes, and can skip the next procedure.</span></span> <span data-ttu-id="1fd4e-112">如果您没有这样的访问权限，可以使用 IBM WebSphere MQ Explorer（IBM WebSphere MQ 浏览器，面向 Windows 平台的客户端组件）来创建队列。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-112">If you do not have such access, you can create the queues using the IBM WebSphere MQ, client components for Windows platforms Explorer.</span></span> <span data-ttu-id="1fd4e-113">若要通过 IBM WebSphere MQ Explorer（IBM WebSphere MQ 浏览器）管理单元创建队列，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-113">To create the queues through the IBM WebSphere MQ Explorer snap-in, perform the following procedure.</span></span>  
  
## <a name="to-create-the-ibm-websphere-mq-queues-through-the-ibm-websphere-mq-explorer"></a><span data-ttu-id="1fd4e-114">通过 IBM WebSphere MQ Explorer（IBM WebSphere MQ 浏览器）创建 IBM WebSphere MQ 队列</span><span class="sxs-lookup"><span data-stu-id="1fd4e-114">To create the IBM WebSphere MQ queues through the IBM WebSphere MQ Explorer</span></span>  
 <span data-ttu-id="1fd4e-115">按照以下步骤，通过 IBM WebSphere MQ Explorer（IBM WebSphere MQ 浏览器）创建 IBM WebSphere MQ 队列：</span><span class="sxs-lookup"><span data-stu-id="1fd4e-115">Follow these steps to create the IBM WebSphere MQ queues through the IBM WebSphere MQ Explorer:</span></span>  
  
1. <span data-ttu-id="1fd4e-116">单击**启动**，依次指向**程序**，指向**IBM WebSphere MQ**，然后单击**WebSphere MQ Explorer**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-116">Click **Start**, point to **Programs**, point to **IBM WebSphere MQ**, and then click **WebSphere MQ Explorer**.</span></span>  
  
2. <span data-ttu-id="1fd4e-117">双击**队列管理器**，然后双击默认的队列管理器。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-117">Double-click **Queue Managers**, and then double-click the default queue manager.</span></span> <span data-ttu-id="1fd4e-118">默认的队列管理器通常命名为 **QM_ * * * < m a c h >* 其中*machine_name*是您的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-118">The default queue manager is typically named **QM_***<machine_name>* where *machine_name* is the name of your computer.</span></span>  
  
3. <span data-ttu-id="1fd4e-119">右键单击**队列**，依次指向**新建**，然后单击**本地队列**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-119">Right-click **Queues**, point to **New**, and then click **Local Queue**.</span></span>  
  
4. <span data-ttu-id="1fd4e-120">在中**创建本地队列**对话框中**队列名称**，类型**BTStoMQS**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-120">In **Create Local Queue** dialog box, in **Queue Name**, type **BTStoMQS**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="1fd4e-121">右键单击**队列**，依次指向**新建**，然后单击**本地队列**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-121">Right-click **Queues**, point to **New**, and then click **Local Queue**.</span></span>  
  
6. <span data-ttu-id="1fd4e-122">在中**创建本地队列**对话框中**队列名称**，类型**MQStoBTS**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-122">In **Create Local Queue** dialog box, in **Queue Name**, type **MQStoBTS**, and then click **OK**.</span></span>  
  
   <span data-ttu-id="1fd4e-123">以下步骤将创建接收位置和发送端口，然后启动该发送端口并启用该接收位置。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-123">The next steps create the receive location and the send port, and start the send port and enable the receive location.</span></span> <span data-ttu-id="1fd4e-124">还将创建 IBM WebSphere MQ 队列。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-124">They also create the IBM WebSphere MQ queues.</span></span>  
  
## <a name="to-create-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="1fd4e-125">创建接收位置和 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="1fd4e-125">To create the receive location and the MQSeries queue</span></span>  
 <span data-ttu-id="1fd4e-126">按照以下步骤创建接收位置和 MQSeries 队列：</span><span class="sxs-lookup"><span data-stu-id="1fd4e-126">Follow these steps to create the receive location and the MQSeries queue:</span></span>  
  
1.  <span data-ttu-id="1fd4e-127">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开默认值应用程序 (**BizTalk Application 1**默认情况下)。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-127">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the default application (**BizTalk Application 1** by default).</span></span>  
  
2.  <span data-ttu-id="1fd4e-128">右键单击**接收端口**节点中，单击**新建**，然后选择**单向端口**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-128">Right-click the **Receive Ports** node, click **New**, and select **One-Way Port**.</span></span>  
  
3.  <span data-ttu-id="1fd4e-129">在中**接收端口属性**对话框中**名称**框中，键入**MQStoBTS**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-129">In the **Receive Port Properties** dialog box, in the **Name** box, type **MQStoBTS**.</span></span>  
  
4.  <span data-ttu-id="1fd4e-130">在左窗格中，单击**接收位置**，然后在右窗格中，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-130">In the left pane, click **Receive Locations**, and in the right pane, click **New**.</span></span>  
  
5.  <span data-ttu-id="1fd4e-131">在中**接收位置属性**对话框中**名称**框中，键入**MQStoBTS**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-131">In the **Receive Location Properties** dialog box, in the **Name** box, type **MQStoBTS**.</span></span>  
  
6.  <span data-ttu-id="1fd4e-132">选择**MQSeries**下拉列表中下一步**类型**选项。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-132">Select **MQSeries** from the drop-down list next to the **Type** option.</span></span>  
  
7.  <span data-ttu-id="1fd4e-133">在中**传输**部分中，单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-133">In the **Transport** section, click **Configure**.</span></span>  
  
8.  <span data-ttu-id="1fd4e-134">在中**MQSeries 传输属性**对话框中**轮询间隔**框中，键入**1**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-134">In the **MQSeries Transport Properties** dialog box, in the **Polling Interval** box, type **1**.</span></span>  
  
9. <span data-ttu-id="1fd4e-135">在中**队列定义**框中，单击省略号 (**...**) 按钮。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-135">In the **Queue Definition** box, click the ellipsis (**…**) button.</span></span>  
  
10. <span data-ttu-id="1fd4e-136">在中**队列定义**对话框中**服务器名称**框中，键入您的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-136">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
11. <span data-ttu-id="1fd4e-137">在中**队列管理器**框中，选择默认的队列管理器。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-137">In the **Queue Manager** box, select the default queue manager.</span></span>  
  
12. <span data-ttu-id="1fd4e-138">在中**队列**框中，键入**MQStoBTS**，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-138">In the **Queue** box, type **MQStoBTS**, and then click **Export**.</span></span>  
  
13. <span data-ttu-id="1fd4e-139">在**导出**对话框中，单击**Create Queue**，然后单击**确定**并**确定**再次以返回到**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-139">In the **Export** dialog box, click **Create Queue**,and then click **OK** and **OK** again to return to the **Receive Location Properties** dialog box.</span></span>  
  
14. <span data-ttu-id="1fd4e-140">在中**接收处理程序**框中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-140">In the **Receive Handler** box, select **BizTalkServerApplication**.</span></span>  
  
15. <span data-ttu-id="1fd4e-141">在中**接收管道**框中，选择**PassThruReceive**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-141">In the **Receive Pipeline** box, select **PassThruReceive**.</span></span>  
  
16. <span data-ttu-id="1fd4e-142">单击**确定**以应用更改。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-142">Click **OK** to apply changes.</span></span>  
  
## <a name="to-create-the-send-port-and-the-mqseries-queue"></a><span data-ttu-id="1fd4e-143">创建发送端口和 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="1fd4e-143">To create the send port and the MQSeries queue</span></span>  
 <span data-ttu-id="1fd4e-144">按照以下步骤创建发送端口和 MQSeries 队列：</span><span class="sxs-lookup"><span data-stu-id="1fd4e-144">Follow these steps to create the send port and the MQSeries queue:</span></span>  
  
1.  <span data-ttu-id="1fd4e-145">右键单击**发送端口**，单击**新建**，然后选择**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-145">Right-click **Send Ports**, click **New**, and select **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="1fd4e-146">在中**发送端口属性**对话框中**名称**框中，键入**BTStoMQS。**</span><span class="sxs-lookup"><span data-stu-id="1fd4e-146">In the **Send Port Properties** dialog box, in the **Name** box, type **BTStoMQS.**</span></span>  
  
3.  <span data-ttu-id="1fd4e-147">选择**MQSeries**下拉列表中下一步**类型**选项。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-147">Select **MQSeries** from the drop-down list next to the **Type** option.</span></span>  
  
4.  <span data-ttu-id="1fd4e-148">在中**传输**部分中，单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-148">In the **Transport** section, click **Configure**.</span></span>  
  
5.  <span data-ttu-id="1fd4e-149">在中**MQSeries 传输属性**对话框中**队列定义**框中，单击省略号 (**...**) 按钮。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-149">In the **MQSeries Transport Properties** dialog box, in the **Queue Definition** box, click the ellipsis (**…**) button.</span></span>  
  
6.  <span data-ttu-id="1fd4e-150">在中**队列定义**对话框中**服务器名称**框中，键入您的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-150">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
7.  <span data-ttu-id="1fd4e-151">在中**队列管理器**框中，选择默认的队列管理器。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-151">In the **Queue Manager** box, select the default queue manager.</span></span>  
  
8.  <span data-ttu-id="1fd4e-152">在中**队列**框中，键入**BTStoMQS**，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-152">In the **Queue** box, type **BTStoMQS**, and then click **Export**.</span></span>  
  
9. <span data-ttu-id="1fd4e-153">在**导出**对话框中，单击**Create Queue**，然后单击**确定**并**确定**再次以返回到**发送端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-153">In the **Export** dialog box, click **Create Queue**, and then click **OK** and **OK** again to return to the **Send Port Properties** dialog box.</span></span>  
  
10. <span data-ttu-id="1fd4e-154">在中**发送管道**框中，选择**PassThruTransmit**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-154">In the **Send Pipeline** box, select **PassThruTransmit**.</span></span>  
  
11. <span data-ttu-id="1fd4e-155">单击此项可选择**筛选器**在左窗格中，然后在右窗格中配置筛选器选项。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-155">Click to select **Filters** in the left pane, and then configure filter options in the right pane.</span></span>  
  
12. <span data-ttu-id="1fd4e-156">在中**属性**下拉列表中，选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-156">In the **Property** drop-down list, select **BTS.ReceivePortName**.</span></span>  
  
13. <span data-ttu-id="1fd4e-157">在中**值**框中，键入**MQStoBTS**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-157">In the **Value** box, type **MQStoBTS**.</span></span>  
  
14. <span data-ttu-id="1fd4e-158">单击**确定**以应用更改。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-158">Click **OK** to apply changes.</span></span>  
  
## <a name="to-enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="1fd4e-159">若要启用接收位置并启动发送端口</span><span class="sxs-lookup"><span data-stu-id="1fd4e-159">To enable the receive location and start the send port</span></span>  
 <span data-ttu-id="1fd4e-160">请遵循以下步骤来启用接收位置和启动发送端口：</span><span class="sxs-lookup"><span data-stu-id="1fd4e-160">Follow these steps to enable the receive location and start the send port:</span></span>  
  
1. <span data-ttu-id="1fd4e-161">右键单击**MQStoBTS**接收位置，然后依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-161">Right-click the **MQStoBTS** receive location, and then click **Enable**.</span></span>  
  
2. <span data-ttu-id="1fd4e-162">右键单击**BTStoMQS**发送端口，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-162">Right-click the **BTStoMQS** send port, and then click **Start**.</span></span>  
  
   <span data-ttu-id="1fd4e-163">下一步将通过向接收队列发送测试消息来测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-163">The next step is to test the application by sending a test message to the receive queue.</span></span>  
  
## <a name="to-test-the-application"></a><span data-ttu-id="1fd4e-164">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="1fd4e-164">To test the application</span></span>  
 <span data-ttu-id="1fd4e-165">按照以下步骤来测试应用程序：</span><span class="sxs-lookup"><span data-stu-id="1fd4e-165">Follow these steps to test the application:</span></span>  
  
1. <span data-ttu-id="1fd4e-166">单击**启动**，依次指向**程序**，指向**IBM WebSphere MQ**，然后单击**WebSphere MQ Explorer**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-166">Click **Start**, point to **Programs**, point to **IBM WebSphere MQ**, and then click **WebSphere MQ Explorer**.</span></span>  
  
2. <span data-ttu-id="1fd4e-167">右键单击**MQStoBTS**，然后单击**放置测试消息**。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-167">Right-click **MQStoBTS**, and then click **Put Test Message**.</span></span>  
  
3. <span data-ttu-id="1fd4e-168">在中**消息数据**框中，键入测试消息。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-168">In the **Message Data** box, type a test message.</span></span> <span data-ttu-id="1fd4e-169">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-169">Click **OK**.</span></span>  
  
   <span data-ttu-id="1fd4e-170">输入数据后**当前深度**有关**MQStoBTS**队列是一 (1)。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-170">After you enter the data, the **Current Depth** for the **MQStoBTS** queue is one (1).</span></span> <span data-ttu-id="1fd4e-171">当应用程序处理消息时，计数将返回到零 (0) 和**当前深度**有关**BTStoMQS**变为一 （1)。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-171">When the application processes the message, the count returns to zero (0) and the **Current Depth** for **BTStoMQS** becomes one (1).</span></span> <span data-ttu-id="1fd4e-172">您还可以查看消息的内容。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-172">You can also view the content of the message.</span></span>  
  
## <a name="to-view-the-message"></a><span data-ttu-id="1fd4e-173">若要查看消息</span><span class="sxs-lookup"><span data-stu-id="1fd4e-173">To view the message</span></span>  
 <span data-ttu-id="1fd4e-174">请遵循以下步骤查看消息：</span><span class="sxs-lookup"><span data-stu-id="1fd4e-174">Follow these steps to view the message:</span></span>  
  
1.  <span data-ttu-id="1fd4e-175">双击**BTStoMQS**队列。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-175">Double-click the **BTStoMQS** queue.</span></span>  
  
2.  <span data-ttu-id="1fd4e-176">双击该消息，并选择**数据**工作表。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-176">Double-click the message, and then select the **Data** sheet.</span></span> <span data-ttu-id="1fd4e-177">您可以查看中的消息的文本**消息数据**框。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-177">You can view the text of the message in the **Message Data** box.</span></span>  
  
3.  <span data-ttu-id="1fd4e-178">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="1fd4e-178">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fd4e-179">请参阅</span><span class="sxs-lookup"><span data-stu-id="1fd4e-179">See Also</span></span>  
 <span data-ttu-id="1fd4e-180">[MQSeries 适配器是什么？](../core/what-is-the-mqseries-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="1fd4e-180">[What Is the MQSeries Adapter?](../core/what-is-the-mqseries-adapter.md) </span></span>  
 [<span data-ttu-id="1fd4e-181">MQSeries 适配器的体系结构</span><span class="sxs-lookup"><span data-stu-id="1fd4e-181">MQSeries Adapter Architecture</span></span>](../core/mqseries-adapter-architecture.md)