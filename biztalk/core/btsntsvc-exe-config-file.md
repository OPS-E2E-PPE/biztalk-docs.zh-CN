---
title: BTSNTSvc.exe.config 文件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2bb89a7-4fff-4ccf-a0a7-20ca610f2ddf
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7fae2fc49487597380e6c5d04a946b1078daeeb
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26004814"
---
# <a name="btsntsvcexeconfig-file"></a><span data-ttu-id="cfcdb-102">BTSNTSvc.exe.config 文件</span><span class="sxs-lookup"><span data-stu-id="cfcdb-102">BTSNTSvc.exe.config File</span></span>
<span data-ttu-id="cfcdb-103">冻结属性及其默认值在[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]中配置，或作为 XML 在 BizTalk 配置文件（BTSNTSvc.exe.config 或 BTSNTSvc64.exe.config）中配置。</span><span class="sxs-lookup"><span data-stu-id="cfcdb-103">Dehydration properties and their default values are configurable in [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] or as XML in the BizTalk configuration file (BTSNTSvc.exe.config or BTSNTSvc64.exe.config).</span></span> <span data-ttu-id="cfcdb-104">将首先应用 BizTalk 配置文件中的值，</span><span class="sxs-lookup"><span data-stu-id="cfcdb-104">The values in the BizTalk configuration file are applied first.</span></span> <span data-ttu-id="cfcdb-105">然后应用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]设置。</span><span class="sxs-lookup"><span data-stu-id="cfcdb-105">Then, the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] settings are applied.</span></span> <span data-ttu-id="cfcdb-106">所有包含业务流程的主机实例启动后，将读取冻结属性。</span><span class="sxs-lookup"><span data-stu-id="cfcdb-106">The dehydration properties are read when all host instances containing an orchestration start.</span></span>  
  
 <span data-ttu-id="cfcdb-107">本主题主要介绍 BizTalk 配置文件（BTSNTSvc.exe.config 或 BTSNTSvc64.exe.config）。</span><span class="sxs-lookup"><span data-stu-id="cfcdb-107">This topic focuses on the BizTalk configuration file (BTSNTSvc.exe.config or BTSNTSvc64.exe.config).</span></span> <span data-ttu-id="cfcdb-108">许多冻结属性并未列出，</span><span class="sxs-lookup"><span data-stu-id="cfcdb-108">Many dehydration properties are not listed.</span></span> <span data-ttu-id="cfcdb-109">但这些属性及其默认值仍然适用，即使并未在配置文件中明确指定它们。</span><span class="sxs-lookup"><span data-stu-id="cfcdb-109">These properties and their default values are still applied, even if they are not explicitly specified in the configuration file.</span></span>  
  
 <span data-ttu-id="cfcdb-110">要更改默认值，必须将它们显式添加到你的配置文件。</span><span class="sxs-lookup"><span data-stu-id="cfcdb-110">To change the default values, you must explicitly add them to your configuration file.</span></span> <span data-ttu-id="cfcdb-111">有关如何更改默认冻结行为的信息，请参阅[如何修改业务流程限制设置](../core/how-to-modify-orchestration-throttling-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="cfcdb-111">For information about how to change the default dehydration behavior, see [How to Modify Orchestration Throttling Settings](../core/how-to-modify-orchestration-throttling-settings.md).</span></span> <span data-ttu-id="cfcdb-112">有关业务流程内存限制的信息，请参阅[如何修改 Orchestration 内存限制设置](../core/how-to-modify-orchestration-memory-throttling-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="cfcdb-112">For information about orchestration memory throttling, see [How to Modify Orchestration Memory Throttling Settings](../core/how-to-modify-orchestration-memory-throttling-settings.md).</span></span>  
  
 <span data-ttu-id="cfcdb-113">以下为 BTSNTSvc.exe.config 文件的内容。</span><span class="sxs-lookup"><span data-stu-id="cfcdb-113">Following is the contents of the BTSNTSvc.exe.config file.</span></span> <span data-ttu-id="cfcdb-114">此文件始终位于 BTSNTSvc.exe 文件，这通常是 C:\Program Files\Microsoft BizTalk Server 所在的同一目录中。</span><span class="sxs-lookup"><span data-stu-id="cfcdb-114">This file is always located in the same directory as the BTSNTSvc.exe file, which is usually C:\Program Files\Microsoft BizTalk Server.</span></span>  
  
```  
<?xml version="1.0" ?>  
<configuration>  
       <configSections>  
              <section name="xlangs" type="Microsoft.XLANGs.BizTalk.CrossProcess.XmlSerializationConfigurationSectionHandler, Microsoft.XLANGs.BizTalk.CrossProcess" />  
       </configSections>  
       <runtime>  
              <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
                     <probing privatePath="BizTalk Assemblies;Developer Tools;Tracking" />  
              </assemblyBinding>  
       </runtime>  
       <xlangs>  
              <Configuration>  
                     <Dehydration MaxThreshold="1800" MinThreshold="1" ConstantThreshold="-1">  
                            <VirtualMemoryThrottlingCriteria OptimalUsage="900" MaximalUsage="1300" IsActive="true" />  
                            <PrivateMemoryThrottlingCriteria OptimalUsage="50" MaximalUsage="350" IsActive="true" />  
                            <PhysicalMemoryThrottlingCriteria OptimalUsage="50" MaximalUsage="350" IsActive="false" />  
                     </Dehydration>  
              </Configuration>  
       </xlangs>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cfcdb-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cfcdb-115">See Also</span></span>  
 [<span data-ttu-id="cfcdb-116">使用设置仪表板进行 BizTalk Server 性能调整</span><span class="sxs-lookup"><span data-stu-id="cfcdb-116">Using Settings Dashboard for BizTalk Server Performance Tuning</span></span>](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)