---
title: 显示 EDI 或 AS2 状态报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60968c3d-6329-411f-9f10-1dd4a6cc9d79
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 699218479eb0d8bb5a37eb21afc4eb814cf51233
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389354"
---
# <a name="displaying-an-edi-or-as2-status-report"></a><span data-ttu-id="32ea8-102">显示 EDI 或 AS2 状态报告</span><span class="sxs-lookup"><span data-stu-id="32ea8-102">Displaying an EDI or AS2 Status Report</span></span>
<span data-ttu-id="32ea8-103">启用 EDI 和 AS2 状态报告后，将有权访问以下状态报告：</span><span class="sxs-lookup"><span data-stu-id="32ea8-103">When EDI and AS2 status reports are enabled, you will have access to the following status reports:</span></span>  
  
|<span data-ttu-id="32ea8-104">类型的报告</span><span class="sxs-lookup"><span data-stu-id="32ea8-104">Type of Report</span></span>|<span data-ttu-id="32ea8-105">更高级别的状态报告</span><span class="sxs-lookup"><span data-stu-id="32ea8-105">Higher-level status report</span></span>|<span data-ttu-id="32ea8-106">较低级别状态报告</span><span class="sxs-lookup"><span data-stu-id="32ea8-106">Lower-level status report</span></span>|  
|--------------------|---------------------------------|--------------------------------|  
|<span data-ttu-id="32ea8-107">EDI</span><span class="sxs-lookup"><span data-stu-id="32ea8-107">EDI</span></span>|<span data-ttu-id="32ea8-108">EDI 交换和相关 ACK 状态</span><span class="sxs-lookup"><span data-stu-id="32ea8-108">EDI Interchange and Correlated ACK Status</span></span>|<span data-ttu-id="32ea8-109">-交换状态和确认详细信息</span><span class="sxs-lookup"><span data-stu-id="32ea8-109">- Interchange Status and ACK Details</span></span><br /><br /> <span data-ttu-id="32ea8-110">--事务集详细信息</span><span class="sxs-lookup"><span data-stu-id="32ea8-110">- Transaction Set Details</span></span><br /><br /> <span data-ttu-id="32ea8-111">EDI 消息内容</span><span class="sxs-lookup"><span data-stu-id="32ea8-111">- EDI Message Content</span></span>|  
|<span data-ttu-id="32ea8-112">EDI</span><span class="sxs-lookup"><span data-stu-id="32ea8-112">EDI</span></span>|<span data-ttu-id="32ea8-113">批处理状态</span><span class="sxs-lookup"><span data-stu-id="32ea8-113">Batch Status</span></span>|-|  
|<span data-ttu-id="32ea8-114">EDI</span><span class="sxs-lookup"><span data-stu-id="32ea8-114">EDI</span></span>|<span data-ttu-id="32ea8-115">交换聚合报告</span><span class="sxs-lookup"><span data-stu-id="32ea8-115">Interchange Aggregation Report</span></span>|-|  
|<span data-ttu-id="32ea8-116">EDI</span><span class="sxs-lookup"><span data-stu-id="32ea8-116">EDI</span></span>|<span data-ttu-id="32ea8-117">事务集聚合报告</span><span class="sxs-lookup"><span data-stu-id="32ea8-117">Transaction Set Aggregation Report</span></span>|-|  
|<span data-ttu-id="32ea8-118">AS2</span><span class="sxs-lookup"><span data-stu-id="32ea8-118">AS2</span></span>|<span data-ttu-id="32ea8-119">AS2 消息和相关的 MDN 状态</span><span class="sxs-lookup"><span data-stu-id="32ea8-119">AS2 Message and Correlated MDN Status</span></span>|<span data-ttu-id="32ea8-120">AS2 消息内容</span><span class="sxs-lookup"><span data-stu-id="32ea8-120">AS2 Message Content</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="32ea8-121">先决条件</span><span class="sxs-lookup"><span data-stu-id="32ea8-121">Prerequisites</span></span>  
 <span data-ttu-id="32ea8-122">在本主题中执行该过程的先决条件如下：</span><span class="sxs-lookup"><span data-stu-id="32ea8-122">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
- <span data-ttu-id="32ea8-123">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组才能自定义任何状态报告。</span><span class="sxs-lookup"><span data-stu-id="32ea8-123">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to customize any of the status reports.</span></span>  
  
- <span data-ttu-id="32ea8-124">如果作为的成员身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Operators 组可以显示只读状态报告。</span><span class="sxs-lookup"><span data-stu-id="32ea8-124">If you are logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators group, you can display read-only status reports.</span></span>  
  
## <a name="display-an-edi-or-as2-status-report"></a><span data-ttu-id="32ea8-125">显示 EDI 或 AS2 状态报告</span><span class="sxs-lookup"><span data-stu-id="32ea8-125">Display an EDI or AS2 status report</span></span>  
  
