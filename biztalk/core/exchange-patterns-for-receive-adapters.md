---
title: 交换模式接收适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e505559e-66be-4c32-a2a8-a242cba10000
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0cf8f36bb128d82a6d6b2e143320f89408f26680
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246293"
---
# <a name="exchange-patterns-for-receive-adapters"></a>接收适配器的交换模式
接收适配器从“线路”(wire) 接收数据并以消息的形式将其提交到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 这一提交过程可以是单向的消息交换模式，也可以是双向的交换模式。  
  
## <a name="one-way-submit"></a>单向提交  
 接收适配器要将消息提交到 BizTalk 消息引擎，首先需要创建一个新的 BizTalk 消息。 IBaseMessage 主题中的代码示例显示了此功能是如何实现的。 适配器设置为消息正文的流通常应为只向前移动的流，这意味着它不应该缓存先前读入内存的数据。  
  
 适配器将消息提交到引擎之前，它必须编写**InboundTransportLocation**消息到 BizTalk 消息的系统命名空间中的上下文属性。 以下代码段说明了这一点：  
  
 `Assembly References:`  
  
 `Microsoft.XLANGs.BaseTypes.dll`  
  
 `Microsoft.BizTalk.Pipeline.dll`  
  
 `Microsoft.BizTalk.GlobalPropertySchemas.dll`  
  
```  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.XLANGs.BaseTypes;  
  
private static readonly PropertyBase InboundTransportLocationProp =   
new BTS.InboundTransportLocation();  
  
private void StampMsgCtxProps(  
IBaseMessage msg, string uri, string adapterType)  
{  
msg.Context.Write(  
 InboundTransportLocationProp.Name.Name,   
 InboundTransportLocationProperty.Name.Namespace,   
  uri);  
}  
```  
  
 此外，适配器可以定义自己的属性架构，并写入与接收消息的终结点相关的消息上下文属性。 例如，HTTP 适配器能够将 HTTP 标头写入消息上下文中，SMTP 接收器能够将邮件的主题写入消息上下文中。 这些信息对于像管道组件、业务流程调度或发送适配器这样的下游组件可能很有用。  
  
 消息准备好后，可以提交到消息引擎。 若要查看如何单向接收适配器可能引擎提交消息，请参阅代码示例[SubmitDirect （BizTalk Server 示例）](../core/submitdirect-biztalk-server-sample.md)。  
  
## <a name="request-response"></a>请求-响应  
 双向接收适配器通常应用于单向或双向接收端口。 适配器确定它所服务的接收位置是否为单向或双向端口通过检查[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置属性包。 中介绍了此过程**IBTTransportConfig.AddReceiveEndpoint 方法 (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
 下面的对象交互图说明了执行请求-响应消息交换的过程。 适配器从传输代理请求一个新的批处理，并通过中对其引用**IBTTransmitter**接口通过**SubmitRequestMessage**方法。 The Messaging Engine 提供此接口上的响应消息通过使用**TransmitMessage**方法。  
  
 由于引擎在异步处理消息，所以可能出现下列情况：  
  
-   **BatchComplete**回调可能会发生之前**完成**已返回。  
  
-   在 BatchComplete 之前，甚至在 Done 之前，可能会发生 TransmitMessage 调用。  
  
 尽管这两种情况都很少见，但适配器应该能够针对其进行自我保护。  
  
 建议使用异步非阻止调用来传输响应消息。  
  
 BaseAdapter 项目具有一个实用工具类， **StandardRequestResponseHandler**，封装此主题中所述的请求-响应语义。  
  
## <a name="request-response-message-time-outs"></a>请求-响应消息超时  
 当适配器提交请求请求消息时，它必须在指定的请求消息的超时**IBTTransportBatch.SubmitRequestMessage 方法 (COM)** API [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 仅在超时期内将响应消息传送到适配器。 超时期过后，向适配器传递的是否定确认 (NACK)，而非响应消息。 如果适配器没有指定超时值，引擎则使用 20 分钟的默认值。  
  
 为进程内接收适配器使用下列注册表项可以控制请求-响应消息的默认超时值：  
  
 **DWORD**  
  
 **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc {主机 Guid} \MessagingReqRespTTL**  
  
 独立的接收适配器的注册表项在另外一个位置：  
  
 **DWORD**  
  
 **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\MessagingReqRespTTL**  
  
 NACK（否定确认）是 SOAP 错误，可以用两种方法对其进行处理。 适配器通常将 NACK 返回给客户端，由客户端处理 NACK。 或者，可以使用映射或自定义管道组件来配置处理响应消息的传输管道，使其更改响应消息的内容。