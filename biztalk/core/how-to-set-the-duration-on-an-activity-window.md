---
title: 如何设置活动时段的持续时间 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Set-ActivityWindow command [BAM]
- activities [BAM], time intervals
- managing [BAM], time intervals
ms.assetid: e39c315e-f215-4f81-9774-cf7aedf6ba33
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c7bab9fe9c5969bf4f5d277b83b63f751e6afc9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334228"
---
# <a name="how-to-set-the-duration-on-an-activity-window"></a><span data-ttu-id="49bd0-102">如何设置活动时段的持续时间</span><span class="sxs-lookup"><span data-stu-id="49bd0-102">How to Set the Duration on an Activity Window</span></span>
<span data-ttu-id="49bd0-103">管理员使用**集 activitywindow**命令以设置指定活动的持续时间。</span><span class="sxs-lookup"><span data-stu-id="49bd0-103">Administrators use the **set-activitywindow** command to set the duration for the specified activity.</span></span>  
  
### <a name="to-set-the-duration-on-an-activity"></a><span data-ttu-id="49bd0-104">若要在活动上设置的持续时间</span><span class="sxs-lookup"><span data-stu-id="49bd0-104">To set the duration on an activity</span></span>  
  
1. <span data-ttu-id="49bd0-105">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="49bd0-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="49bd0-106">通过键入导航到跟踪文件夹[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪在命令提示符处。</span><span class="sxs-lookup"><span data-stu-id="49bd0-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="49bd0-107">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="49bd0-107">Press **ENTER**.</span></span>  
  
3. <span data-ttu-id="49bd0-108">类型**bm 集 activitywindow-活动：\<活动名称\>-TimeLength:\<整数\>-时间单位： 月&#124;天&#124;小时&#124;分钟**。</span><span class="sxs-lookup"><span data-stu-id="49bd0-108">Type **bm set-activitywindow -Activity:\<activity name\> -TimeLength:\<integer number\> -TimeUnit:Month&#124;Day&#124;Hour&#124;Minute**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="49bd0-109">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="49bd0-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="49bd0-110">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="49bd0-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49bd0-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="49bd0-111">See Also</span></span>  
 <span data-ttu-id="49bd0-112">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="49bd0-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="49bd0-113">[BAM 管理实用程序](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="49bd0-113">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="49bd0-114">如何获取活动时段的持续时间</span><span class="sxs-lookup"><span data-stu-id="49bd0-114">How to Get the Duration on an Activity Window</span></span>](../core/how-to-get-the-duration-on-an-activity-window.md)