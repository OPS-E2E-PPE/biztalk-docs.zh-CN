---
title: "SendMSMQMessage |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, examples
- examples, MSMQ adapters
ms.assetid: 398bc396-0c66-4d55-886a-0d9bdab6476f
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39fd92c3d017e9ee88fe60f14c8baf9cb0ff941d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sendmsmqmessage"></a><span data-ttu-id="fe454-102">SendMSMQMessage</span><span class="sxs-lookup"><span data-stu-id="fe454-102">SendMSMQMessage</span></span>
<span data-ttu-id="fe454-103">SendMSMQMessage 示例演示如何从基于 .NET 的应用程序向 MSMQ 端口发送消息。</span><span class="sxs-lookup"><span data-stu-id="fe454-103">The SendMSMQMessage sample demonstrates how to send a message to an MSMQ port from a .NET-based application.</span></span> <span data-ttu-id="fe454-104">它还提供有关如何配置 Microsoft 说明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为了使用 MSMQ 接收位置。</span><span class="sxs-lookup"><span data-stu-id="fe454-104">It also provides instructions about how to configure Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use an MSMQ receive location.</span></span>  
  
 <span data-ttu-id="fe454-105">应注意消息队列中的许多操作都是异步的。</span><span class="sxs-lookup"><span data-stu-id="fe454-105">You should be aware that many operations in Message Queuing are asynchronous.</span></span> <span data-ttu-id="fe454-106">也就是说，许多 MSMQ API 调用 (例如， **System.Messaging.MessageQueue.Send**) 返回到调用方完全完成请求的操作之前。</span><span class="sxs-lookup"><span data-stu-id="fe454-106">That is, many MSMQ API calls (for example, **System.Messaging.MessageQueue.Send**) return to the caller before the requested operation has fully completed.</span></span> <span data-ttu-id="fe454-107">MSMQ 提供了一种在操作完成之后将反馈传送到应用程序的机制。</span><span class="sxs-lookup"><span data-stu-id="fe454-107">MSMQ provides a mechanism to deliver feedback to the application after the operation has completed.</span></span> <span data-ttu-id="fe454-108">此机制涉及“管理队列”的使用。</span><span class="sxs-lookup"><span data-stu-id="fe454-108">This mechanism involves the use of an "Admin Queue."</span></span> <span data-ttu-id="fe454-109">MSMQ 将反馈以管理队列中的消息的形式返回。</span><span class="sxs-lookup"><span data-stu-id="fe454-109">MSMQ returns feedback in the form of a message in the Admin Queue.</span></span> <span data-ttu-id="fe454-110">MSMQ 将向其返回反馈的管理队列是在进行原始 MSMQ API 调用时指定的。</span><span class="sxs-lookup"><span data-stu-id="fe454-110">The Admin Queue to which MSMQ will return feedback is specified when the original MSMQ API call is made.</span></span> <span data-ttu-id="fe454-111">因此，举例来说，当发送消息使用**System.Messaging.MessageQueue.Send** API，应用程序可以指定管理队列的名称，通过使用**PROPID_M_ADMIN_QUEUE** message 属性对消息传递的调用中**System.Messaging.MessageQueue.Send**。</span><span class="sxs-lookup"><span data-stu-id="fe454-111">So, for example, when sending a message using the **System.Messaging.MessageQueue.Send** API, the application can specify the name of an Admin Queue by using the **PROPID_M_ADMIN_QUEUE** message property on the message passed in the call to **System.Messaging.MessageQueue.Send**.</span></span> <span data-ttu-id="fe454-112">即使应用程序可能会成功的返回代码在**System.Messaging.MessageQueue.Send**调用时，如果该消息的发送操作随后失败，MSMQ 将消息针对此效果写入指定的管理队列。</span><span class="sxs-lookup"><span data-stu-id="fe454-112">Even though the application may get a successful return code on the **System.Messaging.MessageQueue.Send** call, if the message send operation subsequently fails, MSMQ writes a message to that effect to the specified Admin Queue.</span></span> <span data-ttu-id="fe454-113">如果应用程序未指定管理队列，发送失败将导致丢失消息和捕获任何诊断-实际上，该消息消失但没有任何证据。</span><span class="sxs-lookup"><span data-stu-id="fe454-113">If the application does not specify an Admin Queue, the send failure results in the message being lost and no diagnostics captured — in effect, the message disappears without any evidence.</span></span> <span data-ttu-id="fe454-114">有大量的错误可能会导致这种情况，例如，执行非事务性的 MSMQ 中的情况下将发送到事务性队列。</span><span class="sxs-lookup"><span data-stu-id="fe454-114">There are a number of error situations in MSMQ that can cause this to happen, for example, doing a non-transactional send to a transactional queue.</span></span>  
  
 <span data-ttu-id="fe454-115">在此示例的上下文，很重要这段代码的调用中指定的事务类型**System.Messaging.MessageQueue.Send**是一致与为队列消息是指定的事务支持发送。</span><span class="sxs-lookup"><span data-stu-id="fe454-115">In the context of this sample, it is important that the code specify a transaction type in the call to **System.Messaging.MessageQueue.Send** that is consistent with the transaction support specified for the queue to which the message is sent.</span></span> <span data-ttu-id="fe454-116">如果未完成此和未管理员指定队列 （就是在此示例中这种情况），如果 MSMQ 放弃时，它还执行该操作没有指示发送的消息 （即，没有错误代码返回给应用程序事件日志中写入任何诊断依此类推)。</span><span class="sxs-lookup"><span data-stu-id="fe454-116">If this is not done and if no Admin Queue is specified (as is the case in this sample), then MSMQ discards the sent message with no indication that it has done so (that is, no error code returned to the application, no diagnostics written to the event log, and so on).</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="fe454-117">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="fe454-117">Where to Find This Sample</span></span>  
 <span data-ttu-id="fe454-118">\<示例路径 > \AdaptersUsage\SendMSMQMessage\\</span><span class="sxs-lookup"><span data-stu-id="fe454-118">\<Samples Path>\AdaptersUsage\SendMSMQMessage\\</span></span>  
  
 <span data-ttu-id="fe454-119">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="fe454-119">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="fe454-120">文件</span><span class="sxs-lookup"><span data-stu-id="fe454-120">Files</span></span>|<span data-ttu-id="fe454-121">Description</span><span class="sxs-lookup"><span data-stu-id="fe454-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fe454-122">App.ico、AssemblyInfo.cs、SendMSMQMessage.csproj、SendMSMQMessage.sln</span><span class="sxs-lookup"><span data-stu-id="fe454-122">App.ico, AssemblyInfo.cs, SendMSMQMessage.csproj, SendMSMQMessage.sln</span></span>|<span data-ttu-id="fe454-123">提供项目、 解决方案和简单图形应用程序，此示例的相关的文件。</span><span class="sxs-lookup"><span data-stu-id="fe454-123">Provide project, solution, and related files for the simple graphical application for this sample.</span></span>|  
