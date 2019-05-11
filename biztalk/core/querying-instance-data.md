---
title: 查询实例数据 |Microsoft Docs
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
ms.openlocfilehash: 083bbe25734f5305c2c7e49837955f648a65a52d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398299"
---
# <a name="querying-instance-data"></a><span data-ttu-id="ea2b1-102">查询实例数据</span><span class="sxs-lookup"><span data-stu-id="ea2b1-102">Querying Instance Data</span></span>
<span data-ttu-id="ea2b1-103">有关各个活动实例的数据是可在 BAM 主导入数据库中动态创建的 SQL 视图中进行查询。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-103">The data about individual activity instances is available for queries in a dynamically created SQL View in the BAM Primary Import Database.</span></span>  
  
 <span data-ttu-id="ea2b1-104">此视图的名称是</span><span class="sxs-lookup"><span data-stu-id="ea2b1-104">The name of this view is</span></span>  
  
 <span data-ttu-id="ea2b1-105">**bam_\<** *ViewName* **\>_\<** *ActivityName* **\>_View**</span><span class="sxs-lookup"><span data-stu-id="ea2b1-105">**bam_\<** *ViewName* **\>_\<** *ActivityName* **\>_View**</span></span>  
  
 <span data-ttu-id="ea2b1-106">位置</span><span class="sxs-lookup"><span data-stu-id="ea2b1-106">Where</span></span>  
  
 <span data-ttu-id="ea2b1-107">**\<** *ViewName* **\>** 是 BAM 定义 XML 中 View 元素的名称属性即相同相关的 Microsoft Excel 向导中输入视图名称。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-107">**\<** *ViewName* **\>** is the Name Attribute of the View element in the BAM Definition XML, which is the same as the View Name entered in the related Microsoft Excel wizards.</span></span>  
  
 <span data-ttu-id="ea2b1-108">**\<** *ActivityName* **\>** 是 BAM 定义 XML 中的 Activity 元素的名称属性即相同在 Excel 向导中输入的活动名称。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-108">**\<** *ActivityName* **\>** is the Name Attribute of the Activity element in the BAM Definition XML, which is the same as the Activity Name entered in the Excel wizards.</span></span>  
  
 <span data-ttu-id="ea2b1-109">请务必查询实例数据时，请注意以下条件：</span><span class="sxs-lookup"><span data-stu-id="ea2b1-109">It is important to note the following conditions when querying instance data:</span></span>  
  
-   <span data-ttu-id="ea2b1-110">如果活动数据发送到通过 DirectEventStream BAM 时，实例数据有没有延迟时间，这意味着，会立刻显示调用应用程序中的事务提交后。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-110">If you send activity data to BAM via the DirectEventStream, the instance data has no latency, meaning that it appears instantaneously when the transaction in the calling application commits.</span></span>  
  
-   <span data-ttu-id="ea2b1-111">如果活动数据发送到 BAM 通过 BufferedEventStream，数据会显示注册实例查询几秒钟后，具体取决于 BAM 事件总线服务和承载 BAM 主导入数据库的 SQL 服务器的负载。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-111">If the activity data is sent to BAM via the BufferedEventStream, the instance data will show up for queries a few seconds later, depending on the load of the BAM Event Bus service and the SQL server that hosts the BAM Primary Import Database.</span></span>  
  
-   <span data-ttu-id="ea2b1-112">此视图背后的表的实际结构是更复杂，以确保当前或最近活动的数据可用于查询，而存档或清除活动的已完成并且不再需要使活动查询数据无需使系统脱机。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-112">The actual structure of tables behind this view is more complex to ensure that the data for the current or recent activities is available for queries, while data for activities that have completed and is no longer required for active queries is archived or purged without taking the system offline.</span></span> <span data-ttu-id="ea2b1-113">有关详细信息，请参阅[活动数据存储](../core/activity-data-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-113">For more information, see [Activity Data Storage](../core/activity-data-storage.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea2b1-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea2b1-114">See Also</span></span>  
 <span data-ttu-id="ea2b1-115">[活动数据存储](../core/activity-data-storage.md) </span><span class="sxs-lookup"><span data-stu-id="ea2b1-115">[Activity Data Storage](../core/activity-data-storage.md) </span></span>  
 [<span data-ttu-id="ea2b1-116">查询 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="ea2b1-116">Querying BAM Data</span></span>](../core/querying-bam-data.md)