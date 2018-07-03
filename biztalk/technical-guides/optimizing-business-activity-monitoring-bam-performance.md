---
title: 优化业务活动监视 (BAM) 性能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9ed29b2-0be6-4a37-be68-9476832fd49f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f28771f2611a8b5f7c2522b7cd45e875897645e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996198"
---
# <a name="optimizing-business-activity-monitoring-bam-performance"></a>优化业务活动监视 (BAM) 性能
本主题介绍了业务活动监视 (BAM) 的性能因素。  
  
## <a name="bam-disk-usage-configuration"></a>BAM 磁盘使用情况配置  
 如果在负载下的大量数据保存到 BAM 数据库的原因是 BizTalk 系统，BAM 会产生很大的开销。 因此，明智地使用 BAM 数据库的磁盘 I/O 技术是非常重要。  
  
## <a name="bam-eventstream-apis"></a>BAM EventStream Api  
 四种类型的 EventStreams 是可用于在 BizTalk BAM 方案中使用：  
  
- DirectEventStream (DES)  
  
- BufferedEventStream (BES)  
  
- OrchestrationEventStream (OES)  
  
- MessageEventStream (MES)  
  
  应选择一种基于以下因素这些 Api:  
  
- 如果关心延迟问题，请选择 DES，可使数据同步地保留到 BAM 主导入数据库。  
  
- 如果您关注的问题的性能和事件插入的吞吐量，请选择异步 API （BES、 OES 或 MES）。  
  
- 如果你正在编写不具有的计算机运行的应用程序安装 BizTalk Server，请使用 DES 和 BES;可以在非 BizTalk 应用程序中使用这些 Api。  
  
  > [!NOTE]  
  >  在有些情况下，您可能需要混合使用 EventStream 类型。 例如，为管道处理，您可能想要捕获特定数据在 BAM 中的，而不考虑是否管道正在回滚其事务。 具体而言，您可能希望捕获有关失败的消息数的数据或管道处理过程中出现多少次重试。 若要在这种情况下捕获数据，应使用 BES。  
  
- 如果您的应用程序运行在安装了 BizTalk Server 的计算机上，请使用 MES 和 OES。 （这些 API 只在 BizTalk 应用程序中可用。）  
  
  > [!NOTE]  
  >  OES 等效于 MES，但对 BizTalk 业务流程除外。  
  
- 如果您希望 BAM 事件持久化与管道事务保持同步，则应使用消息传送事件 Stream (MES)。  
  
  所有异步 EventStreams （BES、 MES 和 OES） 首次保存到 BizTalk MessageBox 数据库的数据。 跟踪数据解码服务 (TDDS) 会定期处理这些数据，并将其持久化到 BAM 主导入数据库。  
  
  有关 BAM EventStream Api 的详细信息，请参阅[EventStream 类](http://go.microsoft.com/fwlink/?LinkId=158046)(http://go.microsoft.com/fwlink/?LinkId=158046) BizTalk Server 文档中。  
  
## <a name="bam-performance-counters"></a>BAM 性能计数器  
 有关 BAM 的性能计数器的详细列表，请参阅[BAM 性能计数器](http://go.microsoft.com/fwlink/?LinkId=158048)(http://go.microsoft.com/fwlink/?LinkId=158048) BizTalk Server 文档中。  
  
## <a name="see-also"></a>请参阅  
 [优化 BizTalk Server 性能](../technical-guides/optimizing-biztalk-server-performance.md)