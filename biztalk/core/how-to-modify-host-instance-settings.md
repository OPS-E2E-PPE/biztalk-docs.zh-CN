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
ms.openlocfilehash: 0e5b2eec6b252417f73f917f1293ffc925f0e1a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336084"
---
# <a name="update-biztalk-host-instance-settings"></a>更新 BizTalk 主机实例设置

## <a name="overview"></a>概述
使用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]，可以跨 BizTalk 组中修改给定的主机实例的配置信息。 本主题提供的分步过程来修改主机实例级别性能设置在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 通常可以另存为 XML 文件的 BizTalk 设置 （来自源环境）。 XML 文件包含允许您复制目标计算机上的设置的信息。 而不是设置新值，您可以导入设置仪表板中，这些设置。 但是，设置新值后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以将其导出到 XML 文件以在另一台计算机中使用。  
  
 有关导入信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]设置，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)并[导入或导出 BizTalk 设置使用 BTSTask](how-to-import-biztalk-settings-using-btstask.md)。 
  
## <a name="prerequisites"></a>先决条件  
 若要执行此操作，必须以 BizTalk Server Administrators 组的成员的身份登录。  
  
## <a name="update-the-host-instance-level-settings"></a>更新主机实例级别设置  
  
1. 在中**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。  
  
2. 在中**BizTalk 设置仪表板**对话框中，在**主机实例**选项卡上，执行以下任一操作：  
  
   -   修改主机实例的.NET CLR 设置。 请参阅[更改.NET CLR 设置](../core/how-to-modify-net-clr-settings.md)。  
  
   -   修改业务流程内存阻止设置。 请参阅[更改业务流程内存阻止设置](../core/how-to-modify-orchestration-memory-throttling-settings.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用设置仪表板进行 BizTalk Server 性能调整](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)