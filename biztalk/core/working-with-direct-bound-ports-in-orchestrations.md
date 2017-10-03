---
title: "使用在业务流程中的直接绑定端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03a37ac0-5131-4d37-b60b-56763c460463
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e7b2b59ccdaa23271ee0707f19f4fd2cddc0508
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="working-with-direct-bound-ports-in-orchestrations"></a>在业务流程中使用直接绑定端口
有三种类型的直接绑定的端口： MessageBox，自相关，和合作伙伴业务流程。  
  
 MessageBox 直接绑定端口允许发布-订阅设计模式。 MessageBox 直接绑定端口发送的消息被发布到 MessageBox 数据库，消息接收方根据订阅从 MessageBox 数据库提取消息。 配置为 MessageBox 直接绑定端口的逻辑接收端口直接从 MessageBox 数据库获得消息。 激活**接收**形状，MessageBox 直接绑定接收端口 get 通过订阅到消息类型和筛选器表达式的消息。 非激活**接收**形状，MessageBox 直接绑定接收端口 get 通过订阅到消息类型和关联集的消息。  
  
 自相关直接绑定端口可以帮助您设计异步业务流程间通信。 发送到自相关直接绑定端口的消息被路由到创建自相关直接绑定端口接收端的业务流程实例。  
  
 合作伙伴业务流程直接绑定端口提供业务流程间通信。 合作伙伴业务流程直接绑定端口发送的消息可以发送到预期的接收方业务流程，合作伙伴业务流程直接绑定端口接收的消息可以从预期的发送方业务流程接收。  
  
 尽管使用了直接绑定（即消息似乎直接从一个业务流程转到另一个业务流程），实际上通过任何类型的逻辑端口发送的所有消息始终都经过 MessageBox 数据库。 另外，直接绑定端口只是逻辑端口，因此直接绑定只是设计时的配置功能。 直接绑定端口无法绑定到物理端口，您只能在设计时更改直接绑定配置。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何直接使用 MessageBox 绑定端口](../core/how-to-use-messagebox-direct-bound-ports.md)  
  
-   [如何使用自关联 Direct 绑定端口](../core/how-to-use-self-correlating-direct-bound-ports.md)  
  
-   [如何直接使用合作伙伴业务流程绑定端口](../core/how-to-use-partner-orchestration-direct-bound-ports.md)  
  
## <a name="see-also"></a>另请参阅  
 [端口绑定](../core/port-bindings.md)