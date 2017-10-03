---
title: "为灾难恢复配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: acdafe68-c8bf-4064-afca-6dfd22d15052
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8c6a188255097f0a1c1e85086688252f9154b36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-for-disaster-recovery"></a>为灾难恢复配置
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]日志传送功能扩展现有的备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]日志传送无需手动还原的备份作业，生成的备份集的一系列，并发生系统故障时减少停机时间。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]日志传送是 BizTalk 灾难恢复过程的关键组件。  
  
> [!NOTE]  
>  每个应用程序团队必须有案可稽的备份和还原进行了补充本主题中提供的概念的灾难恢复计划。 整体计划应该解决整个系统，包括应用程序和操作系统的组件。  
  
 执行灾难恢复操作是非常类似于手动还原到一组新的 BizTalk 组[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库实例。 主要差别在于，[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]日志传送将持续在灾难恢复站点，保存许多手动步骤的日志应用。 因此，仅最后一组日志必须手动恢复时[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]实现日志传送。 否则，上次的完整备份自上次完整备份后跟的所有日志备份将必须手动还原。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]日志传送减少此手动过程，加快了灾难恢复站点还原了工作。  
  
 本部分介绍在生产配置的建议，以便于灾难恢复过程。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [准备灾难恢复站点](../technical-guides/prepare-the-disaster-recovery-site.md)  
  
-   [日志传送用户帐户和角色](../technical-guides/log-shipping-user-accounts-and-roles.md)  
  
-   [配置 BizTalk Server 日志传送](../technical-guides/configuring-biztalk-server-log-shipping.md)  
  
## <a name="see-also"></a>另请参阅  
 [灾难恢复](../technical-guides/disaster-recovery.md)