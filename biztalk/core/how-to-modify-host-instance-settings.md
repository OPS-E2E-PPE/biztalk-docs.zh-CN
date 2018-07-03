---
title: 更新主机实例设置 |Microsoft Docs
description: 更改主机实例设置 BizTalk 服务器管理器中
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2338255b-cc13-4f6a-86c3-9ecc666c43e5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6102e4cce6a850c7e2ed5656a8fd5aacfd5d5a09
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011710"
---
# <a name="update-biztalk-host-instance-settings"></a>更新 BizTalk 主机实例设置

## <a name="overview"></a>概述
使用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]，您可以修改整个 BizTalk 组中给定主机实例的配置信息。 本主题提供了用于修改 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中主机实例级别性能设置的分步过程。  
  
 通常您将 BizTalk 设置（来自源环境）保存为 XML 文件。 XML 文件包含允许您在目标计算机上复制设置的信息。 可以将这些设置导入设置仪表板，而无需设置新值。 另一方面，为  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 设置新值后，您可以将其导出到 XML 文件以用于其他计算机。  
  
 有关导入信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]设置，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)并[导入或导出 BizTalk 设置使用 BTSTask](how-to-import-biztalk-settings-using-btstask.md)。 
  
## <a name="prerequisites"></a>必要條件  
 若要执行此操作，必须以 BizTalk Server Administrators 组的成员的身份登录。  
  
## <a name="update-the-host-instance-level-settings"></a>更新主机实例级别设置  
  
1. 在中**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。  
  
2. 在中**BizTalk 设置仪表板**对话框中，在**主机实例**选项卡上，执行以下任一操作：  
  
   -   修改主机实例的 .NET CLR 设置。 请参阅[更改.NET CLR 设置](../core/how-to-modify-net-clr-settings.md)。  
  
   -   修改业务流程内存阻止设置。 请参阅[更改业务流程内存阻止设置](../core/how-to-modify-orchestration-memory-throttling-settings.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用设置仪表板进行 BizTalk Server 性能调整](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)