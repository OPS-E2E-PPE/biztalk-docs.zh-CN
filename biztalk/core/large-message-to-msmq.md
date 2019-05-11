---
title: 大消息到 MSMQ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fb87b46-5656-42c0-be99-8ab66e51bb4d
caps.latest.revision: 35
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d92428426b7032de36ab63cfd2be286ce3c67569
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329823"
---
# <a name="large-message-to-msmq"></a><span data-ttu-id="9d6b6-102">大到 MSMQ 消息</span><span class="sxs-lookup"><span data-stu-id="9d6b6-102">Large Message to MSMQ</span></span>
<span data-ttu-id="9d6b6-103">大消息示例演示如何将发送的.xml 文档超过 4 兆字节 (MB) 从消息队列 (也称为 MSMQ) 到 BizTalk MSMQ 适配器通过使用**MQSendLargeMessage**由 API 实现MQRTLarge.dll。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-103">The Large Message to MSMQ sample demonstrates how to send an .xml document larger than 4 megabytes (MB) from Message Queuing (also known as MSMQ) to the BizTalk MSMQ adapter by using the **MQSendLargeMessage** API implemented by MQRTLarge.dll.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="9d6b6-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="9d6b6-104">What This Sample Does</span></span>  
 <span data-ttu-id="9d6b6-105">该示例的工作方式如下：</span><span class="sxs-lookup"><span data-stu-id="9d6b6-105">The sample works as follows:</span></span>  
  
1. <span data-ttu-id="9d6b6-106">用户使用 SendLargeMessage.exe 将大型.xml 文件发送到本地计算机上的队列。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-106">A user uses SendLargeMessage.exe to send a large .xml file to a queue on a local computer.</span></span>  
  
