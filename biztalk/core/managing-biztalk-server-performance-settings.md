---
title: "管理 BizTalk Server 性能设置 |Microsoft 文档"
description: "设置仪表板用于更新 BizTalk 组、 主机和在 BizTalk Server 中设置的主机实例"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca56a981-a255-4c4d-82f8-a57d390e425e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0660fd4aa130049d80de4a0c2ee239ef5cae0068
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="manage-biztalk-server-performance-settings"></a><span data-ttu-id="af15f-103">管理 BizTalk Server 性能设置</span><span class="sxs-lookup"><span data-stu-id="af15f-103">Manage BizTalk Server Performance Settings</span></span>
  
 <span data-ttu-id="af15f-104">[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] BizTalk Server 中比较的性能设置，并提供一个中央控制台来管理这些设置。</span><span class="sxs-lookup"><span data-stu-id="af15f-104">The [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] in BizTalk Server collates the performance settings, and provides a central console to manage these settings.</span></span> <span data-ttu-id="af15f-105">这有助于：</span><span class="sxs-lookup"><span data-stu-id="af15f-105">This helps to:</span></span>  
  
-   <span data-ttu-id="af15f-106">改进可以设置的属性的可发现性</span><span class="sxs-lookup"><span data-stu-id="af15f-106">Improve the discoverability of the properties that can be set</span></span>
  
-   <span data-ttu-id="af15f-107">因为所有设置现在可访问在同一个地方，也可以导出/导入轻松减少时间解决方案</span><span class="sxs-lookup"><span data-stu-id="af15f-107">Reduce the time-to-solution because all settings are now accessible in a single place and can be exported/imported easily</span></span>
  
-   <span data-ttu-id="af15f-108">提供的性能优化级别的整体视图在给定的 BizTalk 部署上完成</span><span class="sxs-lookup"><span data-stu-id="af15f-108">Offers a holistic view of level of performance tuning done on a given BizTalk deployment</span></span>
  
## <a name="why-use-it"></a><span data-ttu-id="af15f-109">为何要使用它？</span><span class="sxs-lookup"><span data-stu-id="af15f-109">Why use it?</span></span>  
 <span data-ttu-id="af15f-110">[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] 面向需要广泛地调整性能优化的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 设置的 IT 管理员。</span><span class="sxs-lookup"><span data-stu-id="af15f-110">The [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] is targeted towards IT administrators who need to extensively tweak [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] settings for performance optimization.</span></span>  
  
 <span data-ttu-id="af15f-111">您可以使用 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] 修改 BizTalk 组以及该组中 BizTalk 主机和 BizTalk 主机实例的设置。</span><span class="sxs-lookup"><span data-stu-id="af15f-111">You can use the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] to modify settings for the BizTalk Group, and all the BizTalk Hosts and BizTalk Host Instances in that Group.</span></span>  
  
 <span data-ttu-id="af15f-112">若要了解有关组、 主机和主机实例设置的详细信息，请参阅[如何修改组设置](../core/how-to-modify-group-settings.md)，[如何修改主机设置](../core/how-to-modify-host-settings.md)，和[如何修改主机实例设置](../core/how-to-modify-host-instance-settings.md).</span><span class="sxs-lookup"><span data-stu-id="af15f-112">To know more about the group, host, and host instance settings, see [How to Modify Group Settings](../core/how-to-modify-group-settings.md), [How to Modify Host Settings](../core/how-to-modify-host-settings.md), and [How to Modify Host Instance Settings](../core/how-to-modify-host-instance-settings.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="af15f-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="af15f-113">Prerequisites</span></span> 
 <span data-ttu-id="af15f-114">您可以从 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] 管理控制台启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="af15f-114">You can launch the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="af15f-115">有关如何管理信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能设置，请使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，请参阅[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="af15f-115">For information on how to manage [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance settings using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, see [Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md).</span></span>  
  
## <a name="where-do-i-start"></a><span data-ttu-id="af15f-116">其中开始？</span><span class="sxs-lookup"><span data-stu-id="af15f-116">Where Do I Start?</span></span>  
 <span data-ttu-id="af15f-117">可以用以下任意一种方式访问 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]：</span><span class="sxs-lookup"><span data-stu-id="af15f-117">You can access the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] in any of the following ways:</span></span>  
  
-   <span data-ttu-id="af15f-118">启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**BizTalk 组**在控制台树中，，然后选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="af15f-118">Start the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **BizTalk Group** in the console tree, and then select **Settings**.</span></span>  
  
-   <span data-ttu-id="af15f-119">右键单击任何主机归**平台设置**中 MMC，然后单击节点**设置**。</span><span class="sxs-lookup"><span data-stu-id="af15f-119">Right click any host under the **Platform Settings** node in MMC and click on **Settings**.</span></span> <span data-ttu-id="af15f-120">这将启动 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]，您可以修改与该主机相关的设置。</span><span class="sxs-lookup"><span data-stu-id="af15f-120">This launches [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] and you can modify the settings related to that host.</span></span>  
  
-   <span data-ttu-id="af15f-121">右键单击在任何主机实例**平台设置**中 MMC，然后单击节点**设置**。</span><span class="sxs-lookup"><span data-stu-id="af15f-121">Right click any host instance under the **Platform Settings** node in MMC and click on **Settings**.</span></span> <span data-ttu-id="af15f-122">这将启动 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]，您可以修改与该主机实例相关的设置。</span><span class="sxs-lookup"><span data-stu-id="af15f-122">This launches [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] and you can modify the settings related to that host instance.</span></span>  
  