|<span data-ttu-id="fe454-124">Form1.cs、Form1.resx</span><span class="sxs-lookup"><span data-stu-id="fe454-124">Form1.cs, Form1.resx</span></span>|<span data-ttu-id="fe454-125">为本示例的简单图形应用程序提供 Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].NET 源文件和表单文件。</span><span class="sxs-lookup"><span data-stu-id="fe454-125">Provide Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].NET source and form files for the simple graphical application for this sample.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="fe454-126">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="fe454-126">How to Use This Sample</span></span>  
 <span data-ttu-id="fe454-127">可以将本示例随附的简单图形应用程序中的代码用作以下过程的一个例子：将消息从诸如 Microsoft Office 之类的启用了 .NET 的应用程序、ASP.NET 页或其他地方发送到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 内的 MSMQ 接收位置。</span><span class="sxs-lookup"><span data-stu-id="fe454-127">You can use the code in the simple graphical application included with this sample as an example of how to send messages to MSMQ receive locations within [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] from .NET-enabled applications such as Microsoft Office, from ASP.NET pages, and so on.</span></span>  
  
## <a name="building-and-initializing-the-sample"></a><span data-ttu-id="fe454-128">生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="fe454-128">Building and Initializing the Sample</span></span>  
  
#### <a name="to-build-the-sample-executable"></a><span data-ttu-id="fe454-129">生成示例可执行文件</span><span class="sxs-lookup"><span data-stu-id="fe454-129">To build the sample executable</span></span>  
  
