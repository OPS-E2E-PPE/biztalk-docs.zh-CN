---
title: 步骤 4： 创建用于接受 ADT 接收端口 ^ A03 消息从 ADT 系统使用 MLLP 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 2015-12-09
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive ports
- end-to-end tutorial, receive ports
- creating, receive ports
ms.assetid: 3c4192d5-d011-48b0-a3f9-47c5225780ee
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 865675e12609beea4c909d19a74d3e0ec4f38715
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207733"
---
# <a name="step-4-create-the-receive-port-for-accepting-adta03-messages-from-adt-systems-using-the-mllp-adapter"></a><span data-ttu-id="d5ae0-102">步骤 4： 创建用于接受 ADT 接收端口 ^ A03 消息从 ADT 系统使用 MLLP 适配器</span><span class="sxs-lookup"><span data-stu-id="d5ae0-102">Step 4: Create the Receive Port for Accepting ADT^A03 Messages from ADT Systems Using the MLLP Adapter</span></span>
<span data-ttu-id="d5ae0-103">接收端口用于指定传入消息的接收位置。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-103">You use the receive port to specify the receive location for incoming messages.</span></span> <span data-ttu-id="d5ae0-104">使用以下过程来创建接收端口用于接受 ADT ^ A03 消息从 ADT 系统使用 MLLP 适配器。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-104">Use the following procedure to create the receive port for accepting ADT^A03 messages from the ADT System using the MLLP adapter.</span></span>  
  
## <a name="create-the-receive-port"></a><span data-ttu-id="d5ae0-105">创建接收端口</span><span class="sxs-lookup"><span data-stu-id="d5ae0-105">Create the receive port</span></span>  
  
1.  <span data-ttu-id="d5ae0-106">打开**BizTalk Server 管理**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk 应用程序 1**。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-106">Open **BizTalk Server Administration**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d5ae0-107">BizTalk Server 管理控制台也可以打开从 Visual Studio 中通过单击**BizTalk Server 管理**中**工具**菜单。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-107">The BizTalk Server Administration Console can also be opened from within Visual Studio by clicking **BizTalk Server Administration** in the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="d5ae0-108">右键单击**接收端口**，选择**新建**，然后选择**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-108">Right-click **Receive Ports**, select **New**, and then select **One-way Receive Port**.</span></span>  
  
3.  <span data-ttu-id="d5ae0-109">有关**名称**，输入**Tutorial_1WayReceive**。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-109">For the **Name**, enter **Tutorial_1WayReceive**.</span></span>  
  
4.  <span data-ttu-id="d5ae0-110">选择**应用**要将该端口绑定，然后选择**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-110">Select **Apply** to bind the port, and then select **Receive Locations**.</span></span>  
  
5.  <span data-ttu-id="d5ae0-111">选择**新**。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-111">Select **New**.</span></span>  
  
6.  <span data-ttu-id="d5ae0-112">有关**名称**，输入**Tutorial_MLLPReceive**。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-112">For the **Name**, enter **Tutorial_MLLPReceive**.</span></span>  
  
7. <span data-ttu-id="d5ae0-113">在**传输**部分中，选择**类型**，然后选择**MLLP**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-113">In the **Transport** section, select **Type**, and then select **MLLP** from the drop-down list.</span></span>  
  
