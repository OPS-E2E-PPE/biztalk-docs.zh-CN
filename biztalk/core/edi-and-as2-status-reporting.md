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
ms.openlocfilehash: 8a109398f4b3bff99ce7f45493839df6c3e5320f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993134"
---
# <a name="edi-and-as2-status-reporting"></a><span data-ttu-id="d7b62-102">EDI 和 AS2 状态报告</span><span class="sxs-lookup"><span data-stu-id="d7b62-102">EDI and AS2 Status Reporting</span></span>
<span data-ttu-id="d7b62-103">借助 EDI 状态报告，操作人员可以跟踪 EDI 和 AS2 传输的状态。</span><span class="sxs-lookup"><span data-stu-id="d7b62-103">EDI status reporting enables operations personnel to track the status of EDI and AS2 transmissions.</span></span> <span data-ttu-id="d7b62-104">状态报告（如果已启用）提供了全面的文档交换事务状态信息，包括交换和与交换相关的确认信息。</span><span class="sxs-lookup"><span data-stu-id="d7b62-104">If enabled, status reports provide comprehensive status of a document exchange transaction, including an interchange and any acknowledgments correlated to the interchange.</span></span> <span data-ttu-id="d7b62-105">这些报告提供与 EDI 和 AS2 消息的接收、验证、批处理和确认处理有关的数据。</span><span class="sxs-lookup"><span data-stu-id="d7b62-105">These reports provide data on receipt, validation, batching, and acknowledgment processing of EDI and AS2 messages.</span></span>  
  
 <span data-ttu-id="d7b62-106">可以使用这些报告获取挂起和未确认的交换、完整交换、错误方案或业务方案的状态。</span><span class="sxs-lookup"><span data-stu-id="d7b62-106">You can use these reports to get the status of pending and unacknowledged interchanges, complete interchanges, error scenarios, or business scenarios.</span></span> <span data-ttu-id="d7b62-107">使用这些报告，您可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d7b62-107">With these reports, you can do the following:</span></span>  
  
- <span data-ttu-id="d7b62-108">确认交换的接收</span><span class="sxs-lookup"><span data-stu-id="d7b62-108">Confirm the receipt of interchanges</span></span>  
  
- <span data-ttu-id="d7b62-109">列出等待确认的传出交换</span><span class="sxs-lookup"><span data-stu-id="d7b62-109">List outgoing interchanges awaiting acknowledgment</span></span>  
  
- <span data-ttu-id="d7b62-110">列出所有遭到拒绝的已接收交换</span><span class="sxs-lookup"><span data-stu-id="d7b62-110">List all rejected interchanges received</span></span>  
  
- <span data-ttu-id="d7b62-111">列出报告为“已拒绝”或“部分接受”的传出交换。</span><span class="sxs-lookup"><span data-stu-id="d7b62-111">List outgoing interchanges that are reported as rejected or partially accepted.</span></span>  
  
  <span data-ttu-id="d7b62-112">状态报告中包含的数据是从交换控制段中获取的，如 ISA、TA1、GS、UNB 和 UNG（功能确认状态除外）。</span><span class="sxs-lookup"><span data-stu-id="d7b62-112">Data included in the status reports is obtained from interchange control segments, such as ISA, TA1, GS, UNB, and UNG (with the exception of the Functional ACK status).</span></span>  
  
  <span data-ttu-id="d7b62-113">**状态报告 UI**</span><span class="sxs-lookup"><span data-stu-id="d7b62-113">**Status Reporting UI**</span></span>  
  
  <span data-ttu-id="d7b62-114">从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台可以查看 EDI 和 AS2 状态报告。</span><span class="sxs-lookup"><span data-stu-id="d7b62-114">EDI and AS2 status reports are available from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="d7b62-115">从**组中心**页**BizTalk 组**节点，设有指向 EDI 交换和相关的确认状态、 批处理状态以及 AS2 消息和相关的 MDN 状态。</span><span class="sxs-lookup"><span data-stu-id="d7b62-115">From the **Group Hub** page of the **BizTalk Group** node, you have links to EDI interchange and correlated acknowledgment status, batch status, and AS2 message and correlated MDN status.</span></span> <span data-ttu-id="d7b62-116">这些报告中的每个报告均提供了可包含在查询表达式中或从查询表达式中排除的一组状态参数，从而可使您生成所需的状态报告。</span><span class="sxs-lookup"><span data-stu-id="d7b62-116">Each of these reports provides a range of status parameters that you can include or exclude from a query expression, enabling you to build the status report that they need.</span></span>  
  
  <span data-ttu-id="d7b62-117">除了查看 EDI 交换的状态之外，还可以查看交换中的事务集。</span><span class="sxs-lookup"><span data-stu-id="d7b62-117">In addition to seeing the status of an EDI interchange, you can also view the transaction sets in an interchange.</span></span> <span data-ttu-id="d7b62-118">通过在跟踪数据库 (BizTalkDTADb) 的 EDI 表中启用消息负载存储可实现这一点。</span><span class="sxs-lookup"><span data-stu-id="d7b62-118">You do so by enabling the storage of message payloads in the EDI tables of the tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="d7b62-119">通过在状态报告 UI 中使用查看详细信息命令即可查看事务集。</span><span class="sxs-lookup"><span data-stu-id="d7b62-119">You can view the transaction sets by using the view details command in the status reporting UI.</span></span>  
  
  <span data-ttu-id="d7b62-120">您也可将出站或入站 AS2 消息或 MDN 存储在不可否认数据库中。</span><span class="sxs-lookup"><span data-stu-id="d7b62-120">You can also store inbound or outbound AS2 messages or MDNs in the non-repudiation database.</span></span> <span data-ttu-id="d7b62-121">通过右键单击状态报告中的消息并选择相应命令即可查看事务集或 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="d7b62-121">You can view the transaction sets or AS2 messages by right-clicking the message in the status report and selecting the appropriate command.</span></span>  
  
  <span data-ttu-id="d7b62-122">**状态报告组件**</span><span class="sxs-lookup"><span data-stu-id="d7b62-122">**Status Report Components**</span></span>  
  
  <span data-ttu-id="d7b62-123">以下是状态报告中涉及的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组件：</span><span class="sxs-lookup"><span data-stu-id="d7b62-123">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] components involved in status reporting are the following:</span></span>  
  
