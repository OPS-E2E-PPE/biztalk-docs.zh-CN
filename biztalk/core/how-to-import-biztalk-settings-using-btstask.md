---
title: "导入或导出 BizTalk 设置，请使用 BTSTask |Microsoft 文档"
description: "使用 ImportSettings 或 ExportSettings BTSTask 命令将设置从一个环境移到另一个 BizTalk Server 中"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3fdd8c9-3534-4c11-8acc-6cb6f5bf0989
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99aecaea767133fc5f3cb77d38dc174b09733674
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="use-btstask-to-import-or-export-biztalk-settings"></a><span data-ttu-id="16a3c-103">使用 BTSTask 导入或导出 BizTalk 设置</span><span class="sxs-lookup"><span data-stu-id="16a3c-103">Use BTSTask to import or export BizTalk settings</span></span>

## <a name="overview"></a><span data-ttu-id="16a3c-104">概述</span><span class="sxs-lookup"><span data-stu-id="16a3c-104">Overview</span></span>
<span data-ttu-id="16a3c-105">使用 BTSTask 命令行实用程序，您可以从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中导出设置，并将这些设置导入另一个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境，藉此可减少总体的</span><span class="sxs-lookup"><span data-stu-id="16a3c-105">Using the BTSTask command-line utility, you can export the settings from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment and import them to another [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, thereby reducing the overall time-to-solution.</span></span> <span data-ttu-id="16a3c-106">这在以下情况时尤为有用：当 BizTalk 管理员尝试在临时环境中调整 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 性能，一旦达到预期结果，他们就会将设置导入生产环境。</span><span class="sxs-lookup"><span data-stu-id="16a3c-106">This is especially useful in scenarios where the administrators try to tune [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance in a staging environment, and upon achieving the desired results, they can import the settings into a production environment.</span></span> 

<span data-ttu-id="16a3c-107">本主题列出的步骤导入或从一个环境中的 BizTalk Server 设置导出到另一个使用**BTSTask.exe**。</span><span class="sxs-lookup"><span data-stu-id="16a3c-107">This topic lists the steps to import or export the BizTalk Server settings from one environment to another using **BTSTask.exe**.</span></span>  


## <a name="import-biztalk-settings"></a><span data-ttu-id="16a3c-108">导入 BizTalk 设置</span><span class="sxs-lookup"><span data-stu-id="16a3c-108">Import BizTalk settings</span></span> 
> [!IMPORTANT]
>  <span data-ttu-id="16a3c-109">要从一个特定环境中导入 BizTalk 设置，您应当已导出这些设置并将其保存在一个 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="16a3c-109">To import the BizTalk settings from a certain environment, you should have already exported and saved those settings in an XML file.</span></span> <span data-ttu-id="16a3c-110">有关导出设置的详细信息，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)或**导出 BizTalk 设置使用 BTSTask** （本主题中）。</span><span class="sxs-lookup"><span data-stu-id="16a3c-110">For more information about exporting the settings, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) or **Export BizTalk Settings Using BTSTask** (in this topic).</span></span>  
  
 <span data-ttu-id="16a3c-111">通过导入到 XML 文件，您可以在目标计算机上复制所需的 BizTalk Server 设置。</span><span class="sxs-lookup"><span data-stu-id="16a3c-111">By importing the XML file, you can replicate the required BizTalk Server settings on the target machine.</span></span> <span data-ttu-id="16a3c-112">使用**BTSTask.exe**，你可以导入的组、 主机和主机实例的设置并映射到另一个属性。</span><span class="sxs-lookup"><span data-stu-id="16a3c-112">Using the **BTSTask.exe**, you can import the Group, Host, and Host Instance settings and map the properties of one to another.</span></span> <span data-ttu-id="16a3c-113">以下是有关导入设置的必要假设：</span><span class="sxs-lookup"><span data-stu-id="16a3c-113">Following are the necessary assumptions for importing the settings:</span></span>  
  
