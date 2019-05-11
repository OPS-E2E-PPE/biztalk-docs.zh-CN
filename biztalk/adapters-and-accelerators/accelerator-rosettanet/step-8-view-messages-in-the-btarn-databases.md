---
title: 步骤 8：在 BTARN 数据库中查看消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, viewing
- loopback tutorial, viewing messages
- databases, viewing messages
ms.assetid: c549670c-4428-483c-906c-eff163ddef9a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94f9b676c2f8ea8c212a4ded6f50ee9037cad6ea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280545"
---
# <a name="step-8-view-messages-in-the-btarn-databases"></a><span data-ttu-id="844b4-102">步骤 8：在 BTARN 数据库中查看消息</span><span class="sxs-lookup"><span data-stu-id="844b4-102">Step 8: View Messages in the BTARN Databases</span></span>
<span data-ttu-id="844b4-103">在此步骤中，您使用 SQL 查询分析器来查看业务 (LOB) 消息存储在 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]数据库来验证环回方案是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="844b4-103">In this step, you use SQL Query Analyzer to view line-of-business (LOB) messages stored in the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] database to verify that your loop-back scenario is working correctly.</span></span>  
  
 <span data-ttu-id="844b4-104">LOB 应用程序后实用工具生成 LOB 消息并将其提交到[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]，发起方 （家庭） 和响应方 （合作伙伴） 将发生以下事件：</span><span class="sxs-lookup"><span data-stu-id="844b4-104">After the LOB Application utility generates an LOB message and submits it to [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], the following events occur for the initiator (home) and the responder (partner):</span></span>  
  
 <span data-ttu-id="844b4-105">发起方工作流</span><span class="sxs-lookup"><span data-stu-id="844b4-105">Initiator Workflow</span></span>  
  
- <span data-ttu-id="844b4-106">SubmitRNIF 将 LOB 消息到 MessagesFromLOB 表的提交[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据数据库。</span><span class="sxs-lookup"><span data-stu-id="844b4-106">SubmitRNIF submits the LOB message to the MessagesFromLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] DATA database.</span></span>  
  
- <span data-ttu-id="844b4-107">SQL 适配器接收位置从其中提取消息并将其传送到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="844b4-107">The SQL adapter receive location picks up the message and delivers it to the MessageBox database.</span></span> <span data-ttu-id="844b4-108">SQL 适配器提取一条消息在时间运行`GetMessagesFromLOB`存储过程。</span><span class="sxs-lookup"><span data-stu-id="844b4-108">The SQL adapter picks up one message at a time running the `GetMessagesFromLOB` stored procedure.</span></span>  
  
- <span data-ttu-id="844b4-109">专用发起方会选取该消息从 MessageBox 数据库，然后再次将它放到 MessageBox 数据库与其他已升级的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="844b4-109">The private initiator picks the message from the MessageBox database and then drops it again to the MessageBox database with additional promoted context properties.</span></span>  
  
- <span data-ttu-id="844b4-110">公用发起方会选取该消息从 MessageBox 数据库根据订阅筛选器。</span><span class="sxs-lookup"><span data-stu-id="844b4-110">The public initiator picks the message from the MessageBox database based on the subscription filter.</span></span>  
  
