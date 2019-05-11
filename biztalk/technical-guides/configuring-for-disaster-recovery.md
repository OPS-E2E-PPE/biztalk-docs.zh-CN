---
title: 配置灾难恢复 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acdafe68-c8bf-4064-afca-6dfd22d15052
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0bce395a5873947d006aa84b620b921a4a8e943
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253552"
---
# <a name="configuring-for-disaster-recovery"></a>配置灾难恢复
BizTalk Server 日志传送功能扩展了现有备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业。 BizTalk Server 日志传送无需手动还原一系列的备份作业，生成的备份集，并可以缩短出现系统故障时的停机时间。 BizTalk Server 日志传送是 BizTalk 灾难恢复过程的关键组件。  
  
> [!NOTE]  
>  每个应用程序团队必须有案可稽的备份和还原提供补充了本主题中提供的概念的灾难恢复计划。 总体计划应该处理整个系统，包括应用程序和操作系统的组件。  
  
 执行灾难恢复操作是非常类似于手动执行到一组新的 BizTalk 组的还原[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库实例。 主要区别在于该 BizTalk Server 日志传送适用持续在灾难恢复站点上，保存多的手动步骤的日志。 因此，仅日志的最后一组必须手动还原时 BizTalk Server 实现日志传送。 否则，自上次完整备份之后进行所有日志备份的最后一个完整备份将需要手动还原。 BizTalk Server 日志传送可减少此手动过程，从而加快的灾难恢复站点还原的工作。  
  
 本部分介绍了生产配置的建议来简化灾难恢复过程。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [准备灾难恢复站点](../technical-guides/prepare-the-disaster-recovery-site.md)  
  
-   [日志传送用户帐户和角色](../technical-guides/log-shipping-user-accounts-and-roles.md)  
  
-   [配置 BizTalk Server 日志传送](../technical-guides/configuring-biztalk-server-log-shipping.md)  
  
## <a name="see-also"></a>请参阅  
 [灾难恢复](../technical-guides/disaster-recovery.md)