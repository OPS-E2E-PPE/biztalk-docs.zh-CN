---
title: 使用在业务流程直接绑定端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03a37ac0-5131-4d37-b60b-56763c460463
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3344298fbd569d1e8e3161d6857bddb6fb453aeb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277281"
---
# <a name="working-with-direct-bound-ports-in-orchestrations"></a>使用在业务流程直接绑定端口
有三种类型的直接绑定端口：MessageBox、 自相关，配置文件和合作伙伴业务流程。  
  
 MessageBox 直接绑定的端口允许发布-订阅设计模式。 MessageBox 直接绑定端口上发送的消息发布到 MessageBox 数据库，其中消息收件人中选取它们根据订阅。 逻辑接收端口配置为 MessageBox 直接绑定的端口从 MessageBox 数据库中直接获取消息。 用于激活**接收**形状，MessageBox 直接绑定接收端口获取通过对消息类型和筛选器表达式订阅消息。 对于非激活**接收**形状，MessageBox 直接绑定接收端口获取通过对消息类型和关联集的订阅的消息。  
  
 自相关直接绑定的端口帮助您设计异步业务流程间通信。 发送到自相关直接绑定端口的消息被路由到创建的接收端的自相关直接绑定端口的业务流程的实例。  
  
 合作伙伴业务流程直接绑定的端口提供业务流程间通信。 可以从预期的发送方业务流程接收直接绑定的端口可以发送到预期的接收方业务流程，合作伙伴业务流程上发送的消息和合作伙伴业务流程直接绑定端口上接收到的消息。  
  
 尽管使用了直接绑定消息似乎转直接从一个业务流程到另一个，实际上通过发送任何消息，但是任何类型的逻辑端口始终都经过 MessageBox 数据库。 此外，直接绑定的端口只是逻辑端口，并因此直接绑定仅设计时配置功能。 直接绑定的端口无法绑定到物理端口，并仅可以更改在设计时直接绑定配置。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何使用 MessageBox 直接绑定端口](../core/how-to-use-messagebox-direct-bound-ports.md)  
  
-   [如何使用自相关直接绑定端口](../core/how-to-use-self-correlating-direct-bound-ports.md)  
  
-   [如何使用合作伙伴业务流程直接绑定端口](../core/how-to-use-partner-orchestration-direct-bound-ports.md)  
  
## <a name="see-also"></a>请参阅  
 [端口绑定](../core/port-bindings.md)