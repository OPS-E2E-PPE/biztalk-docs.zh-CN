---
title: "优化业务活动监视 (BAM) 性能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c9ed29b2-0be6-4a37-be68-9476832fd49f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83801a4e147b3e1eaf34c5e264d6adecfbdf8f9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-business-activity-monitoring-bam-performance"></a>优化业务活动监视 (BAM) 性能
本主题介绍业务活动监视 (BAM) 性能因素。  
  
## <a name="bam-disk-usage-configuration"></a>BAM 磁盘使用情况配置  
 BAM 会产生很大的开销，如果在负载下的原因重要的持久保存的 BAM 数据库的数据量是 BizTalk 系统。 因此，磁盘 I/O 技术的 BAM 数据库的明智地使用是至关重要的。  
  
## <a name="bam-eventstream-apis"></a>BAM EventStream Api  
 在 BizTalk BAM 方案中使用有四种类型的 EventStreams:  
  
-   DirectEventStream (DES)  
  
-   BufferedEventStream (BES)  
  
-   OrchestrationEventStream (OES)  
  
-   MessageEventStream (MES)  
  
 你应选择一个这些 Api 基于以下因素：  
  
-   如果关心延迟问题，请选择 DES，可使数据同步地保留到 BAM 主导入数据库。  
  
-   如果你的任务是性能和吞吐量的事件插入，选择 （BES、 可或 MES） 的异步 API。  
  
-   如果你正在编写不具有的计算机运行的应用程序安装 BizTalk Server，使用 DES 和 BES;可以在非 BizTalk 应用程序中使用这些 Api。  
  
    > [!NOTE]  
    >  在有些情况下，您可能需要混合使用 EventStream 类型。 例如，对于管道处理，你可能想要捕获 BAM 中而不考虑是否管道正在回滚其事务的特定数据。 具体而言，您可能希望捕获有关失败的消息数的数据或管道处理期间发生多少次重试。 若要在这种情况下捕获数据，应使用 BES。  
  
-   如果您的应用程序运行在安装了 BizTalk Server 的计算机上，请使用 MES 和 OES。 （这些 API 只在 BizTalk 应用程序中可用。）  
  
    > [!NOTE]  
    >  OES 等效于 MES，但对 BizTalk 业务流程除外。  
  
-   如果你想要与管道事务同步的 BAM 事件持久性，则应使用消息传递事件流 (MES)。  
  
 所有异步 EventStreams （BES、 MES 和可） 到 BizTalk MessageBox 数据库第一次保留数据。 跟踪数据解码服务 (TDDS) 会定期处理这些数据，并将其持久化到 BAM 主导入数据库。  
  
 有关 BAM EventStream Api 的详细信息，请参阅[EventStream 类](http://go.microsoft.com/fwlink/?LinkId=158046)(http://go.microsoft.com/fwlink/?LinkId=158046) BizTalk Server 文档中。  
  
## <a name="bam-performance-counters"></a>BAM 性能计数器  
 BAM 的性能计数器的详细列表，请参阅[BAM 性能计数器](http://go.microsoft.com/fwlink/?LinkId=158048)(http://go.microsoft.com/fwlink/?LinkId=158048) BizTalk Server 文档中。  
  
## <a name="see-also"></a>另请参阅  
 [优化 BizTalk Server 性能](../technical-guides/optimizing-biztalk-server-performance.md)