1.  <span data-ttu-id="fe454-130">使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开解决方案文件 SendMSMQMessage.sln。</span><span class="sxs-lookup"><span data-stu-id="fe454-130">Using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file SendMSMQMessage.sln.</span></span>  
  
2.  <span data-ttu-id="fe454-131">在“生成”  菜单上，单击“生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="fe454-131">On the **Build** menu, click **Build Solution**.</span></span>  
  
## <a name="configuring-biztalk-server-and-creating-the-msmq-queue"></a><span data-ttu-id="fe454-132">配置 BizTalk Server 和创建 MSMQ 队列</span><span class="sxs-lookup"><span data-stu-id="fe454-132">Configuring BizTalk Server and Creating the MSMQ Queue</span></span>  
 <span data-ttu-id="fe454-133">使用以下过程配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 并创建 MSMQ 队列以运行示例。</span><span class="sxs-lookup"><span data-stu-id="fe454-133">Use the following procedures to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and create the MSMQ queue for running the sample.</span></span>  
  
#### <a name="to-create-the-msmq-queue-in-windows-server-2008-r2-or-windows-server-2008-sp2"></a><span data-ttu-id="fe454-134">在 Windows Server 2008 R2 或 Windows Server 2008 SP2 中创建 MSMQ 队列的步骤</span><span class="sxs-lookup"><span data-stu-id="fe454-134">To create the MSMQ queue in Windows Server 2008 R2 or Windows Server 2008 SP2</span></span>  
  
1.  <span data-ttu-id="fe454-135">单击**启动**，右键单击**计算机**，然后单击**管理**。</span><span class="sxs-lookup"><span data-stu-id="fe454-135">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>  
  
2.  <span data-ttu-id="fe454-136">展开**功能**节点。</span><span class="sxs-lookup"><span data-stu-id="fe454-136">Expand the **Features** node.</span></span>  <span data-ttu-id="fe454-137">如果**消息队列**是未安装，请右键单击**功能**和选择**添加功能**。</span><span class="sxs-lookup"><span data-stu-id="fe454-137">If **Message Queuing** is not installed, right-click **Features** and select **Add Features**.</span></span>  <span data-ttu-id="fe454-138">检查**消息队列**，单击**下一步**，然后单击**安装**该系统上安装 MSMQ。</span><span class="sxs-lookup"><span data-stu-id="fe454-138">Check **Message Queuing**, click **Next**, and then click **Install** to install MSMQ on that system.</span></span>  
  
3.  <span data-ttu-id="fe454-139">展开**消息队列**节点。</span><span class="sxs-lookup"><span data-stu-id="fe454-139">Expand the **Message Queuing** node.</span></span>  
  
4.  <span data-ttu-id="fe454-140">右键单击**专用队列**节点，单击**新建**，然后单击**专用队列**。</span><span class="sxs-lookup"><span data-stu-id="fe454-140">Right-click the **Private Queues** node, click **New**, and then click **Private Queue**.</span></span>  
  
5.  <span data-ttu-id="fe454-141">下**队列名称**，输入`test`。</span><span class="sxs-lookup"><span data-stu-id="fe454-141">Under **Queue name**, enter `test`.</span></span> <span data-ttu-id="fe454-142">确保**事务**复选框处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="fe454-142">Ensure that the **Transactional** check box is selected.</span></span>  
  
6.  <span data-ttu-id="fe454-143">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="fe454-143">Click **OK**.</span></span>  
  
#### <a name="to-create-the-msmq-queue-in-windows-7-or-windows-vista-sp2"></a><span data-ttu-id="fe454-144">在 Windows 7 或 Windows Vista SP2 中创建 MSMQ 队列的步骤</span><span class="sxs-lookup"><span data-stu-id="fe454-144">To create the MSMQ queue in Windows 7 or Windows Vista SP2</span></span>  
  
1.  <span data-ttu-id="fe454-145">单击**启动**，右键单击**计算机**，然后单击**管理**。</span><span class="sxs-lookup"><span data-stu-id="fe454-145">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>  
  
