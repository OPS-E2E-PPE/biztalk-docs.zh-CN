---
title: 步骤 8： 在 BTARN 数据库中查看消息 |Microsoft Docs
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
ms.openlocfilehash: 56563473e5865e9b94edefd76e9f230f8cd37f67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998438"
---
# <a name="step-8-view-messages-in-the-btarn-databases"></a><span data-ttu-id="1a892-102">步骤 8： 在 BTARN 数据库中查看消息</span><span class="sxs-lookup"><span data-stu-id="1a892-102">Step 8: View Messages in the BTARN Databases</span></span>
<span data-ttu-id="1a892-103">在此步骤中，您使用 SQL 查询分析器来查看业务 (LOB) 消息存储在 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]数据库来验证环回方案是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="1a892-103">In this step, you use SQL Query Analyzer to view line-of-business (LOB) messages stored in the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] database to verify that your loop-back scenario is working correctly.</span></span>  
  
 <span data-ttu-id="1a892-104">LOB 应用程序实用工具生成 LOB 消息并将其提交到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 后，发起方（本组织）和响应方（合作伙伴）系统中将发生以下事件：</span><span class="sxs-lookup"><span data-stu-id="1a892-104">After the LOB Application utility generates an LOB message and submits it to [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], the following events occur for the initiator (home) and the responder (partner):</span></span>  
  
 <span data-ttu-id="1a892-105">发起方工作流</span><span class="sxs-lookup"><span data-stu-id="1a892-105">Initiator Workflow</span></span>  
  
- <span data-ttu-id="1a892-106">SubmitRNIF 将 LOB 消息提交到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] DATA 数据库的 MessagesFromLOB 表。</span><span class="sxs-lookup"><span data-stu-id="1a892-106">SubmitRNIF submits the LOB message to the MessagesFromLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] DATA database.</span></span>  
  
- <span data-ttu-id="1a892-107">SQL 适配器接收位置提取消息，并将其传送至 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="1a892-107">The SQL adapter receive location picks up the message and delivers it to the MessageBox database.</span></span> <span data-ttu-id="1a892-108">SQL 适配器在运行 `GetMessagesFromLOB` 存储过程时一次提取一条消息。</span><span class="sxs-lookup"><span data-stu-id="1a892-108">The SQL adapter picks up one message at a time running the `GetMessagesFromLOB` stored procedure.</span></span>  
  
- <span data-ttu-id="1a892-109">专用发起方从 MessageBox 数据库中提取消息，然后使用附加的已升级上下文属性将消息重新放到 MessageBox 数据库中。</span><span class="sxs-lookup"><span data-stu-id="1a892-109">The private initiator picks the message from the MessageBox database and then drops it again to the MessageBox database with additional promoted context properties.</span></span>  
  
- <span data-ttu-id="1a892-110">公用发起方根据订阅筛选器从 MessageBox 数据库中提取消息。</span><span class="sxs-lookup"><span data-stu-id="1a892-110">The public initiator picks the message from the MessageBox database based on the subscription filter.</span></span>  
  
- <span data-ttu-id="1a892-111">HTTP 发送端口根据订阅利用 RNIFSend 管道提取消息。</span><span class="sxs-lookup"><span data-stu-id="1a892-111">The HTTP send port picks the message with the RNIFSend pipeline based on the subscriptions.</span></span> <span data-ttu-id="1a892-112">它将消息保存到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archive 数据库的 MessageStorageOut 表中，确保不可否认性，然后再将该消息发送至 RNIFSend.aspx 页。</span><span class="sxs-lookup"><span data-stu-id="1a892-112">It saves the message in the MessageStorageOut table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archive database for non-repudiation, and then sends the message over to the RNIFSend.aspx page.</span></span>  
  
- <span data-ttu-id="1a892-113">RNIFSend.aspx 页接收的 MIME 编码消息带有查询字符串变量，这些变量含有消息的最终目标，即合作伙伴组织的 URL。</span><span class="sxs-lookup"><span data-stu-id="1a892-113">The RNIFSend.aspx page receives the MIME-encoded message with query string variables that include the final destination of the message (partner organization URL).</span></span>  
  
  <span data-ttu-id="1a892-114">响应方工作流</span><span class="sxs-lookup"><span data-stu-id="1a892-114">Responder Workflow</span></span>  
  
