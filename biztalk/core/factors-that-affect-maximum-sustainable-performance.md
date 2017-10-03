---
title: "影响最大可持续性能因素 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maximum sustainable throughput (MST), maintenance
- monitoring, maximum sustainable thoughput (MST)
- maintaining, maximum sustainable thoughput (MST)
- maximum sustainable throughput (MST), monitoring
- maximum sustainable throughput (MST), load patterns
- maximum sustainable throughput (MST), sustainable load test
- sustainable performance
ms.assetid: 99b99655-bc77-425c-a133-204781d7c430
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be96ad552abef66e2a401e334da1c27ee0e08cd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="factors-that-affect-maximum-sustainable-performance"></a>影响最大可持续性能因素
最大可承受吞吐量受一系列众多的因素（例如，可用服务器资源、解决方案中使用的功能类型、消息大小以及总体消息负载）直接影响。 还有其他因素需要考虑，尽管这些因素可能目前还不明显。 估计最大可持续性能时，还应考虑以下因素：  
  
## <a name="load-patterns"></a>负载模式  
 消息通常不会以可预测的一致速率传入生产 BizTalk Server 环境中。 更常见的情况是，业务要求 BizTalk Server 以展现出峰值和低谷的可变速率来处理消息。 出现峰值时，BizTalk Server 的处理要求可能会从可忽略的情况迅速跳至消息接收速度超过其处理速度的过载情况。 在此方案中，已发布的消息将积压在 MessageBox 数据库中，直到 BizTalk 将这些积压的消息传递给相应的订户。 只要 BizTalk Server 能够处理在峰值负载周期之间累积的消息积压，则这样将不会出现问题。  
  
 由于通常情况下消息以可变模式传入 BizTalk Server 环境中，因此应当在较长的时间段内运行测试方案，以确保该解决方案能够无限维持所需的吞吐量，从而可随时间的变化从所有峰值负载中恢复。  
  
## <a name="monitoring-and-maintenance-activities"></a>监视和维护活动  
 在生产解决方案的生命期内，存在一个可以影响 BizTalk 性能的监视和维护活动主机，因此在所有测试方案中都应考虑到该主机。 这些活动包括：  
  
-   **BizTalk 管理控制台查询**这些查询消耗资源，并会影响总体吞吐量根据的类型和查询的频率。  
  
-   **备份、 存档和清除活动**这些活动也消耗资源，应考虑任何测试的方案。 应当定期备份所有的 BizTalk Server 数据库并截断其事务日志。 如果不执行此操作，则事务日志可能会不受限制地增长，并占用该事务数据库的所有可用磁盘空间。 如果正在使用跟踪，则必须定期清除跟踪数据库并将其存档（可选），以避免该数据库增长过大。 有关维护 BizTalk Server 数据库的详细信息，请参阅[Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md)。  
  
## <a name="see-also"></a>另请参阅  
 [测量的最大可持续跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)