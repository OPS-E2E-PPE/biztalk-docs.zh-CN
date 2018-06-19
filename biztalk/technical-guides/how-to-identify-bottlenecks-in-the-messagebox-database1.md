---
title: 如何确定 MessageBox Database1 中的瓶颈 |Microsoft 文档
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
ms.openlocfilehash: b25a575f8cd6a3f7d7239ce20cb4d3befdde1966
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297653"
---
# <a name="how-to-identify-bottlenecks-in-the-messagebox-database"></a>如何找出 MessageBox 数据库的瓶颈
若要找出 MessageBox 数据库的瓶颈，首先要确保 SQL Server 代理服务已启动。 将服务启动状态从手动更改为自动以便重新启动服务器时，如果该服务将自动重新启动。  
  
 默认情况下，BizTalk 服务将限制假脱机、 TrackingData 或 ApplicationQ 表增长。 这些表被修剪，如果未运行，则将导致假脱机增长导致限制到开始和的额外压力从保护数据库的 SQL 代理作业。 检查下列性能计数器的状态：  
  
-   BizTalk:Message Agent (Host Name) Message Delivery Throttling State  
  
-   BizTalk:Message Agent (Host Name) Message Publishing Throttling State  
  
 值为"0"指示在无限制。 "6"的值指示系统限制由于数据库增长。 有关如何解释这些计数器的值的信息，请参阅[主机限制是什么？](http://go.microsoft.com/fwlink/?LinkID=154694) (http://go.microsoft.com/fwlink/?LinkID=154694) 和[主机限制性能计数器](http://go.microsoft.com/fwlink/?LinkID=155285)(http://go.microsoft.com/fwlink/?LinkID=155285) BizTalk Server 2010 文档中。  
  
## <a name="spool-table-growth"></a>假脱机表增长  
 导致 Spool 增长的原因有多种。 假脱机增长的原因之一是应用程序队列都在增长。 它们会变得非常如下游瓶颈和/或资源争用的原因。  
  
 如果应用程序队列都是小且仍然较大假脱机，验证清除作业将保持同步。 请确保 SQL 代理服务正在运行，然后验证下列作业是否成功完成：  
  
-   MessageBox_Message_Cleanup_BizTalkMessageBoxDb  
  
-   MessageBox_Parts_Cleanup_BizTalkMessageBoxDb  
  
 如果 MessageZeroSum 表较大，它指示消息已处理。 这意味着取消排队已成功完成，并且从应用程序队列表中删除数据和行已标记为删除。 但清除作业不能及时删除数据。 可能的原因是运行 SQL Server 的计算机遇到严重的 CPU 争用现象，影响清除作业由于 CPU 资源不足而保持同步。  
  
## <a name="application-queue-table-growth"></a>应用程序队列表增长  
 队列的应用程序承载，一次处理，取消排队的清理正在进行的转换数据。  
  
 在处理这些消息之后，可以清除假脱机表 （保留对这些行的引用）。  
  
 例如，RxHostQ 将数据发布到 orchestration PxHostQ。 此队列将数据发布到发送 TxHostQ 每个引用假脱机表中的行。 通过系统已成功处理的消息的特定 HostQ 后，通过取消排队删除这些行。 删除这些行后，清除作业就可以清理 Spool（已不再被这些行引用）了。  
  
 应用程序队列增长指示主机实例负责排出应用程序队列是无法跟上的传入速率。  
  
 例如，由于负责处理业务流程的服务器争夺不到更多的 CPU 资源而无法加快处理速度，这就会导致业务流程应用程序队列 (PxHostQ) 增长。 但是，如果接收的服务器的速度快，它可能可以快于 orchestration 服务器可以处理应用程序队列增长到的前导发布。  
  
 业务流程队列增长的另一个原因可能是由于内存争用。 很多长时间运行的业务流程实例同时实例化时在内存中，内存膨胀间接导致限制，以收缩线程池，直到内存压力得到缓解。  
  
 为什么发送应用程序队列可能增长的原因是如果下游系统将无法接收消息 （从 BizTalk Server 传出） 足够快的速度。 因此，消息将继续驻留在 BizTalk 系统导致应用程序队列增长。 这可能导致限制，以启动并减少影响系统的整体吞吐量的接收速率。  
  
## <a name="trackingdata-table-growth"></a>TrackingData 表增长  
 MessageBox 数据库中的 TrackingData 表是拦截器向其中写入运行状况和活动 (HAT) 以及业务活动监视 (BAM) 跟踪的跟踪数据的转换表。 如果禁用跟踪，则此表将为空。 默认情况下，HAT 跟踪被启用的管道和业务流程输入/输出事件。  
  
 如果启用了邮件正文跟踪，请确保 MessageBox 数据库服务器 （即，带有"允许主机跟踪"的主机） 正在运行。 确保运行带有"允许主机跟踪"的主机将减少瓶颈发生如主机将数据从 MessageBox 数据库中的 TrackingData 表移动到 BizTalk 跟踪数据库表的可能性。  
  
 它可以通过启用自定义的 HAT 跟踪，例如跟踪自定义事件，在提升的属性和跟踪的消息正文。 除了 HAT 跟踪数据，BAM 数据也会写入到 TrackingData 表。 跟踪数据解码服务 (TDDS，在其启用跟踪的主机实例上运行) 负责将此数据从 MessageBox 数据库移到 BizTalk 跟踪和 BAM 主导入数据库。 然后成功地移动数据之后，TDDS 中删除此数据。 消息正文跟踪数据另由 SQL 代理作业 TrackedMessages_Copy_BizTalkMsgBoxDb 来移动。  
  
 如果无法跟上从该处拦截器将数据写入到 TrackingData 表的速率 TDDS，此表将会增长，导致限制，以启动。 这会影响可持续吞吐量。 若要降低此问题，请确保至少一个主机运行启用了跟踪。  
  
 如果数据仍可以建立，请确保出控件不增长 BizTalk 跟踪数据库。 此外，请确保存档和清除作业正在运行并且能够跟不上的传入数据的速率。  
  
> [!NOTE]  
>  默认情况下，清除作业是无法从 BizTalk 跟踪数据库表中删除数据，直到已存档此数据。 如果不需要存档的跟踪数据，则可以修改作业而无需在步骤存档清除 BizTalk 跟踪数据库[如何清除数据从 BizTalk 跟踪数据库](http://go.microsoft.com/fwlink/?LinkID=153817)(http://go.microsoft.com/fwlink /？LinkID = 153817)。  
  
## <a name="see-also"></a>另请参阅  
 [数据库层中的瓶颈](../technical-guides/bottlenecks-in-the-database-tier.md)