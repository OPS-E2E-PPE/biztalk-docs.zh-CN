---
title: "针对灾难恢复进行规划 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a33e8875-cfde-4a60-9dab-fc6bb3ac4f1c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3619a34c843665750abd4f5d852b0f1af5210e1c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="planning-for-disaster-recovery"></a><span data-ttu-id="cf981-102">针对灾难恢复进行规划</span><span class="sxs-lookup"><span data-stu-id="cf981-102">Planning for Disaster Recovery</span></span>
<span data-ttu-id="cf981-103">本主题提供灾难恢复要求的应用程序团队和 BizTalk Server 的过程指南。</span><span class="sxs-lookup"><span data-stu-id="cf981-103">This topic provides guidance to application teams for disaster recovery requirements and procedures for BizTalk Server.</span></span> <span data-ttu-id="cf981-104">Microsoft BizTalk Server 配置和处理将信息存储在[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cf981-104">Microsoft BizTalk Server stores configuration and processing information in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="cf981-105">BizTalk Server 高可用性和灾难恢复通过的高可用性和灾难恢复功能[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cf981-105">BizTalk Server high availability and disaster recovery is achieved through the high availability and disaster recovery capabilities of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="cf981-106">BizTalk 组定义通过一组的数据库托管在[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cf981-106">A BizTalk group is defined by a set of databases hosted in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="cf981-107">数据库中托管的一套[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]可通过 Windows Server 群集使用高可用。</span><span class="sxs-lookup"><span data-stu-id="cf981-107">The set of databases hosted in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] can be made highly available through the use of a Windows Server cluster.</span></span> <span data-ttu-id="cf981-108">在 BizTalk 环境中，运行的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供运行的计算机上的"运行时环境"和数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]为环境提供持久存储区。</span><span class="sxs-lookup"><span data-stu-id="cf981-108">In a BizTalk environment, the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provide the “run-time environment” and the databases on the computers running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] provide the persistent store for the environment.</span></span> <span data-ttu-id="cf981-109">因此，BizTalk 服务器备份、 还原和灾难恢复过程很大程度侧重于[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cf981-109">Therefore, BizTalk Server backup, restore, and disaster recovery procedures are heavily focused on [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="cf981-110">用途</span><span class="sxs-lookup"><span data-stu-id="cf981-110">Purpose</span></span>  
 <span data-ttu-id="cf981-111">本主题将整合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从的核心文档、 多个 Microsoft Web 站点和中的信息的灾难恢复信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]产品团队定义的灾难恢复过程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="cf981-111">This topic consolidates [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] disaster recovery information from the core documentation, various Microsoft Web sites, and information from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] product team to define disaster recovery procedures for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environments.</span></span>  
  
 <span data-ttu-id="cf981-112">应用程序团队应全面测试备份、 还原和灾难恢复过程。</span><span class="sxs-lookup"><span data-stu-id="cf981-112">Application teams should thoroughly test backup, restore, and disaster recovery procedures.</span></span> <span data-ttu-id="cf981-113">你还应该确保过程专门编写，来满足在进入生产前的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf981-113">You should also ensure the procedures are tailored to meet application requirements before entering production.</span></span>  
  
## <a name="scope"></a><span data-ttu-id="cf981-114">范围</span><span class="sxs-lookup"><span data-stu-id="cf981-114">Scope</span></span>  
 <span data-ttu-id="cf981-115">本部分重点灾难恢复过程的 BizTalk Server 和相关的过程[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cf981-115">This section focuses on disaster recovery procedures for BizTalk Server and related procedures for [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="cf981-116">本指南基于如何备份和还原 BizTalk Server 有关的相关文档。</span><span class="sxs-lookup"><span data-stu-id="cf981-116">This guide builds on related documentation about how to back up and restore BizTalk Server.</span></span>  
  
 <span data-ttu-id="cf981-117">有关备份和还原的详细信息，请参阅本文档并查看[备份和还原 BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=154071) (http://go.microsoft.com/fwlink/?LinkID=154071) BizTalk Server 帮助中。</span><span class="sxs-lookup"><span data-stu-id="cf981-117">For more information about backup and restore, see this documentation and see [Backing Up and Restoring BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=154071) (http://go.microsoft.com/fwlink/?LinkID=154071) in BizTalk Server Help.</span></span> <span data-ttu-id="cf981-118">每个应用程序团队必须增加与其他过程特定于其环境，如文档计算机名，驱动器号，本主题中的信息并群集配置中，以及的灾难恢复过程相关非 BizTalk 应用程序解决方案的一部分。</span><span class="sxs-lookup"><span data-stu-id="cf981-118">Each application team must augment the information in this topic with additional procedures specific to their environment, such as document computer names, drive letters, and cluster configuration, as well as disaster recovery procedures for related non-BizTalk applications that are part of the solution.</span></span>  
  
 <span data-ttu-id="cf981-119">本主题不提供详细的灾难恢复过程对以下方面：</span><span class="sxs-lookup"><span data-stu-id="cf981-119">This topic does not provide detailed disaster recovery procedures for the following areas:</span></span>  
  
-   <span data-ttu-id="cf981-120">非 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="cf981-120">Non-BizTalk applications</span></span>  
  
-   <span data-ttu-id="cf981-121">应用程序源代码</span><span class="sxs-lookup"><span data-stu-id="cf981-121">Application source code</span></span>  
  
-   <span data-ttu-id="cf981-122">证书</span><span class="sxs-lookup"><span data-stu-id="cf981-122">Certificates</span></span>  
  
-   <span data-ttu-id="cf981-123">应用程序操作</span><span class="sxs-lookup"><span data-stu-id="cf981-123">Application operations</span></span>  
  
 <span data-ttu-id="cf981-124">可能有需要，上面未列出的应用程序的灾难恢复计划中的文档必须通过每个应用程序团队进行寻址的其他区域。</span><span class="sxs-lookup"><span data-stu-id="cf981-124">There may be additional areas that require documentation in an application’s disaster recovery plan not listed above that must be addressed by each application team.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cf981-125">本节内容</span><span class="sxs-lookup"><span data-stu-id="cf981-125">In This Section</span></span>  
  
-   [<span data-ttu-id="cf981-126">灾难恢复的最佳做法</span><span class="sxs-lookup"><span data-stu-id="cf981-126">Best Practices for Disaster Recovery</span></span>](../technical-guides/best-practices-for-disaster-recovery.md)  
  
-   [<span data-ttu-id="cf981-127">BizTalk Server 日志传送概述</span><span class="sxs-lookup"><span data-stu-id="cf981-127">What Is BizTalk Server Log Shipping?</span></span>](../technical-guides/what-is-biztalk-server-log-shipping.md)