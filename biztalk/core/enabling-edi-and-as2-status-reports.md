---
title: 启用 EDI 和 AS2 状态报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa40fbad-51ad-40e0-9fe3-68e54beb11a5
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b06ae5e1fde570a9c27c1951a4eca7a7c5481e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349904"
---
# <a name="enabling-edi-and-as2-status-reports"></a><span data-ttu-id="bf002-102">启用 EDI 和 AS2 状态报告</span><span class="sxs-lookup"><span data-stu-id="bf002-102">Enabling EDI and AS2 Status Reports</span></span>
<span data-ttu-id="bf002-103">本主题介绍如何配置 EDI 和 AS2 状态报告中的**组概述**页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="bf002-103">This topic describes how to configure the EDI and AS2 status reports in the **Group Overview** page of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
 <span data-ttu-id="bf002-104">在下面的过程中选择状态报告跟踪数据存储在 BizTalk 跟踪数据库 (BizTalkDTADb) 根据存储属性。</span><span class="sxs-lookup"><span data-stu-id="bf002-104">Status reporting tracking data is stored in the BizTalk tracking database (BizTalkDTADb) in accordance with the storage properties selected in the procedures below.</span></span> <span data-ttu-id="bf002-105">你可以配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]启用状态报告为每个协议。</span><span class="sxs-lookup"><span data-stu-id="bf002-105">You can configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to enable status reporting for each agreement.</span></span> <span data-ttu-id="bf002-106">根据存储的数据量，应定期存档活动存储中的数据和存档存储，根据最终清理。</span><span class="sxs-lookup"><span data-stu-id="bf002-106">Depending upon the amount of data that you store, you should routinely archive the data from the active store and ultimately clean it out from the archival store, as appropriate.</span></span> <span data-ttu-id="bf002-107">有关管理 BizTalkDTADb 数据库的详细信息，请参阅[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)。</span><span class="sxs-lookup"><span data-stu-id="bf002-107">For more information about managing the BizTalkDTADb database, see [Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md).</span></span>  
  
 <span data-ttu-id="bf002-108">您可以启用以下三种方式的状态报告：</span><span class="sxs-lookup"><span data-stu-id="bf002-108">You can enable status reports in three ways:</span></span>  
  
- <span data-ttu-id="bf002-109">对于入站或出站 EDI 交换解析为协议启用状态报告。</span><span class="sxs-lookup"><span data-stu-id="bf002-109">Enable status reports for inbound or outbound EDI interchanges that resolved to an agreement.</span></span>  
  
- <span data-ttu-id="bf002-110">启用对 EDI 备用协议属性的状态报告以便 EDI 交换激活状态报告[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法确定协议。</span><span class="sxs-lookup"><span data-stu-id="bf002-110">Enable status reports for EDI fallback agreement properties, so status reporting is activated for EDI interchanges that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] could not determine an agreement for.</span></span>  
  
- <span data-ttu-id="bf002-111">启用 AS2 消息的状态报告。</span><span class="sxs-lookup"><span data-stu-id="bf002-111">Enable status reports for AS2 messages.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bf002-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="bf002-112">Prerequisites</span></span>  
 <span data-ttu-id="bf002-113">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组或 BizTalk Server B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="bf002-113">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group or BizTalk Server B2B Operators group.</span></span>  
  
### <a name="to-enable-edi-status-reports-for-an-agreement"></a><span data-ttu-id="bf002-114">为协议启用 EDI 状态报告</span><span class="sxs-lookup"><span data-stu-id="bf002-114">To enable EDI status reports for an agreement</span></span>  
  
1. <span data-ttu-id="bf002-115">在中**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**控制台中，单击**方**节点下的[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]并**BizTalk 组**节点。</span><span class="sxs-lookup"><span data-stu-id="bf002-115">In the **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration** Console, click the **Parties** node under the [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] and **BizTalk Group** nodes.</span></span>  
  
2. <span data-ttu-id="bf002-116">在中**参与方和业务配置文件**窗格中，单击包含你想要启用状态报告的 X12 或 EDIFACT 协议的参与方。</span><span class="sxs-lookup"><span data-stu-id="bf002-116">In the **Parties and Business Profiles** pane, click the party that has the X12 or EDIFACT agreement for which you want to enable status reporting.</span></span>  
  
