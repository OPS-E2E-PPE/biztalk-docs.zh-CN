---
title: 配置 EDI 和 AS2 状态报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c7fa76d-0d03-4b74-9a3a-60f4bd0534ff
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7bf9108b2302097373f2930c8408fda13b787842
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391498"
---
# <a name="configuration-of-edi-and-as2-status-reporting"></a><span data-ttu-id="f80a7-102">配置 EDI 和 AS2 状态报告</span><span class="sxs-lookup"><span data-stu-id="f80a7-102">Configuration of EDI and AS2 Status Reporting</span></span>
<span data-ttu-id="f80a7-103">本主题介绍的 EDI 和 AS2 状态报告，请启用和配置状态报告筛选器和显示列的 EDI、 批处理和 AS2 状态报告。</span><span class="sxs-lookup"><span data-stu-id="f80a7-103">This topic describes the enabling of EDI and AS2 status reporting, and the configuration of status report filters and display columns for EDI, batching, and AS2 status reports.</span></span>  
  
## <a name="enabling-status-reporting"></a><span data-ttu-id="f80a7-104">启用状态报告</span><span class="sxs-lookup"><span data-stu-id="f80a7-104">Enabling Status Reporting</span></span>  
 <span data-ttu-id="f80a7-105">EDI 状态报告功能只能在服务器上提供如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]带有 EDI 和 BAM 子系统是该服务器上安装。</span><span class="sxs-lookup"><span data-stu-id="f80a7-105">EDI status reporting will only be available on a server if [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with the EDI and BAM subsystems is installed on that server.</span></span> <span data-ttu-id="f80a7-106">如果未安装 BAM 基础结构，不能启用 EDI/AS2 状态报告。</span><span class="sxs-lookup"><span data-stu-id="f80a7-106">EDI/AS2 status reporting cannot be enabled if the BAM infrastructure is not installed.</span></span> <span data-ttu-id="f80a7-107">服务器还必须是 EDI 处理的成员[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]分组，以便它有权访问 EDI 状态报告数据存储区。</span><span class="sxs-lookup"><span data-stu-id="f80a7-107">The server must also be a member of the EDI Processing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group so that it has access to the EDI status report data store.</span></span>  
  
 <span data-ttu-id="f80a7-108">如果将状态报告 UI 中的参与方的交换输入 EDI 消息条目**打开报告**中选择属性**常规属性**页**常规**选项卡中**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="f80a7-108">EDI message entries will be entered for a party's interchanges in the status report UI if the **Turn ON reporting** property is selected in the **General Properties** page of the **General** tab in the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="f80a7-109">仅当，如果未确定交换发送方或接收，将对这些交换中输入 EDI 消息条目**激活 EDI 报告**为 X12 和 EDIFACT 后备协议中选择属性。</span><span class="sxs-lookup"><span data-stu-id="f80a7-109">If the party sending or being sent interchanges is not determined, EDI message entries will be entered for those interchanges only if the **Activate EDI reporting** property is selected in the fallback agreement for both X12 and EDIFACT.</span></span> <span data-ttu-id="f80a7-110">这适用于 EDI 交换和相关 ACK 状态报表。</span><span class="sxs-lookup"><span data-stu-id="f80a7-110">This applies to the EDI Interchange and Correlated ACK Status report.</span></span> <span data-ttu-id="f80a7-111">仅当已确定协议时，才启用批处理状态报表并**打开报告**中选择属性**常规属性**页**常规**在选项卡**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="f80a7-111">The Batch Status report is enabled only if an agreement has been determined and the **Turn ON reporting** property is selected in **General Properties** page of the **General** tab in the **Agreement Properties** dialog box.</span></span>  
  
 <span data-ttu-id="f80a7-112">将跟踪数据库中存储事务集，如果**存储消息负载以用于报告**中选择属性**常规属性**页**常规**在选项卡**协议属性**对话框中或**存储事务集/负载以用于报告**在后备协议属性中设置属性。</span><span class="sxs-lookup"><span data-stu-id="f80a7-112">Transaction sets will be stored in the tracking database if the **Store message payload for reporting** property is selected in **General Properties** page of the **General** tab in the **Agreement Properties** dialog box or **Store transaction set/payload for reporting** property is set in the fallback agreement properties.</span></span> <span data-ttu-id="f80a7-113">事务集详细信息和消息内容状态报告才可用，如果选择此属性。</span><span class="sxs-lookup"><span data-stu-id="f80a7-113">The Transaction Set Details and Message Content status reports will only be available if this property is selected.</span></span>  
  
 <span data-ttu-id="f80a7-114">如果将状态报告 UI 中输入 AS2 消息条目**打开报告**中选择属性**常规属性**页**常规**中的选项卡**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="f80a7-114">AS2 message entries will be entered in the status report UI if the **Turn ON reporting** property is selected in the **General Properties** page of the **General** tab in the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="f80a7-115">若要将 AS2 消息或 Mdn 存储在不可否认数据库中，您必须选择中的相应属性**发送方不可否认**或**接收方不可否认**页的单向 AS2 协议在选项卡**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="f80a7-115">To store AS2 message or MDNs in the non-repudiation database, you must select the appropriate property in the **Sender Non-repudiation** or **Receiver non-repudiation** pages of the one-way AS2 agreement tab in the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="f80a7-116">这些属性启用的 AS2 消息和相关 MDN 状态报告。</span><span class="sxs-lookup"><span data-stu-id="f80a7-116">These properties enable the AS2 Message and Correlated MDN Status report.</span></span>  
  
 <span data-ttu-id="f80a7-117">会提供可靠的消息传送状态报告如果**MDN 未收到时重新发送 AS2 消息**上启用属性**发送方 MDN 设置**的单向AS2协议选项卡页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="f80a7-117">The Reliable Messaging Status report will be available if the **Resend AS2 message if MDN not received** property is enabled on **Sender MDN Settings** page of the one-way AS2 agreement tab of the **Agreement Properties** dialog box.</span></span>  
  
 <span data-ttu-id="f80a7-118">有关启用状态报告的详细信息，请参阅[启用 EDI 和 AS2 状态报告](../core/enabling-edi-and-as2-status-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="f80a7-118">For more information about enabling status reporting, see [Enabling EDI and AS2 Status Reports](../core/enabling-edi-and-as2-status-reports.md).</span></span>  
  
## <a name="status-report-filters-and-display-columns"></a><span data-ttu-id="f80a7-119">状态报告筛选器和显示列</span><span class="sxs-lookup"><span data-stu-id="f80a7-119">Status Report Filters and Display Columns</span></span>  
 <span data-ttu-id="f80a7-120">EDI 和 AS2 状态报告，可自定义保存为状态报表数据的范围。</span><span class="sxs-lookup"><span data-stu-id="f80a7-120">EDI and AS2 status reporting enables you to customize the range of the data that is saved for the status report.</span></span> <span data-ttu-id="f80a7-121">此，请在**组中心**页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f80a7-121">You do so in the **Group Hub** page of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="f80a7-122">显示状态报告窗格的任何状态报告之后, 您可以选择你想要在报表中看到的数据的范围。</span><span class="sxs-lookup"><span data-stu-id="f80a7-122">Once you have displayed the status report pane for any of the status reports, you can select the range of data that you want to see in the report.</span></span> <span data-ttu-id="f80a7-123">为此，选择要包括在状态报告查询表达式中的筛选器值。</span><span class="sxs-lookup"><span data-stu-id="f80a7-123">You do so by selecting the filter values to include in the status report query expression.</span></span>  
  
 <span data-ttu-id="f80a7-124">此外可以自定义状态报告中显示的数据的类型。</span><span class="sxs-lookup"><span data-stu-id="f80a7-124">You can also customize the type of data that is displayed in the status report.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f80a7-125">每当启用状态报告后，所有状态都将都保存在存储中。</span><span class="sxs-lookup"><span data-stu-id="f80a7-125">Whenever status reporting is enabled, all status will be saved in storage.</span></span> <span data-ttu-id="f80a7-126">通过自定义查询表达式或状态列，可以定义显示的已保存的数据。</span><span class="sxs-lookup"><span data-stu-id="f80a7-126">By customizing the query expression or status columns, you are defining which saved data is displayed.</span></span>  
  
 <span data-ttu-id="f80a7-127">有关详细信息，请参阅[配置 EDI 和 AS2 状态报告](../core/configuring-an-edi-and-as2-status-report.md)。</span><span class="sxs-lookup"><span data-stu-id="f80a7-127">For more information, see [Configuring an EDI and AS2 Status Report](../core/configuring-an-edi-and-as2-status-report.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f80a7-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="f80a7-128">See Also</span></span>  
 <span data-ttu-id="f80a7-129">[EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md) </span><span class="sxs-lookup"><span data-stu-id="f80a7-129">[EDI and AS2 Status Reporting](../core/edi-and-as2-status-reporting.md) </span></span>  
 <span data-ttu-id="f80a7-130">[EDI 交换和相关 ACK 状态报告](../core/edi-interchange-and-correlated-ack-status-report.md) </span><span class="sxs-lookup"><span data-stu-id="f80a7-130">[EDI Interchange and Correlated ACK Status Report](../core/edi-interchange-and-correlated-ack-status-report.md) </span></span>  
 <span data-ttu-id="f80a7-131">[批处理状态报告](../core/batch-status-report.md) </span><span class="sxs-lookup"><span data-stu-id="f80a7-131">[Batch Status Report](../core/batch-status-report.md) </span></span>  
 <span data-ttu-id="f80a7-132">[交换聚合报告](../core/interchange-aggregation-report.md) </span><span class="sxs-lookup"><span data-stu-id="f80a7-132">[Interchange Aggregation Report](../core/interchange-aggregation-report.md) </span></span>  
 <span data-ttu-id="f80a7-133">[事务集聚合报告](../core/transaction-set-aggregation-report.md) </span><span class="sxs-lookup"><span data-stu-id="f80a7-133">[Transaction Set Aggregation Report](../core/transaction-set-aggregation-report.md) </span></span>  
 [<span data-ttu-id="f80a7-134">AS2 消息和相关 MDN 状态报告</span><span class="sxs-lookup"><span data-stu-id="f80a7-134">AS2 Message and Correlated MDN Status Report</span></span>](../core/as2-message-and-correlated-mdn-status-report.md)