- <span data-ttu-id="d7b62-124">EDI 接收管道中的 EDI 拆装器，用于在传入交换的数据存储区中创建和更新状态条目</span><span class="sxs-lookup"><span data-stu-id="d7b62-124">The EDI Disassembler in the EDI receive pipeline that creates and updates status entries in the data store for an incoming interchange</span></span>  
  
- <span data-ttu-id="d7b62-125">EDI 发送管道中的 EDI 组装器，用于在传出交换的数据存储区中创建和更新状态条目</span><span class="sxs-lookup"><span data-stu-id="d7b62-125">The EDI Assembler in the EDI send pipeline that creates and updates status entries in the data store for an outgoing interchange</span></span>  
  
- <span data-ttu-id="d7b62-126">用于存储状态报告条目的数据存储区。</span><span class="sxs-lookup"><span data-stu-id="d7b62-126">The data stores that store the status report entries.</span></span> <span data-ttu-id="d7b62-127">即用于跟踪数据的 BAM 主导入数据库，以及用于 EDI 事务集和/或 AS2 消息内容的 BizTalk 跟踪数据库 (BizTalkDTADb) 中的 EDI Message Content 表</span><span class="sxs-lookup"><span data-stu-id="d7b62-127">These are the BAM Primary Import database for tracking data and the EDI Message Content table of the BizTalk tracking database (BizTalkDTADb) for EDI transaction sets and/or AS2 message contents</span></span>  
  
- <span data-ttu-id="d7b62-128">状态报告 UI**组中心**页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，用于显示状态报告数据</span><span class="sxs-lookup"><span data-stu-id="d7b62-128">Status reporting UI on the **Group Hub** page of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, which is used to display status reporting data</span></span>  
  
- <span data-ttu-id="d7b62-129">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中的协议属性和后备协议属性，用于启用和配置状态报告</span><span class="sxs-lookup"><span data-stu-id="d7b62-129">Agreement property and fallback agreement property options in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, which is used to enable and configure status reporting</span></span>  
  
- <span data-ttu-id="d7b62-130">可利用 BAM 基础结构的 DTA 和 SQL 分析服务器。</span><span class="sxs-lookup"><span data-stu-id="d7b62-130">DTA and SQL Analysis Server that leverage the BAM infrastructure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d7b62-131">本节内容</span><span class="sxs-lookup"><span data-stu-id="d7b62-131">In This Section</span></span>  
  
-   [<span data-ttu-id="d7b62-132">配置 EDI 和 AS2 状态报告功能</span><span class="sxs-lookup"><span data-stu-id="d7b62-132">Configuration of EDI and AS2 Status Reporting</span></span>](../core/configuration-of-edi-and-as2-status-reporting.md)  
  
-   [<span data-ttu-id="d7b62-133">EDI 和 AS2 状态报告的类型</span><span class="sxs-lookup"><span data-stu-id="d7b62-133">Types of EDI and AS2 Status Reports</span></span>](../core/types-of-edi-and-as2-status-reports.md)  
  
-   [<span data-ttu-id="d7b62-134">为 EDI 和 AS2 状态报告存储的数据</span><span class="sxs-lookup"><span data-stu-id="d7b62-134">Data Stored for EDI and AS2 Status Reports</span></span>](../core/data-stored-for-edi-and-as2-status-reports.md)  
  
-   [<span data-ttu-id="d7b62-135">如何为 EDI 和 AS2 状态报告存储数据</span><span class="sxs-lookup"><span data-stu-id="d7b62-135">How Data Is Stored for EDI and AS2 Status Reports</span></span>](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)