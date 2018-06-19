---
title: 业务流程冻结性能计数器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ab92e0e-6a33-4aaa-ab14-0c82322b04d5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e81052f0061ff4ad802a084536c09d48cb6cb55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263781"
---
# <a name="orchestration-dehydration-performance-counters"></a>业务流程冻结性能计数器
下表列出了专门用于监视冻结行为的业务流程引擎性能计数器的名称。 使用性能监视器可以在优化冻结参数的过程中查看这些计数器。  
  
|冻结性能计数器|Description|  
|-------------------------------------|-----------------|  
|Dehydratable orchestrations|当前以主机实例为宿主的能够冻结的业务流程实例数。|  
|Dehydrating orchestrations|正在冻结的业务流程数。|  
|Dehydration cycle in progress|指示当前是否存在正在进行的冻结周期。|  
|Dehydration cycles|已完成的冻结周期数。|  
|Dehydration threshold|确定是否主动冻结业务流程的时间长度（以毫秒计）。 如果业务流程引擎预测某个实例可以冻结一段时间，而且这段时间的长度大于此阈值，则它将冻结该实例。|  
|Orchestrations dehydrated|自从主机实例启动以来，冻结的业务流程实例的数量。|  
|Orchestrations dehydrated/sec|平均每秒冻结的业务流程数。|  
|Orchestrations rehydrated|自从主机实例启动以来，解除冻结的业务流程实例的数量。|  
|Orchestrations rehydrated/sec|平均每秒解除冻结的业务流程数|  
|Orchestrations scheduled for dehydration|冻结请求处于挂起状态的可冻结业务流程的数量。|