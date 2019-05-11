---
title: 异步业务事件跟踪 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, BAM
- events, tracking [BAM]
- BAM, event tracking
- BAM, performance
ms.assetid: 6d51fadf-b329-4536-9618-d982d9c17882
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: daff76641e9c70cc2860aa1571b86e74d664f66e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358805"
---
# <a name="asynchronous-business-event-tracking"></a>异步业务事件跟踪
异步 (使用`BufferedEventStream`)-此模型提供了显著的性能改进。 这将使用类似的 API 与同步模型中，使用其他构造函数。 而不是将数据推送到主导入数据库，BufferedEventStream 累积以二进制形式的内存中的事件数据，然后将其作为单个表记录插入到临时数据库 (MessageBox)。 事件总线服务读取数据通过 BizTalk MessageBox 数据库中排队，并将其导入到主导入数据库。  
  
 要配置 BAM 进行异步操作，事件总线服务和调用应用程序 （例如业务流程主机） 应该运行在不同计算机上。 这样调用应用程序中，若要消除立即要使用不同的计算机上的 CPU 处理的事件数据。  
  
 这种 BAM 拓扑也是事务一致的。 因为事件总线服务只读取已提交的数据从 MessageBox 数据库，您将无法获得调用应用程序中回滚的事务的 BAM 数据。 已提交的事务的 BAM 数据即可用于查询和聚合与较小的延迟。  
  
 如果出现错误，事件总线服务将重试几次、 使用超时设置、 损坏恢复逻辑等。 如果但是数据格式无效，它最终会接受在特殊表中。 事件日志，以指示这种情况中发生的事件。 此附加的故障点增加了系统管理难度。  
  
 使用代码中的，异步方法是通常只需 DirectEventStream 替换为 BufferedEventStream，并将连接字符串传递给构造函数中，而不是在 BAM 主导入中的消息框。  
  
 使用异步业务事件跟踪在代码中遵循以下准则：  
  
-   始终使用继续符，当活动跨多个应用程序，并且以异步方式向 BAM 发送数据，即使传播到所有组件的 ActivityID。 在这种情况下，唯一字符串 （例如应用程序名称） 前加上使用每个应用程序中的 activityid 各不相同。 这是必需的因为不同的应用程序中的数据可能会到达 BAM 的随机顺序和 BAM 必须管理顺序颠倒的事件，以确保正确的查询和聚合结果。  
  
-   事件监视 （例如 COM + 松散耦合事件或 WMI 事件） 的常规方法不适用于 BAM，因为事件数据是独立于事务。 例如，它可能看起来好像只有一个传入的采购订单的 1000 美元，但将其保存到数据库的尝试失败 10 次时收到了 10 张采购订单总计 $10,000。  
  
## <a name="see-also"></a>请参阅  

 [同步业务事件跟踪](../core/synchronous-business-event-tracking.md)