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
# <a name="btsntsvcexeconfig-file"></a>BTSNTSvc.exe.config File
冻结属性和它们的默认值是可在中配置[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]或作为 XML 在 BizTalk 配置文件 （BTSNTSvc.exe.config 或 BTSNTSvc64.exe.config）。 首先应用 BizTalk 配置文件中的值。 然后，[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]应用设置。 所有主机实例包含业务流程开始时将读取冻结属性。  
  
 本主题重点介绍 BizTalk 配置文件 （BTSNTSvc.exe.config 或 BTSNTSvc64.exe.config）。 许多冻结属性不会列出。 这些属性和它们的默认值仍然适用，即使它们未显式指定配置文件中。  
  
 若要更改默认值，您必须显式添加到你的配置文件。 有关如何更改默认冻结行为的信息，请参阅[如何修改业务流程阻止设置](../core/how-to-modify-orchestration-throttling-settings.md)。 有关业务流程内存限制的信息，请参阅[如何修改业务流程内存阻止设置](../core/how-to-modify-orchestration-memory-throttling-settings.md)。  
  
 下面是在 BTSNTSvc.exe.config 文件的内容。 此文件位于始终与 BTSNTSvc.exe 文件，这通常是 C:\Program Files\Microsoft BizTalk Server 的同一目录中。  
  
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
  
## <a name="see-also"></a>请参阅  
 [使用设置仪表板进行 BizTalk Server 性能调整](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)