---
title: BTSNTSvc.exe.config File | Microsoft Docs
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
ms.openlocfilehash: 1c8347f7027371cd77c5b712ed3e12380e30bc34
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357991"
---
# <a name="btsntsvcexeconfig-file"></a><span data-ttu-id="ca63e-102">BTSNTSvc.exe.config File</span><span class="sxs-lookup"><span data-stu-id="ca63e-102">BTSNTSvc.exe.config File</span></span>
<span data-ttu-id="ca63e-103">冻结属性和它们的默认值是可在中配置[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]或作为 XML 在 BizTalk 配置文件 （BTSNTSvc.exe.config 或 BTSNTSvc64.exe.config）。</span><span class="sxs-lookup"><span data-stu-id="ca63e-103">Dehydration properties and their default values are configurable in [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] or as XML in the BizTalk configuration file (BTSNTSvc.exe.config or BTSNTSvc64.exe.config).</span></span> <span data-ttu-id="ca63e-104">首先应用 BizTalk 配置文件中的值。</span><span class="sxs-lookup"><span data-stu-id="ca63e-104">The values in the BizTalk configuration file are applied first.</span></span> <span data-ttu-id="ca63e-105">然后，[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]应用设置。</span><span class="sxs-lookup"><span data-stu-id="ca63e-105">Then, the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] settings are applied.</span></span> <span data-ttu-id="ca63e-106">所有主机实例包含业务流程开始时将读取冻结属性。</span><span class="sxs-lookup"><span data-stu-id="ca63e-106">The dehydration properties are read when all host instances containing an orchestration start.</span></span>  
  
 <span data-ttu-id="ca63e-107">本主题重点介绍 BizTalk 配置文件 （BTSNTSvc.exe.config 或 BTSNTSvc64.exe.config）。</span><span class="sxs-lookup"><span data-stu-id="ca63e-107">This topic focuses on the BizTalk configuration file (BTSNTSvc.exe.config or BTSNTSvc64.exe.config).</span></span> <span data-ttu-id="ca63e-108">许多冻结属性不会列出。</span><span class="sxs-lookup"><span data-stu-id="ca63e-108">Many dehydration properties are not listed.</span></span> <span data-ttu-id="ca63e-109">这些属性和它们的默认值仍然适用，即使它们未显式指定配置文件中。</span><span class="sxs-lookup"><span data-stu-id="ca63e-109">These properties and their default values are still applied, even if they are not explicitly specified in the configuration file.</span></span>  
  
 <span data-ttu-id="ca63e-110">若要更改默认值，您必须显式添加到你的配置文件。</span><span class="sxs-lookup"><span data-stu-id="ca63e-110">To change the default values, you must explicitly add them to your configuration file.</span></span> <span data-ttu-id="ca63e-111">有关如何更改默认冻结行为的信息，请参阅[如何修改业务流程阻止设置](../core/how-to-modify-orchestration-throttling-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="ca63e-111">For information about how to change the default dehydration behavior, see [How to Modify Orchestration Throttling Settings](../core/how-to-modify-orchestration-throttling-settings.md).</span></span> <span data-ttu-id="ca63e-112">有关业务流程内存限制的信息，请参阅[如何修改业务流程内存阻止设置](../core/how-to-modify-orchestration-memory-throttling-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="ca63e-112">For information about orchestration memory throttling, see [How to Modify Orchestration Memory Throttling Settings](../core/how-to-modify-orchestration-memory-throttling-settings.md).</span></span>  
  
 <span data-ttu-id="ca63e-113">下面是在 BTSNTSvc.exe.config 文件的内容。</span><span class="sxs-lookup"><span data-stu-id="ca63e-113">Following is the contents of the BTSNTSvc.exe.config file.</span></span> <span data-ttu-id="ca63e-114">此文件位于始终与 BTSNTSvc.exe 文件，这通常是 C:\Program Files\Microsoft BizTalk Server 的同一目录中。</span><span class="sxs-lookup"><span data-stu-id="ca63e-114">This file is always located in the same directory as the BTSNTSvc.exe file, which is usually C:\Program Files\Microsoft BizTalk Server.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ca63e-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca63e-115">See Also</span></span>  
 [<span data-ttu-id="ca63e-116">使用设置仪表板进行 BizTalk Server 性能调整</span><span class="sxs-lookup"><span data-stu-id="ca63e-116">Using Settings Dashboard for BizTalk Server Performance Tuning</span></span>](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)