2.  <span data-ttu-id="fe454-146">展开**服务和应用程序**，然后展开**消息队列**节点。</span><span class="sxs-lookup"><span data-stu-id="fe454-146">Expand **Services and Applications**, and then expand the **Message Queuing** node.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fe454-147">如果**消息队列**未安装在计算机上，转到**控制面板 > 程序 > 程序和功能**，然后选择**打开或关闭 Windows 功能**。</span><span class="sxs-lookup"><span data-stu-id="fe454-147">If **Message Queuing** is not installed in the computer, go to **Control Panel > Programs > Programs and Features**, and then select **Turn Windows features on or off**.</span></span> <span data-ttu-id="fe454-148">检查下的所有功能**Microsoft Message Queue (MSMQ) 服务器**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fe454-148">Check all the features under **Microsoft Message Queue (MSMQ) Server**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="fe454-149">右键单击**专用队列**节点，单击**新建**，然后单击**专用队列**。</span><span class="sxs-lookup"><span data-stu-id="fe454-149">Right-click the **Private Queues** node, click **New**, and then click **Private Queue**.</span></span>  
  
4.  <span data-ttu-id="fe454-150">下**队列名称**，输入**测试**。</span><span class="sxs-lookup"><span data-stu-id="fe454-150">Under **Queue name**, enter **test**.</span></span> <span data-ttu-id="fe454-151">确保**事务**复选框处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="fe454-151">Ensure that the **Transactional** check box is selected.</span></span>  
  
5.  <span data-ttu-id="fe454-152">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="fe454-152">Click **OK**.</span></span>  
  
#### <a name="to-configure-biztalk-server"></a><span data-ttu-id="fe454-153">若要配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fe454-153">To configure BizTalk Server</span></span>  
  
1.  <span data-ttu-id="fe454-154">选择存放接收消息的文件夹。</span><span class="sxs-lookup"><span data-stu-id="fe454-154">Select a folder in which to receive messages.</span></span> <span data-ttu-id="fe454-155">以下步骤假定您选择了 C:\Demo\Report，但如有必要，可调整这些步骤来使用其他文件夹。</span><span class="sxs-lookup"><span data-stu-id="fe454-155">The following steps assume that you have selected C:\Demo\Report, but you can adjust the steps as necessary for another folder.</span></span>  
  
2.  <span data-ttu-id="fe454-156">打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="fe454-156">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
3.  <span data-ttu-id="fe454-157">创建新的应用程序名为**MSMQSample**。</span><span class="sxs-lookup"><span data-stu-id="fe454-157">Create a new application named **MSMQSample**.</span></span>  
  
4.  <span data-ttu-id="fe454-158">右键单击**接收端口**，单击**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="fe454-158">Right-click **Receive Ports**, click **New**, and then click **One-way Receive Port**.</span></span>  
  
5.  <span data-ttu-id="fe454-159">在**接收端口属性**对话框中，在**名称**框中输入**MyReceivePort**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fe454-159">In the **Receive Port Properties** dialog box, in the **Name** box enter **MyReceivePort**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="fe454-160">右键单击**接收位置**，单击**新建**，然后单击**单向接收位置**。</span><span class="sxs-lookup"><span data-stu-id="fe454-160">Right-click **Receive Locations**, click **New**, and then click **One-way Receive Location**.</span></span> <span data-ttu-id="fe454-161">在**选择接收端口**对话框中，选择你刚接收端口创建，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fe454-161">In the **Select a Receive Port** dialog box, select the receive port you just created and click **OK**.</span></span>  
  
7.  <span data-ttu-id="fe454-162">在**接收位置属性**对话框中，在**名称**框中，键入接收端口的名称，如**MSMQReceiveLocation**。</span><span class="sxs-lookup"><span data-stu-id="fe454-162">In the **Receive Location Properties** dialog box, in the **Name** box, type a name for the receive port, such as **MSMQReceiveLocation**.</span></span>  
  
8.  <span data-ttu-id="fe454-163">在**接收位置属性**对话框中，对于传输类型中，选择**MSMQ** 。</span><span class="sxs-lookup"><span data-stu-id="fe454-163">In the **Receive Location Properties** dialog box, for the transport type, select **MSMQ** .</span></span>  
  
