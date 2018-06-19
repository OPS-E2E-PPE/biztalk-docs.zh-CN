---
title: 查询实例数据 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, instance data
- queries [BAM], instance data
ms.assetid: ae4a8854-d5c2-4b36-a0ef-3f74e138306e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e43310756cf12c0c2a48eb6716221afc5395ecb0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971827"
---
# <a name="querying-instance-data"></a><span data-ttu-id="6ee57-102">查询实例数据</span><span class="sxs-lookup"><span data-stu-id="6ee57-102">Querying Instance Data</span></span>
<span data-ttu-id="6ee57-103">关于各个活动实例的数据可在 BAM 主导入数据库中动态创建的 SQL 视图内进行查询。</span><span class="sxs-lookup"><span data-stu-id="6ee57-103">The data about individual activity instances is available for queries in a dynamically created SQL View in the BAM Primary Import Database.</span></span>  
  
 <span data-ttu-id="6ee57-104">此视图的名称是</span><span class="sxs-lookup"><span data-stu-id="6ee57-104">The name of this view is</span></span>  
  
 <span data-ttu-id="6ee57-105">**bam_\<**  *ViewName*  **\>_\<**  *ActivityName* **\>查看 （_v)**</span><span class="sxs-lookup"><span data-stu-id="6ee57-105">**bam_\<** *ViewName* **\>_\<** *ActivityName* **\>_View**</span></span>  
  
 <span data-ttu-id="6ee57-106">位置</span><span class="sxs-lookup"><span data-stu-id="6ee57-106">Where</span></span>  
  
 <span data-ttu-id="6ee57-107">**\<***ViewName*  **\>** 为在 BAM 定义 XML 中，视图元素的名称属性即相同在相关的 Microsoft Excel 向导中输入视图名称。</span><span class="sxs-lookup"><span data-stu-id="6ee57-107">**\<** *ViewName* **\>** is the Name Attribute of the View element in the BAM Definition XML, which is the same as the View Name entered in the related Microsoft Excel wizards.</span></span>  
  
 <span data-ttu-id="6ee57-108">**\<***ActivityName*  **\>** 为在 BAM 定义 XML 中，活动元素的名称属性即相同当在 Excel 向导中输入的活动名称。</span><span class="sxs-lookup"><span data-stu-id="6ee57-108">**\<** *ActivityName* **\>** is the Name Attribute of the Activity element in the BAM Definition XML, which is the same as the Activity Name entered in the Excel wizards.</span></span>  
  
 <span data-ttu-id="6ee57-109">在查询实例数据时，请一定要注意下列情况：</span><span class="sxs-lookup"><span data-stu-id="6ee57-109">It is important to note the following conditions when querying instance data:</span></span>  
  
-   <span data-ttu-id="6ee57-110">如果您通过 DirectEventStream 向 BAM 发送活动数据，则实例数据没有延迟时间，这意味着调用应用程序中的事务提交后，实例数据会立刻显示。</span><span class="sxs-lookup"><span data-stu-id="6ee57-110">If you send activity data to BAM via the DirectEventStream, the instance data has no latency, meaning that it appears instantaneously when the transaction in the calling application commits.</span></span>  
  
-   <span data-ttu-id="6ee57-111">如果活动数据通过 BufferedEventStream 发送到 BAM，则实例数据将在查询执行几秒钟后显示，具体情况取决于 BAM 事件总线服务的负载以及 BAM 主导入数据库的宿主 SQL 服务器。</span><span class="sxs-lookup"><span data-stu-id="6ee57-111">If the activity data is sent to BAM via the BufferedEventStream, the instance data will show up for queries a few seconds later, depending on the load of the BAM Event Bus service and the SQL server that hosts the BAM Primary Import Database.</span></span>  
  
-   <span data-ttu-id="6ee57-112">此视图背后的表的实际结构较复杂，这是为了确保当前或最新活动的数据可供查询，而活动查询不再需要的已完成活动的数据则被存档或清除，同时又不使系统脱机。</span><span class="sxs-lookup"><span data-stu-id="6ee57-112">The actual structure of tables behind this view is more complex to ensure that the data for the current or recent activities is available for queries, while data for activities that have completed and is no longer required for active queries is archived or purged without taking the system offline.</span></span> <span data-ttu-id="6ee57-113">有关详细信息，请参阅[活动数据存储](../core/activity-data-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="6ee57-113">For more information, see [Activity Data Storage](../core/activity-data-storage.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ee57-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ee57-114">See Also</span></span>  
 <span data-ttu-id="6ee57-115">[活动数据存储](../core/activity-data-storage.md) </span><span class="sxs-lookup"><span data-stu-id="6ee57-115">[Activity Data Storage](../core/activity-data-storage.md) </span></span>  
 [<span data-ttu-id="6ee57-116">查询 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="6ee57-116">Querying BAM Data</span></span>](../core/querying-bam-data.md)