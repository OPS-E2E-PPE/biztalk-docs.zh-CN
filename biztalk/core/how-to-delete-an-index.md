---
title: 如何删除索引 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- indexes [BAM], deleting
- Get-Index command [BAM]
- aggregations [BAM], indexes
ms.assetid: 5f9c7989-3357-451f-8565-1d4b01c1d16a
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aaafdf9515849fb84d569fb50a3e7117f30969b3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978326"
---
# <a name="how-to-delete-an-index"></a><span data-ttu-id="123dc-102">如何删除索引</span><span class="sxs-lookup"><span data-stu-id="123dc-102">How to Delete an Index</span></span>
<span data-ttu-id="123dc-103">管理员使用**删除索引**命令以删除指定的活动在指定检查点的索引。</span><span class="sxs-lookup"><span data-stu-id="123dc-103">Administrators use the **delete-index** command to delete an index on the specified activity at the specified checkpoints.</span></span>  
  
### <a name="to-delete-an-index-on-an-activity"></a><span data-ttu-id="123dc-104">若要删除活动的索引</span><span class="sxs-lookup"><span data-stu-id="123dc-104">To delete an index on an activity</span></span>  
  
1. <span data-ttu-id="123dc-105">按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="123dc-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="123dc-106">通过在命令提示符处键入 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking，导航到跟踪文件夹。</span><span class="sxs-lookup"><span data-stu-id="123dc-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="123dc-107">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="123dc-107">Press **ENTER**.</span></span>  
  
3. <span data-ttu-id="123dc-108">类型**bm 删除索引-IndexName:\<索引名称\>的活动：\<活动名称\>**。</span><span class="sxs-lookup"><span data-stu-id="123dc-108">Type **bm delete-index -IndexName:\<index name\> -Activity:\<activity name\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="123dc-109">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="123dc-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="123dc-110">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="123dc-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="123dc-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="123dc-111">See Also</span></span>  
 <span data-ttu-id="123dc-112">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="123dc-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="123dc-113">[BAM 管理实用程序](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="123dc-113">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 <span data-ttu-id="123dc-114">[如何删除索引](../core/how-to-delete-an-index.md) </span><span class="sxs-lookup"><span data-stu-id="123dc-114">[How to Delete an Index](../core/how-to-delete-an-index.md) </span></span>  
 [<span data-ttu-id="123dc-115">如何获取聚合的索引列表</span><span class="sxs-lookup"><span data-stu-id="123dc-115">How to Get a List of Indexes on an Aggregation</span></span>](../core/how-to-get-a-list-of-indexes-on-an-aggregation.md)