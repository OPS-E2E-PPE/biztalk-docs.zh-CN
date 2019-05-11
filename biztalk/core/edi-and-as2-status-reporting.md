---
title: EDI 和 AS2 状态报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a9e58b29-9be0-41d6-ad35-1aae28e1a784
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bf0f3f5b5e6c50a02451215f56dbc3ec4c2939a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350582"
---
# <a name="edi-and-as2-status-reporting"></a><span data-ttu-id="a43b9-102">EDI 和 AS2 状态报告</span><span class="sxs-lookup"><span data-stu-id="a43b9-102">EDI and AS2 Status Reporting</span></span>
<span data-ttu-id="a43b9-103">EDI 状态报告，操作人员可以跟踪 EDI 和 AS2 传输的状态。</span><span class="sxs-lookup"><span data-stu-id="a43b9-103">EDI status reporting enables operations personnel to track the status of EDI and AS2 transmissions.</span></span> <span data-ttu-id="a43b9-104">如果启用，则状态报告提供的文档交换事务，包括交换和与交换的任何确认的全面状态。</span><span class="sxs-lookup"><span data-stu-id="a43b9-104">If enabled, status reports provide comprehensive status of a document exchange transaction, including an interchange and any acknowledgments correlated to the interchange.</span></span> <span data-ttu-id="a43b9-105">这些报表提供有关回执、 验证、 批处理和确认处理有关 EDI 和 AS2 消息的数据。</span><span class="sxs-lookup"><span data-stu-id="a43b9-105">These reports provide data on receipt, validation, batching, and acknowledgment processing of EDI and AS2 messages.</span></span>  
  
 <span data-ttu-id="a43b9-106">这些报表可用于获取挂起的状态和未确认的交换、 完整交换、 错误方案或业务方案。</span><span class="sxs-lookup"><span data-stu-id="a43b9-106">You can use these reports to get the status of pending and unacknowledged interchanges, complete interchanges, error scenarios, or business scenarios.</span></span> <span data-ttu-id="a43b9-107">使用这些报表，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a43b9-107">With these reports, you can do the following:</span></span>  
  
- <span data-ttu-id="a43b9-108">确认交换的接收</span><span class="sxs-lookup"><span data-stu-id="a43b9-108">Confirm the receipt of interchanges</span></span>  
  
- <span data-ttu-id="a43b9-109">列出等待确认的传出交换</span><span class="sxs-lookup"><span data-stu-id="a43b9-109">List outgoing interchanges awaiting acknowledgment</span></span>  
  
- <span data-ttu-id="a43b9-110">列出所有拒绝收到的交换</span><span class="sxs-lookup"><span data-stu-id="a43b9-110">List all rejected interchanges received</span></span>  
  
- <span data-ttu-id="a43b9-111">接受列表作为被拒绝或部分报告的传出交换。</span><span class="sxs-lookup"><span data-stu-id="a43b9-111">List outgoing interchanges that are reported as rejected or partially accepted.</span></span>  
  
  <span data-ttu-id="a43b9-112">状态报告中包含的数据是从交换控制段，例如 ISA、 TA1、 GS、 UNB 和 UNG （除了功能确认状态中） 获取。</span><span class="sxs-lookup"><span data-stu-id="a43b9-112">Data included in the status reports is obtained from interchange control segments, such as ISA, TA1, GS, UNB, and UNG (with the exception of the Functional ACK status).</span></span>  
  
  <span data-ttu-id="a43b9-113">**状态报告 UI**</span><span class="sxs-lookup"><span data-stu-id="a43b9-113">**Status Reporting UI**</span></span>  
  
  <span data-ttu-id="a43b9-114">EDI 和 AS2 状态报告中有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="a43b9-114">EDI and AS2 status reports are available from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="a43b9-115">从**组中心**页**BizTalk 组**节点，设有指向 EDI 交换和相关的确认状态、 批处理状态以及 AS2 消息和相关的 MDN 状态。</span><span class="sxs-lookup"><span data-stu-id="a43b9-115">From the **Group Hub** page of the **BizTalk Group** node, you have links to EDI interchange and correlated acknowledgment status, batch status, and AS2 message and correlated MDN status.</span></span> <span data-ttu-id="a43b9-116">每个报告提供了一系列可以包括或排除在查询表达式中，因此可以生成所需的状态报告的状态参数。</span><span class="sxs-lookup"><span data-stu-id="a43b9-116">Each of these reports provides a range of status parameters that you can include or exclude from a query expression, enabling you to build the status report that they need.</span></span>  
  
  <span data-ttu-id="a43b9-117">除了查看 EDI 交换的状态，还可以将交换中查看事务集。</span><span class="sxs-lookup"><span data-stu-id="a43b9-117">In addition to seeing the status of an EDI interchange, you can also view the transaction sets in an interchange.</span></span> <span data-ttu-id="a43b9-118">则执行操作来启用消息跟踪 (BizTalkDTADb) 数据库的 EDI 表中的有效负载的存储。</span><span class="sxs-lookup"><span data-stu-id="a43b9-118">You do so by enabling the storage of message payloads in the EDI tables of the tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="a43b9-119">可以通过使用状态报告 UI 中查看详细信息命令来查看事务集。</span><span class="sxs-lookup"><span data-stu-id="a43b9-119">You can view the transaction sets by using the view details command in the status reporting UI.</span></span>  
  
  <span data-ttu-id="a43b9-120">此外可以在不可否认数据库中存储入站或出站 AS2 消息或 Mdn。</span><span class="sxs-lookup"><span data-stu-id="a43b9-120">You can also store inbound or outbound AS2 messages or MDNs in the non-repudiation database.</span></span> <span data-ttu-id="a43b9-121">可以通过右键单击状态报表中的消息并选择相应的命令来查看事务集或 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="a43b9-121">You can view the transaction sets or AS2 messages by right-clicking the message in the status report and selecting the appropriate command.</span></span>  
  
  <span data-ttu-id="a43b9-122">**状态报告组件**</span><span class="sxs-lookup"><span data-stu-id="a43b9-122">**Status Report Components**</span></span>  
  
  <span data-ttu-id="a43b9-123">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]状态报告中涉及的组件如下：</span><span class="sxs-lookup"><span data-stu-id="a43b9-123">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] components involved in status reporting are the following:</span></span>  
  
