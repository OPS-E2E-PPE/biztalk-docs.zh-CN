---
title: 状态报告数据存储 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6cd40ce8-1ac6-43b4-9cef-7cd045e8893c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0cb1d8d2a85cc88364da5bb43131213903b37d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392879"
---
# <a name="status-report-data-stores"></a><span data-ttu-id="b6089-102">状态报告数据存储区</span><span class="sxs-lookup"><span data-stu-id="b6089-102">Status Report Data Stores</span></span>
<span data-ttu-id="b6089-103">状态报告跟踪数据存储在 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="b6089-103">Status reporting tracking data is stored in the BAM Primary Import database.</span></span> <span data-ttu-id="b6089-104">在此数据库中的表数用于 EDI 和 AS2 消息数据，包括开头 dbo.bam_AS2、 dbo.bam.batching、 这些表和其他人的表。</span><span class="sxs-lookup"><span data-stu-id="b6089-104">A number of tables in this database are used for EDI and AS2 message data, including tables starting with dbo.bam_AS2, dbo.bam.batching, dbo.bam.InterchangeStatusActivity, and others.</span></span> <span data-ttu-id="b6089-105">状态数据存储在主导入数据库，即使禁用 EDI 报告。</span><span class="sxs-lookup"><span data-stu-id="b6089-105">Status data is stored in the Primary Import even if EDI reporting is disabled.</span></span> <span data-ttu-id="b6089-106">您将只能查看和查询这些数据在状态报告 UI，激活状态报告。</span><span class="sxs-lookup"><span data-stu-id="b6089-106">You will only be to view and query this data in the status reporting UI if status reporting is activated.</span></span>  
  
 <span data-ttu-id="b6089-107">如果出于不可否认，启用消息数据的存储[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将 EDI 和/或 AS2 数据存储在 BizTalk 跟踪数据库 (BizTalkDTADb) 的 EDI Message Content 表中。</span><span class="sxs-lookup"><span data-stu-id="b6089-107">If you enable storage of message data for non-repudiation purposes, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will store the EDI and/or AS2 data in the EDI Message Content table of the BizTalk tracking database (BizTalkDTADb).</span></span> <span data-ttu-id="b6089-108">如果启用消息内容存储以查看负载的详细信息 (通过选择**存储消息负载以用于报告**协议属性中的**常规属性**页**常规**选项卡中**协议属性**对话框中)，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]还会在此表中存储的事务集。</span><span class="sxs-lookup"><span data-stu-id="b6089-108">If you enable storage of message contents for viewing details of the payload (by selecting the **Store message payload for reporting** agreement property in the **General Properties** page of the **General** tab in the **Agreement Properties** dialog box), [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will also store the transaction sets in this table.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="b6089-109">存档和清除数据从 BAM 主导入和 BizTalkDTADb 数据库。</span><span class="sxs-lookup"><span data-stu-id="b6089-109">archives and purges data from the BAM Primary Import and BizTalkDTADb databases.</span></span> <span data-ttu-id="b6089-110">数据库中的表将定期清除。</span><span class="sxs-lookup"><span data-stu-id="b6089-110">The tables in the databases are cleaned out according to a regular schedule.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6089-111">BAM 主导入和 DTA DB 数据库可能是同步如果每个都有不同的时间间隔进行存档。</span><span class="sxs-lookup"><span data-stu-id="b6089-111">The BAM Primary Import and DTA DB databases could be out of synch if each has a different interval for archiving.</span></span>  
  
 <span data-ttu-id="b6089-112">EDI 和 AS2 状态报告可能会对性能影响。</span><span class="sxs-lookup"><span data-stu-id="b6089-112">EDI and AS2 status reporting may have an impact upon performance.</span></span> <span data-ttu-id="b6089-113">详细信息，请参阅"性能注意事项为 EDI 和 AS2 状态报告"中[EDI 和 AS2 性能的已知问题](../core/known-issues-with-edi-and-as2-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="b6089-113">For more information, see "Performance Considerations for EDI and AS2 Status Reporting" in [Known Issues with EDI and AS2 Performance](../core/known-issues-with-edi-and-as2-performance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6089-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6089-114">See Also</span></span>  
 [<span data-ttu-id="b6089-115">如何为 EDI 和 AS2 状态报告存储数据</span><span class="sxs-lookup"><span data-stu-id="b6089-115">How Data Is Stored for EDI and AS2 Status Reports</span></span>](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)