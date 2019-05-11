---
title: 如何设置 RTA 时段的持续时间 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], aggregations
- aggregations [BAM], time intervals
- Set-RTAWindow command [BAM]
- managing [BAM], time intervals
ms.assetid: 3042c3f5-be0f-48fb-9831-daa4868b90fe
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b090f8b21c58b6e73435c880effd6fb6597b8371
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383885"
---
# <a name="how-to-set-the-duration-on-an-rta-window"></a><span data-ttu-id="8fd77-102">如何设置 RTA 时段的持续时间</span><span class="sxs-lookup"><span data-stu-id="8fd77-102">How to Set the Duration on an RTA Window</span></span>
<span data-ttu-id="8fd77-103">管理员使用**集 rtawindow**命令以设置指定实时聚合 (RTA) 的持续时间。</span><span class="sxs-lookup"><span data-stu-id="8fd77-103">Administrators use the **set-rtawindow** command to set the duration for the specified real-time aggregation (RTA).</span></span>  
  
### <a name="to-set-the-duration-on-an-aggregation"></a><span data-ttu-id="8fd77-104">若要设置聚合的持续时间</span><span class="sxs-lookup"><span data-stu-id="8fd77-104">To set the duration on an aggregation</span></span>  
  
1. <span data-ttu-id="8fd77-105">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8fd77-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="8fd77-106">通过键入导航到跟踪文件夹[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪在命令提示符处。</span><span class="sxs-lookup"><span data-stu-id="8fd77-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="8fd77-107">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="8fd77-107">Press **ENTER**.</span></span>  
  
3. <span data-ttu-id="8fd77-108">类型**bm 集 rtawindow 的视图：\<视图名称\>的活动：\<活动名称\>-名称：\<RTA 名称\>-TimeLength:\<整数\>-时间单位： 天&#124;小时&#124;分钟**。</span><span class="sxs-lookup"><span data-stu-id="8fd77-108">Type **bm set-rtawindow -View:\<view name\> -Activity:\<activity name\> -Name:\<RTA name\> -TimeLength:\<integer number\> -TimeUnit:Day&#124;Hour&#124;Minute**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="8fd77-109">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="8fd77-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="8fd77-110">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="8fd77-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fd77-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="8fd77-111">See Also</span></span>  
 <span data-ttu-id="8fd77-112">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="8fd77-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="8fd77-113">[BAM 管理实用程序](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="8fd77-113">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="8fd77-114">如何获取 RTA 时段的持续时间</span><span class="sxs-lookup"><span data-stu-id="8fd77-114">How to Get the Duration on an RTA Window</span></span>](../core/how-to-get-the-duration-on-an-rta-window.md)