1. <span data-ttu-id="32ea8-126">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**BizTalk 组**节点。</span><span class="sxs-lookup"><span data-stu-id="32ea8-126">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **BizTalk Group** node.</span></span>  
  
2. <span data-ttu-id="32ea8-127">在中**组中心**选项卡**组概述**页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，转到页面底部。</span><span class="sxs-lookup"><span data-stu-id="32ea8-127">In the **Group Hub** tab of the **Group Overview** page of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, move to the bottom of the page.</span></span>  
  
3. <span data-ttu-id="32ea8-128">若要显示**EDI 交换和相关 ACK 状态**报告，则会继续，如下所示：</span><span class="sxs-lookup"><span data-stu-id="32ea8-128">To display the **EDI Interchange and Correlated ACK Status** report, proceed as follows:</span></span>  
  
   1.  <span data-ttu-id="32ea8-129">单击**EDI 交换和相关 ACK 状态**中**EDI 状态报告**区域**组中心**选项卡。</span><span class="sxs-lookup"><span data-stu-id="32ea8-129">Click **EDI Interchange and Correlated ACK Status** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
   2.  <span data-ttu-id="32ea8-130">若要显示交换及其相关的确认的详细信息，请右键单击查询结果中的条目**EDI 交换和相关 ACK 状态**报告，然后依次**交换状态和确认详细信息**。</span><span class="sxs-lookup"><span data-stu-id="32ea8-130">To display details of an interchange and its correlated acknowledgments, right-click an entry in the query results of the **EDI Interchange and Correlated ACK Status** report, and then click **Interchange status and ack details**.</span></span>  
  
   3.  <span data-ttu-id="32ea8-131">若要显示事务集的详细信息，请关闭交换状态和确认详细信息报告，返回到**EDI 交换和相关 ACK 状态**的详细信息报表。</span><span class="sxs-lookup"><span data-stu-id="32ea8-131">To display details of a transaction set, close the Interchange status and ack details report, returning to the **EDI Interchange and Correlated ACK Status** details report.</span></span> <span data-ttu-id="32ea8-132">右键单击查询结果中的条目，然后单击**事务集详细信息**。</span><span class="sxs-lookup"><span data-stu-id="32ea8-132">Right-click an entry in the query results, and then click **Transaction Set Details**.</span></span>  
  
   4.  <span data-ttu-id="32ea8-133">若要显示有关的标头和负载的事务集的详细信息，请右键单击中的条目**事务集详细信息**报告，然后依次**查看事务集内容**。</span><span class="sxs-lookup"><span data-stu-id="32ea8-133">To display details about the headers and payload of a transaction set, right-click an entry in the **Transaction Set Details** report, and then click **View Transaction Set Content**.</span></span>  
  
   5.  <span data-ttu-id="32ea8-134">若要显示包含事务集的交换有关的数据，请右键单击中的条目**事务集详细信息**报告，然后依次**交换 /ACK 状态**。</span><span class="sxs-lookup"><span data-stu-id="32ea8-134">To display data about the interchange containing the transaction set, right-click an entry in the **Transaction Set Details** report, and then click **Interchange/ACK Status**.</span></span> <span data-ttu-id="32ea8-135">包含事务集的交换将在交换 /ACK 状态报告中突出显示。</span><span class="sxs-lookup"><span data-stu-id="32ea8-135">The interchange containing the transaction set will be highlighted in the Interchange/ACK Status report.</span></span>  
  
4. <span data-ttu-id="32ea8-136">若要显示**批状态**报告，则会继续，如下所示：</span><span class="sxs-lookup"><span data-stu-id="32ea8-136">To display the **Batch Status** report, proceed as follows:</span></span>  
  
   1.  <span data-ttu-id="32ea8-137">单击**批状态**中**EDI 状态报告**区域**组中心**选项卡。</span><span class="sxs-lookup"><span data-stu-id="32ea8-137">Click **Batch Status** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
   2.  <span data-ttu-id="32ea8-138">若要显示与中的批处理条目相关联的已完成的批处理**批状态**报告，右键单击该条目，然后单击**完成批处理**。</span><span class="sxs-lookup"><span data-stu-id="32ea8-138">To display the completed batches associated with a batch entry in the **Batch Status** report, right-click the entry and then click **Completed Batches**.</span></span>  
  
   3.  <span data-ttu-id="32ea8-139">若要显示有关已完成的批处理交换的数据，请右键单击中的交换**已完成的批处理**报告，然后依次**交换 /ACK 状态**。</span><span class="sxs-lookup"><span data-stu-id="32ea8-139">To display data about a completed batched interchange, right-click the interchange in the **Completed Batch** report, and then click **Interchange/ACK Status**.</span></span> <span data-ttu-id="32ea8-140">为批处理交换的条目将在交换 /ACK 状态报告中突出显示。</span><span class="sxs-lookup"><span data-stu-id="32ea8-140">The entry for the batched interchange will be highlighted in the Interchange/ACK Status report.</span></span>  
  
