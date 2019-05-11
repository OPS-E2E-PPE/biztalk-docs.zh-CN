---
title: 如何获取聚合的索引列表 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- indexes [BAM], listing indexes
- aggregations [BAM], listing indexes
- Get-Index command [BAM]
ms.assetid: 46a4a2fc-10f8-499c-bf2a-d0a19bb84151
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c7803ba15bb06297b477e9bfcc5ad0535f0168b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385038"
---
# <a name="how-to-get-a-list-of-indexes-on-an-aggregation"></a><span data-ttu-id="bf306-102">如何获取聚合的索引列表</span><span class="sxs-lookup"><span data-stu-id="bf306-102">How to Get a List of Indexes on an Aggregation</span></span>
<span data-ttu-id="bf306-103">管理员使用**获取索引**命令来获取指定的活动上的所有索引列表。</span><span class="sxs-lookup"><span data-stu-id="bf306-103">Administrators use the **get-index** command to get a list of all the indexes on the specified activity.</span></span>  
  
### <a name="to-get-a-list-of-indexes-on-an-aggregation"></a><span data-ttu-id="bf306-104">若要获取聚合的索引列表</span><span class="sxs-lookup"><span data-stu-id="bf306-104">To get a list of indexes on an aggregation</span></span>  
  
1. <span data-ttu-id="bf306-105">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="bf306-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="bf306-106">导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪。</span><span class="sxs-lookup"><span data-stu-id="bf306-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="bf306-107">类型**bm 获取索引的活动：\<活动名称\>**。</span><span class="sxs-lookup"><span data-stu-id="bf306-107">Type **bm get-index -Activity:\<activity name\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="bf306-108">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="bf306-108">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="bf306-109">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="bf306-109">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf306-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf306-110">See Also</span></span>  
 <span data-ttu-id="bf306-111">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="bf306-111">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="bf306-112">[BAM 管理实用程序](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="bf306-112">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 <span data-ttu-id="bf306-113">[如何删除索引](../core/how-to-delete-an-index.md) </span><span class="sxs-lookup"><span data-stu-id="bf306-113">[How to Delete an Index](../core/how-to-delete-an-index.md) </span></span>  
 [<span data-ttu-id="bf306-114">如何创建索引</span><span class="sxs-lookup"><span data-stu-id="bf306-114">How to Create an Index</span></span>](../core/how-to-create-an-index.md)