---
title: 管理 BizTalk Server 性能设置 |Microsoft Docs
description: 使用设置仪表板来更新 BizTalk 组、 主机和 BizTalk Server 中设置的主机实例
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ca56a981-a255-4c4d-82f8-a57d390e425e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9bd8436013c0373a26354fdc73a1bc4075c5776
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380286"
---
# <a name="manage-biztalk-server-performance-settings"></a><span data-ttu-id="74466-103">管理 BizTalk Server 性能设置</span><span class="sxs-lookup"><span data-stu-id="74466-103">Manage BizTalk Server Performance Settings</span></span>
  
 <span data-ttu-id="74466-104">[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] BizTalk Server 中整理性能设置，并提供了一个中央控制台来管理这些设置。</span><span class="sxs-lookup"><span data-stu-id="74466-104">The [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] in BizTalk Server collates the performance settings, and provides a central console to manage these settings.</span></span> <span data-ttu-id="74466-105">这可以帮助：</span><span class="sxs-lookup"><span data-stu-id="74466-105">This helps to:</span></span>  
  
-   <span data-ttu-id="74466-106">提高可设置的属性的可发现的性</span><span class="sxs-lookup"><span data-stu-id="74466-106">Improve the discoverability of the properties that can be set</span></span>
  
-   <span data-ttu-id="74466-107">因为所有设置在单个位置现在均可访问，可以导出/导入轻松减少时解决方案</span><span class="sxs-lookup"><span data-stu-id="74466-107">Reduce the time-to-solution because all settings are now accessible in a single place and can be exported/imported easily</span></span>
  
-   <span data-ttu-id="74466-108">提供的性能优化级别的整体视图上给定的 BizTalk 部署完成</span><span class="sxs-lookup"><span data-stu-id="74466-108">Offers a holistic view of level of performance tuning done on a given BizTalk deployment</span></span>
  
