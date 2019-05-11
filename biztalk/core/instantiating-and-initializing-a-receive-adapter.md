---
title: 实例化和初始化接收适配器 |Microsoft Docs
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
ms.openlocfilehash: 73bb52934483cc47ea45cd0e6ff72e8e57752ffd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331823"
---
# <a name="instantiating-and-initializing-a-receive-adapter"></a>实例化和初始化接收适配器
立即接收适配器实例化后由消息引擎初始化，该引擎将调用为 IBTTransportControl QueryInteraface。 然后，它调用 IBTTransportControl<strong>。初始化</strong>传入适配器的传输代理，该适配器仍然存在的成员变量中。 接下来，引擎将调用**QueryInterface**有关**IPersistPropertyBag**。 这是一个可选的接口;如果适配器实现它，处理程序配置传递给适配器**负载**方法调用。 初始化接收适配器的最后阶段涉及将终结点配置传递到适配器。 在此阶段则引擎将调用**IBTTransportConfig.AddReceiveEndpoint**一次针对每个活动的终结点，在 URI 中传递终结点、 适配器特定配置的终结点，和 BizTalk 配置该终结点。  
  
 下图说明了这一序列的 API 调用。 适配器实现的接口显示为蓝色。  
  
 ![](../core/media/sequence-of-init-calls.gif "Sequence_of_init_calls")  
  
 **实现提示：** 一般情况下，适配器不应阻止消息引擎在调用如**IBTTransportControl.Initialize**， **ipersistpropertybag.load 这样**，和**IBTTransportConfig.AddReceiveEndpoint**。 执行过多的处理中这些调用可以在服务启动时间产生负面影响。  
  
 所有接收适配器具有一个或多个关联接收位置在服务启动时创建。 所有接收适配器是异步的支持批处理。 它们可以是进程内或隔离。 有关其他信息接收适配器变量，请参阅[适配器变量](../core/adapter-variables.md)。