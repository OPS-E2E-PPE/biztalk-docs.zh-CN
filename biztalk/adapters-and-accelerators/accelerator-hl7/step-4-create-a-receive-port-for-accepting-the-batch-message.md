---
title: 步骤 4： 创建用于接受批处理消息接收端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a37eb334-c4ae-40d1-a433-bf0ab39c0765
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56d1aa54639263e6741c6df89c3888b9b4120515
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207605"
---
# <a name="step-4-create-a-receive-port-for-accepting-the-batch-message"></a><span data-ttu-id="45f87-102">步骤 4： 创建用于接受批处理消息接收端口</span><span class="sxs-lookup"><span data-stu-id="45f87-102">Step 4: Create a Receive Port for Accepting the Batch Message</span></span>
<span data-ttu-id="45f87-103">在此步骤中，创建并配置一个端口用于接收传入的批。</span><span class="sxs-lookup"><span data-stu-id="45f87-103">In this step, you create and configure a port to receive the incoming batch.</span></span>  
  
 <span data-ttu-id="45f87-104">创建请求-响应 （双向） 接收端口，因为此情形包括生成的应用程序的接受批处理中的单个消息的确认。</span><span class="sxs-lookup"><span data-stu-id="45f87-104">You create a request-response (two-way) receive port, because the scenario includes the generation of application-accept acknowledgments for the individual messages in the batch.</span></span> <span data-ttu-id="45f87-105">在双向模式下，MLLP 接收适配器将不接受新的传入消息，直到接收管道都生成前面的消息，确认 (ACK)。</span><span class="sxs-lookup"><span data-stu-id="45f87-105">In two-way mode, the MLLP receive adapter will not accept a new incoming message until the receive pipeline has generated the acknowledgment (ACK) for the previous message.</span></span>  
  
## <a name="create-the-receive-port-for-accepting-the-batch-message"></a><span data-ttu-id="45f87-106">创建用于接受批处理消息的接收端口</span><span class="sxs-lookup"><span data-stu-id="45f87-106">Create the receive port for accepting the batch message</span></span>  
  
1.  <span data-ttu-id="45f87-107">打开**BizTalk Server 管理**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk 应用程序 1**。</span><span class="sxs-lookup"><span data-stu-id="45f87-107">Open **BizTalk Server Administration**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="45f87-108">BizTalk Server 管理控制台也可以打开从 Visual Studio 中通过单击**BizTalk Server 管理**中**工具**菜单。</span><span class="sxs-lookup"><span data-stu-id="45f87-108">The BizTalk Server Administration Console can also be opened from within Visual Studio by clicking **BizTalk Server Administration** in the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="45f87-109">右键单击**接收端口**，选择**新建**，然后选择**请求响应接收端口**。</span><span class="sxs-lookup"><span data-stu-id="45f87-109">Right-click **Receive Ports**, select **New**, and then select **Request Response Receive Port**.</span></span>  

3.  <span data-ttu-id="45f87-110">有关**名称**，输入**Tutorial_2WayReceive**。</span><span class="sxs-lookup"><span data-stu-id="45f87-110">For the **Name**, enter **Tutorial_2WayReceive**.</span></span>  

4.  <span data-ttu-id="45f87-111">选择**应用**要将该端口绑定，然后选择**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="45f87-111">Select **Apply** to bind the port, and then select **Receive Locations**.</span></span>  
  
5.  <span data-ttu-id="45f87-112">选择**新**。</span><span class="sxs-lookup"><span data-stu-id="45f87-112">Select **New**.</span></span>  

6.  <span data-ttu-id="45f87-113">有关**名称**，输入**Tutorial_2WayReceive**。</span><span class="sxs-lookup"><span data-stu-id="45f87-113">For the **Name**, enter **Tutorial_2WayReceive**.</span></span>

7. <span data-ttu-id="45f87-114">在**传输**部分中，选择**类型**，然后选择**MLLP**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="45f87-114">In the **Transport** section, select **Type**, and then select **MLLP** from the drop-down list.</span></span>  
  