9. <span data-ttu-id="fe454-164">单击**配置**以打开**MSMQ 传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="fe454-164">Click **Configure** to open the **MSMQ Transport Properties** dialog box.</span></span> <span data-ttu-id="fe454-165">设置**队列**到`localhost\private$\test`，将其设置**事务**到`True`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fe454-165">Set **Queue** to `localhost\private$\test`, set **Transactional** to `True`, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="fe454-166">展开应用程序，选择**发送端口**，选择**新建**，选择**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="fe454-166">Expand the application, select **Send Ports**, select **New**, select **Static One-way Send Port**.</span></span>  
  
11. <span data-ttu-id="fe454-167">在**发送端口属性**对话框中，在**名称**框中，键入发送端口的名称，如**MySendPort**。</span><span class="sxs-lookup"><span data-stu-id="fe454-167">In the **Send Port Properties** dialog box, in the **Name** box, type a name for the send port, such as **MySendPort**.</span></span>  
  
12. <span data-ttu-id="fe454-168">设置**传输类型**属性**文件**。</span><span class="sxs-lookup"><span data-stu-id="fe454-168">Set the **Transport Type** property to **FILE**.</span></span>  
  
13. <span data-ttu-id="fe454-169">单击**配置**以打开**文件传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="fe454-169">Click **Configure** to open the **File Transport Properties** dialog box.</span></span>  
  
14. <span data-ttu-id="fe454-170">在**文件传输属性**对话框中，设置**目标文件夹**属性**C:\Demo\Report**，保留其他属性的默认设置，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fe454-170">In the **FILE Transport Properties** dialog box, set the **Destination Folder** property to **C:\Demo\Report**, keep the default settings for the other properties, and then click **OK**.</span></span>  
  
15. <span data-ttu-id="fe454-171">选择**筛选器**，然后通过设置中添加新行**属性**到**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="fe454-171">Select **Filters**, and then add a new row by setting **Property** to **BTS.ReceivePortName**.</span></span> <span data-ttu-id="fe454-172">保留**运算符**列设置为 **==** ，将其设置**值**列**MyReceivePort**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fe454-172">Leave the **Operator** column set to **==**, set the **Value** column to **MyReceivePort**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="fe454-173">右键单击新发送端口，然后单击**Enlist**。</span><span class="sxs-lookup"><span data-stu-id="fe454-173">Right-click your new send port, and then click **Enlist**.</span></span>  
  
17. <span data-ttu-id="fe454-174">右键单击新发送端口试，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="fe454-174">Right-click your new send port again, and then click **Start**.</span></span>  
  
18. <span data-ttu-id="fe454-175">右键单击新接收位置，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="fe454-175">Right-click your new receive location, and then click **Enable**.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="fe454-176">现在已准备好要使用此示例。</span><span class="sxs-lookup"><span data-stu-id="fe454-176"> is now ready to work with this sample.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="fe454-177">运行示例</span><span class="sxs-lookup"><span data-stu-id="fe454-177">Running the Sample</span></span>  
 <span data-ttu-id="fe454-178">使用以下过程运行 SendMSMQMessage 示例。</span><span class="sxs-lookup"><span data-stu-id="fe454-178">Use the following procedure to run the SendMSMQMessage sample.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="fe454-179">运行示例</span><span class="sxs-lookup"><span data-stu-id="fe454-179">To run the sample</span></span>  
  
1.  <span data-ttu-id="fe454-180">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="fe454-180">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="fe454-181">\<示例路径 > \AdaptersUsage\SendMSMQMessage\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="fe454-181">\<Samples Path>\AdaptersUsage\SendMSMQMessage\bin\Debug</span></span>  
  
2.  <span data-ttu-id="fe454-182">运行文件 SendMSMQMessage.exe，这将启动提供本示例的用户界面的图形应用程序。</span><span class="sxs-lookup"><span data-stu-id="fe454-182">Run the file SendMSMQMessage.exe, which starts the graphical application that provides the user interface for this sample.</span></span>  
  
