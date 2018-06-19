---
title: 清单： 执行每周性能检查 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c36fe78d-1be8-49f2-97ce-b6d0cadffab8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7898702e42253ab1155b0a6e32af3008800db1f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300293"
---
# <a name="checklist-performing-weekly-performance-checks"></a>清单： 执行每周性能检查
本主题列出了以避免性能问题时应遵循周的最佳实践[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。  
  
|步骤|参考|  
|-----------|---------------|  
|将数据库自动增长设置为固定数目|数据库自动增长应设置为固定数量的兆字节为单位，而不是一个百分比，尤其是对于 MessageBox 和跟踪 (DTA) 数据库。 具体取决于你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序和吞吐量、 MessageBox 和跟踪数据库可能会非常大。 如果自动增长设置为百分比，则自动增长可能是非常高。<br />-如果新系统并不明确设定静态大小，然后将文件配置为启用自动增长选项，并指定文件增长等手段中兆字节为单位。 增长增量通常应是不大于 100 MB （适用于大型文件）、 10 MB （适用于中型文件） 或 （适用于小文件） 的 1 MB。 请参阅**附录 B – 建议 BizTalk Server 数据库配置**部分[BizTalk Server 数据库优化白皮书](http://go.microsoft.com/fwlink/p/?LinkID=153594)(http://go.microsoft.com/fwlink/p/?LinkID = 153594) 具有的每个建议的文件大小的表[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。|  
|限制使用 SQL Server 事件探查器监视的事件|使用 SQL Server 事件探查器监视感兴趣的事件。 如果跟踪变得太大，你可以筛选基于所需的信息，以便收集事件数据的一个子集。 监视过多事件会增加服务器和监视进程的开销，并且可能导致跟踪文件或跟踪表变得很大，尤其是当监视进程持续很长时间时。|  
|配置消息批处理，以便提高适配器性能|-最小化适配器由的组合为一个批处理的多个操作的事务的数。<br />-限制基于总批处理，除了邮件计数中的字节数的批次大小。 有关限制的批次大小的详细信息，请参阅[配置批处理提高适配器性能](../technical-guides/configuring-batching-to-improve-adapter-performance.md)。|  
|调整大型消息阈值|若要增加吞吐量，增加大消息阈值，这样就降低了大型进行缓冲的消息数为在映射中磁盘。|  
|调查内存泄漏或 BizTalk Server 过程中的内存不足异常|BizTalk 进程中的内存泄漏可能由于各种原因。 请参阅 Microsoft 知识库文章 918643，[如何进行故障排除内存泄漏或 BizTalk Server 过程中的出现内存不足异常](http://go.microsoft.com/fwlink/p/?LinkId=157212)(http://go.microsoft.com/fwlink/p/?LinkId = 157212) 中可能出现内存泄漏，以及如何修复此错误的方案有关的信息。|  
  
## <a name="see-also"></a>另请参阅  
 [例程性能清单](../technical-guides/routine-performance-checklists.md)   
 [清单： 执行每月性能检查](../technical-guides/checklist-performing-monthly-performance-checks.md)