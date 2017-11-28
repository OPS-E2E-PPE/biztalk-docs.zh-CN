---
title: "步骤 5： 创建用于接受其消息接收端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: interrogative tutorial, receive ports
ms.assetid: c0b311d8-541c-4c21-a514-c93092c36fe2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0df326e3b08438f7a1eb7d3a2df3c5a816e79bc7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-create-the-receive-port-for-accepting-his-messages"></a><span data-ttu-id="0306b-102">步骤 5： 创建用于接受其消息接收端口</span><span class="sxs-lookup"><span data-stu-id="0306b-102">Step 5: Create the Receive Port for Accepting HIS Messages</span></span>
<span data-ttu-id="0306b-103">在此步骤中，你将创建接收端口指定为发送医院信息系统 (HIS) 的传入消息的位置。</span><span class="sxs-lookup"><span data-stu-id="0306b-103">In this step you create a receive port to specify the location for incoming messages sent by the Hospital Information System (HIS).</span></span> <span data-ttu-id="0306b-104">使用以下过程来创建用于接受来自使用最小较低层协议 (MLLP) 适配器 ADT 系统的查询响应消息的接收端口。</span><span class="sxs-lookup"><span data-stu-id="0306b-104">Use the following procedure to create the receive port for accepting query response messages from the ADT system using the Minimal Lower Layer Protocol (MLLP) adapter.</span></span>  
  
## <a name="create-the-hisreceiveport-receive-port"></a><span data-ttu-id="0306b-105">创建 HIS_ReceivePort 接收端口</span><span class="sxs-lookup"><span data-stu-id="0306b-105">Create the HIS_ReceivePort receive port</span></span>  

1.  <span data-ttu-id="0306b-106">打开**BizTalk Server 管理**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk 应用程序 1**。</span><span class="sxs-lookup"><span data-stu-id="0306b-106">Open **BizTalk Server Administration**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
2.  <span data-ttu-id="0306b-107">右键单击**接收端口**，选择**新建**，然后选择**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="0306b-107">Right-click **Receive Ports**, select **New**, and then select **One-way Receive Port**.</span></span>   
  
3.  <span data-ttu-id="0306b-108">有关**名称**，输入**HIS_ReceivePort**。</span><span class="sxs-lookup"><span data-stu-id="0306b-108">For the **Name**, enter **HIS_ReceivePort**.</span></span>  

4.  <span data-ttu-id="0306b-109">选择**应用**要将该端口绑定，然后选择**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="0306b-109">Select **Apply** to bind the port, and then select **Receive Locations**.</span></span>  
  
5.  <span data-ttu-id="0306b-110">选择**新**。</span><span class="sxs-lookup"><span data-stu-id="0306b-110">Select **New**.</span></span>  
  
6.  <span data-ttu-id="0306b-111">有关**名称**，输入**HIS_Receive**。</span><span class="sxs-lookup"><span data-stu-id="0306b-111">For the **Name**, enter **HIS_Receive**.</span></span>  

7. <span data-ttu-id="0306b-112">在**传输**部分中，选择**类型**，然后选择**MLLP**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="0306b-112">In the **Transport** section, select **Type**, and then select **MLLP** from the drop-down list.</span></span>  
  