## <a name="export-and-import-settings"></a><span data-ttu-id="af15f-123">导出和导入设置</span><span class="sxs-lookup"><span data-stu-id="af15f-123">Export and import settings</span></span>  
 <span data-ttu-id="af15f-124">[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] 可用于从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境导出设置，并将其导入另一 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境，从而缩短解决方案的推出时间。</span><span class="sxs-lookup"><span data-stu-id="af15f-124">The [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] can be used to export settings from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment and import it into another [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, thereby reducing the overall time-to-solution.</span></span> <span data-ttu-id="af15f-125">当管理员尝试在测试环境中调整 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 性能时，它们特别有用，而且它们可将设置导入到生产环境中，从而获得期望的结果。</span><span class="sxs-lookup"><span data-stu-id="af15f-125">This is especially useful in scenarios where the administrators try to tune [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance in a test environment, and upon achieving the desired results, they can import the settings into a production environment.</span></span>  
  
 <span data-ttu-id="af15f-126">有关如何导入/导出使用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]用户界面，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="af15f-126">For information about how to import/export using the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] user interface, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md).</span></span>
  
## <a name="scripting-support"></a><span data-ttu-id="af15f-127">脚本支持</span><span class="sxs-lookup"><span data-stu-id="af15f-127">Scripting support</span></span>
 <span data-ttu-id="af15f-128">[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] 不仅提供了一个用于管理 BizTalk 设置的中央用户界面，而且还可确保所有设置和导入/导出任务都可以通过 API 和命令行选项来访问。</span><span class="sxs-lookup"><span data-stu-id="af15f-128">The [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] not only provides a central user interface to manage BizTalk settings but also ensures that all settings and the import/export tasks are accessible via APIs and command-line options.</span></span> <span data-ttu-id="af15f-129">这使得 BizTalk Server 管理员能够自动执行与 BizTalk Server 设置相关的任务。</span><span class="sxs-lookup"><span data-stu-id="af15f-129">This enables BizTalk Server administrators to automate tasks related to BizTalk Server settings.</span></span> <span data-ttu-id="af15f-130">作为脚本的支持的一部分：</span><span class="sxs-lookup"><span data-stu-id="af15f-130">As part of the scripting support:</span></span>  
  
-   <span data-ttu-id="af15f-131">所有组设置可访问，并可以通过 WMI 类修改：`MSBTS_GroupSetting`</span><span class="sxs-lookup"><span data-stu-id="af15f-131">All group settings can be accessed and modified via the WMI Class: `MSBTS_GroupSetting`</span></span>  
  
-   <span data-ttu-id="af15f-132">所有主机设置可访问，并可以通过 WMI 类修改：`MSBTS_HostSetting`</span><span class="sxs-lookup"><span data-stu-id="af15f-132">All host settings can be accessed and modified via the WMI Class: `MSBTS_HostSetting`</span></span>  
  
-   <span data-ttu-id="af15f-133">所有主机实例设置可访问，并可以通过 WMI 类修改：`MSBTS_HostInstanceSetting`</span><span class="sxs-lookup"><span data-stu-id="af15f-133">All host instance settings can be accessed and modified via the WMI Class: `MSBTS_HostInstanceSetting`</span></span>  
  
-   <span data-ttu-id="af15f-134">导入和导出操作可以通过访问**BTSTask.exe**命令：`ExportSettings`和`ImportSettings`</span><span class="sxs-lookup"><span data-stu-id="af15f-134">Import and export operations can be accessed through **BTSTask.exe** commands: `ExportSettings` and `ImportSettings`</span></span>  
  
 <span data-ttu-id="af15f-135">有关如何导入/导出使用 BTSTask.exe 命令行实用工具的详细信息，请参阅[导入或导出 BizTalk 设置使用 BTSTask](how-to-import-biztalk-settings-using-btstask.md)。</span><span class="sxs-lookup"><span data-stu-id="af15f-135">For details about how to import/export using the BTSTask.exe command-line utility, see [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md).</span></span>  
  
## <a name="next"></a><span data-ttu-id="af15f-136">Next</span><span class="sxs-lookup"><span data-stu-id="af15f-136">Next</span></span>  
  
-   [<span data-ttu-id="af15f-137">设置仪表板用于 BizTalk Server 性能优化</span><span class="sxs-lookup"><span data-stu-id="af15f-137">Use Settings Dashboard for BizTalk Server Performance Tuning</span></span>](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)  
  
-   [<span data-ttu-id="af15f-138">自动执行 BizTalk Server 性能优化</span><span class="sxs-lookup"><span data-stu-id="af15f-138">Automate BizTalk Server Performance Tuning</span></span>](../core/automating-biztalk-server-performance-tuning.md)  
  
## <a name="see-also"></a><span data-ttu-id="af15f-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af15f-139">See Also</span></span>  
 [<span data-ttu-id="af15f-140">管理 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="af15f-140">Manage BizTalk Server</span></span>](../core/use-groups-create-artifacts-optimize-performance-and-more-in-biztalk-server.md)