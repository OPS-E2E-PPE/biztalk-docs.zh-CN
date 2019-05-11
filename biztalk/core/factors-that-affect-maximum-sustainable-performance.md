---
title: 影响最大可承受性能的因素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4f14a1915f70856342f61c8c41f5fbb90233205
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345886"
---
# <a name="factors-that-affect-maximum-sustainable-performance"></a>影响最大可承受性能的因素
最大可承受吞吐量直接受各种因素，例如可用服务器资源、 解决方案、 消息大小以及总体消息负载中使用的功能的类型。 还有其他一些因素，但这可能不是明显视为。 在估计最大可承受性能时，还应考虑以下因素：  
  
## <a name="load-patterns"></a>负载模式  
 消息通常流动到生产环境以可预测的一致速率的 BizTalk Server 环境。 更通常情况下，业务需求指示 BizTalk Server 处理消息的可变速率哪些展现出峰值和低谷。 出现峰值时，BizTalk Server 处理要求可能会快速跳从可忽略不计的过载情况超过其处理更快地接收消息。 在此方案中，已发布的消息将积压在 MessageBox 数据库中，直到 BizTalk 将这些积压的消息传递到相应的订户。 只要 BizTalk Server 能够处理的峰值负载周期之间累积，则这不是有问题的消息。  
  
 由于通常变量到 BizTalk Server 环境中的消息流的模式，测试方案应运行的时间，以确保解决方案可以承受所需的吞吐量无限期，从所有峰值负载恢复长时间段时间。  
  
## <a name="monitoring-and-maintenance-activities"></a>监视和维护活动  
 在生产解决方案的生命周期，期间监视的主机并维护活动可能会影响 BizTalk 性能，因此应考虑到所有测试方案。 这些活动包括：  
  
-   **BizTalk 管理控制台查询**这些查询会消耗资源并影响总体吞吐量，具体取决于的类型和查询的频率。  
  
-   **备份、 存档和清除活动**这些活动也会消耗资源并应考虑到所有测试方案。 应定期备份数据库的所有 BizTalk Server 并截断其事务日志。 如果不执行此操作的事务日志可能会不断增长取消选中并占用所有的事务数据库的可用磁盘空间。 如果正在使用跟踪，必须定期清除跟踪数据库和存档 （可选） 以使其变得过大。 有关维护 BizTalk Server 数据库的详细信息，请参阅[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)。  
  
## <a name="see-also"></a>请参阅  
 [测量最大可承受跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)