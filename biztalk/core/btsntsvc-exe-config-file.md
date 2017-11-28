---
title: "BTSNTSvc.exe.config 文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2bb89a7-4fff-4ccf-a0a7-20ca610f2ddf
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 303924e2aaf8304388a18d2ffe70d99fdc69acd3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="btsntsvcexeconfig-file"></a><span data-ttu-id="1a38a-102">BTSNTSvc.exe.config 文件</span><span class="sxs-lookup"><span data-stu-id="1a38a-102">BTSNTSvc.exe.config File</span></span>
<span data-ttu-id="1a38a-103">冻结属性及其默认值在[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]中配置，或作为 XML 在 BizTalk 配置文件（BTSNTSvc.exe.config 或 BTSNTSvc64.exe.config）中配置。</span><span class="sxs-lookup"><span data-stu-id="1a38a-103">Dehydration properties and their default values are configurable in [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] or as XML in the BizTalk configuration file (BTSNTSvc.exe.config or BTSNTSvc64.exe.config).</span></span> <span data-ttu-id="1a38a-104">将首先应用 BizTalk 配置文件中的值，</span><span class="sxs-lookup"><span data-stu-id="1a38a-104">The values in the BizTalk configuration file are applied first.</span></span> <span data-ttu-id="1a38a-105">然后应用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]设置。</span><span class="sxs-lookup"><span data-stu-id="1a38a-105">Then, the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] settings are applied.</span></span> <span data-ttu-id="1a38a-106">所有包含业务流程的主机实例启动后，将读取冻结属性。</span><span class="sxs-lookup"><span data-stu-id="1a38a-106">The dehydration properties are read when all host instances containing an orchestration start.</span></span>  
  
 <span data-ttu-id="1a38a-107">本主题主要介绍 BizTalk 配置文件（BTSNTSvc.exe.config 或 BTSNTSvc64.exe.config）。</span><span class="sxs-lookup"><span data-stu-id="1a38a-107">This topic focuses on the BizTalk configuration file (BTSNTSvc.exe.config or BTSNTSvc64.exe.config).</span></span> <span data-ttu-id="1a38a-108">许多冻结属性并未列出，</span><span class="sxs-lookup"><span data-stu-id="1a38a-108">Many dehydration properties are not listed.</span></span> <span data-ttu-id="1a38a-109">但这些属性及其默认值仍然适用，即使并未在配置文件中明确指定它们。</span><span class="sxs-lookup"><span data-stu-id="1a38a-109">These properties and their default values are still applied, even if they are not explicitly specified in the configuration file.</span></span>  
  
 <span data-ttu-id="1a38a-110">要更改默认值，必须将它们显式添加到你的配置文件。</span><span class="sxs-lookup"><span data-stu-id="1a38a-110">To change the default values, you must explicitly add them to your configuration file.</span></span> <span data-ttu-id="1a38a-111">有关如何更改默认冻结行为的信息，请参阅[如何修改业务流程限制设置](../core/how-to-modify-orchestration-throttling-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="1a38a-111">For information about how to change the default dehydration behavior, see [How to Modify Orchestration Throttling Settings](../core/how-to-modify-orchestration-throttling-settings.md).</span></span> <span data-ttu-id="1a38a-112">有关业务流程内存限制的信息，请参阅[如何修改 Orchestration 内存限制设置](../core/how-to-modify-orchestration-memory-throttling-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="1a38a-112">For information about orchestration memory throttling, see [How to Modify Orchestration Memory Throttling Settings](../core/how-to-modify-orchestration-memory-throttling-settings.md).</span></span>  
  
 <span data-ttu-id="1a38a-113">以下为 BTSNTSvc.exe.config 文件的内容。</span><span class="sxs-lookup"><span data-stu-id="1a38a-113">Following is the contents of the BTSNTSvc.exe.config file.</span></span> <span data-ttu-id="1a38a-114">此文件始终与 BTSNTSvc.exe 文件位于同一目录中，通常为 C:\Program Files\Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1a38a-114">This file is always located in the same directory as the BTSNTSvc.exe file, which is usually C:\Program Files\Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1a38a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a38a-115">See Also</span></span>  
 [<span data-ttu-id="1a38a-116">设置仪表板用于 BizTalk Server 性能优化</span><span class="sxs-lookup"><span data-stu-id="1a38a-116">Using Settings Dashboard for BizTalk Server Performance Tuning</span></span>](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)