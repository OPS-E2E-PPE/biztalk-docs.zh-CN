---
title: 显示的 EDI 或 AS2 状态报告 |Microsoft 文档
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
ms.openlocfilehash: 0564a5c5d904a217ac406befebd3d7c742dc00c1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22242333"
---
# <a name="displaying-an-edi-or-as2-status-report"></a><span data-ttu-id="de187-102">显示 EDI 或 AS2 状态报告</span><span class="sxs-lookup"><span data-stu-id="de187-102">Displaying an EDI or AS2 Status Report</span></span>
<span data-ttu-id="de187-103">EDI 和 AS2 状态报告启用后，您可访问以下状态报告：</span><span class="sxs-lookup"><span data-stu-id="de187-103">When EDI and AS2 status reports are enabled, you will have access to the following status reports:</span></span>  
  
|<span data-ttu-id="de187-104">报告类型</span><span class="sxs-lookup"><span data-stu-id="de187-104">Type of Report</span></span>|<span data-ttu-id="de187-105">级别更高的状态报告</span><span class="sxs-lookup"><span data-stu-id="de187-105">Higher-level status report</span></span>|<span data-ttu-id="de187-106">级别更低的状态报告</span><span class="sxs-lookup"><span data-stu-id="de187-106">Lower-level status report</span></span>|  
|--------------------|---------------------------------|--------------------------------|  
|<span data-ttu-id="de187-107">EDI</span><span class="sxs-lookup"><span data-stu-id="de187-107">EDI</span></span>|<span data-ttu-id="de187-108">EDI 交换和相关 ACK 状态</span><span class="sxs-lookup"><span data-stu-id="de187-108">EDI Interchange and Correlated ACK Status</span></span>|<span data-ttu-id="de187-109">-交换状态和 ACK 详细信息</span><span class="sxs-lookup"><span data-stu-id="de187-109">- Interchange Status and ACK Details</span></span><br /><br /> <span data-ttu-id="de187-110">事务集详细信息</span><span class="sxs-lookup"><span data-stu-id="de187-110">- Transaction Set Details</span></span><br /><br /> <span data-ttu-id="de187-111">EDI 消息内容</span><span class="sxs-lookup"><span data-stu-id="de187-111">- EDI Message Content</span></span>|  
|<span data-ttu-id="de187-112">EDI</span><span class="sxs-lookup"><span data-stu-id="de187-112">EDI</span></span>|<span data-ttu-id="de187-113">批状态</span><span class="sxs-lookup"><span data-stu-id="de187-113">Batch Status</span></span>|-|  
|<span data-ttu-id="de187-114">EDI</span><span class="sxs-lookup"><span data-stu-id="de187-114">EDI</span></span>|<span data-ttu-id="de187-115">交换聚合报表</span><span class="sxs-lookup"><span data-stu-id="de187-115">Interchange Aggregation Report</span></span>|-|  
|<span data-ttu-id="de187-116">EDI</span><span class="sxs-lookup"><span data-stu-id="de187-116">EDI</span></span>|<span data-ttu-id="de187-117">事务集聚合报告</span><span class="sxs-lookup"><span data-stu-id="de187-117">Transaction Set Aggregation Report</span></span>|-|  
|<span data-ttu-id="de187-118">AS2</span><span class="sxs-lookup"><span data-stu-id="de187-118">AS2</span></span>|<span data-ttu-id="de187-119">AS2 消息和相关 MDN 状态</span><span class="sxs-lookup"><span data-stu-id="de187-119">AS2 Message and Correlated MDN Status</span></span>|<span data-ttu-id="de187-120">AS2 消息内容</span><span class="sxs-lookup"><span data-stu-id="de187-120">AS2 Message Content</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="de187-121">先决条件</span><span class="sxs-lookup"><span data-stu-id="de187-121">Prerequisites</span></span>  
 <span data-ttu-id="de187-122">以下为执行本主题中的过程的前提条件：</span><span class="sxs-lookup"><span data-stu-id="de187-122">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="de187-123">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录，才能自定义任何状态报告。</span><span class="sxs-lookup"><span data-stu-id="de187-123">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to customize any of the status reports.</span></span>  
  
-   <span data-ttu-id="de187-124">如果以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 操作员组成员的身份登录，可以显示只读状态报告。</span><span class="sxs-lookup"><span data-stu-id="de187-124">If you are logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators group, you can display read-only status reports.</span></span>  
  
## <a name="display-an-edi-or-as2-status-report"></a><span data-ttu-id="de187-125">显示 EDI 或 AS2 状态报表</span><span class="sxs-lookup"><span data-stu-id="de187-125">Display an EDI or AS2 status report</span></span>  
  
1.  <span data-ttu-id="de187-126">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**BizTalk 组**节点。</span><span class="sxs-lookup"><span data-stu-id="de187-126">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **BizTalk Group** node.</span></span>  
  
