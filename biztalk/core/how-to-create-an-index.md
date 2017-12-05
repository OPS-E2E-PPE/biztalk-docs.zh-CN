---
title: "如何创建索引 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Create-Index command [BAM]
- indexes [BAM], creating
- indexes [BAM], aggregations
- creating, indexes [BAM]
- aggregations [BAM], indexes
ms.assetid: 456d94e6-2e84-4d12-ad38-49f9eeb103f3
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61c0393beae4883359d71915543b629e41c5f6ec
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-create-an-index"></a><span data-ttu-id="2c0a5-102">如何创建索引</span><span class="sxs-lookup"><span data-stu-id="2c0a5-102">How to Create an Index</span></span>
<span data-ttu-id="2c0a5-103">管理员使用**创建索引**命令以在指定的检查点的指定活动上创建索引。</span><span class="sxs-lookup"><span data-stu-id="2c0a5-103">Administrators use the **create-index** command to create an index on the specified activity at the specified checkpoints.</span></span>  
  
### <a name="to-create-an-index-on-an-activity"></a><span data-ttu-id="2c0a5-104">对活动创建索引</span><span class="sxs-lookup"><span data-stu-id="2c0a5-104">To create an index on an activity</span></span>  
  
1.  <span data-ttu-id="2c0a5-105">从命令提示符处，浏览到以下目录：[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪。</span><span class="sxs-lookup"><span data-stu-id="2c0a5-105">From a command prompt, browse to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
2.  <span data-ttu-id="2c0a5-106">类型**bm 创建索引 IndexName:\<索引名称\>的活动：\<活动名称\>的检查点：\<checkpoint1\>**。</span><span class="sxs-lookup"><span data-stu-id="2c0a5-106">Type **bm create-index -IndexName:\<index name\> -Activity:\<activity name\> -Checkpoint:\<checkpoint1\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2c0a5-107">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="2c0a5-107">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
3.  <span data-ttu-id="2c0a5-108">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="2c0a5-108">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c0a5-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c0a5-109">See Also</span></span>  
 <span data-ttu-id="2c0a5-110">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="2c0a5-110">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="2c0a5-111">[BAM 管理实用工具](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="2c0a5-111">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 <span data-ttu-id="2c0a5-112">[如何删除索引](../core/how-to-delete-an-index.md) </span><span class="sxs-lookup"><span data-stu-id="2c0a5-112">[How to Delete an Index](../core/how-to-delete-an-index.md) </span></span>  
 [<span data-ttu-id="2c0a5-113">如何获取有关聚合的索引的列表</span><span class="sxs-lookup"><span data-stu-id="2c0a5-113">How to Get a List of Indexes on an Aggregation</span></span>](../core/how-to-get-a-list-of-indexes-on-an-aggregation.md)