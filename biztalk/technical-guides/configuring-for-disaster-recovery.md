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
ms.openlocfilehash: 3899b27324fa00e0b5c630c7be4433f65a917a1b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="configuring-for-disaster-recovery"></a>为灾难恢复配置
BizTalk Server 日志传送功能扩展现有的备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业。 BizTalk Server 日志传送无需手动还原的备份作业，生成的备份集的一系列，并发生系统故障时减少停机时间。 BizTalk Server 日志传送是 BizTalk 灾难恢复过程的关键组件。  
  
> [!NOTE]  
>  每个应用程序团队必须有案可稽的备份和还原进行了补充本主题中提供的概念的灾难恢复计划。 整体计划应该解决整个系统，包括应用程序和操作系统的组件。  
  
 执行灾难恢复操作是非常类似于手动还原到一组新的 BizTalk 组[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库实例。 主要差别在于该 BizTalk Server 日志传送将持续在灾难恢复站点，保存许多手动步骤的日志应用。 因此，仅最后一组日志必须手动恢复时实现日志传送的 BizTalk Server。 否则，上次的完整备份自上次完整备份后跟的所有日志备份将必须手动还原。 BizTalk Server 日志传送减少了工作，此手动过程，加快了还原的灾难恢复站点。  
  
 本部分介绍在生产配置的建议，以便于灾难恢复过程。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [准备灾难恢复站点](../technical-guides/prepare-the-disaster-recovery-site.md)  
  
-   [日志传送用户帐户和角色](../technical-guides/log-shipping-user-accounts-and-roles.md)  
  
-   [配置 BizTalk Server 日志传送](../technical-guides/configuring-biztalk-server-log-shipping.md)  
  
## <a name="see-also"></a>另请参阅  
 [灾难恢复](../technical-guides/disaster-recovery.md)