---
title: 如何找出 MessageBox 数据库 1 的瓶颈 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a039164-5ca6-4cbc-b307-c5d4ae800689
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60a2c736c191bf38fe1b11d42b900f2d10aece8d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400420"
---
# <a name="how-to-identify-bottlenecks-in-the-messagebox-database"></a>如何找出 MessageBox 数据库的瓶颈
若要找出 MessageBox 数据库的瓶颈，首先要确保 SQL Server 代理服务已启动。 将服务的启动状态从手动更改为自动，以便重新启动服务器，如果该服务将自动重新启动。  
  
 默认情况下，BizTalk 服务会限制如果 Spool、 TrackingData 或 ApplicationQ 表增大。 这些表进行削减 SQL 代理作业，其中，如果未在运行将导致后台处理增长导致服务限流，到启动和保护数据库免受更大压力。 检查下列性能计数器的状态：  
  
- BizTalk:Message Agent (Host Name) Message Delivery Throttling State  
  
- BizTalk:Message Agent (Host Name) Message Publishing Throttling State  
  
  "0"表示没有发生限流。 "6"表示由于数据库增长而阻止系统。 有关如何解释这些计数器的值的信息，请参阅[主机限制是什么？](http://go.microsoft.com/fwlink/?LinkID=154694) (http://go.microsoft.com/fwlink/?LinkID=154694)并[主机阻止性能计数器](http://go.microsoft.com/fwlink/?LinkID=155285)(http://go.microsoft.com/fwlink/?LinkID=155285) BizTalk Server 2010 文档中。  
  
## <a name="spool-table-growth"></a>后台处理表的增长  
 导致 Spool 增长的原因有多种。 后台处理增长的原因之一是如果应用程序队列的增长。 其增长可能由于例如下游瓶颈和/或资源争用的原因。  
  
 如果应用程序队列很小，Spool 却很大，请验证够清除作业。 请确保 SQL 代理服务正在运行，然后验证下列作业是否成功完成：  
  
- MessageBox_Message_Cleanup_BizTalkMessageBoxDb  
  
- MessageBox_Parts_Cleanup_BizTalkMessageBoxDb  
  
  如果 MessageZeroSum 表很大，则表示已处理消息。 这意味着，取消排队已成功完成，并且从应用程序队列表中删除数据行已标记为待删除。 但清除作业不能及时删除数据。 如果运行 SQL Server 的计算机遇到严重的 CPU 资源争用，影响清除作业能够跟上由于 CPU 资源不足，则可能发生此问题。  
  
## <a name="application-queue-table-growth"></a>应用程序队列表的增长  
 应用程序队列承载正在进行的转换数据，处理后立即由 DeQueue 清除。  
  
 这些消息经过处理后，可以清理 Spool 表 （存有对这些行的引用）。  
  
 例如，RxHostQ 将数据发布到业务流程 PxHostQ。 此队列将数据发布到发送 txhostq，它们每个引用后台处理表中的行。 通过系统成功处理了特定 HostQ 的消息后，DeQueue 会删除这些行。 删除这些行后，清除作业就可以清理 Spool（已不再被这些行引用）了。  
  
 应用程序队列的增长说明负责排出应用程序队列的主机实例不能跟上传入速率。  
  
 例如，由于负责处理业务流程的服务器争夺不到更多的 CPU 资源而无法加快处理速度，这就会导致业务流程应用程序队列 (PxHostQ) 增长。 但是，如果接收的服务器的速度很快，它可能可以比业务流程服务器可以处理应用程序队列增长导致更快地发布。  
  
 业务流程队列增长的另一个原因可能是由于内存争用。 如果很多长时间运行的业务流程实例同时实例化在内存中，内存膨胀间接导致限流，压缩线程池，直到内存压力得到缓解。  
  
 为什么应用程序发送队列可能增长的原因是下游系统是否无法足够快地接收消息 （从 BizTalk Server 传出）。 因此，消息将持续驻留在 BizTalk 系统导致应用程序队列增长。 这可能导致限制，以从开始并且降低接收速率，影响系统的整体吞吐量。  
  
## <a name="trackingdata-table-growth"></a>TrackingData 表的增长  
 MessageBox 数据库中的 TrackingData 表是侦听器会将运行状况和活动 (HAT) 和业务活动监视 (BAM) 跟踪的跟踪数据写入到其中一个转换表。 如果禁用跟踪，则此表将为空。 默认情况下，HAT 跟踪可用于管道和业务流程输入/输出事件。  
  
 如果启用了消息正文跟踪，请确保正在运行的 MessageBox 数据库服务器 （即，使用"允许主机跟踪"的主机）。 确保运行具有"允许主机跟踪"的主机将减少瓶颈发生，因为主机将数据从 MessageBox 数据库中的 TrackingData 表移至 BizTalk 跟踪数据库表的可能性。  
  
 它可以通过启用自定义 HAT 跟踪，例如跟踪自定义事件，在升级属性和消息正文跟踪。 HAT 跟踪数据，除了 BAM 数据也写入 TrackingData 表。 跟踪数据解码服务 (TDDS，启用了跟踪主机实例上运行) 是负责将此数据从 MessageBox 数据库移至 BizTalk 跟踪和 BAM 主导入数据库。 然后成功地移动数据后，TDDS 将删除此数据。 消息正文跟踪数据另由 SQL 代理作业 TrackedMessages_Copy_BizTalkMsgBoxDb 来移动。  
  
 如果 TDDS 无法跟上的侦听器向 TrackingData 表写入数据的速率，此表将增长，导致服务限流，以启动。 这会影响可承受吞吐量。 若要降低出现此问题，请确保至少一个主机运行启用了跟踪。  
  
 如果数据仍生成，请确保 BizTalk 跟踪数据库不增长失控。 此外，请确保该存档和清除作业正在运行并且能够及时了解的传入数据的速率。  
  
> [!NOTE]  
>  默认情况下，清除作业是无法从 BizTalk 跟踪数据库表中删除数据，直到已存档此数据。 如果不需要存档跟踪数据，则可以修改该作业，而不进行存档的步骤在清除 BizTalk 跟踪数据库[如何从 BizTalk 跟踪数据库中清除数据](http://go.microsoft.com/fwlink/?LinkID=153817)(http://go.microsoft.com/fwlink/?LinkID=153817)。  
  
## <a name="see-also"></a>请参阅  
 [数据库层的瓶颈](../technical-guides/bottlenecks-in-the-database-tier.md)