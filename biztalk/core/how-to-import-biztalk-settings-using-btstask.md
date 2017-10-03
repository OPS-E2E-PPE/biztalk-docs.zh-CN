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
# <a name="use-btstask-to-import-or-export-biztalk-settings"></a>使用 BTSTask 导入或导出 BizTalk 设置

## <a name="overview"></a>概述
使用 BTSTask 命令行实用程序，您可以从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中导出设置，并将这些设置导入另一个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境，藉此可减少总体的 这在以下情况时尤为有用：当 BizTalk 管理员尝试在临时环境中调整 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 性能，一旦达到预期结果，他们就会将设置导入生产环境。 

本主题列出的步骤导入或从一个环境中的 BizTalk Server 设置导出到另一个使用**BTSTask.exe**。  


## <a name="import-biztalk-settings"></a>导入 BizTalk 设置 
> [!IMPORTANT]
>  要从一个特定环境中导入 BizTalk 设置，您应当已导出这些设置并将其保存在一个 XML 文件中。 有关导出设置的详细信息，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)或**导出 BizTalk 设置使用 BTSTask** （本主题中）。  
  
 通过导入到 XML 文件，您可以在目标计算机上复制所需的 BizTalk Server 设置。 使用**BTSTask.exe**，你可以导入的组、 主机和主机实例的设置并映射到另一个属性。 以下是有关导入设置的必要假设：  
  
-   您可以在类似的拓扑结构之间导入 BizTalk Server 设置。  
  
-   您应该可以将源主机和源实例映射到目标主机和目标实例。  
  
-   目标环境具有与源环境相似的硬件（即使不完全相同）。 因为某些设置取决于基础硬件，所以这很重要。  
  
### <a name="importsettings-command"></a>ImportSettings 命令 
 你可以使用**ImportSettings** BTSTask 命令从源环境的 BizTalk Server 设置导入到目标环境。 请参阅[ImportSettings 命令](../core/importsettings-command.md)的具体细节。  
  
 您可以定义从源主机到目标主机的映射和/或源主机实例到目标主机实例的映射，如下所示：  
  
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
  
 在映射文件中，输入作为 HostName:MachineName 的主机实例。 例如：“Host1:Server1”表示计算机“Server1”上运行（或存在）的主机“Host1”的实例。  
  
 若要在此目标映射到输入 1: n 源，使用分号分隔的列表。 例如：  
  
```  
SourceHost Name="SourceHost1"   
......DestinationHosts   
............DestHost1;DestHost2;DestHost3   
....../DestinationHosts   
/SourceHost  
```  
  
 只有那些已经创建了相应主机映射的主机实例才会被映射。 如果已将“SourceHost1”映射到主机映射中的“DestinationHost1”，则只会将“DestinationHost1”的实例（如果有）映射到“SourceHost1”的实例（如果有）。 UI 导入向导会注意此约束。 您需要将其显式写入到映射文件中。  


## <a name="export-biztalk-settings"></a>导出 BizTalk 设置  

有几种方法导出 BizTalk 设置： 

1. 使用**ExportSettings** BTSTask 命令，将源环境的 BizTalk Server 设置导出到 XML 文件。 请参阅[ExportSettings 命令](../core/exportsettings-command.md)有关详细信息。  

2.  在 BizTalk Server 管理中使用设置仪表板。 请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)有关的步骤。

 
> [!TIP]
>  有关如何将 XML 文件中的 BizTalk Server 设置应用于目标环境的信息，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)。 
  
## <a name="see-also"></a>另请参阅  
 [自动执行 BizTalk Server 性能优化](../core/automating-biztalk-server-performance-tuning.md)