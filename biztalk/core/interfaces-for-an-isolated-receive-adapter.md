---
title: 接收适配器的接口独立 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c6b195e-76bf-4c3e-a324-5513bc24fed1
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d0db026534a15b1c1e3cfe2f5582db8b9e1078f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331492"
---
# <a name="interfaces-for-an-isolated-receive-adapter"></a>接口独立接收适配器
独立接收适配器不是托管在进程空间[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]过程。 若要与消息引擎进行交互，独立接收适配器寄存器本身上启动，以便引擎可以配置并对其进行控制。 适配器创建传输代理，将查询的接口**IBTTransportProxy**，并调用**IBTTransportProxy.RegisterIsolatedReceiver**注册其**IBTTransportConfig**与消息引擎回调接口。 适配器将提交到其第一条消息之前，会发生此同步调用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 这样，消息引擎回调适配器，并告知它哪些终结点处于活动状态，以及应该上侦听传入消息的。 独立的适配器必须实现以下接口：  
  
- **IBTTransport**  
  
- **IBTTransportConfig**  
  
- **IBaseComponent**  
  
- **IPersistPropertyBag**  
  
  注册适配器需要适配器传递一个已配置并启用接收位置。 适配器的主机进程必须是 BizTalk Isolated Host Users 组的成员。 此外，查询该适配器以确保它具有正确的类 ID，并且已配置为该主机实例的计算机上运行。  
  
  适配器已成功注册了传输代理后，消息引擎将传递的配置信息和其他接收位置回适配器通过调用**负载**方法的**IPersistPropertyBag**接口和**AddReceiveEndpoint**方法**IBTTransportConfig**分别接口。  
  
  当独立接收适配器结束消息的处理并即将终止，它必须调用**TerminateIsolatedReceiver**方法**IBTTransportProxy**接口。  
  
  下图显示了接收适配器创建独立所涉及的对象交互。  
  
  ![](../core/media/ebiz-sdk-devadapter9.gif "ebiz_sdk_devadapter9")  
  工作流初始化独立接收适配器。  
  
> [!NOTE]
>  我们建议适配器保持跟踪当前执行的请求的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 适配器应该一直阻止**Terminate**方法，直到工作计数归零。 这项工作在接收端，包括尚未发布到所有未完成请求[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 请注意响应消息通常不传送给接收适配器后**Terminate**调用。 一般情况下，适配器调用后**Terminate**方法中，消息引擎不接受请求发布新消息，但要求-响应对的响应消息除外。  
> 
> [!NOTE]
>  一个进程可以作为宿主独立适配器的多个的实例，而只有一个进程可以作为一个适配器的宿主。  
  
## <a name="see-also"></a>请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发接收适配器](../core/developing-a-receive-adapter.md)   
 [实例化和初始化接收适配器](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [接收适配器的进程内的接口](../core/interfaces-for-an-in-process-receive-adapter.md)   
 [接收适配器的支持批的接口](../core/interfaces-for-a-batch-supported-receive-adapter.md)   
 [接收适配器的接口的事务性批处理支持](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)   
 [同步请求-响应接收适配器的接口](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)