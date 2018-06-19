---
title: SOAP 适配器属性架构和属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ProxyUsername property [SOAP adapters]
- ClientConnectionTimeout property [SOAP adapters]
- SOAP adapters, properties
- ProxyAddress property [SOAP adapters]
- UserDefined property [SOAP adapters]
- AssemblyName property [SOAP adapters]
- ClientCertificate property [SOAP adapters]
- AffiliateApplicationName property [SOAP adapters]
- schemas, SOAP adapters
- AuthenticationScheme property [SOAP adapters]
- UserName property, SOAP adapters
- UseProxy property [SOAP adapters]
- Password property [SOAP adapters]
- configuring [SOAP adapters], schemas
- UnknownHeaders property [SOAP adapters]
- configuring [SOAP adapters], properties
- UseSoap12 property [SOAP adapters]
- UseHandlerSetting property [SOAP adapters]
- SOAP adapters, schemas
- ProxyPassword property [SOAP adapters]
- UseSSO property [SOAP adapters]
- MethodName property [SOAP adapters]
- ProxyPort property [SOAP adapters]
ms.assetid: b471cf4b-2d87-4aa2-ae4a-f48517fd4c94
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a24a9ccfc3a07abe925761fe2d6886646981be9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277509"
---
# <a name="soap-adapter-property-schema-and-properties"></a>SOAP 适配器属性架构和属性
下表列出了 SOAP 适配器属性架构中的属性：  
  
 **Namespace:** http://schemas.microsoft.com/BizTalk/2003/soap-properties  
  
|Name|类型|Description|  
|----------|----------|-----------------|  
|**程序集名称**|xs:string|标识要加载和执行的 .NET 类型和程序集。|  
|**MethodName**|xs:string|标识 .NET 程序集中要调用的目标方法。|  
|**用户名**|xs:string|要使用服务器的身份验证的用户名称。|  
|**密码**|xs:string|要用于服务器的身份验证的用户密码。|  
|**ClientCertificate**|xs:string|客户端 SSL 证书的指纹。|  
|**UseProxy**|xs:Boolean|指定 SOAP 适配器是否使用代理服务器。|  
|**ProxyAddress**|xs:string|指定代理服务器地址。|  
|**友好**|xs:int|指定代理服务器端口。|  
|**ProxyUsername**|xs:string|指定与代理服务器的身份验证的用户名。|  
|**代理**|xs:string|指定与代理服务器的身份验证的用户密码。|  
|**UnknownHeaders**|xs:string|指定未知 SOAP 标头的序列化列表。|  
|**AffiliateApplicationName**|xs:string|定义用于 SSO 的关联应用程序的名称。|  
|**AuthenticationScheme**|xs:string|指定对目标服务器使用的验证类型。|  
|**UseSSO**|xs:boolean|指定 SOAP 适配器是否对发送端口使用 SSO。|  
|**UseHandlerSetting**|xs:boolean|指定 SOAP 发送端口是否使用处理程序的代理配置。|  
|**ClientConnectionTimeout**|xs:int|指定等待服务器响应的超时期限。 如果设置为零 (0)，系统将计算基于对请求消息大小的超时值。|  
|**用户定义**|xs:string|定义用户定义的类。|  
|**UseSoap12**|xs:boolean|指定是否生成支持 SOAP 1.2 协议的代理代码。|  
  
## <a name="see-also"></a>另请参阅  
 [配置 SOAP 适配器](../core/configuring-the-soap-adapter.md)