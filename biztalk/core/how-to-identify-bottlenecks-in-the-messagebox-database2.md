---
title: 如何找出 MessageBox 数据库 2 的瓶颈 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10b2eb1e-541c-457d-9735-ac6fb069b209
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffc04f31544a48f0ab25338c95beefaf14d5097c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010622"
---
# <a name="how-to-identify-bottlenecks-in-the-messagebox-database"></a>如何找出 MessageBox 数据库的瓶颈
若要找出 MessageBox 数据库的瓶颈，首先要确保 SQL Server 代理服务已启动。 将服务的启动状态从“手动”改为“自动”，这样即使服务器重新启动了，服务也会自动重新启动。  
  
 默认情况下，如果 Spool、TrackingData 或 ApplicationQ 表增大了，则 BizTalk 服务将会限流。 SQL 代理作业会对这些表进行削减，如果不这样，将会引起 Spool 的增长，从而导致服务限流，以保护数据库免受更大压力。 检查下列性能计数器的状态：  
  
- BizTalk:Message Agent (Host Name) Message Delivery Throttling State  
  
- BizTalk:Message Agent (Host Name) Message Publishing Throttling State  
  
  值“0”表示没有发生限流。 值“6”表示系统由于数据库增长而限流。 有关如何解释这些计数器的其他值的信息，请参考有关文档。  
  
## <a name="spool-table-growth"></a>Spool 表的增长  
 导致 Spool 增长的原因有多种。 其中一个就是应用程序队列的增长。 其增长可能有多种原因，比如下游瓶颈和/或资源争夺。  
  
 如果应用程序队列很小，但 Spool 却很大，请检查清除作业的速度是否够快。 请确保 SQL 代理服务正在运行，然后验证下列作业是否成功完成：  
  
- MessageBox_Message_Cleanup_BizTalkMessageBoxDb  
  
- MessageBox_Parts_Cleanup_BizTalkMessageBoxDb  
  
  如果 MessageZeroSum 表很大，说明消息已经处理完毕（DeQueue 已经成功完成，并已从应用程序队列表中删除了数据），也标记了要删除的行。 但清除作业不能及时删除数据。 导致这种情况的一个原因是，SQL Server 计算机的 CPU 资源争夺很激烈，CPU 资源的紧张影响了清除作业的能力，使其无法及时完成任务。  
  
## <a name="application-queue-table-growth"></a>应用程序队列表的增长  
 应用程序队列中等待处理的转换数据在处理后立即由 DeQueue 清除。  
  
 处理完这些消息后，就可以清理 Spool（存有对这些行的引用）了。  
  
 例如，RxHostQ 将数据发布到业务流程 PxHostQ，PxHostQ 又将这些数据发布到发送 TxHostQ，它们每个都在 Spool 表中引用一行。 系统成功处理完特定 HostQ 的消息后，DeQueue 会删除这些行。 删除这些行后，清除作业就可以清理 Spool（已不再被这些行引用）了。  
  
 应用程序队列的增长说明负责清理应用程序队列的主机实例已经跟不上传入速度了，传入速率是指向特定应用程序发布消息的速率。  
  
 例如，由于负责处理业务流程的服务器争夺不到更多的 CPU 资源而无法加快处理速度，这就会导致业务流程应用程序队列 (PxHostQ) 增长。 此外，如果接收服务器的速度很快，它的发布速度比业务流程服务器的处理速度快，也会导致应用程序队列增长。  
  
 另一个导致业务流程队列增长的原因是内存争用，如果有大量长时间运行的业务流程实例同时实例化到内存中，将会导致内存膨胀，从而间接引发限流，压缩线程池，直到内存压力缓解为止。 导致应用程序发送队列增长的一个原因是下游系统接收消息（从 BizTalk 传出）的速度不够快。 因此，消息将持续驻留在 BizTalk 系统中，导致应用程序队列增长，最终引起系统限流，降低接收速率，影响系统的整体吞吐量。  
  
## <a name="trackingdata-table-growth"></a>TrackingData 表的增长  
 MessageBox 数据库中的 TrackingData 表是一个转换表，侦听器会将消息和服务实例跟踪及 BAM 跟踪的跟踪数据写入该表。 如果禁用跟踪，则此表将为空。 默认情况下，启用了对管道和业务流程输入/输出事件的消息和服务实例跟踪。  
  
 如果启用消息正文跟踪，请确保 MessageBox 服务器（即“允许主机跟踪”的主机）处于运行状态。 它将数据从 MessageBox 数据库的 TrackingData 表移到 BizTalkDTADb 表，从而缓解瓶颈。  
  
 通过启用自定义消息和服务实例跟踪，可以跟踪自定义事件，例如，跟踪升级属性和消息正文跟踪。 除跟踪数据外，BAM 数据也将写入此表。 TDDS（启用跟踪的主机）负责将此数据从 MessageBox 数据库移至 BizTalkDTADb 和 BAMPrimaryImport 数据库，并在移动成功后，删除这些数据。 消息正文跟踪数据另由 SQL 代理作业 TrackedMessages_Copy_BizTalkMsgBoxDb 来移动。  
  
 如果 TDDS 的速度赶不上侦听器向 TrackingData 表写入数据的速度，则此表将增长，从而导致限流，最终影响可承受吞吐量。 若要缓解此问题，请确保启用跟踪时，至少有一台主机处于运行状态。  
  
 如果数据仍在增长，请检查 BizTalkDTADb 数据库，确定该数据库的增长没有失控。 确保归档和清除作业正在运行，并能跟上数据的到达速度。  
  
> [!NOTE]
>  数据归档前，清除作业是无法从 BizTalkDTADb 表删除数据的。  
  
 验证 TrackingData 表没有增长。 请确保至少有一台正在运行的主机实例启用了跟踪 (TDDS)。 如果 BizTalkDTADb 数据库已经增长得非常大，则会对 TDDS 将数据从 MessageBox 数据库移至 BizTalkDTADb 数据库的能力产生负面影响。  
  
 TrackingData 表的增长会导致限流，从而影响可承受的运行时吞吐量。