- <span data-ttu-id="844b4-111">HTTP 发送端口提取消息利用 RNIFSend 管道根据订阅。</span><span class="sxs-lookup"><span data-stu-id="844b4-111">The HTTP send port picks the message with the RNIFSend pipeline based on the subscriptions.</span></span> <span data-ttu-id="844b4-112">将消息保存在 MessageStorageOut 表中[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不可否认性的存档数据库，然后将该消息发送至 RNIFSend.aspx 页。</span><span class="sxs-lookup"><span data-stu-id="844b4-112">It saves the message in the MessageStorageOut table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archive database for non-repudiation, and then sends the message over to the RNIFSend.aspx page.</span></span>  
  
- <span data-ttu-id="844b4-113">RNIFSend.aspx 页接收查询字符串变量，包括消息 (合作伙伴组织的 URL) 的最终目标的 MIME 编码消息。</span><span class="sxs-lookup"><span data-stu-id="844b4-113">The RNIFSend.aspx page receives the MIME-encoded message with query string variables that include the final destination of the message (partner organization URL).</span></span>  
  
  <span data-ttu-id="844b4-114">响应方工作流</span><span class="sxs-lookup"><span data-stu-id="844b4-114">Responder Workflow</span></span>  
  
- [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="844b4-115">将 RNIF 消息发送到 RNIFReceive.aspx 页删除 MIME 解码包装器的情况。</span><span class="sxs-lookup"><span data-stu-id="844b4-115">sends the RNIF message to the RNIFReceive.aspx page where the MIME-decoded wrapper is removed.</span></span> <span data-ttu-id="844b4-116">消息被标识为同步或异步的然后转发到同步或异步接收位置 （RNIF_Sync_Receive 或 RNIF_Async_Receive）。</span><span class="sxs-lookup"><span data-stu-id="844b4-116">The message is identified as either synchronous or asynchronous, and then forwarded to either the synchronous or asynchronous receive location (RNIF_Sync_Receive or RNIF_Async_Receive).</span></span>  
  
- <span data-ttu-id="844b4-117">HTTP 的不可否认的 MessageStorageIn 表中接收位置的第一个保存消息的传输格式[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]存档数据库。</span><span class="sxs-lookup"><span data-stu-id="844b4-117">The HTTP receive location first saves the wire format of the message in the MessageStorageIn table for non-repudiation of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archive database.</span></span> <span data-ttu-id="844b4-118">HTTP 接收位置然后进行解码、 解密 （对于 RNIF 2.0) 中，验证其签名、 拆装 XML 消息部分、 授权基于该签名，然后将其放入 MessageBox 数据库具有正确的升级属性</span><span class="sxs-lookup"><span data-stu-id="844b4-118">The HTTP receive location then decodes, decrypts (for RNIF 2.0), validates on its signature, disassembles the XML message parts, authorizes based on the signature, and then drops it in the MessageBox database with the correct promoted properties</span></span>  
  
- <span data-ttu-id="844b4-119">公用响应方选择消息部分基于订阅，然后验证并根据正确的 RNIF 标准对消息进行处理。</span><span class="sxs-lookup"><span data-stu-id="844b4-119">The public responder picks the message parts based on subscription, and then validates and processes the message based on the correct RNIF standard.</span></span> <span data-ttu-id="844b4-120">服务内容部分会将消息放到 MessageBox 数据库中具有正确的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="844b4-120">The service content part drops the message into the MessageBox database with the correct context properties.</span></span>  
  
- <span data-ttu-id="844b4-121">SQL 发送端口提取消息根据订阅筛选器。</span><span class="sxs-lookup"><span data-stu-id="844b4-121">The SQL send port picks the message based on the subscription filter.</span></span> <span data-ttu-id="844b4-122">它然后将该消息保存在 MessagesToLOB 表中的[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据数据库。</span><span class="sxs-lookup"><span data-stu-id="844b4-122">It then saves the message in the MessagesToLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] DATA database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="844b4-123">响应方各，公用响应方负责生成的确认回执或异常信号回发起方。</span><span class="sxs-lookup"><span data-stu-id="844b4-123">On the responder side, the Public Responder is responsible for generating the acknowledgement receipt or the exception signal back to the initiator.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="844b4-124">不保存在 MessagesFromLOB 表中的信号消息。</span><span class="sxs-lookup"><span data-stu-id="844b4-124">does not save the signal message in the MessagesFromLOB table.</span></span> <span data-ttu-id="844b4-125">这是因为 LOB 应用程序不会生成信号消息。</span><span class="sxs-lookup"><span data-stu-id="844b4-125">This is because the LOB application does not generate the signal message.</span></span> <span data-ttu-id="844b4-126">操作消息将继续通过专用响应方，和[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将其保存到 MessagesToLOB 表。</span><span class="sxs-lookup"><span data-stu-id="844b4-126">The Action message will continue through the Private Responder, and [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] saves it to the MessagesToLOB table.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="844b4-127">对于双操作 Pip，响应方各 LOB 负责生成响应消息。</span><span class="sxs-lookup"><span data-stu-id="844b4-127">For double-action PIPs, the LOB on the responder side is responsible for generating a response message.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="844b4-128">将其放到 MessagesFromLOB 表中通过发起方流程与相同的进程。</span><span class="sxs-lookup"><span data-stu-id="844b4-128">drops it to the MessagesFromLOB table to go through the same process as the initiator-side process.</span></span> <span data-ttu-id="844b4-129">在这种情况下，发起方公用发起方流程发回响应消息的确认回执或异常信号。</span><span class="sxs-lookup"><span data-stu-id="844b4-129">In this case, the Public Initiator Process on the initiator side sends back an acknowledgement receipt or exception signal for the response message.</span></span>  
  
### <a name="to-view-messages-in-the-btarn-databases"></a><span data-ttu-id="844b4-130">在 BTARN 数据库中查看消息</span><span class="sxs-lookup"><span data-stu-id="844b4-130">To view messages in the BTARN databases</span></span>  
  
1. <span data-ttu-id="844b4-131">单击**启动**，依次指向**所有程序**，指向**Microsoft SQL Server\<版本\>**，然后单击**SQL ServerManagement Studio**。</span><span class="sxs-lookup"><span data-stu-id="844b4-131">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server \<version\>**, and then click **SQL Server Management Studio**.</span></span>  
  
2. <span data-ttu-id="844b4-132">在连接到服务器对话框中，单击**Connect**。</span><span class="sxs-lookup"><span data-stu-id="844b4-132">In the Connect to Server dialog box, click **Connect**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="844b4-133">在对象资源管理器窗格中，验证 SQL Server 代理已启动。</span><span class="sxs-lookup"><span data-stu-id="844b4-133">In the Object Explorer pane, verify that the SQL Server Agent is started.</span></span> <span data-ttu-id="844b4-134">如果没有，请右键单击**SQL Server 代理**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="844b4-134">If not, right-click **SQL Server Agent**, and click **Start**.</span></span>  
  
3. <span data-ttu-id="844b4-135">在 Microsoft SQL Server Management Studio 中，单击**新查询**。</span><span class="sxs-lookup"><span data-stu-id="844b4-135">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4. <span data-ttu-id="844b4-136">在空白查询窗口中，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="844b4-136">In the Blank Query window, type the following:</span></span>  
  
   ```  
   use BTARNArchive  
   SELECT * FROM         MessageStorageIn ORDER BY TIMECREATED ASC  
   SELECT * FROM         MessageStorageOut ORDER BY TIMECREATED ASC  
  
   use BTARNData  
   SELECT     * FROM         MessagesFromLOB ORDER BY TIMECREATED ASC  
   SELECT     * FROM         MessagesToLOB ORDER BY TIMECREATED ASC  
   SELECT     * FROM         Attachments ORDER BY TIMECREATED ASC  
   ```  
  
5. <span data-ttu-id="844b4-137">在 Microsoft SQL Server Management Studio 中，单击**Execute**。</span><span class="sxs-lookup"><span data-stu-id="844b4-137">In the Microsoft SQL Server Management Studio, click **Execute**.</span></span>  
  
   <span data-ttu-id="844b4-138">您将看到在 MessagesFromLOB 表中，操作消息，如果在几分钟时间 （时间可能因您的系统配置） 再次运行查询，您将看到在 MessagesToLOB 表中的其 MessageCategory 值生成的两条消息AsyncAckSignal (25) 和 AsyncAction (10)。</span><span class="sxs-lookup"><span data-stu-id="844b4-138">You will see an action message in the MessagesFromLOB table, and if you run the query again in several minutes (time may vary depending on your system configuration), you will see two messages generated in the MessagesToLOB table with MessageCategory values of AsyncAckSignal (25) and AsyncAction (10).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="844b4-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="844b4-139">See Also</span></span>  
 <span data-ttu-id="844b4-140">[Loopback](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md) </span><span class="sxs-lookup"><span data-stu-id="844b4-140">[Loopback](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md) </span></span>  
 [<span data-ttu-id="844b4-141">Loopback 教程</span><span class="sxs-lookup"><span data-stu-id="844b4-141">Loopback Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/loopback-tutorial.md)
