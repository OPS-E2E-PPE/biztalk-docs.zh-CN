---
title: 如何获取活动时段的持续时间 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], time intervals
- managing [BAM], time intervals
- Get-ActivityWindow command [BAM]
ms.assetid: d70f6767-f6f7-4ecf-ad9d-4a9d8c76edea
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cd175c4bc4f96a9717371ad3fe72433231cbc44
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337641"
---
# <a name="how-to-get-the-duration-on-an-activity-window"></a><span data-ttu-id="12cf0-102">如何获取活动时段的持续时间</span><span class="sxs-lookup"><span data-stu-id="12cf0-102">How to Get the Duration on an Activity Window</span></span>
<span data-ttu-id="12cf0-103">管理员使用**get activitywindow**命令来获取指定活动的持续时间。</span><span class="sxs-lookup"><span data-stu-id="12cf0-103">Administrators use the **get-activitywindow** command to get the duration for the specified activity.</span></span> <span data-ttu-id="12cf0-104">该命令返回持续时间和持续时间单位所依据的单位的长度。</span><span class="sxs-lookup"><span data-stu-id="12cf0-104">The command returns the length of the duration and the units by which the duration is measured.</span></span>  
  
### <a name="to-get-the-duration-on-an-activity"></a><span data-ttu-id="12cf0-105">若要获取活动的持续时间</span><span class="sxs-lookup"><span data-stu-id="12cf0-105">To get the duration on an activity</span></span>  
  
1. <span data-ttu-id="12cf0-106">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="12cf0-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="12cf0-107">导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪。</span><span class="sxs-lookup"><span data-stu-id="12cf0-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="12cf0-108">键入 bm get activitywindow-活动：\<活动名称\>。</span><span class="sxs-lookup"><span data-stu-id="12cf0-108">Type  bm get-activitywindow -Activity:\<activity name\>.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="12cf0-109">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="12cf0-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="12cf0-110">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="12cf0-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12cf0-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="12cf0-111">See Also</span></span>  
 <span data-ttu-id="12cf0-112">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="12cf0-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="12cf0-113">[BAM 管理实用程序](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="12cf0-113">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="12cf0-114">如何设置活动时段的持续时间</span><span class="sxs-lookup"><span data-stu-id="12cf0-114">How to Set the Duration on an Activity Window</span></span>](../core/how-to-set-the-duration-on-an-activity-window.md)