3. <span data-ttu-id="bf002-117">在中**协议**部分中，右键单击你想要启用状态报告，然后单击的协议**属性**。</span><span class="sxs-lookup"><span data-stu-id="bf002-117">In the **Agreements** section, right-click the agreement for which you want to enable status reporting and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="bf002-118">在中**常规**选项卡上，在**公用主机设置**部分中，单击**打开报告**。</span><span class="sxs-lookup"><span data-stu-id="bf002-118">In the **General** tab, in the **Common Host Settings** section, click **Turn ON Reporting**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="bf002-119">此步骤会导致消息条目进入状态报告 UI 中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="bf002-119">This step causes message entries to be entered in the status report UI in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
5. <span data-ttu-id="bf002-120">选择**存储事务集/负载以用于报告**来存储事务集跟踪 (BizTalkDTADb) 数据库的 EDI 表中。</span><span class="sxs-lookup"><span data-stu-id="bf002-120">Select **Store transaction set/payload for reporting** to store transaction sets in the EDI tables of the tracking (BizTalkDTADb) database.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="bf002-121">如果您启用的事务集存储在激活批处理业务流程实例，将不存储创建的批的事务集。</span><span class="sxs-lookup"><span data-stu-id="bf002-121">If you enable storage of transaction sets while an instance of the batching orchestration is activated, transaction sets will not be stored for the batch being created.</span></span> <span data-ttu-id="bf002-122">但是，如果您禁用事务集存储在激活批处理业务流程实例，将在批处理过程禁用存储。</span><span class="sxs-lookup"><span data-stu-id="bf002-122">However, if you disable storage of transaction sets while an instance of the batching orchestration is activated, the storage will be disabled in the middle of the batching.</span></span>  
  
6. <span data-ttu-id="bf002-123">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="bf002-123">Click **OK**.</span></span>  
  
7. <span data-ttu-id="bf002-124">重新启动 BizTalk 服务 （在计算机管理对话框中）。</span><span class="sxs-lookup"><span data-stu-id="bf002-124">Restart the BizTalk Service (in the Computer Management dialog box).</span></span> <span data-ttu-id="bf002-125">如果你的解决方案中正在使用 AS2EdiReceive 管道或 AS2EdiSend 管道，重新启动 IIS Admin 服务 (使用*iisreset*命令)，因此也。</span><span class="sxs-lookup"><span data-stu-id="bf002-125">If the AS2EdiReceive pipeline or the AS2EdiSend pipeline is being used in your solution, restart the IIS Admin service (using the *iisreset* command), as well.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="bf002-126">BizTalk 服务需要重新启动后 EDI 状态报告已激活或停用的更改才能生效。</span><span class="sxs-lookup"><span data-stu-id="bf002-126">The BizTalk Service needs to be restarted after EDI status reporting has been activated or deactivated for the change to take effect.</span></span> <span data-ttu-id="bf002-127">如果你的解决方案中使用 AS2EdiReceive 或 AS2EdiSend 管道，BizTalk 服务和 IIS 服务需要更改才能生效，必须重新启动。</span><span class="sxs-lookup"><span data-stu-id="bf002-127">If the AS2EdiReceive or AS2EdiSend pipeline is being used in your solution, both the BizTalk Service and the IIS service need to be restarted for the change to take effect.</span></span> <span data-ttu-id="bf002-128">请注意，这不是必要时启用 AS2 状态报告。</span><span class="sxs-lookup"><span data-stu-id="bf002-128">Note that this is not necessary when enabling AS2 status reporting.</span></span>  
  
### <a name="to-enable-edi-status-reports-for-fallback-agreements"></a><span data-ttu-id="bf002-129">为备用协议启用 EDI 状态报告</span><span class="sxs-lookup"><span data-stu-id="bf002-129">To enable EDI status reports for fallback agreements</span></span>  
  
1. <span data-ttu-id="bf002-130">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**节点，右键单击**参与方**，然后选择**X12 后备设置**或**EDIFACT 后备设置**。</span><span class="sxs-lookup"><span data-stu-id="bf002-130">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group** nodes, right-click **Parties**, and select **X12 Fallback Settings** or **EDIFACT Fallback Settings**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="bf002-131">当在备用协议中配置状态报告时，配置仅适用于任何协议确定消息。</span><span class="sxs-lookup"><span data-stu-id="bf002-131">When you configure status reports in the fallback agreements, the configuration only applies when no agreement has been determined for a message.</span></span>  
  