2.  <span data-ttu-id="de187-127">在**组中心数据库**选项卡**组概述**页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，移动到页面底部。</span><span class="sxs-lookup"><span data-stu-id="de187-127">In the **Group Hub** tab of the **Group Overview** page of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, move to the bottom of the page.</span></span>  
  
3.  <span data-ttu-id="de187-128">若要显示**EDI 交换和关联 ACK 状态**报告，则会继续，如下所示：</span><span class="sxs-lookup"><span data-stu-id="de187-128">To display the **EDI Interchange and Correlated ACK Status** report, proceed as follows:</span></span>  
  
    1.  <span data-ttu-id="de187-129">单击**EDI 交换和关联 ACK 状态**中**EDI 状态报告**区域**组中心数据库**选项卡。</span><span class="sxs-lookup"><span data-stu-id="de187-129">Click **EDI Interchange and Correlated ACK Status** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
    2.  <span data-ttu-id="de187-130">若要显示将交换和其关联的确认的详细信息，请右键单击的查询结果中某个条目**EDI 交换和关联的 ACK 状态**报告，并依次**交换状态和 ack详细信息**。</span><span class="sxs-lookup"><span data-stu-id="de187-130">To display details of an interchange and its correlated acknowledgments, right-click an entry in the query results of the **EDI Interchange and Correlated ACK Status** report, and then click **Interchange status and ack details**.</span></span>  
  
    3.  <span data-ttu-id="de187-131">若要显示的事务集的详细信息，请关闭交换状态和 ack 的详细信息报表，将返回到**EDI 交换和关联 ACK 状态**的详细信息报表。</span><span class="sxs-lookup"><span data-stu-id="de187-131">To display details of a transaction set, close the Interchange status and ack details report, returning to the **EDI Interchange and Correlated ACK Status** details report.</span></span> <span data-ttu-id="de187-132">右键单击在查询结果中，某个条目，然后单击**设置事务的详细信息**。</span><span class="sxs-lookup"><span data-stu-id="de187-132">Right-click an entry in the query results, and then click **Transaction Set Details**.</span></span>  
  
    4.  <span data-ttu-id="de187-133">若要显示的标头和负载的事务集详细信息，请右键单击中的条目**设置事务的详细信息**报告，并依次**查看事务设置内容**。</span><span class="sxs-lookup"><span data-stu-id="de187-133">To display details about the headers and payload of a transaction set, right-click an entry in the **Transaction Set Details** report, and then click **View Transaction Set Content**.</span></span>  
  
    5.  <span data-ttu-id="de187-134">若要显示有关该交换包含事务集数据，右键单击中的条目**设置事务的详细信息**报告，并依次**交换/ACK 状态**。</span><span class="sxs-lookup"><span data-stu-id="de187-134">To display data about the interchange containing the transaction set, right-click an entry in the **Transaction Set Details** report, and then click **Interchange/ACK Status**.</span></span> <span data-ttu-id="de187-135">包含事务集的交换会在“交换/ACK 状态”报告中突出显示。</span><span class="sxs-lookup"><span data-stu-id="de187-135">The interchange containing the transaction set will be highlighted in the Interchange/ACK Status report.</span></span>  
  
4.  <span data-ttu-id="de187-136">若要显示**批处理状态**报告，则会继续，如下所示：</span><span class="sxs-lookup"><span data-stu-id="de187-136">To display the **Batch Status** report, proceed as follows:</span></span>  
  
    1.  <span data-ttu-id="de187-137">单击**批处理状态**中**EDI 状态报告**区域**组中心数据库**选项卡。</span><span class="sxs-lookup"><span data-stu-id="de187-137">Click **Batch Status** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
    2.  <span data-ttu-id="de187-138">若要显示与中的批处理项关联的已完成的批**批处理状态**报告，右键单击该条目，然后单击**完成批**。</span><span class="sxs-lookup"><span data-stu-id="de187-138">To display the completed batches associated with a batch entry in the **Batch Status** report, right-click the entry and then click **Completed Batches**.</span></span>  
  
    3.  <span data-ttu-id="de187-139">若要显示有关已完成的批处理的交换的数据，右键单击在交换**完成批处理**报告，并依次**交换/ACK 状态**。</span><span class="sxs-lookup"><span data-stu-id="de187-139">To display data about a completed batched interchange, right-click the interchange in the **Completed Batch** report, and then click **Interchange/ACK Status**.</span></span> <span data-ttu-id="de187-140">批处理交换的条目会在“交换/ACK 状态”报告中突出显示。</span><span class="sxs-lookup"><span data-stu-id="de187-140">The entry for the batched interchange will be highlighted in the Interchange/ACK Status report.</span></span>  
  
