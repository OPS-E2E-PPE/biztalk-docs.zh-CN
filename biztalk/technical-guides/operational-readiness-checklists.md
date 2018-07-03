---
title: 操作准备就绪清单 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c308a876-9872-43b3-a1fb-76e81396612f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76cab24c2ba0d47baa22dbe694a1d929e98c8f9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002750"
---
# <a name="operational-readiness-checklists"></a><span data-ttu-id="c248d-102">操作准备就绪清单</span><span class="sxs-lookup"><span data-stu-id="c248d-102">Operational Readiness Checklists</span></span>
<span data-ttu-id="c248d-103">操作准备就绪清单包含应考虑的建议和部署 BizTalk 解决方案到生产环境之前应执行的任务。</span><span class="sxs-lookup"><span data-stu-id="c248d-103">The Operational Readiness checklists contain recommendations that you should consider and tasks that you should perform before deploying a BizTalk solution into production.</span></span> <span data-ttu-id="c248d-104">这些清单提供信息，以便配置必备软件，从而提高可用性，监视[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中和用于测试的过程。</span><span class="sxs-lookup"><span data-stu-id="c248d-104">These checklists include information for configuring prerequisite software, increasing availability, monitoring the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, and procedures for testing.</span></span>  
  
 <span data-ttu-id="c248d-105">因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上维护依赖关系，因此许多其他 Microsoft 技术，您应该完成每项依赖的技术来帮助确保您的生产任务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境能够顺利运行。</span><span class="sxs-lookup"><span data-stu-id="c248d-105">Because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] maintains dependencies on so many other Microsoft technologies, you should complete the tasks for each dependent technology to help ensure that your production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment runs smoothly.</span></span>  
  
## <a name="typical-prerequisite-software"></a><span data-ttu-id="c248d-106">典型的必备软件</span><span class="sxs-lookup"><span data-stu-id="c248d-106">Typical Prerequisite Software</span></span>  
 <span data-ttu-id="c248d-107">必备软件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序平台通常包括以下产品：</span><span class="sxs-lookup"><span data-stu-id="c248d-107">Prerequisite software for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application platform typically includes the following products:</span></span>  
  
- <span data-ttu-id="c248d-108">Windows 操作系统</span><span class="sxs-lookup"><span data-stu-id="c248d-108">The Windows operating system</span></span>  
  
- <span data-ttu-id="c248d-109">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c248d-109">SQL Server</span></span> 
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- <span data-ttu-id="c248d-110">Visual Studio （适用于开发目的，不是在运行时）</span><span class="sxs-lookup"><span data-stu-id="c248d-110">Visual Studio (for development purposes, not at run time)</span></span>  
  
## <a name="additional-components"></a><span data-ttu-id="c248d-111">其他组件</span><span class="sxs-lookup"><span data-stu-id="c248d-111">Additional Components</span></span>  
 <span data-ttu-id="c248d-112">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序平台可能还需要多个以下的软件组件：</span><span class="sxs-lookup"><span data-stu-id="c248d-112">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application platform may also require several of the following software components:</span></span>  
  
- <span data-ttu-id="c248d-113">Internet 信息服务 (IIS)</span><span class="sxs-lookup"><span data-stu-id="c248d-113">Internet Information Services (IIS)</span></span>  
  
- <span data-ttu-id="c248d-114">SharePoint</span><span class="sxs-lookup"><span data-stu-id="c248d-114">SharePoint</span></span>
  
- <span data-ttu-id="c248d-115">Microsoft Office Excel</span><span class="sxs-lookup"><span data-stu-id="c248d-115">Microsoft Office Excel</span></span> 
  
  > [!NOTE]  
  >  <span data-ttu-id="c248d-116">BizTalk Server 支持 Microsoft Office 的 32 位版本。</span><span class="sxs-lookup"><span data-stu-id="c248d-116">BizTalk Server supports only the 32-bit version of Microsoft Office.</span></span>  
  
- <span data-ttu-id="c248d-117">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c248d-117">SQL Server</span></span>
  
- <span data-ttu-id="c248d-118">SQLXML</span><span class="sxs-lookup"><span data-stu-id="c248d-118">SQLXML</span></span> 
  
- <span data-ttu-id="c248d-119">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="c248d-119">.NET Framework</span></span> 
  
- <span data-ttu-id="c248d-120">非 Microsoft 组件，以便为某些功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器。</span><span class="sxs-lookup"><span data-stu-id="c248d-120">Non-Microsoft components to enable functionality for certain [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapters.</span></span>  
  
  <span data-ttu-id="c248d-121">有关各种 Windows 操作系统版本的 BizTalk 应用程序平台的特定功能所需的依赖关系软件的详细信息，请参阅[新增功能、 安装、 配置和升级](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="c248d-121">For more information about the dependency software that is required for specific features of the BizTalk application platform for various Windows operating system versions, see [What's New, Installation, Configuration, and Upgrade](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span>
- 
  
## <a name="next-steps"></a><span data-ttu-id="c248d-122">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c248d-122">Next steps</span></span>
  
-   [<span data-ttu-id="c248d-123">清单：BizTalk Server 入门</span><span class="sxs-lookup"><span data-stu-id="c248d-123">Checklist: Getting Started with BizTalk Server</span></span>](http://msdn.microsoft.com/library/37d265cd-c393-46ac-ac21-129a1511359b)  
  
-   [<span data-ttu-id="c248d-124">清单：配置 Windows Server</span><span class="sxs-lookup"><span data-stu-id="c248d-124">Checklist: Configuring Windows Server</span></span>](../technical-guides/checklist-configuring-windows-server.md)  
  
-   [<span data-ttu-id="c248d-125">清单：配置 Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="c248d-125">Checklist: Configuring Internet Information Services</span></span>](../technical-guides/checklist-configuring-internet-information-services.md)  
  
-   [<span data-ttu-id="c248d-126">清单：配置 SQL Server</span><span class="sxs-lookup"><span data-stu-id="c248d-126">Checklist: Configuring SQL Server</span></span>](~/technical-guides/checklist-configuring-sql-server.md)  
  
-   [<span data-ttu-id="c248d-127">清单：配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c248d-127">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)  
  
-   [<span data-ttu-id="c248d-128">清单：提供高可用性容错或负载均衡</span><span class="sxs-lookup"><span data-stu-id="c248d-128">Checklist: Providing High Availability with Fault Tolerance or Load Balancing</span></span>](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)  
  
-   [<span data-ttu-id="c248d-129">清单：提供高可用性灾难恢复</span><span class="sxs-lookup"><span data-stu-id="c248d-129">Checklist: Increasing Availability with Disaster Recovery</span></span>](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)  
  
-   [<span data-ttu-id="c248d-130">清单：监视操作准备就绪</span><span class="sxs-lookup"><span data-stu-id="c248d-130">Checklist: Monitoring Operational Readiness</span></span>](../technical-guides/checklist-monitoring-operational-readiness.md)  
  
-   [<span data-ttu-id="c248d-131">清单：维护 BizTalk Server 数据库并进行故障排除</span><span class="sxs-lookup"><span data-stu-id="c248d-131">Checklist: Maintaining and Troubleshooting BizTalk Server Databases</span></span>](~/technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="c248d-132">清单：测试操作准备情况</span><span class="sxs-lookup"><span data-stu-id="c248d-132">Checklist: Testing Operational Readiness</span></span>](../technical-guides/checklist-testing-operational-readiness.md)