---
title: 实例化隔离的适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b8359a3-b098-4bb6-87b4-d3432d2671b1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e3090252f63221547604a4fdf88388bcbf8296f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257485"
---
# <a name="instantiating-isolated-adapters"></a>实例化隔离的适配器
如前面所述，由 BizTalk Server 未实例化隔离的适配器。 而是在另一个进程中实例化并以此进程为宿主。 负责创建其传输代理的适配器**QueryInterface**，为**IBTTransportProxy**，然后调用**IBTTransportProxy**。**RegisterIsolatedReceiver**注册消息引擎。  
  
 重新注册需要其配置和启用的适配器传递一个接收到消息引擎的位置。 适配器的主机进程凭据必须是 BizTalk 隔离主机用户组的成员。 只需使用模拟此处是不够的除非用户是该组的成员。 此外，该适配器将查询以确保它具有正确**ClassID**并且为该主机实例已配置的计算机上运行。 适配器已成功向其传输代理注册后，将其配置发送给它使用通过调用的 Load 方法**IPersistPropertyBag**接口。  
  
 下图说明了这一序列的 API 调用。 以蓝色表示接口实现的适配器。  
  
 ![](../core/media/isolated-adapter-init.gif "Isolated_adapter_init")  
  
 下面的代码片段阐释了注册 API 调用：  
  
```  
using Microsoft.BizTalk.TransportProxy.Interop;  
using Microsoft.BizTalk.Component.Interop;  
using Microsoft.BizTalk.Message.Interop;  
  
public class MyAdapter : IBTTransport,   
 IBTTransportConfig,   
 IBTTransportControl,   
 IBaseComponent  
{  
...  
private IBTTransportProxy transportProxy;  
  
 public void Register(string uri)  
 {  
 // Create the Transport Proxy...  
 this.transportProxy =   
 (IBTTransportProxy)new BTTransportProxy();  
  
// Register on of the adapters uri’s with the TP  
 this.transportProxy.RegisterIsolatedReceiver(  
 uri,   
 (IBTTransportConfig)this );  
 }  
}  
```  
  
 **实现提示：** 建议适配器保留工作正在进行的计数。 适配器应阻止**终止**直到消息计数已达到零。 在接收端此工作包括尚未发布到 BizTalk Server 任何未完成的请求。 响应消息还未发送到接收适配器后**终止**已调用。  
  
 对于发送适配器，应适当地处理正在进行的消息。 这意味着应从要阻止不止一次发送消息的适配器的私有应用程序消息队列中删除已成功传递的任何消息。  
  
 后**终止**称为 the Messaging Engine 不接受请求以发布新消息，但对于请求-响应对响应消息除外。