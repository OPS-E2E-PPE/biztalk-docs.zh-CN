---
title: HTTP 适配器属性架构和属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2f4fdfbd082bb9bbb8e3a37355068b3c8d29c63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332893"
---
# <a name="http-adapter-property-schema-and-properties"></a>HTTP 适配器属性架构和属性
下表列出了 HTTP 适配器属性架构中的属性。  
  
 **Namespace**： http://schemas.microsoft.com/BizTalk/2003/http-properties  
  
|“属性”|类型|Description|  
|----------|----------|-----------------|  
|**ProxyName**|xs:string|指定代理服务器名称。|  
|**ProxyPort**|xs:int|指定代理服务器端口。|  
|**UseHandlerProxySettings**|xs:boolean|指定 HTTP 发送端口是否使用处理程序的代理配置。|  
|**UseProxy**|xs:boolean|指定 HTTP 适配器是否使用代理服务器。|  
|**RequestTimeout**|xs:int|超时期限的等待来自服务器的响应。 如果此属性设置为零 (0)，系统会计算请求消息的大小的超时值。|  
|**用户名**|xs:string|要用于服务器的身份验证的用户名称。|  
|**密码**|xs:string|要使用的服务器的身份验证的用户密码。|  
|**ProxyUsername**|xs:string|指定与代理服务器进行身份验证的用户名。|  
|**ProxyPassword**|xs:string|指定与代理服务器进行身份验证的用户密码。|  
|**MaxRedirects**|xs:int|HTTP 适配器将重定向请求最大次数。|  
|**ContentType**|xs:string|请求消息的内容类型。|  
|**AuthenticationScheme**|xs:string|要对目标服务器使用的身份验证类型。|  
|**证书**|xs:string|客户端 SSL 证书的指纹。|  
|**UseSSO**|xs:boolean|指定 HTTP 发送端口是否将使用 SSO。|  
|**AffiliateApplicationName**|xs:string|要使用的 SSO 关联应用程序的名称。|  
|**InboundHttpHeaders**|xs:string|包含从入站 HTTP 请求的 HTTP 标头。|  
|**SubmissionHandle**|xs:string|包含请求消息的 BizTalk Server 相关标记 (GUID)。|  
|**EnableChunkedEncoding**|xs:boolean|指定 chunked 编码使用的 HTTP 适配器。|  
|**UserHttpHeaders**|xs:string|包含 HTTP 请求或响应消息中包含的自定义标头<br /><br /> 值**UserHttpHeaders**属性必须具有以下格式：<br /><br /> `Header1: value\r\nHeader2: value\r\n`<br /><br /> **请注意**放置冒号 （:）和标头和值之间的空格字符 （）。 标头为空将导致要筛选出的项。空值是可行的。<br /><br /> 可以通过使用修改下面的五个标准 HTTP 标头**UserHttpHeaders**属性：<br /><br /> -接受<br /><br /> -引用网站<br /><br /> -预期<br /><br /> -如果-修改-自<br /><br /> -用户代理|  
  
## <a name="see-also"></a>请参阅  
 [配置 HTTP 适配器](../core/configuring-the-http-adapter.md)