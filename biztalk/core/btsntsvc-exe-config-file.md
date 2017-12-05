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
ms.openlocfilehash: a7fae2fc49487597380e6c5d04a946b1078daeeb
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="btsntsvcexeconfig-file"></a>BTSNTSvc.exe.config 文件
冻结属性及其默认值在[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]中配置，或作为 XML 在 BizTalk 配置文件（BTSNTSvc.exe.config 或 BTSNTSvc64.exe.config）中配置。 将首先应用 BizTalk 配置文件中的值， 然后应用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]设置。 所有包含业务流程的主机实例启动后，将读取冻结属性。  
  
 本主题主要介绍 BizTalk 配置文件（BTSNTSvc.exe.config 或 BTSNTSvc64.exe.config）。 许多冻结属性并未列出， 但这些属性及其默认值仍然适用，即使并未在配置文件中明确指定它们。  
  
 要更改默认值，必须将它们显式添加到你的配置文件。 有关如何更改默认冻结行为的信息，请参阅[如何修改业务流程限制设置](../core/how-to-modify-orchestration-throttling-settings.md)。 有关业务流程内存限制的信息，请参阅[如何修改 Orchestration 内存限制设置](../core/how-to-modify-orchestration-memory-throttling-settings.md)。  
  
 以下为 BTSNTSvc.exe.config 文件的内容。 此文件始终位于 BTSNTSvc.exe 文件，这通常是 C:\Program Files\Microsoft BizTalk Server 所在的同一目录中。  
  
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
  
## <a name="see-also"></a>另请参阅  
 [使用设置仪表板进行 BizTalk Server 性能调整](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)