---
title: 如何修改主机设置 |Microsoft Docs
description: 更改 BizTalk Server 管理来提高性能和带宽限制中的 BizTalk 主机设置
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0759b3a0-560e-4a11-92e6-9de0e15f463b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93b2ea993e044d1cb18efcc73f631e8ba3fcb8ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975838"
---
# <a name="update-biztalk-host-settings"></a>更新 BizTalk 主机设置

## <a name="overview"></a>概述
使用设置仪表板，您可以修改整个 BizTalk 组中给定主机的配置信息。 本主题提供了用于修改 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中主机级别性能设置的分步过程。  
  
> [!NOTE]
>  您还可以修改组和主机实例设置。 有关如何修改的设置的信息，请参阅[使用设置仪表板进行 BizTalk Server 性能调整](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)。  
  
 可以将当前的 BizTalk Server 设置导出到 XML 文件。 然后，将这些设置导入到“设置仪表板”，而不是设置新值。 有关导入信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]设置，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)并[导入或导出 BizTalk 设置使用 BTSTask](how-to-import-biztalk-settings-using-btstask.md)。 
  
## <a name="prerequisites"></a>必要條件  
 若要执行此操作，必须以 BizTalk Server Administrators 组的成员的身份登录。  
  
## <a name="update-the-host-level-settings"></a>更新主机级别设置  
  
1. 在中**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。  
  
2. 在中**BizTalk 设置仪表板**对话框中，在**主机**页上，执行一个或多个以下。  
  
   -   修改 BizTalk 主机的常规性能设置。 请参阅[如何修改常规设置](../core/how-to-modify-general-settings.md)。  
  
   -   修改 BizTalk 主机基于资源的阻止设置。 请参阅[基于如何修改资源的阻止设置](../core/how-to-modify-resource-based-throttling-settings.md)。  
  
   -   修改 BizTalk 主机基于速率的阻止设置。 请参阅[如何修改基于速率的阻止设置](../core/how-to-modify-rate-based-throttling-settings.md)。  
  
   -   修改 BizTalk 主机的业务流程阻止设置。 请参阅[如何修改业务流程阻止设置](../core/how-to-modify-orchestration-throttling-settings.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用设置仪表板进行 BizTalk Server 性能调整](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)