2. <span data-ttu-id="bf002-132">在中**回退设置常规页**选项卡上，单击**激活 EDI 报告**。</span><span class="sxs-lookup"><span data-stu-id="bf002-132">In the **Fallback Settings General Pages** tab, click **Activate EDI reporting**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="bf002-133">此步骤会导致消息条目进入状态报告 UI 中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="bf002-133">This step causes message entries to be entered in the status report UI in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
3. <span data-ttu-id="bf002-134">选择**存储事务集/负载以用于报告**来存储事务集跟踪 (BizTalkDTADb) 数据库的 EDI 表中。</span><span class="sxs-lookup"><span data-stu-id="bf002-134">Select **Store transaction set/payload for reporting** to store transaction sets in the EDI tables of the tracking (BizTalkDTADb) database.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="bf002-135">**对于 EDIFACT 编码的消息**:如果选择此属性，还必须在 EDI 全局属性对话框中的 UNB 段定义页中选择 UNB3.2 字段 （代码限定符） 的值。</span><span class="sxs-lookup"><span data-stu-id="bf002-135">**For EDIFACT-encoded messages**: If you select this property, you must also select a value for the UNB3.2 field (Code qualifier) in the UNB Segment Definition page of the EDI Global Properties dialog box.</span></span> <span data-ttu-id="bf002-136">默认情况下，未设置此属性并且会挂起该交换，如果**存储事务集/负载以用于报告**选择，但不是选择 UNB3.2 的值。</span><span class="sxs-lookup"><span data-stu-id="bf002-136">This property is not set by default, and the interchange will be suspended if **Store transaction set/payload for reporting** is selected, but a value is not selected for UNB3.2.</span></span>  
  
4. <span data-ttu-id="bf002-137">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="bf002-137">Click **OK**.</span></span>  
  
### <a name="to-enable-as2-status-reports"></a><span data-ttu-id="bf002-138">若要启用 AS2 状态报告</span><span class="sxs-lookup"><span data-stu-id="bf002-138">To enable AS2 status reports</span></span>  
  
1. <span data-ttu-id="bf002-139">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]并**BizTalk 组**节点，单击**参与方**节点。</span><span class="sxs-lookup"><span data-stu-id="bf002-139">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] and **BizTalk Group** nodes, click the **Parties** node.</span></span>  
  
2. <span data-ttu-id="bf002-140">在中**参与方和业务配置文件**窗格中，单击包含你想要启用状态报告的 X12 或 EDIFACT 协议的参与方。</span><span class="sxs-lookup"><span data-stu-id="bf002-140">In the **Parties and Business Profiles** pane, click the party that has the X12 or EDIFACT agreement for which you want to enable status reporting.</span></span>  
  
3. <span data-ttu-id="bf002-141">在中**协议**部分中，右键单击你想要启用状态报告，然后单击的协议**属性**。</span><span class="sxs-lookup"><span data-stu-id="bf002-141">In the **Agreements** section, right-click the agreement for which you want to enable status reporting and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="bf002-142">在中**公用主机设置**部分中，单击**打开报告**。</span><span class="sxs-lookup"><span data-stu-id="bf002-142">In the **Common Host Settings** section, click **Turn ON Reporting**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="bf002-143">此步骤会导致消息条目进入状态报告 UI 中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="bf002-143">This step causes message entries to be entered in the status report UI in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
5. <span data-ttu-id="bf002-144">在单向协议选项卡中的**协议属性**对话框中，单击**接收方消息跟踪 (NRR)** 页。</span><span class="sxs-lookup"><span data-stu-id="bf002-144">In the one-way agreement tab of the **Agreement Properties** dialog box, click the **Receiver Message Tracking (NRR)** page.</span></span>  
  