-   <span data-ttu-id="16a3c-114">您可以在类似的拓扑结构之间导入 BizTalk Server 设置。</span><span class="sxs-lookup"><span data-stu-id="16a3c-114">You can import the BizTalk Server settings across similar topologies.</span></span>  
  
-   <span data-ttu-id="16a3c-115">您应该可以将源主机和源实例映射到目标主机和目标实例。</span><span class="sxs-lookup"><span data-stu-id="16a3c-115">You should be able to map the source Host and Host Instances to the destination counterparts.</span></span>  
  
-   <span data-ttu-id="16a3c-116">目标环境具有与源环境相似的硬件（即使不完全相同）。</span><span class="sxs-lookup"><span data-stu-id="16a3c-116">The destination environment has hardware similar (if not identical) to the source environment.</span></span> <span data-ttu-id="16a3c-117">因为某些设置取决于基础硬件，所以这很重要。</span><span class="sxs-lookup"><span data-stu-id="16a3c-117">This is essential as some of the settings depend on the underlying hardware.</span></span>  
  
### <a name="importsettings-command"></a><span data-ttu-id="16a3c-118">ImportSettings 命令</span><span class="sxs-lookup"><span data-stu-id="16a3c-118">ImportSettings command</span></span> 
 <span data-ttu-id="16a3c-119">你可以使用**ImportSettings** BTSTask 命令从源环境的 BizTalk Server 设置导入到目标环境。</span><span class="sxs-lookup"><span data-stu-id="16a3c-119">You can use the **ImportSettings** BTSTask command to import BizTalk Server settings from the source environment to destination environment.</span></span> <span data-ttu-id="16a3c-120">请参阅[ImportSettings 命令](../core/importsettings-command.md)的具体细节。</span><span class="sxs-lookup"><span data-stu-id="16a3c-120">See [ImportSettings Command](../core/importsettings-command.md) for specific details.</span></span>  
  
 <span data-ttu-id="16a3c-121">您可以定义从源主机到目标主机的映射和/或源主机实例到目标主机实例的映射，如下所示：</span><span class="sxs-lookup"><span data-stu-id="16a3c-121">You can define the mapping from a source host to a destination host and/or a source host instance to a destination host instance as shown:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SettingsMap>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <HostMappings>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHost Name="BizTalkServerApplication">  
  <DestinationHosts>BizTalkServerApplication</DestinationHosts>   
  </SourceHost>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHost Name="BizTalkServerIsolatedHost">  
  <DestinationHosts>BizTalkServerIsolatedHost</DestinationHosts>   
  </SourceHost>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHost Name="Host1">  
  <DestinationHosts>Host2</DestinationHosts>   
  </SourceHost>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHost Name="Host2">  
  <DestinationHosts>Host1;Host3;Host4;Host5</DestinationHosts>   
  </SourceHost>  
  </HostMappings>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <HostInstanceMappings>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHostInstance Name="BizTalkServerApplication:COMPUTER_NAME1">  
  <DestinationHostInstances>BizTalkServerApplication:COMPUTER_NAME2</DestinationHostInstances>   
  </SourceHostInstance>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHostInstance Name="Host1:COMPUTER_NAME1">  
  <DestinationHostInstances>Host2:COMPUTER_NAME2;Host3:COMPUTER_NAME3;Host4:COMPUTER_NAME4;Host5:COMPUTER_NAME5</DestinationHostInstances>   
  </SourceHostInstance>  
  </HostInstanceMappings>  
  </SettingsMap>  
  