3.  <span data-ttu-id="fe454-183">在图形应用程序中**BizTalk 计算机名称**框中，键入本地计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="fe454-183">In the graphical application, in the **BizTalk machine name** box, type the name of the local computer.</span></span>  
  
4.  <span data-ttu-id="fe454-184">请尝试**发送包装**选项：</span><span class="sxs-lookup"><span data-stu-id="fe454-184">Try the **Send Wrapped** option:</span></span>  
  
    1.  <span data-ttu-id="fe454-185">（可选） 更改中的文本**消息正文**框。</span><span class="sxs-lookup"><span data-stu-id="fe454-185">Optionally change the text in the **Message body** box.</span></span>  
  
    2.  <span data-ttu-id="fe454-186">单击**发送已包装**。</span><span class="sxs-lookup"><span data-stu-id="fe454-186">Click **Send wrapped**.</span></span>  
  
     <span data-ttu-id="fe454-187">如果操作成功，则将看到以下内容：</span><span class="sxs-lookup"><span data-stu-id="fe454-187">If the operation succeeds, you will see the following:</span></span>  
  
    -   <span data-ttu-id="fe454-188">Word**成功**立即上方的按钮的框中的红色字体显示。</span><span class="sxs-lookup"><span data-stu-id="fe454-188">The word **Success** appears in red font in the box immediately above the buttons.</span></span>  
  
    -   <span data-ttu-id="fe454-189">将在目标文件夹 C:\Demo\Reports 中显示一个文件。</span><span class="sxs-lookup"><span data-stu-id="fe454-189">A file appears in your destination folder, C:\Demo\Reports.</span></span> <span data-ttu-id="fe454-190">此文件包含中的文本**消息正文**包装在简单的 XML 标记，由.NET 消息队列库中的框。</span><span class="sxs-lookup"><span data-stu-id="fe454-190">This file contains the text from the **Message body** box wrapped in simple XML tags by the .NET message queuing library.</span></span>  
  
     <span data-ttu-id="fe454-191">如果操作失败，则将在按钮上方紧挨的框中显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="fe454-191">If the operation fails, you will see an error message in the box immediately above the buttons.</span></span>  
  
5.  <span data-ttu-id="fe454-192">请尝试**发送确切**选项：</span><span class="sxs-lookup"><span data-stu-id="fe454-192">Try the **Send Exact** option:</span></span>  
  
    1.  <span data-ttu-id="fe454-193">（可选） 更改中的文本**消息正文**框。</span><span class="sxs-lookup"><span data-stu-id="fe454-193">Optionally change the text in the **Message body** box.</span></span>  
  
    2.  <span data-ttu-id="fe454-194">单击**发送确切**。</span><span class="sxs-lookup"><span data-stu-id="fe454-194">Click **Send exact**.</span></span>  
  
     <span data-ttu-id="fe454-195">如果操作成功，则将看到以下内容：</span><span class="sxs-lookup"><span data-stu-id="fe454-195">If the operation succeeds, you will see the following:</span></span>  
  
    -   <span data-ttu-id="fe454-196">Word**成功**立即上方的按钮的框中的红色字体显示。</span><span class="sxs-lookup"><span data-stu-id="fe454-196">The word **Success** appears in red font in the box immediately above the buttons.</span></span>  
  
    -   <span data-ttu-id="fe454-197">将在目标文件夹 C:\Demo\Reports 中显示一个文件。</span><span class="sxs-lookup"><span data-stu-id="fe454-197">A file appears in your destination folder, C:\Demo\Reports.</span></span> <span data-ttu-id="fe454-198">此文件包含中的文本**消息正文**框中的文本框中显示的完全相同。</span><span class="sxs-lookup"><span data-stu-id="fe454-198">This file contains the text from the **Message body** box exactly as it appears in the text box.</span></span>  
  
     <span data-ttu-id="fe454-199">如果操作失败，则将在按钮上方紧挨的框中显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="fe454-199">If the operation fails, you will see an error message in the box immediately above the buttons.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe454-200">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe454-200">See Also</span></span>  
 [<span data-ttu-id="fe454-201">适配器示例-使用情况</span><span class="sxs-lookup"><span data-stu-id="fe454-201">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)