5. <span data-ttu-id="32ea8-141">若要显示**交换聚合报告**，继续操作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="32ea8-141">To display the **Interchange Aggregation Report**, proceed as follows:</span></span>  
  
   -   <span data-ttu-id="32ea8-142">单击**交换聚合报告**中**EDI 状态报告**区域**组中心**选项卡。</span><span class="sxs-lookup"><span data-stu-id="32ea8-142">Click **Interchange Aggregation Report** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
6. <span data-ttu-id="32ea8-143">若要显示**事务集聚合报告**，继续操作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="32ea8-143">To display the **Transaction Set Aggregation Report**, proceed as follows:</span></span>  
  
   -   <span data-ttu-id="32ea8-144">单击**事务集聚合报告**中**EDI 状态报告**区域**组中心**选项卡。</span><span class="sxs-lookup"><span data-stu-id="32ea8-144">Click **Transaction Set Aggregation Report** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
7. <span data-ttu-id="32ea8-145">若要显示**AS2 消息和相关 MDN 状态**报告，则会继续，如下所示：</span><span class="sxs-lookup"><span data-stu-id="32ea8-145">To display the **AS2 Message and Correlated MDN Status** report, proceed as follows:</span></span>  
  
   1.  <span data-ttu-id="32ea8-146">单击**AS2 消息和相关 MDN 状态**中**EDIINT 状态报告**区域**组中心**选项卡。</span><span class="sxs-lookup"><span data-stu-id="32ea8-146">Click **AS2 Message and Correlated MDN Status** in the **EDIINT Status Reports** area of the **Group Hub** tab.</span></span>  
  
   2.  <span data-ttu-id="32ea8-147">若要显示 AS2 消息中的 EDI 交换的状态，请右键单击中的条目**AS2 消息和相关 MDN 状态**报告，然后依次**交换 /ACK 状态**。</span><span class="sxs-lookup"><span data-stu-id="32ea8-147">To display the status of the EDI interchange in an AS2 message, right-click an entry in the **AS2 Message and Correlated MDN Status** report, and then click **Interchange/ACK Status**.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="32ea8-148">有关如何关联起来 EDI 及 AS2 的状态的详细信息，请参阅的"关联 AS2 消息与其 EDI 负载"部分[AS2 消息和相关 MDN 状态报告](../core/as2-message-and-correlated-mdn-status-report.md)。</span><span class="sxs-lookup"><span data-stu-id="32ea8-148">For more information on how EDI status and AS2 status are correlated, see the "Correlating an AS2 Message with its EDI Payload" section of [AS2 Message and Correlated MDN Status Report](../core/as2-message-and-correlated-mdn-status-report.md).</span></span>  
  
   3.  <span data-ttu-id="32ea8-149">要以传输格式显示 AS2 消息，请右键单击 AS2/MDN 状态报告中中的条目，然后单击**消息传输格式**。</span><span class="sxs-lookup"><span data-stu-id="32ea8-149">To display an AS2 message in wire format, right-click an entry in the AS2/MDN Status report, and then click **Message Wire Format**.</span></span>  
  
   4.  <span data-ttu-id="32ea8-150">若要显示 AS2 消息解码格式中，右键单击 AS2/MDN 状态报告中中的条目，然后单击**消息解码格式**。</span><span class="sxs-lookup"><span data-stu-id="32ea8-150">To display an AS2 message in decoded format, right-click an entry in the AS2/MDN Status report, and then click **Message Decoded Format**.</span></span>  
  
   5.  <span data-ttu-id="32ea8-151">要显示 MDN 消息，请右键单击 AS2/MDN 状态报告中中的条目，然后单击**Mdn 消息**。</span><span class="sxs-lookup"><span data-stu-id="32ea8-151">To display an MDN message, right-click an entry in the AS2/MDN Status report, and then click **Mdn Message**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32ea8-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="32ea8-152">See Also</span></span>  
 <span data-ttu-id="32ea8-153">[监视 EDI 和 AS2 解决方案](../core/monitoring-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="32ea8-153">[Monitoring EDI and AS2 Solutions](../core/monitoring-edi-and-as2-solutions.md) </span></span>  
 <span data-ttu-id="32ea8-154">[EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md) </span><span class="sxs-lookup"><span data-stu-id="32ea8-154">[EDI and AS2 Status Reporting](../core/edi-and-as2-status-reporting.md) </span></span>  
 <span data-ttu-id="32ea8-155">[启用 EDI 和 AS2 状态报告](../core/enabling-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="32ea8-155">[Enabling EDI and AS2 Status Reports](../core/enabling-edi-and-as2-status-reports.md) </span></span>  
 [<span data-ttu-id="32ea8-156">配置 EDI 和 AS2 状态报告</span><span class="sxs-lookup"><span data-stu-id="32ea8-156">Configuring an EDI and AS2 Status Report</span></span>](../core/configuring-an-edi-and-as2-status-report.md)