```  
  
 <span data-ttu-id="16a3c-122">在映射文件中，输入作为 HostName:MachineName 的主机实例。</span><span class="sxs-lookup"><span data-stu-id="16a3c-122">In a map file, enter a host instance as 'HostName:MachineName'.</span></span> <span data-ttu-id="16a3c-123">例如：“Host1:Server1”表示计算机“Server1”上运行（或存在）的主机“Host1”的实例。</span><span class="sxs-lookup"><span data-stu-id="16a3c-123">For example: "Host1:Server1" means the instance of host 'Host1' which is running (or present) on machine 'Server1".</span></span>  
  
 <span data-ttu-id="16a3c-124">若要在此目标映射到输入 1: n 源，使用分号分隔的列表。</span><span class="sxs-lookup"><span data-stu-id="16a3c-124">To enter 1:n source to destination mappings, use a semicolon-separated list.</span></span> <span data-ttu-id="16a3c-125">例如：</span><span class="sxs-lookup"><span data-stu-id="16a3c-125">For example:</span></span>  
  
```  
SourceHost Name="SourceHost1"   
......DestinationHosts   
............DestHost1;DestHost2;DestHost3   
....../DestinationHosts   
/SourceHost  
```  
  
 <span data-ttu-id="16a3c-126">只有那些已经创建了相应主机映射的主机实例才会被映射。</span><span class="sxs-lookup"><span data-stu-id="16a3c-126">Only those host-instances can be mapped for which the corresponding host mapping has also been created.</span></span> <span data-ttu-id="16a3c-127">如果已将“SourceHost1”映射到主机映射中的“DestinationHost1”，则只会将“DestinationHost1”的实例（如果有）映射到“SourceHost1”的实例（如果有）。</span><span class="sxs-lookup"><span data-stu-id="16a3c-127">If 'SourceHost1' has been mapped to 'DestinationHost1' in host mappings, the instances (if any) of 'DestinationHost1' can be mapped only to the instances (if any) of 'SourceHost1'.</span></span> <span data-ttu-id="16a3c-128">UI 导入向导会注意此约束。</span><span class="sxs-lookup"><span data-stu-id="16a3c-128">The UI Import Wizard takes care of this constraint.</span></span> <span data-ttu-id="16a3c-129">您需要将其显式写入到映射文件中。</span><span class="sxs-lookup"><span data-stu-id="16a3c-129">You would need to explicitly write it in the map file.</span></span>  


## <a name="export-biztalk-settings"></a><span data-ttu-id="16a3c-130">导出 BizTalk 设置</span><span class="sxs-lookup"><span data-stu-id="16a3c-130">Export BizTalk settings</span></span>  

<span data-ttu-id="16a3c-131">有几种方法导出 BizTalk 设置：</span><span class="sxs-lookup"><span data-stu-id="16a3c-131">There are a couple of ways to export the BizTalk settings:</span></span> 

1. <span data-ttu-id="16a3c-132">使用**ExportSettings** BTSTask 命令，将源环境的 BizTalk Server 设置导出到 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="16a3c-132">Use the **ExportSettings** BTSTask command to export the BizTalk Server settings of the source environment to an XML file.</span></span> <span data-ttu-id="16a3c-133">请参阅[ExportSettings 命令](../core/exportsettings-command.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="16a3c-133">See [ExportSettings Command](../core/exportsettings-command.md) for more details.</span></span>  

2.  <span data-ttu-id="16a3c-134">在 BizTalk Server 管理中使用设置仪表板。</span><span class="sxs-lookup"><span data-stu-id="16a3c-134">Use the Settings Dashboard in BizTalk Server Administration.</span></span> <span data-ttu-id="16a3c-135">请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)有关的步骤。</span><span class="sxs-lookup"><span data-stu-id="16a3c-135">See [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) for the steps.</span></span>

 
> [!TIP]
>  <span data-ttu-id="16a3c-136">有关如何将 XML 文件中的 BizTalk Server 设置应用于目标环境的信息，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="16a3c-136">For information about how the BizTalk Server settings in an XML file are applied to the target environment, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="16a3c-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16a3c-137">See Also</span></span>  
 [<span data-ttu-id="16a3c-138">自动执行 BizTalk Server 性能优化</span><span class="sxs-lookup"><span data-stu-id="16a3c-138">Automate BizTalk Server Performance Tuning</span></span>](../core/automating-biztalk-server-performance-tuning.md)