8. <span data-ttu-id="d5ae0-114">选择 **“配置”**。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-114">Select **Configure**.</span></span> <span data-ttu-id="d5ae0-115">在**MLLP 传输属性**，配置以下内容，，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-115">In **MLLP Transport Properties**, configure the following, and then select **OK**.</span></span>  
  
    |<span data-ttu-id="d5ae0-116">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d5ae0-116">Use this</span></span>|<span data-ttu-id="d5ae0-117">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d5ae0-117">To do this</span></span>|  
    |---|---|  
    |<span data-ttu-id="d5ae0-118">**连接重试时间 （秒）**</span><span class="sxs-lookup"><span data-stu-id="d5ae0-118">**Connect retry time (sec)**</span></span>|<span data-ttu-id="d5ae0-119">新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-119">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="d5ae0-120">在尝试重新连接被删除或已关闭连接之前等待的时间上限。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-120">The upper limit of time to wait before attempting to reconnect a dropped or closed connection.</span></span> <span data-ttu-id="d5ae0-121">可用**连接由**设置为**本地**。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-121">Applicable when **Connection Initiated by** is set to **Local**.</span></span><br/><br/><span data-ttu-id="d5ae0-122">默认值为 20 秒。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-122">Default is 20 seconds.</span></span>|
    |<span data-ttu-id="d5ae0-123">**由启动的连接**</span><span class="sxs-lookup"><span data-stu-id="d5ae0-123">**Connection initiated by**</span></span>| <span data-ttu-id="d5ae0-124">新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-124">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="d5ae0-125">输入**本地**对于 MLLP 收到位置以启动远程的 LOB 服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-125">Enter **Local** for the MLLP receive location to initiate the connection to a remote LOB server.</span></span> <span data-ttu-id="d5ae0-126">这是新的选项。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-126">This is the new option.</span></span><br/><br/><span data-ttu-id="d5ae0-127">输入**远程**对于 MLLP 收到位置继续侦听从远程 LOB 服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-127">Enter **Remote** for the MLLP receive location to continue to listen for a connection from the remote LOB server.</span></span> <span data-ttu-id="d5ae0-128">这是向后兼容默认选项。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-128">This is the backwards-compatible default option.</span></span><br/><br/><span data-ttu-id="d5ae0-129">默认值为远程。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-129">Default is Remote.</span></span>| 
    |<span data-ttu-id="d5ae0-130">**连接名称**</span><span class="sxs-lookup"><span data-stu-id="d5ae0-130">**Connection Name**</span></span>|<span data-ttu-id="d5ae0-131">输入**1Way**。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-131">Enter **1Way**.</span></span>|  
    |<span data-ttu-id="d5ae0-132">**主机名**</span><span class="sxs-lookup"><span data-stu-id="d5ae0-132">**Host name**</span></span>|<span data-ttu-id="d5ae0-133">特定于[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]和较旧版本。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-133">Specific to [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] and older versions.</span></span> <br/><br/><span data-ttu-id="d5ae0-134">输入**localhost**。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-134">Enter **localhost**.</span></span>|  
    |<span data-ttu-id="d5ae0-135">**本地主机名**</span><span class="sxs-lookup"><span data-stu-id="d5ae0-135">**Local Host name**</span></span>|<span data-ttu-id="d5ae0-136">新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-136">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="d5ae0-137">输入的 DNS 名称或 IP 地址的本地[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-137">Enter the DNS name or IP address of the local [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d5ae0-138">你也可以输入**localhost**。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-138">You can also enter **localhost**.</span></span>|  
    |<span data-ttu-id="d5ae0-139">**端口**</span><span class="sxs-lookup"><span data-stu-id="d5ae0-139">**Port**</span></span>|<span data-ttu-id="d5ae0-140">特定于[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]和较旧版本。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-140">Specific to [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] and older versions.</span></span> <br/><br/><span data-ttu-id="d5ae0-141">默认值是**11000**。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-141">Default is **11000**.</span></span>|  
    |<span data-ttu-id="d5ae0-142">**本地端口**</span><span class="sxs-lookup"><span data-stu-id="d5ae0-142">**Local Port**</span></span>|<span data-ttu-id="d5ae0-143">新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-143">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="d5ae0-144">输入本地主机连接的 TCP 端口号。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-144">Enter the TCP port number for the LocalHost connection.</span></span> <span data-ttu-id="d5ae0-145">适用时，才**连接由**是**远程**。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-145">Applicable only when **Connection Initiated by** is **Remote**.</span></span> <br/><br/><span data-ttu-id="d5ae0-146">默认值是**11000**。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-146">Default is **11000**.</span></span>|
    |<span data-ttu-id="d5ae0-147">**远程主机**</span><span class="sxs-lookup"><span data-stu-id="d5ae0-147">**Remote Host**</span></span>|<span data-ttu-id="d5ae0-148">新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-148">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="d5ae0-149">输入的 DNS 名称或远程的 LOB 服务器 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-149">Enter the DNS name or IP address of the remote LOB server.</span></span> <span data-ttu-id="d5ae0-150">可用**连接由**设置为**本地**。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-150">Applicable when **Connection Initiated by** is set to **Local**.</span></span>|  
    |<span data-ttu-id="d5ae0-151">**远程端口**</span><span class="sxs-lookup"><span data-stu-id="d5ae0-151">**Remote Port**</span></span>|<span data-ttu-id="d5ae0-152">新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-152">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="d5ae0-153">输入对远程主机连接的 TCP 端口号。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-153">Enter the TCP port number for the remote host connection.</span></span> <span data-ttu-id="d5ae0-154">可用**连接由**设置为**本地**。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-154">Applicable when **Connection Initiated by** is set to **Local**.</span></span>|  

9. <span data-ttu-id="d5ae0-155">设置**接收处理者**到**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-155">Set the **Receive Handler** to **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="d5ae0-156">设置**接收管道**到**BTAHL72XPipelines.BTAHL72XReceivePipeline**。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-156">Set the **Receive Pipeline** to **BTAHL72XPipelines.BTAHL72XReceivePipeline**.</span></span>  
  
11. <span data-ttu-id="d5ae0-157">单击“确定”保存更改。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-157">Select **OK** to save your changes.</span></span>  
  
12. <span data-ttu-id="d5ae0-158">启用接收位置你刚刚创建，请右键单击它，并选择**启用**。</span><span class="sxs-lookup"><span data-stu-id="d5ae0-158">Enable the receive location you just created by right-clicking it, and then select **Enable**.</span></span>  

## <a name="next-step"></a><span data-ttu-id="d5ae0-159">下一步</span><span class="sxs-lookup"><span data-stu-id="d5ae0-159">Next step</span></span>  
[<span data-ttu-id="d5ae0-160">步骤 5： 创建发送端口将确认传递到使用文件适配器的 ADT 系统</span><span class="sxs-lookup"><span data-stu-id="d5ae0-160">Step 5: Create a Send Port to Deliver Acknowledgments to the ADT System Using the File Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-send-port-to-deliver-acknowledgments-to-adt-system-using-file.md)