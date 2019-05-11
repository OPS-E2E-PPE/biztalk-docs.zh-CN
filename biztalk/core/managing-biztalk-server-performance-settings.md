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
# <a name="manage-biztalk-server-performance-settings"></a>管理 BizTalk Server 性能设置
  
 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] BizTalk Server 中整理性能设置，并提供了一个中央控制台来管理这些设置。 这可以帮助：  
  
-   提高可设置的属性的可发现的性
  
-   因为所有设置在单个位置现在均可访问，可以导出/导入轻松减少时解决方案
  
-   提供的性能优化级别的整体视图上给定的 BizTalk 部署完成
  
## <a name="why-use-it"></a>为什么要使用它？  
 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]面向 IT 管理员需要广泛地调整[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]设置以优化性能。  
  
 可以使用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]修改 BizTalk 组和所有的 BizTalk 主机和 BizTalk 主机实例在该组中的设置。  
  
 若要了解有关组、 主机和主机实例设置的详细信息，请参阅[如何修改组设置](../core/how-to-modify-group-settings.md)，[如何修改主机设置](../core/how-to-modify-host-settings.md)，和[如何修改主机实例设置](../core/how-to-modify-host-instance-settings.md).  
  
## <a name="prerequisites"></a>先决条件 
 您可以启动[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关如何管理的信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能设置，请使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，请参阅[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)。  
  
## <a name="where-do-i-start"></a>如何开始？  
 您可以访问[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]任何以下方法：  
  
- 启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**BizTalk 组**在控制台树中，然后选择**设置**。  
  
- 右键单击下的任一主机**平台设置**节点中 MMC，然后单击**设置**。 这将启动[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]，可以修改与该主机相关的设置。  
  
- 右键单击下的任何主机实例**平台设置**节点中 MMC，然后单击**设置**。 这将启动[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]，可以修改与该主机实例相关的设置。  
  
## <a name="export-and-import-settings"></a>导出和导入设置  
 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]可用于导出中的设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境导入另一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境，从而减少总体到解决方案的时间。 这是管理员尝试优化的情境中尤其有用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能在测试环境中，并在达到预期的结果时，他们可以设置导入生产环境。  
  
 有关如何使用导入/导出[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]用户界面，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)。
  
## <a name="scripting-support"></a>脚本支持
 [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]不仅提供了一个中央用户界面来管理 BizTalk 设置，而且还可确保所有设置和导入/导出任务都可通过 Api 和命令行选项进行访问。 这使 BizTalk Server 管理员能够自动执行与 BizTalk Server 设置相关的任务。 作为脚本的支持的一部分：  
  
- 可以访问和修改通过 WMI 类所有组设置： `MSBTS_GroupSetting`  
  
- 可以访问和修改通过 WMI 类所有主机设置： `MSBTS_HostSetting`  
  
- 可以访问和修改通过 WMI 类所有主机实例设置： `MSBTS_HostInstanceSetting`  
  
- 导入和导出操作可以通过访问**BTSTask.exe**命令：`ExportSettings`和 `ImportSettings`  
  
  有关如何使用 BTSTask.exe 命令行实用程序导入/导出的详细信息，请参阅[导入或导出 BizTalk 设置使用 BTSTask](how-to-import-biztalk-settings-using-btstask.md)。  
  
## <a name="next"></a>Next  
  
-   [使用设置仪表板进行 BizTalk Server 性能调整](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)  
  
-   [自动进行 BizTalk Server 性能调整](../core/automating-biztalk-server-performance-tuning.md)  
  
## <a name="see-also"></a>请参阅  
 [管理 BizTalk Server](../core/use-groups-create-artifacts-optimize-performance-and-more-in-biztalk-server.md)