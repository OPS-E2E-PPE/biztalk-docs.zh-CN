---
title: "HTTP 适配器属性架构和属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AffiliateApplicationName property [HTTP adapters]
- Certificate property [HTTP adapters]
- Password property [HTTP adapters]
- HTTP adapters, properties
- InboundHttpHeaders property [HTTP adapters]
- UseHandlerProxySettings property [HTTP adapters]
- configuring [HTTP adapters], properties
- schemas, HTTP adapters
- RequestTimeout property [HTTP adapters]
- ProxyPassword property [HTTP adapters]
- UseSSO property [HTTP adapters]
- HTTP adapters, schemas
- AuthenticationScheme property [HTTP adapters]
- ProxyName property [HTTP adapters]
- ProxyPort property [HTTP adapters]
- UseProxy property [HTTP adapters]
- configuring [HTTP adapters], schemas
- ContentType property [HTTP adapters]
- MaxRedirects property [HTTP adapters]
- ProxyUsername property [HTTP adapters]
- UserName property, HTTP adapters
ms.assetid: c9b50a82-8cb1-4521-9cf3-5fd77a3531e1
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 416ad39e804a4907dc39c7cef941e9a1bb57d3dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="http-adapter-property-schema-and-properties"></a>HTTP 适配器属性架构和属性
下表列出了 HTTP 适配器属性架构中的属性。  
  
 **Namespace:** http://schemas.microsoft.com/BizTalk/2003/http-properties  
  
|Name|类型|Description|  
|----------|----------|-----------------|  
|**ProxyName**|xs:string|指定代理服务器名称。|  
|**友好**|xs:int|指定代理服务器端口。|  
|**UseHandlerProxySettings**|xs:boolean|指定 HTTP 发送端口是否使用处理程序的代理配置。|  
|**UseProxy**|xs:boolean|指定 HTTP 适配器是否使用代理服务器。|  
|**RequestTimeout**|xs:int|超时来自服务器的响应的等待的时间。 如果此属性设置为零 (0)，则系统将根据请求消息的大小来计算超时值。|  
|**用户名**|xs:string|对服务器进行验证所使用的用户名。|  
|**密码**|xs:string|对服务器进行验证所使用的密码。|  
|**ProxyUsername**|xs:string|指定与代理服务器的身份验证的用户名。|  
|**代理**|xs:string|指定与代理服务器的身份验证的用户密码。|  
|**MaxRedirects**|xs:int|HTTP 适配器可重定向请求的最大次数。|  
|**ContentType**|xs:string|请求消息的内容类型。|  
|**AuthenticationScheme**|xs:string|要使用与目标服务器的身份验证的类型。|  
|**证书**|xs:string|客户端 SSL 证书的指纹。|  
|**UseSSO**|xs:boolean|指定 HTTP 发送端口是否使用 SSO。|  
|**AffiliateApplicationName**|xs:string|用于 SSO 的关联应用程序的名称。|  
|**InboundHttpHeaders**|xs:string|包含来自入站 HTTP 请求的 HTTP 标头。|  
|**SubmissionHandle**|xs:string|包含请求消息的 BizTalk Server 的相关标记 (GUID)。|  
|**EnableChunkedEncoding**|xs:boolean|指定 HTTP 适配器是否使用 Chunked 编码。|  
|**UserHttpHeaders**|xs:string|包含 HTTP 请求或响应消息中包含的自定义标头<br /><br /> 值**UserHttpHeaders**属性必须具有以下格式：<br /><br /> `Header1: value\r\nHeader2: value\r\n`<br /><br /> **请注意**将冒号 （:） 和标头和值之间的空格字符 （）。 如果标头为空，则会将对应的条目筛选出去。此处允许空值。<br /><br /> 你可以通过修改下面的五个标准 HTTP 标头**UserHttpHeaders**属性：<br /><br /> 接受<br /><br /> -引用网站<br /><br /> -预期<br /><br /> -如果-修改-自<br /><br /> -用户代理|  
  
## <a name="see-also"></a>另请参阅  
 [配置 HTTP 适配器](../core/configuring-the-http-adapter.md)