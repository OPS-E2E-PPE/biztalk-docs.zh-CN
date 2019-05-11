---
title: 导入或导出 BizTalk 设置，请使用 BTSTask |Microsoft Docs
description: 使用 ImportSettings 或 ExportSettings BTSTask 命令将设置从一个环境移到另一个 BizTalk Server 中
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3fdd8c9-3534-4c11-8acc-6cb6f5bf0989
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19143ff1f5da248b3924ce87d7dc2e686bdd80d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384959"
---
# <a name="use-btstask-to-import-or-export-biztalk-settings"></a><span data-ttu-id="f2eaa-103">使用 BTSTask 导入或导出 BizTalk 设置</span><span class="sxs-lookup"><span data-stu-id="f2eaa-103">Use BTSTask to import or export BizTalk settings</span></span>

## <a name="overview"></a><span data-ttu-id="f2eaa-104">概述</span><span class="sxs-lookup"><span data-stu-id="f2eaa-104">Overview</span></span>
<span data-ttu-id="f2eaa-105">使用 BTSTask 命令行实用工具，您可以导出中的设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境并将其导入到另一个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境，从而减少总体到解决方案的时间。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-105">Using the BTSTask command-line utility, you can export the settings from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment and import them to another [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, thereby reducing the overall time-to-solution.</span></span> <span data-ttu-id="f2eaa-106">这是管理员尝试优化的情境中尤其有用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能在过渡环境中，并在达到预期的结果时，他们可以设置导入生产环境。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-106">This is especially useful in scenarios where the administrators try to tune [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance in a staging environment, and upon achieving the desired results, they can import the settings into a production environment.</span></span> 

<span data-ttu-id="f2eaa-107">本主题列出了导入或从一个环境中的 BizTalk Server 设置导出到另一个使用的步骤**BTSTask.exe**。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-107">This topic lists the steps to import or export the BizTalk Server settings from one environment to another using **BTSTask.exe**.</span></span>  


## <a name="import-biztalk-settings"></a><span data-ttu-id="f2eaa-108">导入 BizTalk 设置</span><span class="sxs-lookup"><span data-stu-id="f2eaa-108">Import BizTalk settings</span></span> 
> [!IMPORTANT]
>  <span data-ttu-id="f2eaa-109">若要从某个环境导入 BizTalk 设置，应已导出并保存的 XML 文件中的这些设置。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-109">To import the BizTalk settings from a certain environment, you should have already exported and saved those settings in an XML file.</span></span> <span data-ttu-id="f2eaa-110">有关导出设置的详细信息，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)或**使用 BTSTask 导出 BizTalk 设置**（在本主题中）。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-110">For more information about exporting the settings, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) or **Export BizTalk Settings Using BTSTask** (in this topic).</span></span>  
  
 <span data-ttu-id="f2eaa-111">通过导入 XML 文件，可以复制目标计算机上所需的 BizTalk Server 设置。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-111">By importing the XML file, you can replicate the required BizTalk Server settings on the target machine.</span></span> <span data-ttu-id="f2eaa-112">使用**BTSTask.exe**，可以导入组、 主机和主机实例设置并将映射到另一个属性。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-112">Using the **BTSTask.exe**, you can import the Group, Host, and Host Instance settings and map the properties of one to another.</span></span> <span data-ttu-id="f2eaa-113">以下是有关导入设置的必要假设：</span><span class="sxs-lookup"><span data-stu-id="f2eaa-113">Following are the necessary assumptions for importing the settings:</span></span>  
  
-   <span data-ttu-id="f2eaa-114">您可以在类似的拓扑结构之间导入 BizTalk Server 设置。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-114">You can import the BizTalk Server settings across similar topologies.</span></span>  
  
-   <span data-ttu-id="f2eaa-115">您应能够将源主机和主机实例映射到目标对应项。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-115">You should be able to map the source Host and Host Instances to the destination counterparts.</span></span>  
  
-   <span data-ttu-id="f2eaa-116">目标环境中出现相似的硬件 （即使不完全相同） 与源环境。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-116">The destination environment has hardware similar (if not identical) to the source environment.</span></span> <span data-ttu-id="f2eaa-117">这是必须的某些设置取决于基础硬件。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-117">This is essential as some of the settings depend on the underlying hardware.</span></span>  
  
