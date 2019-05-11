---
title: HTTP 适配器配置属性 |Microsoft Docs
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
ms.openlocfilehash: 2a2388a442923674f9b0eea52ffba1ed09a7b2e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332845"
---
# <a name="http-adapter-configuration-properties"></a>HTTP 适配器配置属性
下表列出了可以设置为 HTTP 适配器的配置属性接收位置：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|ReturnCorrelationHandle|VT_BOOL|指定，是否成功，接收位置提交消息的相关标记上发送到客户端的 HTTP 响应。|此属性才有效仅对单向接收位置。<br /><br /> 有效值为<br /><br /> -   -1 (true)<br />-0 (false)|None|  
|ResponseContentType|VT_BSTR|指定接收位置发回客户端的 HTTP 响应消息的内容类型。|此属性仅对请求响应接收位置有效。<br /><br /> 最小长度：0<br /><br /> 最大长度：256|默认值为 text/xml。|  
|SuspendFailedRequests|VT_BOOL|指定挂起入站的处理失败的 HTTP 请求。|有效值为<br /><br /> -   -1 (true)<br />-0 (false)|值为 0 (false) 表示将放弃失败的请求并向客户端发送错误状态代码 （401 或 500）。<br /><br /> 值-1 (true) 指示挂起失败的请求并发送"已接受"状态代码 (200) 的一种方法适用于客户端为接收端口或"错误"状态代码 (500) 客户端以便双向接收端口。<br /><br /> 默认值为 0 (false)。|  
|UseSSO|VT_BOOL|指定使用是企业单一登录。|有效值为<br /><br /> -   -1 (true)<br />-0 (false)|默认值为 0 (false)。|  
|LoopBack|VT_BOOL|指定此位置上接收的请求消息路由到发送端口或回此接收位置以作为响应发送。|此属性仅对请求响应接收位置有效。<br /><br /> 有效值为<br /><br /> -   -1 (true)<br />-0 (false)|默认值为 0 (false)。|  
  
 下面的代码显示了使用设置的属性的 XML 字符串的格式：  
  
```  
<CustomProps>  
<ReturnCorrelationHandle vt="11">-1</ReturnCorrelationHandle>  
<ResponseContentType vt="8">text/xml</ResponseContentType>  
<SuspendFailedRequests vt="11">-1</SuspendFailedRequests>  
<UseSSO vt="11">-1</UseSSO>  
<LoopBack vt="11">-1</LoopBack>  
</CustomProps></  
```  
  
 下表列出了发送端口可以设置为 HTTP 适配器的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|ProxyPort|VT_I4|指定此发送端口的代理服务器端口。|有效值为从 0 到 65535 之间。|此属性不需要一个值，如果 UseProxy 设置为 0 (false)。<br /><br /> 默认值为 80。|  
|RequestTimeout|VT_I4|指定以秒为单位进行 HTTP/HTTPS 传输的超时值。|有效值为从 0 到 MAX_LONG。|如果 HTTP 适配器在此时间内未收到响应，服务将记录错误并重新提交消息基于重试基础结构。<br /><br /> 如果设置为 0，BizTalk 消息引擎计算超时值根据请求消息的大小。 如果未提供一个值，使用处理程序的值。|  
|证书|VT_BSTR|指定要用于建立安全套接字层 (SSL) 连接的客户端证书的指纹。|最小长度：0<br /><br /> 最大长度：59|默认值为空。|  
|AuthenticationScheme|VT_BSTR|指定要对目标服务器使用身份验证的类型。|有效值为<br /><br /> 匿名<br />-基本<br />-摘要<br />-   Kerberos|默认值为 Anonymous。|  
|用户名|VT_BSTR|指定要用于目标服务器的身份验证的用户名。|此属性需要一个值，如果 AuthenticationScheme 的基本或使用摘要，并且没有使用企业单一登录。<br /><br /> 最小长度：0<br /><br /> 最大长度：256|None|  
|EnableChunkedEncoding|VT_BOOL|指定要使用 chunked 编码。|如果 HTTP 发送处理程序配置为使用代理服务器，将隐式禁用 chunked 编码。<br /><br /> 有效值为<br /><br /> -   -1 (true)<br />-0 (false)|如果启用此选项，则 HTTP 适配器将使用的 HTTP chunked 编码为 8 Kb 的最大块大小。<br /><br /> 默认值为 0 (false)。|  
|UseProxy|VT_BOOL|指定是否 HTTP 发送处理程序使用代理服务器。|有效值为<br /><br /> -   -1 (true)<br />-0 (false)|默认值为 0 (false)。|  
|ProxyName|VT_BSTR|指定此发送端口的代理服务器地址。|最小长度：0<br /><br /> 最大长度：256|此属性不需要一个值，如果 UseProxy 设置为 0 (false)。|  
|UseSSO|VT_BOOL|指定是否使用单一登录检索客户端凭据的目标服务器的身份验证。|有效值为<br /><br /> -   -1 (true)<br />-0 (false)|默认值为 0 (false)。|  
|Password|VT_NULL|指定要用于目标服务器的身份验证的密码。|此属性需要一个值，如果 AuthenticationScheme 的基本或使用摘要，并且没有使用企业单一登录。<br /><br /> 此值始终设置为 null 时导出绑定文件。 此字段前，必须手动填充密码与绑定文件导入目标 BizTalk Server 配置。<br /><br /> 最小长度：0<br /><br /> 最大长度：256|将此属性的类型设置为 VT_BSTR (vt ="8") 之前导入绑定文件，如果为此字段提供值。|  
|MaxRedirects|VT_I4|指定发送的消息所允许的最大重定向。|有效值为从 0 到 10。|默认值为 5。|  
|ContentType|VT_BSTR|指定请求消息的内容类型。|最小长度：0<br /><br /> 最大长度：256|如果未设置此值，使用处理程序的值。|  
|ProxyPassword|VT_NULL|指定代理服务器进行身份验证的用户密码。|此值始终设置为 null 时导出绑定文件。 此字段前，必须手动填充密码与绑定文件导入目标 BizTalk Server 配置。<br /><br /> 最小长度：0<br /><br /> 最大长度：256|此属性不需要一个值，如果 UseProxy 设置为 0 (false)。|  
|ProxyUsername|VT_BSTR|指定代理服务器进行身份验证的用户名。|最小长度：0<br /><br /> 最大长度：256|此属性不需要一个值，如果 UseProxy 设置为 0 (false)。|  
|UseHandlerSetting|VT_BOOL|指定发送端口配置必须使用指定的 HTTP 发送处理程序的代理设置。|有效值为<br /><br /> -   -1 (true)<br />-0 (false)|默认值为-1 (true)。|  
  
 下面的代码显示了使用设置的属性的 XML 字符串的格式：  
  
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