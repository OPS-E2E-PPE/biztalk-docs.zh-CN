---
title: "状态报告数据存储区 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cd40ce8-1ac6-43b4-9cef-7cd045e8893c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da876f1151b641216cf9613f6830ed84049da83d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="status-report-data-stores"></a><span data-ttu-id="86fde-102">状态报告数据存储区</span><span class="sxs-lookup"><span data-stu-id="86fde-102">Status Report Data Stores</span></span>
<span data-ttu-id="86fde-103">状态报告跟踪数据存储在 BAM 主导入数据库中。</span><span class="sxs-lookup"><span data-stu-id="86fde-103">Status reporting tracking data is stored in the BAM Primary Import database.</span></span> <span data-ttu-id="86fde-104">该数据库中的许多表都用于 EDI 和 AS2 消息数据，这些表包括以 dbo.bam_AS2、dbo.bam.batching、dbo.bam.InterchangeStatusActivity 等开头的表。</span><span class="sxs-lookup"><span data-stu-id="86fde-104">A number of tables in this database are used for EDI and AS2 message data, including tables starting with dbo.bam_AS2, dbo.bam.batching, dbo.bam.InterchangeStatusActivity, and others.</span></span> <span data-ttu-id="86fde-105">即使在禁用 EDI 报告的情况下，状态数据也存储在主导入数据库中。</span><span class="sxs-lookup"><span data-stu-id="86fde-105">Status data is stored in the Primary Import even if EDI reporting is disabled.</span></span> <span data-ttu-id="86fde-106">如果激活了状态报告，则您将只能在该状态报告 UI 中查看和查询此类数据。</span><span class="sxs-lookup"><span data-stu-id="86fde-106">You will only be to view and query this data in the status reporting UI if status reporting is activated.</span></span>  
  
 <span data-ttu-id="86fde-107">如果您启用消息数据存储以确保不可否认性，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会将 EDI 和/或 AS2 数据存储在 BizTalk 跟踪数据库 (BizTalkDTADb) 的 EDI Message Content 表中。</span><span class="sxs-lookup"><span data-stu-id="86fde-107">If you enable storage of message data for non-repudiation purposes, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will store the EDI and/or AS2 data in the EDI Message Content table of the BizTalk tracking database (BizTalkDTADb).</span></span> <span data-ttu-id="86fde-108">如果启用存储用于查看负载的详细信息的消息内容 (通过选择**用于报告的应用商店消息负载**中的协议属性**常规属性**页**常规**选项卡中**协议属性**对话框中)，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]还将在此表中存储的事务集。</span><span class="sxs-lookup"><span data-stu-id="86fde-108">If you enable storage of message contents for viewing details of the payload (by selecting the **Store message payload for reporting** agreement property in the **General Properties** page of the **General** tab in the **Agreement Properties** dialog box), [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will also store the transaction sets in this table.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="86fde-109"> 从 BAM 主导入数据库和 BizTalkDTADb 数据库中存档和清除数据。</span><span class="sxs-lookup"><span data-stu-id="86fde-109"> archives and purges data from the BAM Primary Import and BizTalkDTADb databases.</span></span> <span data-ttu-id="86fde-110">数据库中的表将定期进行清除。</span><span class="sxs-lookup"><span data-stu-id="86fde-110">The tables in the databases are cleaned out according to a regular schedule.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86fde-111">如果 BAM 主导入数据库和 DTA DB 数据库执行存档的时间间隔不同，则它们可能无法保持同步。</span><span class="sxs-lookup"><span data-stu-id="86fde-111">The BAM Primary Import and DTA DB databases could be out of synch if each has a different interval for archiving.</span></span>  
  
 <span data-ttu-id="86fde-112">EDI 和 AS2 状态报告可能会对性能产生影响。</span><span class="sxs-lookup"><span data-stu-id="86fde-112">EDI and AS2 status reporting may have an impact upon performance.</span></span> <span data-ttu-id="86fde-113">有关详细信息，请参阅"性能注意事项的 EDI 和 AS2 状态报告" [EDI 和 AS2 性能已知问题](../core/known-issues-with-edi-and-as2-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="86fde-113">For more information, see "Performance Considerations for EDI and AS2 Status Reporting" in [Known Issues with EDI and AS2 Performance](../core/known-issues-with-edi-and-as2-performance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86fde-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86fde-114">See Also</span></span>  
 [<span data-ttu-id="86fde-115">如何将数据存储用于 EDI 和 AS2 状态报表</span><span class="sxs-lookup"><span data-stu-id="86fde-115">How Data Is Stored for EDI and AS2 Status Reports</span></span>](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)