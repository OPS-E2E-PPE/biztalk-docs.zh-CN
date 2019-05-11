---
title: 维护 BizTalk Server2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5b9c10d1-101b-4b9d-8eab-767b853f17d8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b09c8f6ffd1a7467a992c51a737d1f77a75ba93
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396268"
---
# <a name="maintaining-biztalk-server2"></a><span data-ttu-id="36522-102">维护 BizTalk Server2</span><span class="sxs-lookup"><span data-stu-id="36522-102">Maintaining BizTalk Server2</span></span>
<span data-ttu-id="36522-103">维护活动是在服务监视和控制 (SMC) 系统管理函数定义由 Microsoft Operations Framework (MOF) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="36522-103">Maintenance activities are part of the Service Monitoring and Control (SMC) system management function as defined by the Microsoft Operations Framework (MOF).</span></span> <span data-ttu-id="36522-104">SMC 的主要目标是要观察的运行状况在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。</span><span class="sxs-lookup"><span data-stu-id="36522-104">The primary goal of SMC is to observe the health of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span> <span data-ttu-id="36522-105">SMC 检查可能会启动补救措施以避免潜在的服务事件并在出现时，服务事件的影响降至最低。</span><span class="sxs-lookup"><span data-stu-id="36522-105">SMC checks may initiate remedial actions to avoid potential service incidents and to minimize the impact of service incidents when they do occur.</span></span>  
  
 <span data-ttu-id="36522-106">用于指南的本部分的目的，SMC 活动分为四个三大类： 可靠性、 管理、 安全性和性能。</span><span class="sxs-lookup"><span data-stu-id="36522-106">For the purposes of this section of the guide, SMC activities are divided into four three broad categories: reliability, administration, security, and performance.</span></span> <span data-ttu-id="36522-107">每日、 每周和每月维护清单组织 SMC 检查根据每个检查应执行的频率。</span><span class="sxs-lookup"><span data-stu-id="36522-107">The daily, weekly, and monthly maintenance checklists organize SMC checks according to how frequently each check should be performed.</span></span> <span data-ttu-id="36522-108">如果 SMC 检查指示需要更正操作，清单将定向到的附加信息来解决该问题的源。</span><span class="sxs-lookup"><span data-stu-id="36522-108">If SMC checks indicate that remedial action is necessary, the checklists will direct you to sources of additional information to resolve the problem.</span></span>  
  
 <span data-ttu-id="36522-109">解决可靠性相关的各节，管理、 安全性和性能问题包含有关识别和解决过程中遇到的许多常见问题的信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]操作。</span><span class="sxs-lookup"><span data-stu-id="36522-109">The sections pertaining to resolving reliability, administration, security, and performance issues contain information about identifying and resolving many common problems encountered during [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] operations.</span></span>  
  
 <span data-ttu-id="36522-110">有关 Microsoft Operations Framework 的详细信息，请参阅[ http://go.microsoft.com/fwlink/?linkid=88047 ](http://go.microsoft.com/fwlink/?linkid=88047)。</span><span class="sxs-lookup"><span data-stu-id="36522-110">For more information about the Microsoft Operations Framework, see [http://go.microsoft.com/fwlink/?linkid=88047](http://go.microsoft.com/fwlink/?linkid=88047).</span></span> <span data-ttu-id="36522-111">有关服务监视和控制函数的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=155341 ](http://go.microsoft.com/fwlink/?LinkId=155341)。</span><span class="sxs-lookup"><span data-stu-id="36522-111">For more information about the Service Monitoring and Control function, see [http://go.microsoft.com/fwlink/?LinkId=155341](http://go.microsoft.com/fwlink/?LinkId=155341).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="36522-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="36522-112">In This Section</span></span>  
  
-   [<span data-ttu-id="36522-113">维护可靠性</span><span class="sxs-lookup"><span data-stu-id="36522-113">Maintaining Reliability</span></span>](../technical-guides/maintaining-reliability.md)  
  
-   [<span data-ttu-id="36522-114">管理维护</span><span class="sxs-lookup"><span data-stu-id="36522-114">Administrative Maintenance</span></span>](../technical-guides/administrative-maintenance.md)  
  
-   [<span data-ttu-id="36522-115">维护性能</span><span class="sxs-lookup"><span data-stu-id="36522-115">Maintaining Performance</span></span>](../technical-guides/maintaining-performance.md)  
  
-   [<span data-ttu-id="36522-116">维护 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="36522-116">Maintaining BizTalk Server Databases</span></span>](../technical-guides/maintaining-biztalk-server-databases.md)  
  
## <a name="related-sections"></a><span data-ttu-id="36522-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="36522-117">Related Sections</span></span>  
 [<span data-ttu-id="36522-118">清单：执行每日维护检查</span><span class="sxs-lookup"><span data-stu-id="36522-118">Checklist: Performing Daily Maintenance Checks</span></span>](../technical-guides/checklist-performing-daily-maintenance-checks.md)  
  
 [<span data-ttu-id="36522-119">清单：执行每周维护检查</span><span class="sxs-lookup"><span data-stu-id="36522-119">Checklist: Performing Weekly Maintenance Checks</span></span>](../technical-guides/checklist-performing-weekly-maintenance-checks.md)  
  
 [<span data-ttu-id="36522-120">清单：执行每月维护检查</span><span class="sxs-lookup"><span data-stu-id="36522-120">Checklist: Performing Monthly Maintenance Checks</span></span>](../technical-guides/checklist-performing-monthly-maintenance-checks.md)