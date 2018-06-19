---
title: 为批处理状态报表存储的数据 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d55aa0e1-095f-434e-8530-f1a946ad4430
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db9831aafce56845fe7b75e91f5369a8860d8996
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238589"
---
# <a name="data-stored-for-batching-status-reports"></a><span data-ttu-id="a8b2d-102">为批处理状态报告存储的数据</span><span class="sxs-lookup"><span data-stu-id="a8b2d-102">Data Stored for Batching Status Reports</span></span>
<span data-ttu-id="a8b2d-103">当**打开 ON Reporting**为一个协议，选中属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将存储每个批处理的实例的状态。</span><span class="sxs-lookup"><span data-stu-id="a8b2d-103">When the **Turn ON Reporting** property is selected for an agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will store the status of each batching instance.</span></span> <span data-ttu-id="a8b2d-104">此属性是在位于**常规属性**页**常规**选项卡中**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="a8b2d-104">This property is in available in the **General Properties** page of the **General** tab in the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="a8b2d-105">状态可以为以下任意状态：</span><span class="sxs-lookup"><span data-stu-id="a8b2d-105">The status can be any of the following:</span></span>  
  
-   <span data-ttu-id="a8b2d-106">**定义**： 批处理实例配置。</span><span class="sxs-lookup"><span data-stu-id="a8b2d-106">**Defined**: The batch instance is configured.</span></span> <span data-ttu-id="a8b2d-107">批的激活起始日期时间晚于当前日期时间。</span><span class="sxs-lookup"><span data-stu-id="a8b2d-107">The batch activation start date time is greater than the current date time.</span></span> <span data-ttu-id="a8b2d-108">所有批参数均已定义，但批没有运行（没有接受文档）。</span><span class="sxs-lookup"><span data-stu-id="a8b2d-108">All batch parameters are defined, but the batch is not running (not accepting documents).</span></span>  
  
-   <span data-ttu-id="a8b2d-109">**Active**： 批处理实例已激活和聚合事务集。</span><span class="sxs-lookup"><span data-stu-id="a8b2d-109">**Active**: The batch instance has been activated and is aggregating transaction sets.</span></span> <span data-ttu-id="a8b2d-110">可以查看已接受/已拒绝事务集的数量。</span><span class="sxs-lookup"><span data-stu-id="a8b2d-110">You can view the number of accepted/rejected transaction sets.</span></span>  
  
-   <span data-ttu-id="a8b2d-111">**发布**： 批处理满足释放条件和发布到 MessageBox，但尚未释放通过发送管道中，或在处理任何消息之前停止批处理。</span><span class="sxs-lookup"><span data-stu-id="a8b2d-111">**Released**: The batch met the release criteria and was released into the MessageBox, but has not been released by the send pipeline, or that the batch was stopped before processing any messages.</span></span>  
  
-   <span data-ttu-id="a8b2d-112">**完成**: EdiSend 管道发送批处理。</span><span class="sxs-lookup"><span data-stu-id="a8b2d-112">**Completed**: The batch was sent by the EdiSend pipeline.</span></span>  
  
 <span data-ttu-id="a8b2d-113">如果 EdiSend 管道已经发送了批，可以将 UI 中的批记录与所发送 Edi 交换的记录关联在一起，并查看事务集详细信息。</span><span class="sxs-lookup"><span data-stu-id="a8b2d-113">If the batch was sent by the EdiSend pipeline, you can correlate the batch record in the UI with a record of the sent Edi interchange, and view transaction set details.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8b2d-114">批配置可以有多个状态为“已完成”的批实例。</span><span class="sxs-lookup"><span data-stu-id="a8b2d-114">There may be multiple batch instances with a status of Completed for a batch configuration.</span></span>  
  
 <span data-ttu-id="a8b2d-115">**关联的批处理的交换**</span><span class="sxs-lookup"><span data-stu-id="a8b2d-115">**Correlating an Interchange with a Batch**</span></span>  
  
 <span data-ttu-id="a8b2d-116">通过 BusinessMessageJournal BAM 活动，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以将收到的包含事务集的 EDI 交换与包含相同事务集的传出批交换相关联。</span><span class="sxs-lookup"><span data-stu-id="a8b2d-116">The BusinessMessageJournal BAM activity enables [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to correlate a received EDI interchange containing a transaction set with an outgoing batched interchange that contains the same transaction set.</span></span> <span data-ttu-id="a8b2d-117">有关如何实现和使用此相关信息的信息，请参阅[关联传出批的传入事务集](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md)。</span><span class="sxs-lookup"><span data-stu-id="a8b2d-117">For information about how to implement and use this correlation information, see [Correlating an Incoming Transaction Set with an Outgoing Batch](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8b2d-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8b2d-118">See Also</span></span>  
 <span data-ttu-id="a8b2d-119">[对于 EDI 和 AS2 状态报表存储的数据](../core/data-stored-for-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="a8b2d-119">[Data Stored for EDI and AS2 Status Reports](../core/data-stored-for-edi-and-as2-status-reports.md) </span></span>  
 <span data-ttu-id="a8b2d-120">[对于 EDI 状态报表存储的数据](../core/data-stored-for-edi-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="a8b2d-120">[Data Stored for EDI Status Reports](../core/data-stored-for-edi-status-reports.md) </span></span>  
 [<span data-ttu-id="a8b2d-121">AS2 状态报告为存储的数据</span><span class="sxs-lookup"><span data-stu-id="a8b2d-121">Data Stored for AS2 Status Reports</span></span>](../core/data-stored-for-as2-status-reports.md)