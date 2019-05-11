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
# <a name="use-btstask-to-import-or-export-biztalk-settings"></a>使用 BTSTask 导入或导出 BizTalk 设置

## <a name="overview"></a>概述
使用 BTSTask 命令行实用工具，您可以导出中的设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境并将其导入到另一个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境，从而减少总体到解决方案的时间。 这是管理员尝试优化的情境中尤其有用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能在过渡环境中，并在达到预期的结果时，他们可以设置导入生产环境。 

本主题列出了导入或从一个环境中的 BizTalk Server 设置导出到另一个使用的步骤**BTSTask.exe**。  


## <a name="import-biztalk-settings"></a>导入 BizTalk 设置 
> [!IMPORTANT]
>  若要从某个环境导入 BizTalk 设置，应已导出并保存的 XML 文件中的这些设置。 有关导出设置的详细信息，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)或**使用 BTSTask 导出 BizTalk 设置**（在本主题中）。  
  
 通过导入 XML 文件，可以复制目标计算机上所需的 BizTalk Server 设置。 使用**BTSTask.exe**，可以导入组、 主机和主机实例设置并将映射到另一个属性。 以下是有关导入设置的必要假设：  
  
-   您可以在类似的拓扑结构之间导入 BizTalk Server 设置。  
  
-   您应能够将源主机和主机实例映射到目标对应项。  
  
-   目标环境中出现相似的硬件 （即使不完全相同） 与源环境。 这是必须的某些设置取决于基础硬件。  
  
### <a name="importsettings-command"></a>ImportSettings 命令 
 可以使用**ImportSettings** BTSTask 命令导入 BizTalk Server 设置从源环境到目标环境。 请参阅[ImportSettings 命令](../core/importsettings-command.md)的具体详细信息。  
  
 你可以定义从源主机向目标主机和/或源主机实例映射到目标主机实例所示：  
  
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
  
 在映射文件中，输入作为 hostname: Machinename 的主机实例。 例如："Host1: server1"表示这是运行 （或提供） 在计算机上的主机 Host1 的实例 Server1"。  
  
 若要输入 1: n 源到目标的映射，使用分号分隔的列表。 例如：  
  
```  
SourceHost Name="SourceHost1"   
......DestinationHosts   
............DestHost1;DestHost2;DestHost3   
....../DestinationHosts   
/SourceHost  
```  
  
 仅这些主机的实例可以为其相应主机映射还创建映射。 如果主机映射中已将 SourceHost1 映射到 DestinationHost1，DestinationHost1 的实例 （如果有） 可以只能映射到 SourceHost1 的实例 （如果有）。 此约束将负责 UI 导入向导。 您需要将其显式写入映射文件中。  


## <a name="export-biztalk-settings"></a>导出 BizTalk 设置  

有两种方法导出 BizTalk 设置： 

1. 使用**ExportSettings** BTSTask 命令，将源环境的 BizTalk Server 设置导出到 XML 文件。 请参阅[ExportSettings 命令](../core/exportsettings-command.md)的更多详细信息。  

2.  在 BizTalk Server 管理中使用设置仪表板。 请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)有关的步骤。

 
> [!TIP]
>  有关如何将 XML 文件中的 BizTalk Server 设置应用于目标环境的信息，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)。 
  
## <a name="see-also"></a>请参阅  
 [自动进行 BizTalk Server 性能调整](../core/automating-biztalk-server-performance-tuning.md)