2. <span data-ttu-id="9d6b6-107">BizTalk Server 从队列接收大型.xml 文件，并将其复制到本地目录。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-107">BizTalk Server receives the large .xml file from the queue and copies it to a local directory.</span></span>  
  
   <span data-ttu-id="9d6b6-108">消息队列中的许多操作都是异步的。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-108">Many operations in Message Queuing are asynchronous.</span></span> <span data-ttu-id="9d6b6-109">即，许多 MSMQ API 呼叫 (例如， **MQSendLargeMessage**) 返回给调用方请求的操作完全完成之前。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-109">That is, many MSMQ API calls (for example, **MQSendLargeMessage**) return to the caller before the requested operation has fully completed.</span></span>  
  
   <span data-ttu-id="9d6b6-110">MSMQ 提供了一种在操作完成之后将反馈传送到应用程序的机制。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-110">MSMQ provides a mechanism to deliver feedback to the application after the operation has completed.</span></span> <span data-ttu-id="9d6b6-111">此机制涉及到使用"管理队列"。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-111">This mechanism involves the use of an "Admin Queue."</span></span> <span data-ttu-id="9d6b6-112">MSMQ 管理队列中消息的形式返回的反馈。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-112">MSMQ returns feedback in the form of a message in the Admin Queue.</span></span> <span data-ttu-id="9d6b6-113">MSMQ 将反馈返回到的管理队列进行原始 MSMQ API 调用时指定。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-113">The Admin Queue to which MSMQ will return feedback is specified when the original MSMQ API call is made.</span></span> <span data-ttu-id="9d6b6-114">因此，举例来说，当发送消息使用**MQSendLargeMessage** API，应用程序可以指定管理队列的名称，通过使用**PROPID_M_ADMIN_QUEUE**消息在消息上的属性对的调用中传递**MQSendLargeMessage**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-114">So, for example, when sending a message using the **MQSendLargeMessage** API, the application can specify the name of an Admin Queue by using the **PROPID_M_ADMIN_QUEUE** message property on the message passed in the call to **MQSendLargeMessage**.</span></span> <span data-ttu-id="9d6b6-115">即使应用程序可能会获得成功返回代码**MQSendLargeMessage**调用时，如果消息的发送操作随后失败，MSMQ 消息写入该结果指定的管理队列。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-115">Even though the application may get a successful return code on the **MQSendLargeMessage** call, if the message send operation subsequently fails, MSMQ writes a message to that effect to the specified Admin Queue.</span></span>  
  
   <span data-ttu-id="9d6b6-116">如果应用程序未指定管理队列，发送失败会导致消息丢失并且捕获任何诊断 — 实际上，该消息消失但没有任何证据。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-116">If the application does not specify an Admin Queue, a send failure results in the message being lost and no diagnostics captured — in effect, the message disappears without any evidence.</span></span> <span data-ttu-id="9d6b6-117">很多 MSMQ 中的错误情况可能会导致这种情况发生，例如，非事务性发送到事务性队列。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-117">A number of error situations in MSMQ can cause this to happen, for example, doing a non-transactional send to a transactional queue.</span></span>  
  
   <span data-ttu-id="9d6b6-118">在本示例的上下文，非常重要的代码对的调用中指定的事务类型**MQSendLargeMessage**这就是与为向其发送消息的队列指定的事务支持一致。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-118">In the context of this sample, it is important that the code specify a transaction type in the call to **MQSendLargeMessage** that is consistent with the transaction support specified for the queue to which the message is sent.</span></span> <span data-ttu-id="9d6b6-119">如果这不是，如果 （如在此示例中） 不指定任何管理队列，则 MSMQ 放弃时，它还执行该操作没有指示发送的消息 （即，没有错误代码返回给应用程序事件日志中写入任何诊断等等)。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-119">If this is not done and if no Admin Queue is specified (as is the case in this sample), then MSMQ discards the sent message with no indication that it has done so (that is, no error code returned to the application, no diagnostics written to the event log, and so on).</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="9d6b6-120">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="9d6b6-120">Where to Find This Sample</span></span>  
 <span data-ttu-id="9d6b6-121">\<Samples Path\>\AdaptersUsage\MSMQLarge</span><span class="sxs-lookup"><span data-stu-id="9d6b6-121">\<Samples Path\>\AdaptersUsage\MSMQLarge</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d6b6-122">如果使用 Windows 和 BizTalk Server 的 64 位版本，该示例将安装在**C:\Program Files (x86) \Microsoft BizTalk Server\<版本\>\SDK\Samples\AdaptersUsage\MSMQLarge**文件夹。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-122">If using a 64-bit version of Windows and BizTalk Server, the sample will be installed in the **C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\SDK\Samples\AdaptersUsage\MSMQLarge** folder.</span></span>  <span data-ttu-id="9d6b6-123">请注意在该文档中使用的任何其他说明此更改**C:\Program Files**文件夹。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-123">Note this change for any other instructions in this document using the **C:\Program Files** folder.</span></span>  
  
 <span data-ttu-id="9d6b6-124">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="9d6b6-124">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="9d6b6-125">**File**</span><span class="sxs-lookup"><span data-stu-id="9d6b6-125">**File**</span></span>|<span data-ttu-id="9d6b6-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="9d6b6-126">**Description**</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="9d6b6-127">**MQRTLarge.dll**</span><span class="sxs-lookup"><span data-stu-id="9d6b6-127">**MQRTLarge.dll**</span></span>|<span data-ttu-id="9d6b6-128">提供外接程序的本地消息队列。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-128">Provides an add-on for native message queuing.</span></span> <span data-ttu-id="9d6b6-129">公开**MQSendLargeMessage**并**MQReceiveLargeMessage** Api。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-129">Exposes the **MQSendLargeMessage** and **MQReceiveLargeMessage** APIs.</span></span><br /><br /> <span data-ttu-id="9d6b6-130">必须在 64 位版本的 Windows 上安装 BizTalk Server，才能访问 64 位版本的 MQRTLarge.dll。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-130">You must install BizTalk Server on a 64-bit version of Windows in order to access the 64-bit version of MQRTLarge.dll.</span></span><br /><br /> <span data-ttu-id="9d6b6-131">对于 MSMQ 解决方案未使用 BizTalk Server，MQRTLarge.dll 仍可正常运行。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-131">For an MSMQ solution without BizTalk Server, the MQRTLarge.dll may still function correctly.</span></span> <span data-ttu-id="9d6b6-132">但是，这不的建议的配置，Microsoft 支持，并且如果在 BizTalk Server 环境外部使用，可能会发生意外的结果。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-132">However, this is not a recommended configuration that Microsoft supports, and unexpected results may occur if used outside of the BizTalk Server environment.</span></span>|  
