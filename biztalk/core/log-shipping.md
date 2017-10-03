---
title: "日志传送 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, log shipping
- log shipping
ms.assetid: 25bc9724-1c99-43d0-8cd1-3ed8eaa60268
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bd90e23fc99988bb134a77befe3195ca507037d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="log-shipping"></a>日志传送
日志传送具有备用服务器功能，有时称为热备份，它可以缩短出现系统失败时的停机时间。  
  
 由于的分布式的数据库设计[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，当你生成必须确保提供一个一致的备份到备份可以还原点。 事务可跨越多个数据库，如果一个数据库脱机并且必须还原，则其他相关数据库也必须及时还原到同一时间点，以确保系统处于一致的状态。 分布式事务并不涉及所有数据库。 有关详细信息，请参阅[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-the-biztalk-server-databases.md)。  
  
 备份 BizTalk Server 作业使用 Microsoft SQL Server 日志标记自动生成数据库备份集。 这些备份集包含还原过程中将使用的同步点。 在还原由备份 BizTalk Server 作业生成的数据库集的过程中，利用倒数第二个标记，将每个数据库的最近的日志备份文件还原到某个特定的日志标记。 这使您可将数据库还原到一致的状态，并有效地减少数据丢失量。 建议使用倒数第二个日志标记。 尽管 SQL Server 也具有日志传送功能，但是在备份和还原 BizTalk Server 数据库时，仅应使用 BizTalk Server 的日志传送功能。  
  
> [!NOTE]
>  由于简单恢复模式不会备份事务集，从而不会维护自最近备份以来的活动记录，因此，不支持将 SQL Server 简单恢复模式与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库一起使用。  SQL Server 配置为使用完整恢复模型来确保中数据的完整性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库备份集。  
  
## <a name="see-also"></a>另请参阅  
 [有关备份和还原的高级的信息](../core/advanced-information-about-backup-and-restore1.md)