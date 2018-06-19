---
title: 实例化和初始化接收适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5cb5ba7-e2b5-49d2-adf5-a8df0bb81def
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 565712faecf11b728c4f552798b1e3daebf962f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257477"
---
# <a name="instantiating-and-initializing-a-receive-adapter"></a>实例化和初始化接收适配器
立即实例化接收适配器后 the Messaging Engine 会初始化它时，该引擎将调用为 IBTTransportControl QueryInteraface。 然后，它调用 IBTTransportControl **。初始化**传递中的适配器传输代理，该适配器中的成员变量仍然存在。 接下来引擎将调用**QueryInterface**为**IPersistPropertyBag**。 这是一个可选接口;如果适配器实现它，将处理程序配置传递给在适配器**负载**方法调用。 初始化接收适配器的最后一个阶段涉及到适配器传递终结点配置。 在此期间阶段引擎调用**IBTTransportConfig.AddReceiveEndpoint**一次针对每个活动的终结点，在 URI 中传递终结点、 终结点，该适配器特定配置和的 BizTalk 配置该终结点。  
  
 下图说明了这一序列的 API 调用。 适配器实现的接口显示为蓝色。  
  
 ![](../core/media/sequence-of-init-calls.gif "Sequence_of_init_calls")  
  
 **实现提示：** 一般情况下，适配器不应阻止调用中的消息传递引擎如**IBTTransportControl.Initialize**， **IPersistPropertyBag.Load**，和**IBTTransportConfig.AddReceiveEndpoint**。 执行过多的处理中这些调用，就可以在服务启动时间上产生负面影响。  
  
 所有接收适配器拥有一个或多个关联接收位置在服务启动时创建。 所有接收适配器是异步的支持批处理。 它们可以是进程内或独立。 有关其他信息接收适配器变量，请参阅[适配器变量](../core/adapter-variables.md)。