5.  <span data-ttu-id="de187-141">若要显示**交换聚合报表**，继续，如下所示：</span><span class="sxs-lookup"><span data-stu-id="de187-141">To display the **Interchange Aggregation Report**, proceed as follows:</span></span>  
  
    -   <span data-ttu-id="de187-142">单击**交换聚合报表**中**EDI 状态报告**区域**组中心数据库**选项卡。</span><span class="sxs-lookup"><span data-stu-id="de187-142">Click **Interchange Aggregation Report** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
6.  <span data-ttu-id="de187-143">若要显示**事务组聚合报表**，继续，如下所示：</span><span class="sxs-lookup"><span data-stu-id="de187-143">To display the **Transaction Set Aggregation Report**, proceed as follows:</span></span>  
  
    -   <span data-ttu-id="de187-144">单击**事务组聚合报表**中**EDI 状态报告**区域**组中心数据库**选项卡。</span><span class="sxs-lookup"><span data-stu-id="de187-144">Click **Transaction Set Aggregation Report** in the **EDI Status Reports** area of the **Group Hub** tab.</span></span>  
  
7.  <span data-ttu-id="de187-145">若要显示**AS2 消息和相关 MDN 状态**报告，则会继续，如下所示：</span><span class="sxs-lookup"><span data-stu-id="de187-145">To display the **AS2 Message and Correlated MDN Status** report, proceed as follows:</span></span>  
  
    1.  <span data-ttu-id="de187-146">单击**AS2 消息和相关 MDN 状态**中**EDIINT 状态报告**区域**组中心数据库**选项卡。</span><span class="sxs-lookup"><span data-stu-id="de187-146">Click **AS2 Message and Correlated MDN Status** in the **EDIINT Status Reports** area of the **Group Hub** tab.</span></span>  
  
    2.  <span data-ttu-id="de187-147">若要显示的状态的 EDI 交换 AS2 消息中，右键单击中的条目**AS2 消息和相关 MDN 状态**报告，并依次**交换/ACK 状态**。</span><span class="sxs-lookup"><span data-stu-id="de187-147">To display the status of the EDI interchange in an AS2 message, right-click an entry in the **AS2 Message and Correlated MDN Status** report, and then click **Interchange/ACK Status**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="de187-148">有关如何关联起来 EDI 状态和 AS2 状态的详细信息，请参阅的"关联 AS2 消息与及其 EDI 负载"部分的[AS2 消息和相关 MDN 状态报表](../core/as2-message-and-correlated-mdn-status-report.md)。</span><span class="sxs-lookup"><span data-stu-id="de187-148">For more information on how EDI status and AS2 status are correlated, see the "Correlating an AS2 Message with its EDI Payload" section of [AS2 Message and Correlated MDN Status Report](../core/as2-message-and-correlated-mdn-status-report.md).</span></span>  
  
    3.  <span data-ttu-id="de187-149">要显示 AS2 消息中的连网格式，请右键单击 AS2/MDN 状态报表中中的条目，然后单击**消息连网格式**。</span><span class="sxs-lookup"><span data-stu-id="de187-149">To display an AS2 message in wire format, right-click an entry in the AS2/MDN Status report, and then click **Message Wire Format**.</span></span>  
  
    4.  <span data-ttu-id="de187-150">要显示格式为已解码 AS2 消息，请右键单击 AS2/MDN 状态报表中中的条目，然后单击**消息已解码格式**。</span><span class="sxs-lookup"><span data-stu-id="de187-150">To display an AS2 message in decoded format, right-click an entry in the AS2/MDN Status report, and then click **Message Decoded Format**.</span></span>  
  
    5.  <span data-ttu-id="de187-151">要显示 MDN 消息，请右键单击 AS2/MDN 状态报表中中的条目，然后单击**Mdn 消息**。</span><span class="sxs-lookup"><span data-stu-id="de187-151">To display an MDN message, right-click an entry in the AS2/MDN Status report, and then click **Mdn Message**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de187-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de187-152">See Also</span></span>  
 <span data-ttu-id="de187-153">[监视 EDI 和 AS2 解决方案](../core/monitoring-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="de187-153">[Monitoring EDI and AS2 Solutions](../core/monitoring-edi-and-as2-solutions.md) </span></span>  
 <span data-ttu-id="de187-154">[EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md) </span><span class="sxs-lookup"><span data-stu-id="de187-154">[EDI and AS2 Status Reporting](../core/edi-and-as2-status-reporting.md) </span></span>  
 <span data-ttu-id="de187-155">[启用 EDI 和 AS2 状态报表](../core/enabling-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="de187-155">[Enabling EDI and AS2 Status Reports](../core/enabling-edi-and-as2-status-reports.md) </span></span>  
 [<span data-ttu-id="de187-156">配置 EDI 和 AS2 状态报表</span><span class="sxs-lookup"><span data-stu-id="de187-156">Configuring an EDI and AS2 Status Report</span></span>](../core/configuring-an-edi-and-as2-status-report.md)