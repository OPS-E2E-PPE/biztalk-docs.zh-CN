---
title: 监视 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7effa38f-f9f2-40b7-8d8b-fa13cf94aa4f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8c7d6e8870d435163c83c053f981d42bad1858d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249627"
---
# <a name="monitoring"></a><span data-ttu-id="b66f2-102">监视</span><span class="sxs-lookup"><span data-stu-id="b66f2-102">Monitoring</span></span>
<span data-ttu-id="b66f2-103">默认情况下，所有 BizTalk 服务器监视和任务都使用的默认操作帐户没有特定的运行方式帐户定义的运行方式配置文件的 BizTalk Server 监视帐户中的目标时。</span><span class="sxs-lookup"><span data-stu-id="b66f2-103">By default, all BizTalk Server monitoring and tasks use the default action account when there is no specific Run As Account defined for the target in the Run As Profile of the BizTalk Server Monitoring Account.</span></span> <span data-ttu-id="b66f2-104">若要配置运行方式帐户与最小所需的监视目的的 BizTalk Server 的权限集，都需要以下权限：</span><span class="sxs-lookup"><span data-stu-id="b66f2-104">To configure a Run As Account with the minimum set of permissions that are required for BizTalk Server monitoring purposes, the following permissions are required:</span></span>  
  
-   <span data-ttu-id="b66f2-105">该帐户必须是受监视的计算机的内置管理员组和性能监视器用户组的成员。</span><span class="sxs-lookup"><span data-stu-id="b66f2-105">The account must be a member of the monitored computer’s built-in Administrators group and Performance Monitors Users group.</span></span>  
  
-   <span data-ttu-id="b66f2-106">该帐户必须是 SQL 实例或托管的数据库和 BizTalk 组所监视的作业实例中 SysAdmin 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="b66f2-106">The account must be a member of the SysAdmin role within the SQL instance or instances hosting the databases and jobs for the BizTalk group that is being monitored.</span></span>  
  
-   <span data-ttu-id="b66f2-107">有关 BizTalk Server 中监视的目的，帐户必须是 BizTalk Operators 组的一部分。</span><span class="sxs-lookup"><span data-stu-id="b66f2-107">For BizTalk Server monitoring purposes, the account must be a part of BizTalk Operators group.</span></span>  
  
-   <span data-ttu-id="b66f2-108">用于通过 SCOM 控制台运行任务，该帐户必须是 BizTalk Application Users 组的一部分。</span><span class="sxs-lookup"><span data-stu-id="b66f2-108">For running tasks through SCOM console, the account must be a part of BizTalk Application Users group.</span></span>  
  
-   <span data-ttu-id="b66f2-109">用于执行管理任务，该帐户必须是 BizTalk 管理员组的一部分。</span><span class="sxs-lookup"><span data-stu-id="b66f2-109">For performing administrative tasks, the account must be a part of BizTalk Administrator group.</span></span>