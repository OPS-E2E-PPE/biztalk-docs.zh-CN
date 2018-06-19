---
title: HTTP 适配器配置属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, properties
- receive locations, adapters
- HTTP adapters, code sample
- HTTP adapters, send ports
- HTTP adapters, receive locations
- send ports, adapters
ms.assetid: 3d4e9d88-ea40-4478-a0cf-77057fadd3b2
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 731f08106c698d50e95c36b8325cc3d92aa0debb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22258653"
---
# <a name="http-adapter-configuration-properties"></a>HTTP 适配器配置属性
下表列出了可为 HTTP 适配器接收位置设置的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|ReturnCorrelationHandle|VT_BOOL|指定在操作成功时，接收位置基于 HTTP 响应向客户端发送的已提交消息的相关标记。|此属性仅对单向接收位置有效。<br /><br /> 有效值为<br /><br /> --1 (true)<br />-0 (false)|无|  
|ResponseContentType|VT_BSTR|指定接收位置发回客户端的 HTTP 响应消息的内容类型。|此属性仅对请求响应接收位置有效。<br /><br /> 最小长度：0<br /><br /> 最大长度：256|默认值为 text/xml。|  
|SuspendFailedRequests|VT_BOOL|指定是否挂起入站处理失败的 HTTP 请求。|有效值为<br /><br /> --1 (true)<br />-0 (false)|值为 0 (false) 表示将放弃失败的请求并向客户端发送错误状态代码（401 或 500）。<br /><br /> 值为 -1 (true) 指示将挂起失败的请求，并且对于单向接收端口，将向客户端发送“已接受”状态代码 (200)，而对于双向接收端口，将向客户端发送“错误”状态代码 (500)。<br /><br /> 默认值为 0 (false)。|  
|UseSSO|VT_BOOL|指定是否使用企业单一登录。|有效值为<br /><br /> --1 (true)<br />-0 (false)|默认值为 0 (false)。|  
|LoopBack|VT_BOOL|指定此位置上接收的请求消息是路由到发送端口，还是路由回此接收位置以作为响应发送。|此属性仅对请求响应接收位置有效。<br /><br /> 有效值为<br /><br /> --1 (true)<br />-0 (false)|默认值为 0 (false)。|  
  
 下面的代码演示使用设置的属性的 XML 字符串的格式：  
  
```  
<CustomProps>  
<ReturnCorrelationHandle vt="11">-1</ReturnCorrelationHandle>  
<ResponseContentType vt="8">text/xml</ResponseContentType>  
<SuspendFailedRequests vt="11">-1</SuspendFailedRequests>  
<UseSSO vt="11">-1</UseSSO>  
<LoopBack vt="11">-1</LoopBack>  
</CustomProps></  
```  
  
 下表列出了可为 HTTP 适配器发送端口设置的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|友好|VT_I4|指定此发送端口的代理服务器端口。|有效值为从 0 到 65535 之间。|如果 UseProxy 设置为 0 (false)，则此属性不需要值。<br /><br /> 默认值为 80。|  