### <a name="importsettings-command"></a><span data-ttu-id="f2eaa-118">ImportSettings 命令</span><span class="sxs-lookup"><span data-stu-id="f2eaa-118">ImportSettings command</span></span> 
 <span data-ttu-id="f2eaa-119">可以使用**ImportSettings** BTSTask 命令导入 BizTalk Server 设置从源环境到目标环境。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-119">You can use the **ImportSettings** BTSTask command to import BizTalk Server settings from the source environment to destination environment.</span></span> <span data-ttu-id="f2eaa-120">请参阅[ImportSettings 命令](../core/importsettings-command.md)的具体详细信息。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-120">See [ImportSettings Command](../core/importsettings-command.md) for specific details.</span></span>  
  
 <span data-ttu-id="f2eaa-121">你可以定义从源主机向目标主机和/或源主机实例映射到目标主机实例所示：</span><span class="sxs-lookup"><span data-stu-id="f2eaa-121">You can define the mapping from a source host to a destination host and/or a source host instance to a destination host instance as shown:</span></span>  
  
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
  
 <span data-ttu-id="f2eaa-122">在映射文件中，输入作为 hostname: Machinename 的主机实例。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-122">In a map file, enter a host instance as 'HostName:MachineName'.</span></span> <span data-ttu-id="f2eaa-123">例如："Host1: server1"表示这是运行 （或提供） 在计算机上的主机 Host1 的实例 Server1"。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-123">For example: "Host1:Server1" means the instance of host 'Host1' which is running (or present) on machine 'Server1".</span></span>  
  
 <span data-ttu-id="f2eaa-124">若要输入 1: n 源到目标的映射，使用分号分隔的列表。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-124">To enter 1:n source to destination mappings, use a semicolon-separated list.</span></span> <span data-ttu-id="f2eaa-125">例如：</span><span class="sxs-lookup"><span data-stu-id="f2eaa-125">For example:</span></span>  
  
```  
SourceHost Name="SourceHost1"   
......DestinationHosts   
............DestHost1;DestHost2;DestHost3   
....../DestinationHosts   
/SourceHost  
```  
  
 <span data-ttu-id="f2eaa-126">仅这些主机的实例可以为其相应主机映射还创建映射。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-126">Only those host-instances can be mapped for which the corresponding host mapping has also been created.</span></span> <span data-ttu-id="f2eaa-127">如果主机映射中已将 SourceHost1 映射到 DestinationHost1，DestinationHost1 的实例 （如果有） 可以只能映射到 SourceHost1 的实例 （如果有）。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-127">If 'SourceHost1' has been mapped to 'DestinationHost1' in host mappings, the instances (if any) of 'DestinationHost1' can be mapped only to the instances (if any) of 'SourceHost1'.</span></span> <span data-ttu-id="f2eaa-128">此约束将负责 UI 导入向导。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-128">The UI Import Wizard takes care of this constraint.</span></span> <span data-ttu-id="f2eaa-129">您需要将其显式写入映射文件中。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-129">You would need to explicitly write it in the map file.</span></span>  


## <a name="export-biztalk-settings"></a><span data-ttu-id="f2eaa-130">导出 BizTalk 设置</span><span class="sxs-lookup"><span data-stu-id="f2eaa-130">Export BizTalk settings</span></span>  

<span data-ttu-id="f2eaa-131">有两种方法导出 BizTalk 设置：</span><span class="sxs-lookup"><span data-stu-id="f2eaa-131">There are a couple of ways to export the BizTalk settings:</span></span> 

1. <span data-ttu-id="f2eaa-132">使用**ExportSettings** BTSTask 命令，将源环境的 BizTalk Server 设置导出到 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-132">Use the **ExportSettings** BTSTask command to export the BizTalk Server settings of the source environment to an XML file.</span></span> <span data-ttu-id="f2eaa-133">请参阅[ExportSettings 命令](../core/exportsettings-command.md)的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-133">See [ExportSettings Command](../core/exportsettings-command.md) for more details.</span></span>  

2.  <span data-ttu-id="f2eaa-134">在 BizTalk Server 管理中使用设置仪表板。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-134">Use the Settings Dashboard in BizTalk Server Administration.</span></span> <span data-ttu-id="f2eaa-135">请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)有关的步骤。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-135">See [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) for the steps.</span></span>

 
> [!TIP]
>  <span data-ttu-id="f2eaa-136">有关如何将 XML 文件中的 BizTalk Server 设置应用于目标环境的信息，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="f2eaa-136">For information about how the BizTalk Server settings in an XML file are applied to the target environment, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f2eaa-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2eaa-137">See Also</span></span>  
 [<span data-ttu-id="f2eaa-138">自动进行 BizTalk Server 性能调整</span><span class="sxs-lookup"><span data-stu-id="f2eaa-138">Automate BizTalk Server Performance Tuning</span></span>](../core/automating-biztalk-server-performance-tuning.md)