|||  
|<span data-ttu-id="9d6b6-133">**LargeMessages.sln**</span><span class="sxs-lookup"><span data-stu-id="9d6b6-133">**LargeMessages.sln**</span></span>|<span data-ttu-id="9d6b6-134">提供 Visual Studio 解决方案，以创建示例中使用的 SendLargeMessage 可执行文件。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-134">Provides a Visual Studio solution to create the SendLargeMessage executable used in the sample.</span></span>|  
|<span data-ttu-id="9d6b6-135">**XMLCreator.sln**</span><span class="sxs-lookup"><span data-stu-id="9d6b6-135">**XMLCreator.sln**</span></span>|<span data-ttu-id="9d6b6-136">提供 Visual Studio 解决方案，以创建 XMLCreator 可执行文件生成为 SDK 示例.xml 测试文件。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-136">Provides a Visual Studio solution to create the XMLCreator executable to generate a test .xml file for the SDK sample.</span></span>|  
  
## <a name="configure-biztalk-and-create-the-msmq-queue"></a><span data-ttu-id="9d6b6-137">配置 BizTalk 和创建 MSMQ 队列</span><span class="sxs-lookup"><span data-stu-id="9d6b6-137">Configure BizTalk and Create the MSMQ Queue</span></span>  
 <span data-ttu-id="9d6b6-138">请确保 Visual Studio、 Microsoft 消息队列和 BizTalk Server 安装。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-138">Ensure that Visual Studio, Microsoft Message Queuing, and BizTalk Server installed.</span></span>  
  
#### <a name="to-configure-biztalk-server"></a><span data-ttu-id="9d6b6-139">若要配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="9d6b6-139">To configure BizTalk Server</span></span>  
  
1. <span data-ttu-id="9d6b6-140">在 Visual Studio 中打开**C:\Program Files\Microsoft BizTalk Server\<版本\>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeMessages.sln**解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-140">In Visual Studio, open the **C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeMessages.sln** solution file.</span></span>  <span data-ttu-id="9d6b6-141">生成该示例。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-141">Build the sample.</span></span>  
  
2. <span data-ttu-id="9d6b6-142">创建**C:\Demo** BizTalk Server 将放置来自 MSMQ 的消息目录。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-142">Create a **C:\Demo** directory where BizTalk Server will place the messages from MSMQ.</span></span>  
  
3. <span data-ttu-id="9d6b6-143">打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-143">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
4. <span data-ttu-id="9d6b6-144">创建示例以写入消息的发送端口。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-144">Create a send port for the sample to write the message.</span></span>  
  
   -   <span data-ttu-id="9d6b6-145">展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，右键单击**发送端口**，单击**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-145">Expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, right-click **Send Ports**, click **New**, and then click **Static One-Way Send Port**.</span></span>  
  
5. <span data-ttu-id="9d6b6-146">在中**静态单向发送端口属性**对话框框中，设置到的端口的名称**MySendPort**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-146">In the **Static One-Way Send Port Properties** dialog box, set the name of the port to **MySendPort**.</span></span>  
  
6. <span data-ttu-id="9d6b6-147">将传输类型设置为**文件**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-147">Set the transport type to **File**.</span></span>  
  
7. <span data-ttu-id="9d6b6-148">单击**配置**按钮以打开**File 传输属性**窗体。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-148">Click the **Configure** button to open the **File Transport Properties** form.</span></span> <span data-ttu-id="9d6b6-149">输入**C:\Demo**中**目标文件夹**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-149">Enter **C:\Demo** in **Destination Folder**.</span></span> <span data-ttu-id="9d6b6-150">确保主机实例标识具有对 C:\Demo 文件夹的访问。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-150">Ensure that the host instance identity has access to the C:\Demo folder.</span></span>  
  
