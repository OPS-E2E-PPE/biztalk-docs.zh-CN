---
title: 使用设置仪表板进行 BizTalk Server 性能优化 |Microsoft Docs
description: 在 BizTalk Server 管理中使用设置仪表板来更新组、 主机和主机实例设置
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bb1ddac-1e8f-4928-9c70-8326ae64a734
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b906ccae0e17d79f5783a3689a517fe4cba310ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395394"
---
# <a name="use-settings-dashboard-for-biztalk-server-performance-tuning"></a>使用设置仪表板进行 BizTalk Server 性能优化

## <a name="overview"></a>概述
使用设置仪表板，你可以广泛地调整[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]设置以优化性能。 此外可以修改 BizTalk 组、 BizTalk 主机和 BizTalk 主机实例设置。  
  
- **组级别设置**:在组级别，可以使用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]若要设置属性，如配置刷新间隔、 最大消息批大小、 组级别跟踪，等等。这些设置应用于 BizTalk 组中的所有计算机中。  
  
- **主机级别设置**:在主机级别，可以修改设置，如主机跟踪，与基于资源的阻止，与消息进程阻止相关的属性相关的属性以及与业务流程阻止相关的属性。 这些设置不适用于所选主机的所有实例。  
  
- **主机实例级别设置**:在主机实例级别，可以修改.NET CLR 设置和与业务流程内存阻止相关的属性。 这些设置不适用于仅所选的主机实例。  
  
  有关 BizTalk 组、 BizTalk 主机和 BizTalk 主机实例设置的详细信息，请参阅[如何修改组设置](../core/how-to-modify-group-settings.md)，[如何修改主机设置](../core/how-to-modify-host-settings.md)，和[如何修改主机实例设置](../core/how-to-modify-host-instance-settings.md)。  
  
  设置仪表板，可以导入/导出 BizTalk 设置不需要相同的部署中。 使用用户界面，可以映射的主机和主机实例从目标到源部署。 这可帮助你将设置应用于主机和计算机名称或各自计数是不同的环境。 有关导入/导出 BizTalk 设置的更多详细信息，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)。  
  
## <a name="see-also"></a>请参阅  
 [管理 BizTalk Server 性能设置](../core/managing-biztalk-server-performance-settings.md)