8. <span data-ttu-id="45f87-115">选择 **“配置”**。</span><span class="sxs-lookup"><span data-stu-id="45f87-115">Select **Configure**.</span></span> <span data-ttu-id="45f87-116">在**MLLP 传输属性**，配置以下内容，，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="45f87-116">In **MLLP Transport Properties**, configure the following, and then select **OK**.</span></span>  

    |<span data-ttu-id="45f87-117">使用此选项</span><span class="sxs-lookup"><span data-stu-id="45f87-117">Use this</span></span>|<span data-ttu-id="45f87-118">执行的操作</span><span class="sxs-lookup"><span data-stu-id="45f87-118">To do this</span></span>|  
    |---|---|  
    |<span data-ttu-id="45f87-119">**连接重试时间 （秒）**</span><span class="sxs-lookup"><span data-stu-id="45f87-119">**Connect retry time (sec)**</span></span>|<span data-ttu-id="45f87-120">新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="45f87-120">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="45f87-121">在尝试重新连接被删除或已关闭连接之前等待的时间上限。</span><span class="sxs-lookup"><span data-stu-id="45f87-121">The upper limit of time to wait before attempting to reconnect a dropped or closed connection.</span></span> <span data-ttu-id="45f87-122">可用**连接由**设置为**本地**。</span><span class="sxs-lookup"><span data-stu-id="45f87-122">Applicable when **Connection Initiated by** is set to **Local**.</span></span><br/><br/><span data-ttu-id="45f87-123">默认值为 20 秒。</span><span class="sxs-lookup"><span data-stu-id="45f87-123">Default is 20 seconds.</span></span>|
    |<span data-ttu-id="45f87-124">**由启动的连接**</span><span class="sxs-lookup"><span data-stu-id="45f87-124">**Connection initiated by**</span></span>| <span data-ttu-id="45f87-125">新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="45f87-125">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="45f87-126">输入**本地**对于 MLLP 收到位置以启动远程的 LOB 服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="45f87-126">Enter **Local** for the MLLP receive location to initiate the connection to a remote LOB server.</span></span> <span data-ttu-id="45f87-127">这是新的选项。</span><span class="sxs-lookup"><span data-stu-id="45f87-127">This is the new option.</span></span><br/><br/><span data-ttu-id="45f87-128">输入**远程**对于 MLLP 收到位置继续侦听从远程 LOB 服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="45f87-128">Enter **Remote** for the MLLP receive location to continue to listen for a connection from the remote LOB server.</span></span> <span data-ttu-id="45f87-129">这是向后兼容默认选项。</span><span class="sxs-lookup"><span data-stu-id="45f87-129">This is the backwards-compatible default option.</span></span><br/><br/><span data-ttu-id="45f87-130">默认值为远程。</span><span class="sxs-lookup"><span data-stu-id="45f87-130">Default is Remote.</span></span>| 
    |<span data-ttu-id="45f87-131">**连接名称**</span><span class="sxs-lookup"><span data-stu-id="45f87-131">**Connection Name**</span></span>|<span data-ttu-id="45f87-132">输入**2Way**。</span><span class="sxs-lookup"><span data-stu-id="45f87-132">Enter **2Way**.</span></span>|  
    |<span data-ttu-id="45f87-133">**主机名**</span><span class="sxs-lookup"><span data-stu-id="45f87-133">**Host name**</span></span>|<span data-ttu-id="45f87-134">特定于[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]和较旧版本。</span><span class="sxs-lookup"><span data-stu-id="45f87-134">Specific to [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] and older versions.</span></span> <br/><br/><span data-ttu-id="45f87-135">输入**localhost**。</span><span class="sxs-lookup"><span data-stu-id="45f87-135">Enter **localhost**.</span></span>|  
    |<span data-ttu-id="45f87-136">**本地主机名**</span><span class="sxs-lookup"><span data-stu-id="45f87-136">**Local Host name**</span></span>|<span data-ttu-id="45f87-137">新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="45f87-137">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="45f87-138">输入的 DNS 名称或 IP 地址的本地[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="45f87-138">Enter the DNS name or IP address of the local [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="45f87-139">你也可以输入**localhost**。</span><span class="sxs-lookup"><span data-stu-id="45f87-139">You can also enter **localhost**.</span></span>|  
    |<span data-ttu-id="45f87-140">**端口**</span><span class="sxs-lookup"><span data-stu-id="45f87-140">**Port**</span></span>|<span data-ttu-id="45f87-141">特定于[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]和较旧版本。</span><span class="sxs-lookup"><span data-stu-id="45f87-141">Specific to [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] and older versions.</span></span> <br/><br/><span data-ttu-id="45f87-142">设置为**21000**。</span><span class="sxs-lookup"><span data-stu-id="45f87-142">Set to **21000**.</span></span>|  
    |<span data-ttu-id="45f87-143">**本地端口**</span><span class="sxs-lookup"><span data-stu-id="45f87-143">**Local Port**</span></span>|<span data-ttu-id="45f87-144">新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="45f87-144">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="45f87-145">输入本地主机连接的 TCP 端口号。</span><span class="sxs-lookup"><span data-stu-id="45f87-145">Enter the TCP port number for the LocalHost connection.</span></span> <span data-ttu-id="45f87-146">适用时，才**连接由**是**远程**。</span><span class="sxs-lookup"><span data-stu-id="45f87-146">Applicable only when **Connection Initiated by** is **Remote**.</span></span> <br/><br/><span data-ttu-id="45f87-147">设置为**21000**。</span><span class="sxs-lookup"><span data-stu-id="45f87-147">Set to **21000**.</span></span>|
    |<span data-ttu-id="45f87-148">**远程主机**</span><span class="sxs-lookup"><span data-stu-id="45f87-148">**Remote Host**</span></span>|<span data-ttu-id="45f87-149">新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="45f87-149">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="45f87-150">输入的 DNS 名称或远程的 LOB 服务器 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="45f87-150">Enter the DNS name or IP address of the remote LOB server.</span></span> <span data-ttu-id="45f87-151">可用**连接由**设置为**本地**。</span><span class="sxs-lookup"><span data-stu-id="45f87-151">Applicable when **Connection Initiated by** is set to **Local**.</span></span>|  
    |<span data-ttu-id="45f87-152">**远程端口**</span><span class="sxs-lookup"><span data-stu-id="45f87-152">**Remote Port**</span></span>|<span data-ttu-id="45f87-153">新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="45f87-153">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="45f87-154">输入对远程主机连接的 TCP 端口号。</span><span class="sxs-lookup"><span data-stu-id="45f87-154">Enter the TCP port number for the remote host connection.</span></span> <span data-ttu-id="45f87-155">可用**连接由**设置为**本地**。</span><span class="sxs-lookup"><span data-stu-id="45f87-155">Applicable when **Connection Initiated by** is set to **Local**.</span></span><br/><br/><span data-ttu-id="45f87-156">设置为**21000**。</span><span class="sxs-lookup"><span data-stu-id="45f87-156">Set to **21000**.</span></span>|  

9. <span data-ttu-id="45f87-157">在接收位置属性中，选择以下项：</span><span class="sxs-lookup"><span data-stu-id="45f87-157">In the Receive Location properties, select the following:</span></span>  
  
    |<span data-ttu-id="45f87-158">使用此选项</span><span class="sxs-lookup"><span data-stu-id="45f87-158">Use this</span></span>|<span data-ttu-id="45f87-159">执行的操作</span><span class="sxs-lookup"><span data-stu-id="45f87-159">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="45f87-160">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="45f87-160">**Receive Handler**</span></span>|<span data-ttu-id="45f87-161">选择**BizTalkServerApplication**从下拉列表</span><span class="sxs-lookup"><span data-stu-id="45f87-161">Select **BizTalkServerApplication** from the drop-down list</span></span>|  
    |<span data-ttu-id="45f87-162">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="45f87-162">**Receive Pipeline**</span></span>|<span data-ttu-id="45f87-163">选择**BTAHL72XPipelines.BTAHL72XReceivePipeline**</span><span class="sxs-lookup"><span data-stu-id="45f87-163">Select **BTAHL72XPipelines.BTAHL72XReceivePipeline**</span></span>|  
    |<span data-ttu-id="45f87-164">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="45f87-164">**Send Pipeline**</span></span>|<span data-ttu-id="45f87-165">选择**BTAHL72XPipelines.BTAHL72XSendPipeline**</span><span class="sxs-lookup"><span data-stu-id="45f87-165">Select **BTAHL72XPipelines.BTAHL72XSendPipeline**</span></span>|  

11. <span data-ttu-id="45f87-166">单击“确定”保存更改。</span><span class="sxs-lookup"><span data-stu-id="45f87-166">Select **OK** to save your changes.</span></span>  
  
12. <span data-ttu-id="45f87-167">启用接收位置你刚刚创建，请右键单击它，并选择**启用**。</span><span class="sxs-lookup"><span data-stu-id="45f87-167">Enable the receive location you just created by right-clicking it, and then select **Enable**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="45f87-168">下一步</span><span class="sxs-lookup"><span data-stu-id="45f87-168">Next step</span></span>
[<span data-ttu-id="45f87-169">步骤 5： 创建发送端口将消息传递</span><span class="sxs-lookup"><span data-stu-id="45f87-169">Step 5: Create a Send Port to Deliver Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md)