8. <span data-ttu-id="9d6b6-151">絋粄**文件名**设置为 **%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-151">Ensure that **File Name** is set to **%MessageID%.xml**.</span></span> <span data-ttu-id="9d6b6-152">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-152">Click **OK**.</span></span>  
  
9. <span data-ttu-id="9d6b6-153">单击 **“筛选器”**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-153">Click **Filters**.</span></span>  
  
    1.  <span data-ttu-id="9d6b6-154">设置**属性**到**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-154">Set **Property** to **BTS.ReceivePortName**.</span></span>  
  
    2.  <span data-ttu-id="9d6b6-155">设置**运算符**到**=**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-155">Set **Operator** to **=**.</span></span>  
  
    3.  <span data-ttu-id="9d6b6-156">设置**值**到**MyReceivePort**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-156">Set **Value** to **MyReceivePort**.</span></span>  
  
    4.  <span data-ttu-id="9d6b6-157">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-157">Click **OK**.</span></span>  
  
10. <span data-ttu-id="9d6b6-158">创建用于接受来自 MSMQ 的消息的接收端口。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-158">Create a receive port to accept the message from MSMQ.</span></span>  
  
    1. <span data-ttu-id="9d6b6-159">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-159">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **Receive Ports**.</span></span>  
  
    2. <span data-ttu-id="9d6b6-160">单击**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-160">Click **New**, and then click **One-way Receive Port**.</span></span>  
  
11. <span data-ttu-id="9d6b6-161">在中**接收端口属性**对话框框中，设置到的端口的名称**MyReceivePort**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-161">In the **Receive Port Properties** dialog box, set the name of the port to **MyReceivePort**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="9d6b6-162">创建示例接收端口后，必须创建接收位置。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-162">After creating a receive port for the sample, you must create a receive location.</span></span>  
  
    1. <span data-ttu-id="9d6b6-163">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-163">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **Receive Locations**.</span></span>  
  
    2. <span data-ttu-id="9d6b6-164">单击**新建**，然后单击**单向接收位置**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-164">Click **New**, and then click **One-way Receive Location**.</span></span>  
  
    3. <span data-ttu-id="9d6b6-165">设置为接收位置的名称**MSMQReceiveLocation**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-165">Set the name of the receive location to **MSMQReceiveLocation**.</span></span>  
  
    4. <span data-ttu-id="9d6b6-166">在中**选择接收端口**对话框中，选择**MyReceivePort**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-166">In the **Select a Receive Port** dialog box, select **MyReceivePort**.</span></span>  
  
    5. <span data-ttu-id="9d6b6-167">在中**接收位置属性**对话框中，将**传输类型**到**MSMQ**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-167">In the **Receive Location Properties** dialog box, set **Transport Type** to **MSMQ**.</span></span>  
  
    6. <span data-ttu-id="9d6b6-168">在中**地址 (URI)** 部分中，单击**配置**以打开**MSMQ 传输属性**窗体。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-168">In the **Address (URI)** section, click **Configure** to open the **MSMQ Transport Properties** form.</span></span> <span data-ttu-id="9d6b6-169">设置**队列**到**localhost\private$ \test**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-169">Set **Queue** to **localhost\private$\test**.</span></span>  
  
    7. <span data-ttu-id="9d6b6-170">设置**事务性**到`True`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-170">Set **Transactional** to `True`, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="9d6b6-171">您必须使端口和接收位置可用于通过使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-171">You must make the ports and receive locations available for use through the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
    1.  <span data-ttu-id="9d6b6-172">右键单击**MySendPort**，然后单击**登记**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-172">Right-click **MySendPort**, and then click **Enlist**.</span></span>  
  
    2.  <span data-ttu-id="9d6b6-173">右键单击**MySendPort**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-173">Right-click **MySendPort**, and then click **Start**.</span></span>  
  
    3.  <span data-ttu-id="9d6b6-174">右键单击**MSMQReceiveLocation**，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-174">Right-click **MSMQReceiveLocation**, and then click **Enable**.</span></span>  
  
#### <a name="to-create-the-msmq-queue-in-windows-server"></a><span data-ttu-id="9d6b6-175">若要在 Windows Server 中创建 MSMQ 队列</span><span class="sxs-lookup"><span data-stu-id="9d6b6-175">To create the MSMQ queue in Windows Server</span></span>
  
