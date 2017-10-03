---
title: "操作的准备工作核对清单 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c308a876-9872-43b3-a1fb-76e81396612f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87da295129a4cb90ecf643cd06eb18ac3e6aa18e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="operational-readiness-checklists"></a><span data-ttu-id="bdd00-102">操作的准备工作核对清单</span><span class="sxs-lookup"><span data-stu-id="bdd00-102">Operational Readiness Checklists</span></span>
<span data-ttu-id="bdd00-103">操作的准备情况清单包含应考虑的建议和在 BizTalk 解决方案部署到生产环境之前应执行的任务。</span><span class="sxs-lookup"><span data-stu-id="bdd00-103">The Operational Readiness checklists contain recommendations that you should consider and tasks that you should perform before deploying a BizTalk solution into production.</span></span> <span data-ttu-id="bdd00-104">这些清单包括用于配置必备软件，提高可用性，信息监视[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，并用于测试的步骤。</span><span class="sxs-lookup"><span data-stu-id="bdd00-104">These checklists include information for configuring prerequisite software, increasing availability, monitoring the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, and procedures for testing.</span></span>  
  
 <span data-ttu-id="bdd00-105">因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上维护依赖关系，因此许多其他 Microsoft 技术，您应该完成的任务的每个相关的技术，以帮助确保你的生产[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]平稳运行环境。</span><span class="sxs-lookup"><span data-stu-id="bdd00-105">Because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] maintains dependencies on so many other Microsoft technologies, you should complete the tasks for each dependent technology to help ensure that your production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment runs smoothly.</span></span>  
  
## <a name="typical-prerequisite-software"></a><span data-ttu-id="bdd00-106">典型的必备软件</span><span class="sxs-lookup"><span data-stu-id="bdd00-106">Typical Prerequisite Software</span></span>  
 <span data-ttu-id="bdd00-107">有关必备软件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序平台通常包括以下产品：</span><span class="sxs-lookup"><span data-stu-id="bdd00-107">Prerequisite software for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application platform typically includes the following products:</span></span>  
  
-   <span data-ttu-id="bdd00-108">Windows 操作系统</span><span class="sxs-lookup"><span data-stu-id="bdd00-108">The Windows operating system</span></span>  
  