- <span data-ttu-id="a43b9-124">EDI 拆装器在 EDI 接收管道，用于创建和更新状态条目将传入交换的数据存储中</span><span class="sxs-lookup"><span data-stu-id="a43b9-124">The EDI Disassembler in the EDI receive pipeline that creates and updates status entries in the data store for an incoming interchange</span></span>  
  
- <span data-ttu-id="a43b9-125">EDI 组装器中的 EDI 发送管道，用于创建和更新在传出交换的数据存储中的状态条目</span><span class="sxs-lookup"><span data-stu-id="a43b9-125">The EDI Assembler in the EDI send pipeline that creates and updates status entries in the data store for an outgoing interchange</span></span>  
  
- <span data-ttu-id="a43b9-126">数据存储的存储状态报告条目。</span><span class="sxs-lookup"><span data-stu-id="a43b9-126">The data stores that store the status report entries.</span></span> <span data-ttu-id="a43b9-127">这些是用于跟踪数据和 BizTalk 跟踪数据库 (BizTalkDTADb) 的 EDI 事务集和/或 AS2 消息内容的 EDI Message Content 表的 BAM 主导入数据库</span><span class="sxs-lookup"><span data-stu-id="a43b9-127">These are the BAM Primary Import database for tracking data and the EDI Message Content table of the BizTalk tracking database (BizTalkDTADb) for EDI transaction sets and/or AS2 message contents</span></span>  
  
- <span data-ttu-id="a43b9-128">状态报告 UI**组中心**页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，用于显示状态报告数据</span><span class="sxs-lookup"><span data-stu-id="a43b9-128">Status reporting UI on the **Group Hub** page of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, which is used to display status reporting data</span></span>  
  
- <span data-ttu-id="a43b9-129">协议属性和后备协议属性中的选项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，用于启用和配置状态报告</span><span class="sxs-lookup"><span data-stu-id="a43b9-129">Agreement property and fallback agreement property options in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, which is used to enable and configure status reporting</span></span>  
  
- <span data-ttu-id="a43b9-130">DTA 和 SQL 分析服务器利用 BAM 基础结构。</span><span class="sxs-lookup"><span data-stu-id="a43b9-130">DTA and SQL Analysis Server that leverage the BAM infrastructure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a43b9-131">本节内容</span><span class="sxs-lookup"><span data-stu-id="a43b9-131">In This Section</span></span>  
  
-   [<span data-ttu-id="a43b9-132">配置 EDI 和 AS2 状态报告功能</span><span class="sxs-lookup"><span data-stu-id="a43b9-132">Configuration of EDI and AS2 Status Reporting</span></span>](../core/configuration-of-edi-and-as2-status-reporting.md)  
  
-   [<span data-ttu-id="a43b9-133">EDI 和 AS2 状态报告的类型</span><span class="sxs-lookup"><span data-stu-id="a43b9-133">Types of EDI and AS2 Status Reports</span></span>](../core/types-of-edi-and-as2-status-reports.md)  
  
-   [<span data-ttu-id="a43b9-134">为 EDI 和 AS2 状态报告存储的数据</span><span class="sxs-lookup"><span data-stu-id="a43b9-134">Data Stored for EDI and AS2 Status Reports</span></span>](../core/data-stored-for-edi-and-as2-status-reports.md)  
  
-   [<span data-ttu-id="a43b9-135">如何为 EDI 和 AS2 状态报告存储数据</span><span class="sxs-lookup"><span data-stu-id="a43b9-135">How Data Is Stored for EDI and AS2 Status Reports</span></span>](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)