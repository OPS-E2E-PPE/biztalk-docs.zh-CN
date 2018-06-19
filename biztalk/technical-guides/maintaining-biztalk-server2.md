---
title: 维护 BizTalk Server2 |Microsoft 文档
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
ms.openlocfilehash: c2d1b171f0506d7855d5faf23f2ebea393d21f60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298365"
---
# <a name="maintaining-biztalk-server2"></a><span data-ttu-id="410df-102">维护 BizTalk Server2</span><span class="sxs-lookup"><span data-stu-id="410df-102">Maintaining BizTalk Server2</span></span>
<span data-ttu-id="410df-103">维护活动是服务监视和控制 (SMC) 系统管理函数定义由 Microsoft Operations Framework (MOF) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="410df-103">Maintenance activities are part of the Service Monitoring and Control (SMC) system management function as defined by the Microsoft Operations Framework (MOF).</span></span> <span data-ttu-id="410df-104">SMC 的主要目标是观察的运行状况你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。</span><span class="sxs-lookup"><span data-stu-id="410df-104">The primary goal of SMC is to observe the health of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span> <span data-ttu-id="410df-105">SMC 检查可能启动更正操作来避免潜在的服务事件以及发生时，服务事件的影响降至最低。</span><span class="sxs-lookup"><span data-stu-id="410df-105">SMC checks may initiate remedial actions to avoid potential service incidents and to minimize the impact of service incidents when they do occur.</span></span>  
  
 <span data-ttu-id="410df-106">对于本指南此部分，SMC 活动划分为四个三大类： 可靠性、 管理、 安全性和性能。</span><span class="sxs-lookup"><span data-stu-id="410df-106">For the purposes of this section of the guide, SMC activities are divided into four three broad categories: reliability, administration, security, and performance.</span></span> <span data-ttu-id="410df-107">每日、 每周和每月的维护清单组织 SMC 检查根据应执行每个检查的频率。</span><span class="sxs-lookup"><span data-stu-id="410df-107">The daily, weekly, and monthly maintenance checklists organize SMC checks according to how frequently each check should be performed.</span></span> <span data-ttu-id="410df-108">如果 SMC 检查指示不需要执行更正操作，清单将定向到的其他信息来解决该问题的源。</span><span class="sxs-lookup"><span data-stu-id="410df-108">If SMC checks indicate that remedial action is necessary, the checklists will direct you to sources of additional information to resolve the problem.</span></span>  
  
 <span data-ttu-id="410df-109">与解决可靠性相关的各节，管理、 安全性和性能问题包含有关识别和解决过程中遇到的许多常见问题信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]操作。</span><span class="sxs-lookup"><span data-stu-id="410df-109">The sections pertaining to resolving reliability, administration, security, and performance issues contain information about identifying and resolving many common problems encountered during [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] operations.</span></span>  
  
 <span data-ttu-id="410df-110">有关 Microsoft Operations Framework 的详细信息，请参阅[http://go.microsoft.com/fwlink/?linkid=88047](http://go.microsoft.com/fwlink/?linkid=88047)。</span><span class="sxs-lookup"><span data-stu-id="410df-110">For more information about the Microsoft Operations Framework, see [http://go.microsoft.com/fwlink/?linkid=88047](http://go.microsoft.com/fwlink/?linkid=88047).</span></span> <span data-ttu-id="410df-111">有关服务监视和控制函数的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=155341](http://go.microsoft.com/fwlink/?LinkId=155341)。</span><span class="sxs-lookup"><span data-stu-id="410df-111">For more information about the Service Monitoring and Control function, see [http://go.microsoft.com/fwlink/?LinkId=155341](http://go.microsoft.com/fwlink/?LinkId=155341).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="410df-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="410df-112">In This Section</span></span>  
  
-   [<span data-ttu-id="410df-113">维护可靠性</span><span class="sxs-lookup"><span data-stu-id="410df-113">Maintaining Reliability</span></span>](../technical-guides/maintaining-reliability.md)  
  
-   [<span data-ttu-id="410df-114">管理维护</span><span class="sxs-lookup"><span data-stu-id="410df-114">Administrative Maintenance</span></span>](../technical-guides/administrative-maintenance.md)  
  
-   [<span data-ttu-id="410df-115">保持性能</span><span class="sxs-lookup"><span data-stu-id="410df-115">Maintaining Performance</span></span>](../technical-guides/maintaining-performance.md)  
  
-   [<span data-ttu-id="410df-116">维护 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="410df-116">Maintaining BizTalk Server Databases</span></span>](../technical-guides/maintaining-biztalk-server-databases.md)  
  
## <a name="related-sections"></a><span data-ttu-id="410df-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="410df-117">Related Sections</span></span>  
 [<span data-ttu-id="410df-118">清单： 执行日常维护检查</span><span class="sxs-lookup"><span data-stu-id="410df-118">Checklist: Performing Daily Maintenance Checks</span></span>](../technical-guides/checklist-performing-daily-maintenance-checks.md)  
  
 [<span data-ttu-id="410df-119">清单： 执行每周维护检查</span><span class="sxs-lookup"><span data-stu-id="410df-119">Checklist: Performing Weekly Maintenance Checks</span></span>](../technical-guides/checklist-performing-weekly-maintenance-checks.md)  
  
 [<span data-ttu-id="410df-120">清单： 执行每月的维护检查</span><span class="sxs-lookup"><span data-stu-id="410df-120">Checklist: Performing Monthly Maintenance Checks</span></span>](../technical-guides/checklist-performing-monthly-maintenance-checks.md)