-   [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]<span data-ttu-id="bdd00-109">SP1 或[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdd00-109"> SP1 or [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]<span data-ttu-id="bdd00-110">（出于开发目的，不在运行时）</span><span class="sxs-lookup"><span data-stu-id="bdd00-110"> (for development purposes, not at run time)</span></span>  
  
## <a name="additional-components"></a><span data-ttu-id="bdd00-111">其他组件</span><span class="sxs-lookup"><span data-stu-id="bdd00-111">Additional Components</span></span>  
 <span data-ttu-id="bdd00-112">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序平台可能还需要多个以下的软件组件：</span><span class="sxs-lookup"><span data-stu-id="bdd00-112">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application platform may also require several of the following software components:</span></span>  
  
-   <span data-ttu-id="bdd00-113">Internet 信息服务 (IIS)</span><span class="sxs-lookup"><span data-stu-id="bdd00-113">Internet Information Services (IIS)</span></span>  
  
-   <span data-ttu-id="bdd00-114">Windows SharePoint® Services 2010</span><span class="sxs-lookup"><span data-stu-id="bdd00-114">Windows SharePoint® Services 2010</span></span>  
  
-   <span data-ttu-id="bdd00-115">SharePoint Foundation 2010</span><span class="sxs-lookup"><span data-stu-id="bdd00-115">SharePoint Foundation 2010</span></span>  
  
-   <span data-ttu-id="bdd00-116">Microsoft Office SharePoint Server 2007 Service Pack 1 (SP1) (MOSS)</span><span class="sxs-lookup"><span data-stu-id="bdd00-116">Microsoft Office SharePoint Server 2007 Service Pack 1 (SP1) (MOSS)</span></span>  
  
-   <span data-ttu-id="bdd00-117">SP1 或 SP2 的 Windows SharePoint Services 3.0</span><span class="sxs-lookup"><span data-stu-id="bdd00-117">Windows SharePoint Services 3.0 with SP1 or SP2</span></span>  
  
-   <span data-ttu-id="bdd00-118">Microsoft Office Excel 2010 或 2007</span><span class="sxs-lookup"><span data-stu-id="bdd00-118">Microsoft Office Excel 2010 or 2007</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="bdd00-119">支持 Microsoft Office 2010 的 32 位版本。</span><span class="sxs-lookup"><span data-stu-id="bdd00-119"> supports only the 32-bit version of Microsoft Office 2010.</span></span>  
  
-   <span data-ttu-id="bdd00-120">SQL Server 2005 Notification Services</span><span class="sxs-lookup"><span data-stu-id="bdd00-120">SQL Server 2005 Notification Services</span></span>  
  
-   <span data-ttu-id="bdd00-121">带有 Service Pack 1 的 SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="bdd00-121">SQLXML 4.0 with Service Pack 1</span></span>  
  
-   <span data-ttu-id="bdd00-122">.NET framework 1.0</span><span class="sxs-lookup"><span data-stu-id="bdd00-122">.NET Framework 1.0</span></span>  
  
-   <span data-ttu-id="bdd00-123">.NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="bdd00-123">.NET Framework 2.0</span></span>  
  
-   <span data-ttu-id="bdd00-124">.NET framework 3.0</span><span class="sxs-lookup"><span data-stu-id="bdd00-124">.NET Framework 3.0</span></span>  
  
-   <span data-ttu-id="bdd00-125">Microsoft.NET Framework 4 和.Net Framework 3.5 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="bdd00-125">Microsoft .NET Framework 4 and .Net Framework 3.5 with Service Pack 1 (SP1)</span></span>  
  
-   <span data-ttu-id="bdd00-126">非 Microsoft 组件，以便为某些功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器。</span><span class="sxs-lookup"><span data-stu-id="bdd00-126">Non-Microsoft components to enable functionality for certain [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapters.</span></span>  
  
 <span data-ttu-id="bdd00-127">有关依赖软件所需的各种 Windows 操作系统版本的 BizTalk 应用程序平台的特定功能的详细信息，请参阅中的"功能依赖关系矩阵"一节[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]安装和升级为特定的 Windows 操作系统版本的指南。</span><span class="sxs-lookup"><span data-stu-id="bdd00-127">For more information about the dependency software that is required for specific features of the BizTalk application platform for various Windows operating system versions, see the "Feature Dependency Matrix" section in the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] installation and upgrade guide for the specific Windows operating system version.</span></span> <span data-ttu-id="bdd00-128">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]安装和升级指南位于[http://go.microsoft.com/fwlink/?LinkID=152913](http://go.microsoft.com/fwlink/?LinkID=152913)。</span><span class="sxs-lookup"><span data-stu-id="bdd00-128">The [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] installation and upgrade guides are available at [http://go.microsoft.com/fwlink/?LinkID=152913](http://go.microsoft.com/fwlink/?LinkID=152913).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bdd00-129">本节内容</span><span class="sxs-lookup"><span data-stu-id="bdd00-129">In This Section</span></span>  
  
-   [<span data-ttu-id="bdd00-130">清单： BizTalk Server 入门</span><span class="sxs-lookup"><span data-stu-id="bdd00-130">Checklist: Getting Started with BizTalk Server</span></span>](http://msdn.microsoft.com/library/37d265cd-c393-46ac-ac21-129a1511359b)  
  
-   [<span data-ttu-id="bdd00-131">清单： 配置 Windows Server</span><span class="sxs-lookup"><span data-stu-id="bdd00-131">Checklist: Configuring Windows Server</span></span>](../technical-guides/checklist-configuring-windows-server.md)  
  
-   [<span data-ttu-id="bdd00-132">清单： 配置 Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="bdd00-132">Checklist: Configuring Internet Information Services</span></span>](../technical-guides/checklist-configuring-internet-information-services.md)  
  
-   [<span data-ttu-id="bdd00-133">清单： 配置 SQL Server</span><span class="sxs-lookup"><span data-stu-id="bdd00-133">Checklist: Configuring SQL Server</span></span>](~/technical-guides/checklist-configuring-sql-server.md)  
  
-   [<span data-ttu-id="bdd00-134">清单： 配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="bdd00-134">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)  
  
-   [<span data-ttu-id="bdd00-135">清单： 会提供高可用性容错或负载平衡</span><span class="sxs-lookup"><span data-stu-id="bdd00-135">Checklist: Providing High Availability with Fault Tolerance or Load Balancing</span></span>](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)  
  
-   [<span data-ttu-id="bdd00-136">清单： 提高可用性与灾难恢复</span><span class="sxs-lookup"><span data-stu-id="bdd00-136">Checklist: Increasing Availability with Disaster Recovery</span></span>](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)  
  
-   [<span data-ttu-id="bdd00-137">清单： 监视操作的准备情况</span><span class="sxs-lookup"><span data-stu-id="bdd00-137">Checklist: Monitoring Operational Readiness</span></span>](../technical-guides/checklist-monitoring-operational-readiness.md)  
  
-   [<span data-ttu-id="bdd00-138">清单： 维护和故障排除 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="bdd00-138">Checklist: Maintaining and Troubleshooting BizTalk Server Databases</span></span>](~/technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="bdd00-139">清单： 测试操作的准备情况</span><span class="sxs-lookup"><span data-stu-id="bdd00-139">Checklist: Testing Operational Readiness</span></span>](../technical-guides/checklist-testing-operational-readiness.md)