---
title: "设置仪表板用于 BizTalk Server 性能优化 |Microsoft 文档"
description: "使用 BizTalk Server 管理中的设置仪表板来更新组、 主机和主机实例设置"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bb1ddac-1e8f-4928-9c70-8326ae64a734
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be1978f92cbbbce945cb7b5a97458577cbf6f725
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="use-settings-dashboard-for-biztalk-server-performance-tuning"></a><span data-ttu-id="58699-103">设置仪表板用于 BizTalk Server 性能优化</span><span class="sxs-lookup"><span data-stu-id="58699-103">Use Settings Dashboard for BizTalk Server Performance Tuning</span></span>

## <a name="overview"></a><span data-ttu-id="58699-104">概述</span><span class="sxs-lookup"><span data-stu-id="58699-104">Overview</span></span>
<span data-ttu-id="58699-105">使用设置仪表板，可以广泛地调整用于性能优化的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 设置。</span><span class="sxs-lookup"><span data-stu-id="58699-105">Using the Settings Dashboard, you can extensively tweak [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] settings for performance optimization.</span></span> <span data-ttu-id="58699-106">还可以修改 BizTalk 组、BizTalk 主机和 BizTalk 主机实例的设置。</span><span class="sxs-lookup"><span data-stu-id="58699-106">You can also modify settings for the BizTalk Group, BizTalk Host, and BizTalk Host Instance.</span></span>  
  
-   <span data-ttu-id="58699-107">**组级别设置**： 在组级别中，你可以使用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]若要设置属性，例如配置刷新间隔、 最大消息批大小、 组级别跟踪，等等。这些设置适用于 BizTalk 组中的所有计算机。</span><span class="sxs-lookup"><span data-stu-id="58699-107">**Group-level settings**: At the group level, you can use the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] to set properties like the configuration refresh interval, maximum message batch size, group level tracking, etc. These settings are applied to all machines in a BizTalk Group.</span></span>  
  
-   <span data-ttu-id="58699-108">**主机级别设置**： 在主机级别，你可以修改设置，例如主机跟踪、 与相关的基于资源限制属性、 与消息进程限制，相关的属性和与限制的业务流程相关的属性。</span><span class="sxs-lookup"><span data-stu-id="58699-108">**Host-level settings**: At the host level, you can modify settings like host tracking, properties related to resource based throttling, properties related to message process throttling, and properties related to orchestrations throttling.</span></span> <span data-ttu-id="58699-109">这些设置适用于所选主机的全部实例。</span><span class="sxs-lookup"><span data-stu-id="58699-109">These settings are applied to all instances of the selected host.</span></span>  
  
-   <span data-ttu-id="58699-110">**主机实例级别设置**： 在主机实例级别，您可以修改.NET CLR 设置和与业务流程内存限制相关的属性。</span><span class="sxs-lookup"><span data-stu-id="58699-110">**Host instance level settings**: At the host instance level, you can modify .NET CLR settings and properties related to orchestration memory throttling.</span></span> <span data-ttu-id="58699-111">这些设置只适用于所选主机实例。</span><span class="sxs-lookup"><span data-stu-id="58699-111">These settings are applied to only the selected host instance.</span></span>  
  
 <span data-ttu-id="58699-112">有关 BizTalk 组、 BizTalk 主机以及 BizTalk 主机实例设置的详细信息，请参阅[如何修改组设置](../core/how-to-modify-group-settings.md)，[如何修改主机设置](../core/how-to-modify-host-settings.md)，和[如何修改主机实例设置](../core/how-to-modify-host-instance-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="58699-112">For more information about BizTalk Group, BizTalk Host, and BizTalk Host Instance settings, see [How to Modify Group Settings](../core/how-to-modify-group-settings.md), [How to Modify Host Settings](../core/how-to-modify-host-settings.md), and [How to Modify Host Instance Settings](../core/how-to-modify-host-instance-settings.md).</span></span>  
  
 <span data-ttu-id="58699-113">使用设置仪表板，可以跨部署（不需要相同）导入/导出 BizTalk 设置。</span><span class="sxs-lookup"><span data-stu-id="58699-113">The Settings Dashboard enables you to import/export BizTalk settings across deployments that need not be identical.</span></span> <span data-ttu-id="58699-114">使用用户界面，可以将主机和主机实例从目标部署映射到源部署。</span><span class="sxs-lookup"><span data-stu-id="58699-114">Using the user interface, you can map the hosts and host instances from destination to source deployments.</span></span> <span data-ttu-id="58699-115">这样，可帮助您将设置应用于主机和计算机名称或各自计数不同的环境中。</span><span class="sxs-lookup"><span data-stu-id="58699-115">This helps you apply settings to an environment where host and machine names, or their respective counts, are different.</span></span> <span data-ttu-id="58699-116">有关导入/导出 BizTalk 设置的详细信息，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="58699-116">For more details about importing/exporting BizTalk settings, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58699-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58699-117">See Also</span></span>  
 [<span data-ttu-id="58699-118">管理 BizTalk Server 性能设置</span><span class="sxs-lookup"><span data-stu-id="58699-118">Manage BizTalk Server Performance Settings</span></span>](../core/managing-biztalk-server-performance-settings.md)