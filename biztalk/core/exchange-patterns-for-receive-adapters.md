---
title: 接收适配器的交换模式 |Microsoft Docs
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
ms.openlocfilehash: 856200bbd511f580f8ef58fd0be78ee1fb6718b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388275"
---
# <a name="exchange-patterns-for-receive-adapters"></a>接收适配器的交换模式
接收适配器接收从"网络"的数据，并将其作为消息提交[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 这一提交过程可以是单向或双向消息交换模式。  
  
## <a name="one-way-submit"></a>单向提交  
 接收适配器将消息提交到 BizTalk 消息引擎，它首先需要创建新的 BizTalk 消息。 IBaseMessage 主题中的代码示例演示如何做到这一点。 适配器设置为消息正文的流通常应为只进流，这意味着它不应该缓存先前已读入内存的数据。  
  
 该适配器将消息提交到引擎之前，它必须编写**InboundTransportLocation**消息上下文属性在 BizTalk 消息将系统命名空间中的。 下面的代码段所示：  
  
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
  
 此外，适配器可以定义其自己的属性架构并写入与对其接收消息的终结点相关的消息上下文属性。 例如，HTTP 适配器可能会将 HTTP 标头写入消息上下文，并且 SMTP 接收方可能会将邮件的主题写入消息上下文。 此信息可能非常有用到下游组件，如管道组件、 业务流程调度或发送适配器。  
  
 消息准备好后，它们可以提交到消息引擎。 若要查看如何的单向接收适配器可能会将消息提交到引擎，请参阅代码示例[SubmitDirect （BizTalk Server 示例）](../core/submitdirect-biztalk-server-sample.md)。  
  
## <a name="request-response"></a>请求-响应  
 双向接收适配器通常应用于单向或双向接收端口。 适配器可以确定它所服务的接收位置是否为单向或双向端口通过检查[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置属性包。 此过程所述**IBTTransportConfig.AddReceiveEndpoint 方法 (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
 以下对象交互图说明了执行请求-响应消息交换的过程。 适配器从传输代理请求一个新的批处理，并将传递到它的引用**IBTTransmitter**接口通过**SubmitRequestMessage**方法。 消息引擎通过使用提供此接口上的响应消息**TransmitMessage**方法。  
  
 该引擎以异步方式处理消息，因为很可能出现下列情况：  
  
- **BatchComplete**回调可能会发生之前**完成**已返回。  
  
- TransmitMessage 调用可能会在 BatchComplete 之前所做和甚至之前完成。  
  
  虽然这两个方案都很少见，适配器应保护自身免遭这。  
  
  建议使用异步非阻止调用传输响应消息。  
  
  BaseAdapter 项目有一个实用工具类， **StandardRequestResponseHandler**，它封装了本主题中所述的请求-响应语义。  
  
## <a name="request-response-message-time-outs"></a>请求-响应消息超时  
 当适配器提交请求-响应消息时，需要在指定的请求消息的超时值**IBTTransportBatch.SubmitRequestMessage 方法 (COM)** API [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 此超时期间内仅响应消息将传送到适配器。 超时过期后，会将一个否定确认 (NACK) 传递到而不是响应消息的适配器。 如果适配器未指定超时值，引擎将使用默认值 20 分钟。  
  
 请求-响应消息的默认超时值可能会受为进程内接收适配器使用以下注册表项：  
  
 **DWORD**  
  
 **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc{Host Guid}\MessagingReqRespTTL**  
  
 注册表项是在不同的位置，对于独立接收适配器：  
  
 **DWORD**  
  
 **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc.3.0\MessagingReqRespTTL**  
  
 Nack （否定确认） 是 SOAP 错误，有两种方法来处理它们。 通常，适配器将 NACK 返回给客户端和客户端处理 NACK。 或者可能将处理响应消息的传输管道配置为使用映射或自定义管道组件中更改响应消息的内容。