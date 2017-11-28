---
title: "已知问题 EDI 和 AS2 性能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c47294f9-f728-4b6b-abe1-578434eb54df
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e034cf228ee92157c4b29c36660111bb1856c358
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-edi-and-as2-performance"></a><span data-ttu-id="d1a05-102">EDI 和 AS2 性能的已知问题</span><span class="sxs-lookup"><span data-stu-id="d1a05-102">Known Issues with EDI and AS2 Performance</span></span>
<span data-ttu-id="d1a05-103">本主题介绍有关 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的性能和 AS2 解决方案的已知问题。</span><span class="sxs-lookup"><span data-stu-id="d1a05-103">This topic describes known issues with the performance of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2 solutions.</span></span>  
  
## <a name="performance-considerations-for-edi-and-as2-status-reporting"></a><span data-ttu-id="d1a05-104">EDI 和 AS2 状态报告在性能方面的注意事项</span><span class="sxs-lookup"><span data-stu-id="d1a05-104">Performance Considerations for EDI and AS2 Status Reporting</span></span>  
 <span data-ttu-id="d1a05-105">激活 EDI 或 AS2 状态报告后，为多少消息执行状态报告可能会影响系统的性能。</span><span class="sxs-lookup"><span data-stu-id="d1a05-105">When you activate EDI or AS2 status reporting, the performance of your system may be affected by the number of messages that status reporting is performed for.</span></span> <span data-ttu-id="d1a05-106">为 EDI 或 AS2 处理选择了“存储事务集/负载以用于报告”属性后，为多大的消息执行状态报告可能会影响系统的性能。</span><span class="sxs-lookup"><span data-stu-id="d1a05-106">When you select the "Store transaction set/payload for reporting" property for either EDI or AS2 processing, the performance of your system may be affected by the size of the messages that status reporting is performed for.</span></span>  
  
 <span data-ttu-id="d1a05-107">BAMPrimaryImport 数据库中用于 EDI 或 AS2 状态报告的表已进行了优化。</span><span class="sxs-lookup"><span data-stu-id="d1a05-107">The tables used in the BAMPrimaryImport database for EDI or AS2 status reporting are optimized.</span></span> <span data-ttu-id="d1a05-108">不需要进行进一步的优化。</span><span class="sxs-lookup"><span data-stu-id="d1a05-108">No further optimization is required.</span></span> <span data-ttu-id="d1a05-109">但可以增大 BAM 主导入数据库中数据的存档速率，方法是更改 BAMPrimaryImport 数据库中活动实例数据的存档时段。</span><span class="sxs-lookup"><span data-stu-id="d1a05-109">You can, however, increase the rate at which data from the BAM primary import database is archived by changing the time window for archiving activity instance data in the BAMPrimaryImport database.</span></span> <span data-ttu-id="d1a05-110">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 文档中的“存档主导入数据库数据”。</span><span class="sxs-lookup"><span data-stu-id="d1a05-110">For more information, see "Archiving Primary Import Database Data" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
 <span data-ttu-id="d1a05-111">事务集/负载数据存储在 BizTalkDTADb 数据库中。</span><span class="sxs-lookup"><span data-stu-id="d1a05-111">Transaction set/payload data is stored in the BizTalkDTADb database.</span></span> <span data-ttu-id="d1a05-112">有关此数据库性能的详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 文档中的“了解 DTA 跟踪性能行为”。</span><span class="sxs-lookup"><span data-stu-id="d1a05-112">For more information about the performance of this database, see "Understanding DTA Tracking Performance Behavior" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
 <span data-ttu-id="d1a05-113">系统的性能还可能受在系统配置中启用的状态报告的程度影响。</span><span class="sxs-lookup"><span data-stu-id="d1a05-113">Performance of your system may also be affected by the degree of status reporting enabled in the configuration of your system.</span></span> <span data-ttu-id="d1a05-114">通过禁用特定类型的状态报告，或许能够提高性能。</span><span class="sxs-lookup"><span data-stu-id="d1a05-114">You may be able to improve performance by disabling a specific type of status reporting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1a05-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1a05-115">See Also</span></span>  
 [<span data-ttu-id="d1a05-116">EDI 和 AS2 解决方案疑难解答</span><span class="sxs-lookup"><span data-stu-id="d1a05-116">Troubleshooting EDI and AS2 Solutions</span></span>](../core/troubleshooting-edi-and-as2-solutions.md)