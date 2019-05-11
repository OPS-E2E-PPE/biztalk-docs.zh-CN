---
title: 实例化独立的适配器 |Microsoft Docs
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
ms.openlocfilehash: 89f534ab91f940a179c765fba6f109a9da6df5ae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331835"
---
# <a name="instantiating-isolated-adapters"></a>实例化独立的适配器
如前面所述，独立的适配器是通过 BizTalk Server 未实例化。 相反，它们是实例化，在另一个进程中托管。 若要创建其传输代理的适配器负责**QueryInterface**，对于**IBTTransportProxy**，然后调用**IBTTransportProxy**。**RegisterIsolatedReceiver**向消息引擎注册。  
  
 注册需要适配器传递一个其配置和启用的接收到消息引擎的位置。 适配器的主机进程凭据必须是 BizTalk Isolated Host Users 组的成员。 只需在此处使用模拟是不够的除非用户是该组的成员。 此外，查询该适配器以确保它具有正确**ClassID**和已配置为该主机实例的计算机上运行。 向其传输代理，该适配器已成功注册后，将其配置发送给它使用通过调用 Load 方法**IPersistPropertyBag**接口。  
  
 下图说明了这一序列的 API 调用。 蓝色的接口由适配器实现。  
  
 ![](../core/media/isolated-adapter-init.gif "Isolated_adapter_init")  
  
 下面的代码段演示如何注册 API 调用：  
  
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
  
 **实现提示：** 我们建议适配器对正在进行的工作的计数。 适配器应该一直阻止**Terminate**直到消息计数归零。 在接收端这项工作包括尚未发布到 BizTalk Server 的任何未完成请求。 响应消息不传送给接收适配器后**Terminate**已调用。  
  
 对于发送适配器，应适当地处理正在进行中的消息。 这意味着应从要阻止消息多次发送适配器的专用应用程序消息队列中删除已成功传递任何消息。  
  
 之后**Terminate**调用消息引擎不接受请求发布新消息，但要求-响应对的响应消息除外。