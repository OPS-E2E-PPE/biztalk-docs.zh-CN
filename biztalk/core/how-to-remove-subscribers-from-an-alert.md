---
title: "如何从警报中删除订阅服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- subscriptions, subscribers
- managing [BAM], deleting alert subscibers
- alerts, subscribers
ms.assetid: d5571863-26e3-4c1b-991f-538cd1fef347
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9122b74ecc82e32230d09e2d0e01b553aaa2bd06
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-remove-subscribers-from-an-alert"></a><span data-ttu-id="45159-102">如何从警报删除订户</span><span class="sxs-lookup"><span data-stu-id="45159-102">How to Remove Subscribers from an Alert</span></span>
<span data-ttu-id="45159-103">管理员使用**删除订阅**命令从警报作为订阅服务器中删除指定的用户。</span><span class="sxs-lookup"><span data-stu-id="45159-103">Administrators use the **remove-subscription** command to remove the specified user as a subscriber from an alert.</span></span>  
  
### <a name="to-remove-subscribers-from-an-alert"></a><span data-ttu-id="45159-104">从警报中删除订户</span><span class="sxs-lookup"><span data-stu-id="45159-104">To remove subscribers from an alert</span></span>  
  
1.  <span data-ttu-id="45159-105">如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="45159-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="45159-106">导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。</span><span class="sxs-lookup"><span data-stu-id="45159-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="45159-107">类型**bm 删除订阅的视图：\<视图名称\>-警报：\<警报名称\>-AccountName:\<帐户名称\>**。</span><span class="sxs-lookup"><span data-stu-id="45159-107">Type **bm remove-subscription -View:\<view name\> -Alert:\<alert name\> -AccountName:\<account name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="45159-108">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="45159-108">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="45159-109">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="45159-109">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45159-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45159-110">See Also</span></span>  
 <span data-ttu-id="45159-111">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="45159-111">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="45159-112">[BAM 管理实用工具](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="45159-112">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="45159-113">如何将订阅服务器添加到警报</span><span class="sxs-lookup"><span data-stu-id="45159-113">How to Add Subscribers to an Alert</span></span>](../core/how-to-add-subscribers-to-an-alert.md)