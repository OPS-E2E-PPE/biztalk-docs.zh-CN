---
title: 如何获取 RTA 时段的持续时间 |Microsoft Docs
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
- managing [BAM], time intervals
- Get-RTAWindow command [BAM]
ms.assetid: 4e7ad0fd-e7ed-47f7-9435-ef01bbe17afa
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6893200c498fc387d9a1948d332db409cf3b4d61
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992694"
---
# <a name="how-to-get-the-duration-on-an-rta-window"></a><span data-ttu-id="cba94-102">如何获取 RTA 时段的持续时间</span><span class="sxs-lookup"><span data-stu-id="cba94-102">How to Get the Duration on an RTA Window</span></span>
<span data-ttu-id="cba94-103">管理员使用**get rtawindow**命令来获取指定实时聚合 (RTA) 的持续时间。</span><span class="sxs-lookup"><span data-stu-id="cba94-103">Administrators use the **get-rtawindow** command to get the duration for the specified real-time aggregation (RTA).</span></span> <span data-ttu-id="cba94-104">该命令返回持续时间的长度和度量单位。</span><span class="sxs-lookup"><span data-stu-id="cba94-104">The command returns the length of the duration and the units by which the duration is measured.</span></span>  
  
### <a name="to-get-the-duration-on-an-aggregation"></a><span data-ttu-id="cba94-105">获取聚合的持续时间</span><span class="sxs-lookup"><span data-stu-id="cba94-105">To get the duration on an aggregation</span></span>  
  
1. <span data-ttu-id="cba94-106">按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cba94-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="cba94-107">导航到文件夹 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。</span><span class="sxs-lookup"><span data-stu-id="cba94-107">Navigate to the folder [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="cba94-108">类型**bm get rtawindow 的视图：\<视图名称\>的活动：\<活动名称\>-Rta:\<RTA 名称\>**。</span><span class="sxs-lookup"><span data-stu-id="cba94-108">Type **bm get-rtawindow -View:\<view name\> -Activity:\<activity name\> -Rta:\<RTA name\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="cba94-109">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="cba94-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="cba94-110">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="cba94-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cba94-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="cba94-111">See Also</span></span>  
 <span data-ttu-id="cba94-112">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="cba94-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="cba94-113">[BAM 管理实用程序](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="cba94-113">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="cba94-114">如何设置 RTA 时段的持续时间</span><span class="sxs-lookup"><span data-stu-id="cba94-114">How to Set the Duration on an RTA Window</span></span>](../core/how-to-set-the-duration-on-an-rta-window.md)