## <a name="why-use-it"></a><span data-ttu-id="74466-109">为什么要使用它？</span><span class="sxs-lookup"><span data-stu-id="74466-109">Why use it?</span></span>  
 <span data-ttu-id="74466-110">[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]面向 IT 管理员需要广泛地调整[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]设置以优化性能。</span><span class="sxs-lookup"><span data-stu-id="74466-110">The [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] is targeted towards IT administrators who need to extensively tweak [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] settings for performance optimization.</span></span>  
  
 <span data-ttu-id="74466-111">可以使用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]修改 BizTalk 组和所有的 BizTalk 主机和 BizTalk 主机实例在该组中的设置。</span><span class="sxs-lookup"><span data-stu-id="74466-111">You can use the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] to modify settings for the BizTalk Group, and all the BizTalk Hosts and BizTalk Host Instances in that Group.</span></span>  
  
 <span data-ttu-id="74466-112">若要了解有关组、 主机和主机实例设置的详细信息，请参阅[如何修改组设置](../core/how-to-modify-group-settings.md)，[如何修改主机设置](../core/how-to-modify-host-settings.md)，和[如何修改主机实例设置](../core/how-to-modify-host-instance-settings.md).</span><span class="sxs-lookup"><span data-stu-id="74466-112">To know more about the group, host, and host instance settings, see [How to Modify Group Settings](../core/how-to-modify-group-settings.md), [How to Modify Host Settings](../core/how-to-modify-host-settings.md), and [How to Modify Host Instance Settings](../core/how-to-modify-host-instance-settings.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="74466-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="74466-113">Prerequisites</span></span> 
 <span data-ttu-id="74466-114">您可以启动[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="74466-114">You can launch the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="74466-115">有关如何管理的信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能设置，请使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，请参阅[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="74466-115">For information on how to manage [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance settings using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, see [Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md).</span></span>  
  
## <a name="where-do-i-start"></a><span data-ttu-id="74466-116">如何开始？</span><span class="sxs-lookup"><span data-stu-id="74466-116">Where Do I Start?</span></span>  
 <span data-ttu-id="74466-117">您可以访问[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]任何以下方法：</span><span class="sxs-lookup"><span data-stu-id="74466-117">You can access the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] in any of the following ways:</span></span>  
  
- <span data-ttu-id="74466-118">启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**BizTalk 组**在控制台树中，然后选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="74466-118">Start the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **BizTalk Group** in the console tree, and then select **Settings**.</span></span>  
  
- <span data-ttu-id="74466-119">右键单击下的任一主机**平台设置**节点中 MMC，然后单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="74466-119">Right click any host under the **Platform Settings** node in MMC and click on **Settings**.</span></span> <span data-ttu-id="74466-120">这将启动[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]，可以修改与该主机相关的设置。</span><span class="sxs-lookup"><span data-stu-id="74466-120">This launches [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] and you can modify the settings related to that host.</span></span>  
  
- <span data-ttu-id="74466-121">右键单击下的任何主机实例**平台设置**节点中 MMC，然后单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="74466-121">Right click any host instance under the **Platform Settings** node in MMC and click on **Settings**.</span></span> <span data-ttu-id="74466-122">这将启动[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]，可以修改与该主机实例相关的设置。</span><span class="sxs-lookup"><span data-stu-id="74466-122">This launches [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] and you can modify the settings related to that host instance.</span></span>  
  
## <a name="export-and-import-settings"></a><span data-ttu-id="74466-123">导出和导入设置</span><span class="sxs-lookup"><span data-stu-id="74466-123">Export and import settings</span></span>  
 <span data-ttu-id="74466-124">[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]可用于导出中的设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境导入另一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境，从而减少总体到解决方案的时间。</span><span class="sxs-lookup"><span data-stu-id="74466-124">The [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] can be used to export settings from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment and import it into another [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, thereby reducing the overall time-to-solution.</span></span> <span data-ttu-id="74466-125">这是管理员尝试优化的情境中尤其有用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能在测试环境中，并在达到预期的结果时，他们可以设置导入生产环境。</span><span class="sxs-lookup"><span data-stu-id="74466-125">This is especially useful in scenarios where the administrators try to tune [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance in a test environment, and upon achieving the desired results, they can import the settings into a production environment.</span></span>  
  
 <span data-ttu-id="74466-126">有关如何使用导入/导出[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]用户界面，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="74466-126">For information about how to import/export using the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] user interface, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md).</span></span>
  
## <a name="scripting-support"></a><span data-ttu-id="74466-127">脚本支持</span><span class="sxs-lookup"><span data-stu-id="74466-127">Scripting support</span></span>
 <span data-ttu-id="74466-128">[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]不仅提供了一个中央用户界面来管理 BizTalk 设置，而且还可确保所有设置和导入/导出任务都可通过 Api 和命令行选项进行访问。</span><span class="sxs-lookup"><span data-stu-id="74466-128">The [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] not only provides a central user interface to manage BizTalk settings but also ensures that all settings and the import/export tasks are accessible via APIs and command-line options.</span></span> <span data-ttu-id="74466-129">这使 BizTalk Server 管理员能够自动执行与 BizTalk Server 设置相关的任务。</span><span class="sxs-lookup"><span data-stu-id="74466-129">This enables BizTalk Server administrators to automate tasks related to BizTalk Server settings.</span></span> <span data-ttu-id="74466-130">作为脚本的支持的一部分：</span><span class="sxs-lookup"><span data-stu-id="74466-130">As part of the scripting support:</span></span>  
  
- <span data-ttu-id="74466-131">可以访问和修改通过 WMI 类所有组设置： `MSBTS_GroupSetting`</span><span class="sxs-lookup"><span data-stu-id="74466-131">All group settings can be accessed and modified via the WMI Class: `MSBTS_GroupSetting`</span></span>  
  
- <span data-ttu-id="74466-132">可以访问和修改通过 WMI 类所有主机设置： `MSBTS_HostSetting`</span><span class="sxs-lookup"><span data-stu-id="74466-132">All host settings can be accessed and modified via the WMI Class: `MSBTS_HostSetting`</span></span>  
  
- <span data-ttu-id="74466-133">可以访问和修改通过 WMI 类所有主机实例设置： `MSBTS_HostInstanceSetting`</span><span class="sxs-lookup"><span data-stu-id="74466-133">All host instance settings can be accessed and modified via the WMI Class: `MSBTS_HostInstanceSetting`</span></span>  
  
- <span data-ttu-id="74466-134">导入和导出操作可以通过访问**BTSTask.exe**命令：`ExportSettings`和 `ImportSettings`</span><span class="sxs-lookup"><span data-stu-id="74466-134">Import and export operations can be accessed through **BTSTask.exe** commands: `ExportSettings` and `ImportSettings`</span></span>  
  
  <span data-ttu-id="74466-135">有关如何使用 BTSTask.exe 命令行实用程序导入/导出的详细信息，请参阅[导入或导出 BizTalk 设置使用 BTSTask](how-to-import-biztalk-settings-using-btstask.md)。</span><span class="sxs-lookup"><span data-stu-id="74466-135">For details about how to import/export using the BTSTask.exe command-line utility, see [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md).</span></span>  
  
## <a name="next"></a><span data-ttu-id="74466-136">Next</span><span class="sxs-lookup"><span data-stu-id="74466-136">Next</span></span>  
  
-   [<span data-ttu-id="74466-137">使用设置仪表板进行 BizTalk Server 性能调整</span><span class="sxs-lookup"><span data-stu-id="74466-137">Use Settings Dashboard for BizTalk Server Performance Tuning</span></span>](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)  
  
-   [<span data-ttu-id="74466-138">自动进行 BizTalk Server 性能调整</span><span class="sxs-lookup"><span data-stu-id="74466-138">Automate BizTalk Server Performance Tuning</span></span>](../core/automating-biztalk-server-performance-tuning.md)  
  
## <a name="see-also"></a><span data-ttu-id="74466-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="74466-139">See Also</span></span>  
 [<span data-ttu-id="74466-140">管理 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="74466-140">Manage BizTalk Server</span></span>](../core/use-groups-create-artifacts-optimize-performance-and-more-in-biztalk-server.md)