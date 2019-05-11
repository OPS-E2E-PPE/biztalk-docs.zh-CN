---
title: 如何删除 BAM 视图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, views
- managing [BAM definitions], deleting views
- Remove-View command [BAM]
ms.assetid: 1a43ec81-20b1-41f7-941f-753132ac9ed2
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bab2394ab3e2d93f9e333c9f4c58940996dd431
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334989"
---
# <a name="how-to-remove-bam-views"></a><span data-ttu-id="e54bc-102">如何删除 BAM 视图</span><span class="sxs-lookup"><span data-stu-id="e54bc-102">How to Remove BAM Views</span></span>
<span data-ttu-id="e54bc-103">管理员使用**删除视图**命令以从 BAM 主导入数据库中删除视图。</span><span class="sxs-lookup"><span data-stu-id="e54bc-103">Administrators use the **remove-view** command to remove a view from the BAM Primary Import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e54bc-104">删除视图时，您还会自动删除该视图的定义的所有警报。</span><span class="sxs-lookup"><span data-stu-id="e54bc-104">When you remove a view, you also automatically remove any alerts defined for that view.</span></span>  
  
### <a name="to-remove-bam-views"></a><span data-ttu-id="e54bc-105">若要删除 BAM 视图</span><span class="sxs-lookup"><span data-stu-id="e54bc-105">To remove BAM views</span></span>  
  
1.  <span data-ttu-id="e54bc-106">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e54bc-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="e54bc-107">通过键入导航到跟踪文件夹**C:\Program Files\Microsoft BizTalk Server 2009\Tracking**在命令提示符处。</span><span class="sxs-lookup"><span data-stu-id="e54bc-107">Navigate to the tracking folder by typing **C:\Program Files\Microsoft BizTalk Server 2009\Tracking** at the command prompt.</span></span> <span data-ttu-id="e54bc-108">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="e54bc-108">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="e54bc-109">类型**bm 删除视图的名称：\<视图名称\>**。</span><span class="sxs-lookup"><span data-stu-id="e54bc-109">Type **bm remove-view -Name:\<view name\>**.</span></span>  
  
4.  <span data-ttu-id="e54bc-110">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="e54bc-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e54bc-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="e54bc-111">See Also</span></span>  
 <span data-ttu-id="e54bc-112">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="e54bc-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="e54bc-113">[BAM 安全建议](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="e54bc-113">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 <span data-ttu-id="e54bc-114">[BAM 管理实用程序](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="e54bc-114">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="e54bc-115">如何删除 BAM 警报</span><span class="sxs-lookup"><span data-stu-id="e54bc-115">How to Remove BAM Alerts</span></span>](../core/how-to-remove-bam-alerts.md)