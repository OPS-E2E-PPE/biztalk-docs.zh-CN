---
title: "异步业务事件跟踪 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance, BAM
- events, tracking [BAM]
- BAM, event tracking
- BAM, performance
ms.assetid: 6d51fadf-b329-4536-9618-d982d9c17882
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7191d9b0be94b4b089a91e78dd526867171c68a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="asynchronous-business-event-tracking"></a>异步业务事件跟踪
异步 (使用`BufferedEventStream`)-此模型提供了显著的性能改进。 此模型使用的 API 与同步模型相似，只是使用不同的构造函数。 BufferedEventStream 不是将数据放入主导入数据库中，而是以二进制形式将事件数据累计在内存中，然后将其作为单个表记录插入到临时数据库 (MessageBox) 中。 事件总线服务读取 MessageBox 数据库中由 BizTalk 排队的数据，将其导入到主导入数据库中。  
  
 要配置 BAM 进行异步操作，事件总线服务和调用应用程序（例如业务流程主机）应该运行在不同的计算机上。 这样，调用应用程序就可以立即清除使用其他计算机上的 CPU 处理的事件数据。  
  
 这种 BAM 拓扑结构也具有事务一致性。 您将无法获得在调用应用程序中回滚的事务的 BAM 数据，因为事件总线服务只读取 MessageBox 数据库中已提交的数据。 已提交的事务的 BAM 数据在一段短时延迟后即可用于查询和聚合。  
  
 如果出现错误，事件总线服务将重试几次、使用超时设置并执行损坏恢复逻辑等。 如果数据的格式无效，它会在特殊表中结束。 事件日志中会生成一个事件以指示此情况。 这种附加的故障点增加了系统管理难度。  
  
 在代码中使用异步方法非常简单，只需将 DirectEventStream 替换为 BufferedEventStream，然后将连接字符串传递到构造函数中的 MessageBox，而不是传递到 BAM 主导入数据库的 MessageBox。  
  
 要在代码中执行异步业务事件跟踪，请遵循以下准则：  
  
-   当活动跨多个应用程序且向 BAM 异步发送数据时，请始终使用继续符，即使将 ActivityID 传播到了所有组件，也应该如此。 在这种情况下，请将唯一字符串（例如应用程序名）作为 ActivityID 的前缀，使每个应用程序中的 ActivityID 各不相同。 这很有必要，因为来自不同应用程序的数据到达 BAM 的顺序可能是随机的，BAM 必须管理顺序颠倒的事件以确保得到正确的查询和聚合结果。  
  
-   事件监视的常规方法（例如 COM+ 松散耦合事件或 WMI 事件）不适用于 BAM，因为这些事件数据与事务无关。 例如，如果只有一个价值 $1000 的传入采购订单，但尝试将其保存到数据库时失败了 10 次，如果采用常规的事件监视方法，会使得该事件看起来好像收到了 10 张采购订单，总计 $10,000。  
  
## <a name="see-also"></a>另请参阅  

 [同步业务事件跟踪](../core/synchronous-business-event-tracking.md)