- [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="1a892-115"> 将 RNIF 消息发送到 RNIFReceive.aspx 页，MIME 解码包装程序在该页上被删除。</span><span class="sxs-lookup"><span data-stu-id="1a892-115"> sends the RNIF message to the RNIFReceive.aspx page where the MIME-decoded wrapper is removed.</span></span> <span data-ttu-id="1a892-116">消息被标识为同步或异步，然后转发到同步接收位置或异步接收位置（RNIF_Sync_Receive 或 RNIF_Async_Receive）。</span><span class="sxs-lookup"><span data-stu-id="1a892-116">The message is identified as either synchronous or asynchronous, and then forwarded to either the synchronous or asynchronous receive location (RNIF_Sync_Receive or RNIF_Async_Receive).</span></span>  
  
- <span data-ttu-id="1a892-117">HTTP 接收位置首先将消息的线路格式保存到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archive 数据库的 MessageStorageIn 表中，确保不可否认性。</span><span class="sxs-lookup"><span data-stu-id="1a892-117">The HTTP receive location first saves the wire format of the message in the MessageStorageIn table for non-repudiation of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archive database.</span></span> <span data-ttu-id="1a892-118">HTTP 接收位置然后进行解码、解密（对于 RNIF 2.0）、验证消息签名、拆装 XML 消息各部分、根据签名进行授权，最后使用正确的已升级属性将消息放到 MessageBox 数据库中</span><span class="sxs-lookup"><span data-stu-id="1a892-118">The HTTP receive location then decodes, decrypts (for RNIF 2.0), validates on its signature, disassembles the XML message parts, authorizes based on the signature, and then drops it in the MessageBox database with the correct promoted properties</span></span>  
  
- <span data-ttu-id="1a892-119">公用响应方根据订阅提取消息各部分，然后根据正确的 RNIF 标准验证和处理消息。</span><span class="sxs-lookup"><span data-stu-id="1a892-119">The public responder picks the message parts based on subscription, and then validates and processes the message based on the correct RNIF standard.</span></span> <span data-ttu-id="1a892-120">服务内容部分使用正确的上下文属性将消息放到 MessageBox 数据库中。</span><span class="sxs-lookup"><span data-stu-id="1a892-120">The service content part drops the message into the MessageBox database with the correct context properties.</span></span>  
  
- <span data-ttu-id="1a892-121">SQL 发送端口根据订阅筛选器提取消息。</span><span class="sxs-lookup"><span data-stu-id="1a892-121">The SQL send port picks the message based on the subscription filter.</span></span> <span data-ttu-id="1a892-122">然后将消息保存到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] DATA 数据库的 MessagesToLOB 表中。</span><span class="sxs-lookup"><span data-stu-id="1a892-122">It then saves the message in the MessagesToLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] DATA database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a892-123">响应方各，公用响应方负责生成的确认回执或异常信号回发起方。</span><span class="sxs-lookup"><span data-stu-id="1a892-123">On the responder side, the Public Responder is responsible for generating the acknowledgement receipt or the exception signal back to the initiator.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="1a892-124"> 不保存在 MessagesFromLOB 表中的信号消息。</span><span class="sxs-lookup"><span data-stu-id="1a892-124"> does not save the signal message in the MessagesFromLOB table.</span></span> <span data-ttu-id="1a892-125">这是因为 LOB 应用程序不生成信号消息。</span><span class="sxs-lookup"><span data-stu-id="1a892-125">This is because the LOB application does not generate the signal message.</span></span> <span data-ttu-id="1a892-126">操作消息将继续通过专用响应方，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将操作消息保存到 MessagesToLOB 表中。</span><span class="sxs-lookup"><span data-stu-id="1a892-126">The Action message will continue through the Private Responder, and [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] saves it to the MessagesToLOB table.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="1a892-127">对于双操作 Pip，响应方各 LOB 负责生成响应消息。</span><span class="sxs-lookup"><span data-stu-id="1a892-127">For double-action PIPs, the LOB on the responder side is responsible for generating a response message.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="1a892-128"> 将其放到 MessagesFromLOB 表中通过发起方流程与相同的进程。</span><span class="sxs-lookup"><span data-stu-id="1a892-128"> drops it to the MessagesFromLOB table to go through the same process as the initiator-side process.</span></span> <span data-ttu-id="1a892-129">在这种情况下，发起方方面的公用发起方流程将返回响应消息的确认回执或异常信号。</span><span class="sxs-lookup"><span data-stu-id="1a892-129">In this case, the Public Initiator Process on the initiator side sends back an acknowledgement receipt or exception signal for the response message.</span></span>  
  