8. <span data-ttu-id="0306b-113">选择 **“配置”**。</span><span class="sxs-lookup"><span data-stu-id="0306b-113">Select **Configure**.</span></span> <span data-ttu-id="0306b-114">在**MLLP 传输属性**，配置以下内容，，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="0306b-114">In **MLLP Transport Properties**, configure the following, and then select **OK**.</span></span>  

    |<span data-ttu-id="0306b-115">使用此选项</span><span class="sxs-lookup"><span data-stu-id="0306b-115">Use this</span></span>|<span data-ttu-id="0306b-116">执行的操作</span><span class="sxs-lookup"><span data-stu-id="0306b-116">To do this</span></span>|  
    |---|---|  
    |<span data-ttu-id="0306b-117">**连接重试时间 （秒）**</span><span class="sxs-lookup"><span data-stu-id="0306b-117">**Connect retry time (sec)**</span></span>|<span data-ttu-id="0306b-118">新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0306b-118">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="0306b-119">在尝试重新连接被删除或已关闭连接之前等待的时间上限。</span><span class="sxs-lookup"><span data-stu-id="0306b-119">The upper limit of time to wait before attempting to reconnect a dropped or closed connection.</span></span> <span data-ttu-id="0306b-120">可用**连接由**设置为**本地**。</span><span class="sxs-lookup"><span data-stu-id="0306b-120">Applicable when **Connection Initiated by** is set to **Local**.</span></span><br/><br/><span data-ttu-id="0306b-121">默认值为 20 秒。</span><span class="sxs-lookup"><span data-stu-id="0306b-121">Default is 20 seconds.</span></span>|
    |<span data-ttu-id="0306b-122">**由启动的连接**</span><span class="sxs-lookup"><span data-stu-id="0306b-122">**Connection initiated by**</span></span>| <span data-ttu-id="0306b-123">新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0306b-123">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="0306b-124">输入**本地**对于 MLLP 收到位置以启动远程的 LOB 服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="0306b-124">Enter **Local** for the MLLP receive location to initiate the connection to a remote LOB server.</span></span> <span data-ttu-id="0306b-125">这是新的选项。</span><span class="sxs-lookup"><span data-stu-id="0306b-125">This is the new option.</span></span><br/><br/><span data-ttu-id="0306b-126">输入**远程**对于 MLLP 收到位置继续侦听从远程 LOB 服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="0306b-126">Enter **Remote** for the MLLP receive location to continue to listen for a connection from the remote LOB server.</span></span> <span data-ttu-id="0306b-127">这是向后兼容默认选项。</span><span class="sxs-lookup"><span data-stu-id="0306b-127">This is the backwards-compatible default option.</span></span><br/><br/><span data-ttu-id="0306b-128">默认值为远程。</span><span class="sxs-lookup"><span data-stu-id="0306b-128">Default is Remote.</span></span>| 
    |<span data-ttu-id="0306b-129">**连接名称**</span><span class="sxs-lookup"><span data-stu-id="0306b-129">**Connection Name**</span></span>|<span data-ttu-id="0306b-130">输入**HIS_ReceiveMLLP**。</span><span class="sxs-lookup"><span data-stu-id="0306b-130">Enter **HIS_ReceiveMLLP**.</span></span>|  
    |<span data-ttu-id="0306b-131">**主机名**</span><span class="sxs-lookup"><span data-stu-id="0306b-131">**Host name**</span></span>|<span data-ttu-id="0306b-132">特定于[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]和较旧版本。</span><span class="sxs-lookup"><span data-stu-id="0306b-132">Specific to [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] and older versions.</span></span> <br/><br/><span data-ttu-id="0306b-133">输入**localhost**。</span><span class="sxs-lookup"><span data-stu-id="0306b-133">Enter **localhost**.</span></span>|  
    |<span data-ttu-id="0306b-134">**本地主机名**</span><span class="sxs-lookup"><span data-stu-id="0306b-134">**Local Host name**</span></span>|<span data-ttu-id="0306b-135">新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0306b-135">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="0306b-136">输入的 DNS 名称或 IP 地址的本地[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0306b-136">Enter the DNS name or IP address of the local [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="0306b-137">你也可以输入**localhost**。</span><span class="sxs-lookup"><span data-stu-id="0306b-137">You can also enter **localhost**.</span></span>|  
    |<span data-ttu-id="0306b-138">**端口**</span><span class="sxs-lookup"><span data-stu-id="0306b-138">**Port**</span></span>|<span data-ttu-id="0306b-139">特定于[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]和较旧版本。</span><span class="sxs-lookup"><span data-stu-id="0306b-139">Specific to [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] and older versions.</span></span> <br/><br/><span data-ttu-id="0306b-140">设置为**23000**。</span><span class="sxs-lookup"><span data-stu-id="0306b-140">Set to **23000**.</span></span>|  
    |<span data-ttu-id="0306b-141">**本地端口**</span><span class="sxs-lookup"><span data-stu-id="0306b-141">**Local Port**</span></span>|<span data-ttu-id="0306b-142">新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0306b-142">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="0306b-143">输入本地主机连接的 TCP 端口号。</span><span class="sxs-lookup"><span data-stu-id="0306b-143">Enter the TCP port number for the LocalHost connection.</span></span> <span data-ttu-id="0306b-144">适用时，才**连接由**是**远程**。</span><span class="sxs-lookup"><span data-stu-id="0306b-144">Applicable only when **Connection Initiated by** is **Remote**.</span></span> <br/><br/><span data-ttu-id="0306b-145">设置为**23000**。</span><span class="sxs-lookup"><span data-stu-id="0306b-145">Set to **23000**.</span></span>|
    |<span data-ttu-id="0306b-146">**远程主机**</span><span class="sxs-lookup"><span data-stu-id="0306b-146">**Remote Host**</span></span>|<span data-ttu-id="0306b-147">新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0306b-147">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="0306b-148">输入的 DNS 名称或远程的 LOB 服务器 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="0306b-148">Enter the DNS name or IP address of the remote LOB server.</span></span> <span data-ttu-id="0306b-149">可用**连接由**设置为**本地**。</span><span class="sxs-lookup"><span data-stu-id="0306b-149">Applicable when **Connection Initiated by** is set to **Local**.</span></span>|  
    |<span data-ttu-id="0306b-150">**远程端口**</span><span class="sxs-lookup"><span data-stu-id="0306b-150">**Remote Port**</span></span>|<span data-ttu-id="0306b-151">新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0306b-151">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="0306b-152">输入对远程主机连接的 TCP 端口号。</span><span class="sxs-lookup"><span data-stu-id="0306b-152">Enter the TCP port number for the remote host connection.</span></span> <span data-ttu-id="0306b-153">可用**连接由**设置为**本地**。</span><span class="sxs-lookup"><span data-stu-id="0306b-153">Applicable when **Connection Initiated by** is set to **Local**.</span></span><br/><br/><span data-ttu-id="0306b-154">设置为**23000**。</span><span class="sxs-lookup"><span data-stu-id="0306b-154">Set to **23000**.</span></span>|  
    
9. <span data-ttu-id="0306b-155">设置**接收处理者**到**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="0306b-155">Set the **Receive Handler** to **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="0306b-156">设置**接收管道**到**BTAHL72XPipelines.BTAHL72XReceivePipeline**。</span><span class="sxs-lookup"><span data-stu-id="0306b-156">Set the **Receive Pipeline** to **BTAHL72XPipelines.BTAHL72XReceivePipeline**.</span></span>  
  
11. <span data-ttu-id="0306b-157">单击“确定”保存更改。</span><span class="sxs-lookup"><span data-stu-id="0306b-157">Select **OK** to save your changes.</span></span>  
  
12. <span data-ttu-id="0306b-158">启用接收位置你刚刚创建，请右键单击它，并选择**启用**。</span><span class="sxs-lookup"><span data-stu-id="0306b-158">Enable the receive location you just created by right-clicking it, and then select **Enable**.</span></span>  

## <a name="next-step"></a><span data-ttu-id="0306b-159">下一步</span><span class="sxs-lookup"><span data-stu-id="0306b-159">Next step</span></span>  
[<span data-ttu-id="0306b-160">步骤 6： 创建发送端口将查询消息传递</span><span class="sxs-lookup"><span data-stu-id="0306b-160">Step 6: Create a Send Port to Deliver Query Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-query-messages.md)