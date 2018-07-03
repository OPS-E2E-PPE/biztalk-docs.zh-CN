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
ms.openlocfilehash: 129a0d16100ed7f38f49d0cfa5cc329446c3e72e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997182"
---
# <a name="interfaces-for-an-isolated-receive-adapter"></a>接口独立接收适配器
独立接收适配器不是托管在进程空间[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]过程。 独立接收适配器若要与消息引擎进行交互，需要在启动时注册自身，以便引擎可以配置和控制它。 适配器创建传输代理，将查询的接口**IBTTransportProxy**，并调用**IBTTransportProxy.RegisterIsolatedReceiver**注册其**IBTTransportConfig**与消息引擎回调接口。 适配器将提交到其第一条消息之前，会发生此同步调用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 这使消息引擎可以通过回调进入适配器，通知适配器哪些终结点是活动的，因而应该侦听上面的传入消息。 独立适配器必须实现以下接口：  
  
- **IBTTransport**  
  
- **IBTTransportConfig**  
  
- **IBaseComponent**  
  
- **IPersistPropertyBag**  
  
  注册适配器需要适配器传递一个已配置并已启用的接收位置。 适配器的主机进程必须是 BizTalk Isolated Host Users 组的成员。 此外，还需查询该适配器以确保它具有正确的类 ID，并且运行在之前为该主机实例配置的计算机上。  
  
  适配器已成功注册了传输代理后，消息引擎将传递的配置信息和其他接收位置回适配器通过调用**负载**方法的**IPersistPropertyBag**接口和**AddReceiveEndpoint**方法**IBTTransportConfig**分别接口。  
  
  当独立接收适配器结束消息的处理并即将终止，它必须调用**TerminateIsolatedReceiver**方法**IBTTransportProxy**接口。  
  
  下图显示创建独立接收适配器时涉及到的对象交互。  
  
  ![](../core/media/ebiz-sdk-devadapter9.gif "ebiz_sdk_devadapter9")  
  初始化独立接收适配器的工作流。  
  
> [!NOTE]
>  我们建议适配器保持跟踪当前执行的请求的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 适配器应该一直阻止**Terminate**方法，直到工作计数归零。 这项工作在接收端，包括尚未发布到所有未完成请求[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 请注意响应消息通常不传送给接收适配器后**Terminate**调用。 一般情况下，适配器调用后**Terminate**方法中，消息引擎不接受请求发布新消息，但要求-响应对的响应消息除外。  
> 
> [!NOTE]
>  一个进程可以作为多个独立适配器实例的宿主，但是只能作为一个适配器的宿主。  
  
## <a name="see-also"></a>请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发接收适配器](../core/developing-a-receive-adapter.md)   
 [实例化和初始化接收适配器](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [接收适配器的进程内的接口](../core/interfaces-for-an-in-process-receive-adapter.md)   
 [接收适配器的支持批的接口](../core/interfaces-for-a-batch-supported-receive-adapter.md)   
 [接收适配器的接口的事务性批处理支持](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)   
 [同步请求-响应接收适配器的接口](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)