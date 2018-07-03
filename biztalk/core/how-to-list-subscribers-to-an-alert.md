---
title: 如何列出警报的订户 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- alerts, listing subscribers
- managing [BAM], listing alert subscribers
- subscriptions, listing subscribers
ms.assetid: 760cc88f-896d-43a3-a4af-b2a836190276
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae95582e2923c682a5d4138235029f21293fd847
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972646"
---
# <a name="how-to-list-subscribers-to-an-alert"></a><span data-ttu-id="acda6-102">如何列出警报的订户</span><span class="sxs-lookup"><span data-stu-id="acda6-102">How to List Subscribers to an Alert</span></span>
<span data-ttu-id="acda6-103">管理员使用**获取订阅**命令以列出所有订阅服务器对指定的警报。</span><span class="sxs-lookup"><span data-stu-id="acda6-103">Administrators use the **get-subscriptions** command to list all of the subscribers to a specified alert.</span></span>  
  
### <a name="to-list-subscribers-to-an-alert"></a><span data-ttu-id="acda6-104">列出警报的订户</span><span class="sxs-lookup"><span data-stu-id="acda6-104">To list subscribers to an alert</span></span>  
  
1. <span data-ttu-id="acda6-105">按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="acda6-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="acda6-106">导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。</span><span class="sxs-lookup"><span data-stu-id="acda6-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="acda6-107">类型**bm 获取订阅的视图：\<视图名称\>-警报：\<警报名称\>**。</span><span class="sxs-lookup"><span data-stu-id="acda6-107">Type **bm get-subscriptions -View:\<view name\> -Alert:\<alert name\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="acda6-108">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="acda6-108">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="acda6-109">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="acda6-109">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acda6-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="acda6-110">See Also</span></span>  
 <span data-ttu-id="acda6-111">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="acda6-111">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="acda6-112">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="acda6-112">BAM Management Utility</span></span>](../core/bam-management-utility.md)