1.  <span data-ttu-id="9d6b6-176">单击**启动**，右键单击**计算机**，然后单击**管理**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-176">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>  
  
2.  <span data-ttu-id="9d6b6-177">展开**功能**节点。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-177">Expand the **Features** node.</span></span>  
  
3.  <span data-ttu-id="9d6b6-178">展开**消息队列**节点。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-178">Expand the **Message Queuing** node.</span></span>  
  
4.  <span data-ttu-id="9d6b6-179">右键单击**专用队列**节点中，单击**新建**，然后单击**专用队列**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-179">Right-click the **Private Queues** node, click **New**, and then click **Private Queue**.</span></span>  
  
5.  <span data-ttu-id="9d6b6-180">下**队列名称**，输入**测试**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-180">Under **Queue name**, enter **test**.</span></span> <span data-ttu-id="9d6b6-181">絋粄**事务性**复选框处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-181">Ensure that the **Transactional** check box is selected.</span></span>  
  
6.  <span data-ttu-id="9d6b6-182">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-182">Click **OK**.</span></span>  
  
#### <a name="to-create-the-msmq-queue-in-windows"></a><span data-ttu-id="9d6b6-183">若要在 Windows 中创建 MSMQ 队列</span><span class="sxs-lookup"><span data-stu-id="9d6b6-183">To create the MSMQ queue in Windows</span></span> 
  
1.  <span data-ttu-id="9d6b6-184">单击**启动**，右键单击**计算机**，然后单击**管理**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-184">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>  
  
2.  <span data-ttu-id="9d6b6-185">展开**服务和应用程序**，然后展开**消息队列**节点。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-185">Expand **Services and Applications**, and then expand the **Message Queuing** node.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9d6b6-186">如果**消息队列**未安装在计算机中，转到**控制面板 > 程序 > 程序和功能**，然后选择**打开或关闭打开的 Windows 功能**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-186">If **Message Queuing** is not installed in the computer, go to **Control Panel > Programs > Programs and Features**, and then select **Turn Windows features on or off**.</span></span> <span data-ttu-id="9d6b6-187">检查下的所有功能**Microsoft 消息队列 (MSMQ) 服务器**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-187">Check all the features under **Microsoft Message Queue (MSMQ) Server**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="9d6b6-188">右键单击**专用队列**节点中，单击**新建**，然后单击**专用队列**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-188">Right-click the **Private Queues** node, click **New**, and then click **Private Queue**.</span></span>  
  
4.  <span data-ttu-id="9d6b6-189">下**队列名称**，输入**测试**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-189">Under **Queue name**, enter **test**.</span></span> <span data-ttu-id="9d6b6-190">絋粄**事务性**复选框处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-190">Ensure that the **Transactional** check box is selected.</span></span>  
  
5.  <span data-ttu-id="9d6b6-191">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-191">Click **OK**.</span></span>  
  
## <a name="creating-a-test-file-and-running-the-sample"></a><span data-ttu-id="9d6b6-192">创建测试文件和运行示例</span><span class="sxs-lookup"><span data-stu-id="9d6b6-192">Creating a Test File and Running the Sample</span></span>  
  
#### <a name="to-create-a-large-test-file"></a><span data-ttu-id="9d6b6-193">若要创建一个大型测试文件</span><span class="sxs-lookup"><span data-stu-id="9d6b6-193">To create a large test file</span></span>  
  
1.  <span data-ttu-id="9d6b6-194">在 Visual Studio 中，打开解决方案**C:\Program Files\Microsoft BizTalk Server\<版本\>\SDK\Samples\AdaptersUsage\MSMQLarge\XMLCreator\XMLCreator.sln**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-194">In Visual Studio, open the solution **C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Samples\AdaptersUsage\MSMQLarge\XMLCreator\XMLCreator.sln**.</span></span>  
  
2.  <span data-ttu-id="9d6b6-195">生成并运行该项目。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-195">Build and run the project.</span></span>  
  