|requestTimeout|VT_I4|以秒为单位指定 HTTP/HTTPS 传输的超时时间。|有效值为从 0 到 MAX_LONG。|如果 HTTP 适配器在此时间内未收到响应，则服务将记录错误并根据重试基础结构重新提交消息。<br /><br /> 如果此属性设置为 0，则 BizTalk 消息引擎将根据请求消息的大小来计算超时值。 如果未提供任何值，则使用处理程序的值。|  
|证书|VT_BSTR|指定用于建立安全套接字层 (SSL) 连接的客户端证书的指纹。|最小长度：0<br /><br /> 最大长度： 59|默认值为空。|  
|AuthenticationScheme|VT_BSTR|指定目标服务器使用的验证类型。|有效值为<br /><br /> 匿名<br />-基本<br />-摘要<br />-Kerberos|默认值为“匿名”。|  
|用户名|VT_BSTR|指定用于目标服务器验证的用户名。|如果 AuthenticationScheme 为“基本”或“摘要”，而且没有使用企业单一登录服务，则需要为此属性输入值。<br /><br /> 最小长度：0<br /><br /> 最大长度：256|无|  
|EnableChunkedEncoding|VT_BOOL|指定使用 Chunked 编码。|如果将 HTTP 发送处理程序配置为“使用代理”，则隐式禁用了 Chunked 编码。<br /><br /> 有效值为<br /><br /> --1 (true)<br />-0 (false)|如果启用此选项，则 HTTP 适配器将使用 HTTP 分块使用 8 kb 的最大的块区大小进行编码。<br /><br /> 默认值为 0 (false)。|  
|UseProxy|VT_BOOL|指定 HTTP 发送处理程序是否使用代理服务器。|有效值为<br /><br /> --1 (true)<br />-0 (false)|默认值为 0 (false)。|  
|ProxyName|VT_BSTR|指定此发送端口的代理服务器地址。|最小长度：0<br /><br /> 最大长度：256|如果 UseProxy 设置为 0 (false)，则此属性不需要值。|  
|UseSSO|VT_BOOL|指定是否使用单一登录检索客户端凭据，以便在目标服务器上进行验证。|有效值为<br /><br /> --1 (true)<br />-0 (false)|默认值为 0 (false)。|  
|密码|VT_NULL|指定用于目标服务器验证的密码。|如果 AuthenticationScheme 为“基本”或“摘要”，而且没有使用企业单一登录服务，则需要为此属性输入值。<br /><br /> 此值在导出绑定文件时始终设置为空。 在将绑定文件导入目标 BizTalk Server 配置前，必须手动在此字段中填充密码。<br /><br /> 最小长度：0<br /><br /> 最大长度：256|如果为此字段提供值，则应在导入绑定文件之前，将此属性的类型设置为 VT_BSTR (vt="8")。|  
|MaxRedirects|VT_I4|指定对发送的消息所允许的最大重定向次数。|有效值为从 0 到 10。|默认值为 5。|  
|ContentType|VT_BSTR|指定请求消息的内容类型。|最小长度：0<br /><br /> 最大长度：256|如果未设置此值，则使用处理程序的值。|  
|ProxyPassword|VT_NULL|指定用于对代理服务器进行验证的用户密码。|此值在导出绑定文件时始终设置为空。 在将绑定文件导入目标 BizTalk Server 配置前，必须手动在此字段中填充密码。<br /><br /> 最小长度：0<br /><br /> 最大长度：256|如果 UseProxy 设置为 0 (false)，则此属性不需要值。|  
|ProxyUsername|VT_BSTR|指定用于对代理服务器进行验证的用户名。|最小长度：0<br /><br /> 最大长度：256|如果 UseProxy 设置为 0 (false)，则此属性不需要值。|  
|UseHandlerSetting|VT_BOOL|指定发送端口配置必须使用为 HTTP 发送处理程序指定的代理设置。|有效值为<br /><br /> --1 (true)<br />-0 (false)|默认值为 -1 (true)。|  
  
 下面的代码演示使用设置的属性的 XML 字符串的格式：  
  
```  
<CustomProps>  
<ProxyPort vt="3">80</ProxyPort>  
<RequestTimeout vt="3">60</RequestTimeout>  
<Certificate vt="8">A7 6D F9 06 5E FC 97 66 75 59 B5 D6 67 0C 84 DC 64 F5 BF B9</Certificate>  
<AuthenticationScheme vt="8">Basic</AuthenticationScheme>  
<Username vt="8">authenticateduser</Username>  
<EnableChunkedEncoding vt="11">-1</EnableChunkedEncoding>  
<UseProxy vt="11">-1</UseProxy>  
<ProxyName vt="8">proxyserver</ProxyName>  
<UseSSO vt="11">0</UseSSO>  
<Password vt="1" />  
<MaxRedirects vt="3">5</MaxRedirects>  
<ContentType vt="8">text/xml</ContentType>  
<ProxyPassword vt="1" />  
<ProxyUsername vt="8">proxyuser</ProxyUsername>  
<UseHandlerSetting vt="11">0</UseHandlerSetting>  
</CustomProps>  
```