### <a name="to-view-messages-in-the-btarn-databases"></a><span data-ttu-id="1a892-130">在 BTARN 数据库中查看消息</span><span class="sxs-lookup"><span data-stu-id="1a892-130">To view messages in the BTARN databases</span></span>  
  
1. <span data-ttu-id="1a892-131">单击**启动**，依次指向**所有程序**，指向**Microsoft SQL Server\<版本\>**，然后单击**SQL ServerManagement Studio**。</span><span class="sxs-lookup"><span data-stu-id="1a892-131">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server \<version\>**, and then click **SQL Server Management Studio**.</span></span>  
  
2. <span data-ttu-id="1a892-132">在连接到服务器对话框中，单击**Connect**。</span><span class="sxs-lookup"><span data-stu-id="1a892-132">In the Connect to Server dialog box, click **Connect**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="1a892-133">在“对象资源管理器”窗格中，检验 SQL Server 代理是否已启动。</span><span class="sxs-lookup"><span data-stu-id="1a892-133">In the Object Explorer pane, verify that the SQL Server Agent is started.</span></span> <span data-ttu-id="1a892-134">如果没有，请右键单击**SQL Server 代理**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="1a892-134">If not, right-click **SQL Server Agent**, and click **Start**.</span></span>  
  
3. <span data-ttu-id="1a892-135">在 Microsoft SQL Server Management Studio 中，单击**新查询**。</span><span class="sxs-lookup"><span data-stu-id="1a892-135">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4. <span data-ttu-id="1a892-136">在“空查询”窗口中，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="1a892-136">In the Blank Query window, type the following:</span></span>  
  
   ```  
   use BTARNArchive  
   SELECT * FROM         MessageStorageIn ORDER BY TIMECREATED ASC  
   SELECT * FROM         MessageStorageOut ORDER BY TIMECREATED ASC  
  
   use BTARNData  
   SELECT     * FROM         MessagesFromLOB ORDER BY TIMECREATED ASC  
   SELECT     * FROM         MessagesToLOB ORDER BY TIMECREATED ASC  
   SELECT     * FROM         Attachments ORDER BY TIMECREATED ASC  
   ```  
  
5. <span data-ttu-id="1a892-137">在 Microsoft SQL Server Management Studio 中，单击**Execute**。</span><span class="sxs-lookup"><span data-stu-id="1a892-137">In the Microsoft SQL Server Management Studio, click **Execute**.</span></span>  
  
   <span data-ttu-id="1a892-138">您将在 MessagesFromLOB 表中看到一条操作消息，如果几分钟后（此时间取决于您的系统配置）再次运行查询，您将在 MessagesToLOB 表中看到所生成的两条消息，其 MessageCategory 值分别为 AsyncAckSignal (25) 和 AsyncAction (10)。</span><span class="sxs-lookup"><span data-stu-id="1a892-138">You will see an action message in the MessagesFromLOB table, and if you run the query again in several minutes (time may vary depending on your system configuration), you will see two messages generated in the MessagesToLOB table with MessageCategory values of AsyncAckSignal (25) and AsyncAction (10).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a892-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a892-139">See Also</span></span>  
 <span data-ttu-id="1a892-140">[Loopback](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md) </span><span class="sxs-lookup"><span data-stu-id="1a892-140">[Loopback](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md) </span></span>  
 [<span data-ttu-id="1a892-141">Loopback 教程</span><span class="sxs-lookup"><span data-stu-id="1a892-141">Loopback Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/loopback-tutorial.md)