6. <span data-ttu-id="bf002-145">在中**接收方消息跟踪 (NRR)** 页上，单击**已为入站编码 AS2 消息启用 NRR**以启用显示传入消息的传输格式。</span><span class="sxs-lookup"><span data-stu-id="bf002-145">In the **Receiver Message Tracking (NRR)** page, click **NRR enabled for inbound encoded AS2 messages** to enable display of the wire format of incoming messages.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="bf002-146">当您右键单击 AS2 消息和相关 MDN 状态页中的消息，然后单击时，将显示该消息的传输格式**消息传输格式**。</span><span class="sxs-lookup"><span data-stu-id="bf002-146">The wire format of the message will be displayed when you right-click the message in the AS2 Message and Correlated MDN Status Page, and then click **Message Wire Format**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="bf002-147">**打开报告**属性必须选择要启用不可否认数据库中的任何数据存储。</span><span class="sxs-lookup"><span data-stu-id="bf002-147">The **Turn ON Reporting** property must be selected for you to enable storage of any data in the non-repudiation database.</span></span> <span data-ttu-id="bf002-148">如果选择此属性或任何启用的不可否认数据库中存储的其他属性，则将显示一个弹出窗口，提示您进行激活 AS2 报告。</span><span class="sxs-lookup"><span data-stu-id="bf002-148">If you select this or any of the other properties enabling storage in the non-repudiation database, a popup will be displayed prompting you to activate AS2 reporting.</span></span> <span data-ttu-id="bf002-149">如果单击**是**，将为你激活 AS2 报告。</span><span class="sxs-lookup"><span data-stu-id="bf002-149">If you click **Yes**, AS2 reporting will be activated for you.</span></span>  
  
7. <span data-ttu-id="bf002-150">在中**接收方消息跟踪 (NRR)** 页上，单击**已为入站解码 AS2 消息启用 NRR**以启用显示传入消息的解码格式。</span><span class="sxs-lookup"><span data-stu-id="bf002-150">In the **Receiver Message Tracking (NRR)** page, click **NRR enabled for inbound decoded AS2 messages** to enable display of the decoded format of incoming messages.</span></span>  
  
8. <span data-ttu-id="bf002-151">在中**接收方消息跟踪 (NRR)** 页上，单击**对出站 MDN 启用 NRR**以启用显示对传入消息的 MDN 响应。</span><span class="sxs-lookup"><span data-stu-id="bf002-151">In the **Receiver Message Tracking (NRR)** page, click **NRR enabled for outbound MDN** to enable display of MDN responses to incoming messages.</span></span>  
  
9. <span data-ttu-id="bf002-152">在单向协议选项卡中的**协议属性**对话框中，单击**发件人消息跟踪 (NRR)** 页。</span><span class="sxs-lookup"><span data-stu-id="bf002-152">In the one-way agreement tab of the **Agreement Properties** dialog box, click the **Sender Message Tracking (NRR)** page.</span></span>  
  
10. <span data-ttu-id="bf002-153">在中**发件人消息跟踪 (NRR)** 页上，单击**已为出站编码 AS2 消息启用 NRR**以启用显示传出消息的传输格式。</span><span class="sxs-lookup"><span data-stu-id="bf002-153">In the **Sender Message Tracking (NRR)** page, click **NRR enabled for outbound encoded AS2 messages** to enable display of the wire format of outgoing messages.</span></span>  
  
11. <span data-ttu-id="bf002-154">在中**发件人消息跟踪 (NRR)** 页上，单击**已为解码后的出站 AS2 消息启用 NRR**以启用显示传出消息的解码格式。</span><span class="sxs-lookup"><span data-stu-id="bf002-154">In the **Sender Message Tracking (NRR)** page, click **NRR enabled for outbound decoded AS2 messages** to enable display of the decoded format of outgoing messages.</span></span>  
  
12. <span data-ttu-id="bf002-155">在中**发件人消息跟踪 (NRR)** 页上，单击**对入站 MDN 启用 NRR**以启用对传出消息的 MDN 响应显示。</span><span class="sxs-lookup"><span data-stu-id="bf002-155">In the **Sender Message Tracking (NRR)** page, click **NRR enabled for inbound MDN** to enable display of MDN responses to outgoing messages.</span></span>  
  
13. <span data-ttu-id="bf002-156">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="bf002-156">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf002-157">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf002-157">See Also</span></span>  
 <span data-ttu-id="bf002-158">[监视 EDI 和 AS2 解决方案](../core/monitoring-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="bf002-158">[Monitoring EDI and AS2 Solutions](../core/monitoring-edi-and-as2-solutions.md) </span></span>  
 <span data-ttu-id="bf002-159">[配置 EDI 和 AS2 状态报告](../core/configuring-an-edi-and-as2-status-report.md) </span><span class="sxs-lookup"><span data-stu-id="bf002-159">[Configuring an EDI and AS2 Status Report](../core/configuring-an-edi-and-as2-status-report.md) </span></span>  
 [<span data-ttu-id="bf002-160">EDI 和 AS2 状态报告</span><span class="sxs-lookup"><span data-stu-id="bf002-160">EDI and AS2 Status Reporting</span></span>](../core/edi-and-as2-status-reporting.md)   