3.  <span data-ttu-id="9d6b6-196">下**XML 正文**，类型**这是测试消息**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-196">Under **XML Body**, type **This is a test message**.</span></span>  
  
4.  <span data-ttu-id="9d6b6-197">下**数次以复制 XML 正文**，类型`250000`。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-197">Under **# of times to copy XML body**, type `250000`.</span></span>  
  
5.  <span data-ttu-id="9d6b6-198">下**XML 文件位置**，类型`C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml`。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-198">Under **XML File Location**, type `C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml`.</span></span>  
  
6.  <span data-ttu-id="9d6b6-199">单击**创建 XML**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-199">Click **Create XML**, and then click **OK**.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="9d6b6-200">若要运行示例</span><span class="sxs-lookup"><span data-stu-id="9d6b6-200">To run the sample</span></span>  
  
1.  <span data-ttu-id="9d6b6-201">打开命令提示符，并将目录更改为**C:\Program Files\Microsoft BizTalk Server\<版本\>\SDK\Samples\AdaptersUsage\MSMQLarge\SendLargeMessage\bin\debug**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-201">Open a command prompt and change directory to **C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Samples\AdaptersUsage\MSMQLarge\SendLargeMessage\bin\debug**.</span></span>  
  
2.  <span data-ttu-id="9d6b6-202">在命令提示符处，运行**SendLargeMessage.exe**。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-202">At the command prompt, run **SendLargeMessage.exe**.</span></span> <span data-ttu-id="9d6b6-203">SendLargeMessage 可执行文件接受两个变量，第一个是 MSMQ 队列的位置，第二个是要发送的.xml 文件的位置：</span><span class="sxs-lookup"><span data-stu-id="9d6b6-203">The SendLargeMessage executable accepts two variables — the first is the location of the MSMQ queue, and the second is the location of the .xml file to send:</span></span>  
  
    ```  
    DIRECT=OS:localhost\private$\Test  "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml"  
    ```  
  
3.  <span data-ttu-id="9d6b6-204">验证是否已在 BizTalk Server 计算机上创建大小相同的文件**C:\Demo**目录。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-204">Verify that a file of the same size was created on the BizTalk Server computer in the **C:\Demo** directory.</span></span> <span data-ttu-id="9d6b6-205">这是在 MySendPort 发送端口中标识的目录中。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-205">This is the directory you identified in the MySendPort send port.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="9d6b6-206">注释</span><span class="sxs-lookup"><span data-stu-id="9d6b6-206">Comments</span></span>  
 <span data-ttu-id="9d6b6-207">SendLargeMessage.exe 引用**LargeMessages** API，后者又引用 BizTalk 消息队列大消息扩展 (MQRTLarge.dll) API。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-207">SendLargeMessage.exe references the **LargeMessages** API, which in turn references the BizTalk Message Queuing Large Message Extension (MQRTLarge.dll) API.</span></span> <span data-ttu-id="9d6b6-208">消息队列大消息扩展 API 是本地消息队列的外接程序允许处理大于 4 MB 的限制的本机消息队列的消息。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-208">The Message Queuing Large Message Extension API is an add-on for native message queuing that enables the processing of messages larger than the 4 MB limit of native message queuing.</span></span>  
  
 <span data-ttu-id="9d6b6-209">此示例使用**MQSendLargeMessage** API 并公开 API 到.NET Framework 通过使用**LargeMessages** API。</span><span class="sxs-lookup"><span data-stu-id="9d6b6-209">This sample uses the **MQSendLargeMessage** API and exposes the API to the .NET Framework by using the **LargeMessages** API.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d6b6-210">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d6b6-210">See Also</span></span>  
 <span data-ttu-id="9d6b6-211">[BizTalk 消息队列大消息扩展](../core/biztalk-message-queuing-large-message-extension.md) </span><span class="sxs-lookup"><span data-stu-id="9d6b6-211">[BizTalk Message Queuing Large Message Extension](../core/biztalk-message-queuing-large-message-extension.md) </span></span>  
 [<span data-ttu-id="9d6b6-212">适配器示例 - 用法</span><span class="sxs-lookup"><span data-stu-id="9d6b6-212">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)