---
title: "如何修改主机设置 |Microsoft 文档"
description: "更改在 BizTalk Server 管理来提高性能和限制 BizTalk 主机设置"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0759b3a0-560e-4a11-92e6-9de0e15f463b
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 998c668bf787c9db260597c3a350e0e571492212
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="update-biztalk-host-settings"></a>更新 BizTalk 主机设置

## <a name="overview"></a>概述
使用设置仪表板，您可以修改整个 BizTalk 组中给定主机的配置信息。 本主题提供了用于修改 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中主机级别性能设置的分步过程。  
  
> [!NOTE]
>  您还可以修改组和主机实例设置。 有关如何修改设置的信息，请参阅[BizTalk Server 性能优化使用设置仪表板](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)。  
  
 可以将当前的 BizTalk Server 设置导出到 XML 文件。 然后，将这些设置导入到“设置仪表板”，而不是设置新值。 有关导入信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]设置，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)和[导入或导出 BizTalk 设置使用 BTSTask](how-to-import-biztalk-settings-using-btstask.md)。 
  
## <a name="prerequisites"></a>先决条件  
 若要执行此操作，你必须作为 BizTalk Server Administrators 组的成员身份登录。  
  
## <a name="update-the-host-level-settings"></a>更新主机级别设置  
  
1.  在**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。  
  
2.  在**BizTalk 设置仪表板**对话框中，在**主机**页上，执行一个或多个以下。  
  
    -   修改 BizTalk 主机的常规性能设置。 请参阅[如何修改常规设置](../core/how-to-modify-general-settings.md)。  
  
    -   修改 BizTalk 主机基于资源的阻止设置。 请参阅[如何修改资源基于限制设置](../core/how-to-modify-resource-based-throttling-settings.md)。  
  
    -   修改基于速率限制设置的 BizTalk 主机。 请参阅[如何修改速率基于限制设置](../core/how-to-modify-rate-based-throttling-settings.md)。  
  
    -   修改 BizTalk 主机的业务流程阻止设置。 请参阅[如何修改限制设置的业务流程](../core/how-to-modify-orchestration-throttling-settings.md)。  
  
## <a name="see-also"></a>另请参阅  
 [设置仪表板用于 BizTalk Server 性能优化](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)