---
title: SOAP 适配器配置属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP adapters, send ports
- SOAP adapters, code samples
- SOAP adapters, properties
- receive locations, adapters
- SOAP adapters, receive locations
- send ports, adapters
ms.assetid: 0d033371-ee31-4e43-a7d3-e0975791d981
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe4ef2a17df290c78c821d85995d450e8af90ca9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314037"
---
# <a name="soap-adapter-configuration-properties"></a>SOAP 适配器配置属性
下表列出了可以设置为 SOAP 适配器的配置属性接收位置：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|UseSSO|VT_BOOL|指定是否使用单一登录。|有效值为：<br />-   -1 (true)<br />-0 (false)|默认值为 0 (false)。|  
  
 下面的代码显示了使用设置的属性的 XML 字符串的格式：  
  
```  
<CustomProps>  
<UseSSO vt="11">0</UseSSO>  
</CustomProps>  
```  
  
 下表列出了发送端口可以设置为 SOAP 适配器的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|ProxyPort|VT_I4|指定此发送端口的代理服务器端口。|None|此属性不需要一个值，除非 UseProxy 属性设置为-1 (true)。<br /><br /> 默认值为 80。|  
|AuthenticationScheme|VT_BSTR|指定要对目标服务器使用身份验证的类型。|有效值为<br /><br /> 匿名<br />-基本<br />-摘要<br />-   NTLM|默认值为 Anonymous。|  
|用户名|VT_BSTR|指定要用于目标服务器的身份验证的用户名。|最小长度：0<br /><br /> 最大长度：256|此属性不需要一个值，除非 AuthenticationScheme 属性设置为基本或摘要式并且 UseSSO 属性设置为 0 (false)。|  
|UseProxy|VT_BOOL|指定是否在 SOAP 发送处理程序将使用代理服务器。|有效值为<br /><br /> -   -1 (true)<br />-0 (false)|默认值为 0 (false)。|  
|UseSoap12|VT_BOOL|指定要生成将支持 SOAP 1.2 协议的代理代码。|如果不选择此选项，将生成 SOAP 1.1 兼容的代理代码。<br /><br /> 有效值为<br /><br /> -   -1 (true)<br />-0 (false)|默认值为 0 (false)。|  
|UsingOrchestration|VT_BOOL|指定是否使用与此发送端口地址相关联的 Web 服务代理。|有效值为<br /><br /> -   -1 (true)<br />-0 (false)|默认值为-1 (true)。|  
|UseSSO|VT_BOOL|指定使用是企业单一登录。|有效值为<br /><br /> -   -1 (true)<br />-0 (false)|默认值为 0 (false)。|  
|ProxyAddress|VT_BSTR|指定代理服务器的名称。|如果 UseProxy 属性设置为-1 (true)，此属性才有效。|None|  
|Password|VT_NULL|指定要用于目标服务器的身份验证的密码。|此值始终设置为 null 时导出绑定文件。 此字段前，必须手动填充密码与绑定文件导入目标 BizTalk Server 配置。|此属性不需要一个值，除非 AuthenticationScheme 属性设置为基本或摘要式并且 UseSSO 属性设置为 0 (false)。|  
|AssemblyPath|VT_BSTR|指定包含 Web 服务代理的程序集的路径。|None|None|  
|TypeName|VT_BSTR|指定包含要调用的 Web 方法的类的名称。|None|None|  
|MethodName|VT_BSTR|指定将调用的类的方法。|None|None|  
|UseHandlerSetting|VT_BOOL|指定是否要使用 SOAP 发送处理程序的默认代理配置。|有效值为<br /><br /> -   -1 (true)<br />-0 (false)|默认值为-1 (true)。|  
|ClientCertificate|VT_BSTR|指定要用于建立连接的客户端证书的指纹。|最小长度：0<br /><br /> 最大长度：59|None|  
|ProxyPassword|VT_NULL|指定要使用代理服务器进行身份验证的密码。|此值始终设置为 null 时导出绑定文件。 此字段前，必须手动填充密码与绑定文件导入目标 BizTalk Server 配置。|此属性不需要一个值，如果 UseProxy 设置为 0 (false)。|  
|ProxyUsername|VT_BSTR|指定要使用代理服务器进行身份验证的用户名。|None|此属性不需要一个值，除非 UseProxy 属性设置为-1 (true)。|  
  
 下面的代码显示了使用设置的属性的 XML 字符串的格式：  
  
```  
<CustomProps>  
<ProxyPort vt="3">80</ProxyPort>  
<AuthenticationScheme vt="8">Basic</AuthenticationScheme>  
<Username vt="8">domain\testuser</Username>  
<UseProxy vt="11">-1</UseProxy>  
<UseSoap12 vt="11">-1</UseSoap12>  
<UsingOrchestration vt="11">-1</UsingOrchestration>  
<UseSSO vt="11">0</UseSSO>  
<ProxyAddress vt="8">proxy</ProxyAddress>  
<Password vt="1" />  
<ProxyPort vt="3">80</ProxyPort>  
<AssemblyPath vt="8">C:\Websvc.dll</AssemblyPath>  
<TypeName vt="8">Websvc.svc</TypeName>  
<MethodName vt="8">WebMethod</MethodName>  
<UseHandlerSetting vt="11">0</UseHandlerSetting></  
<ClientCertificate vt="8">23779A5EEA9693A37409021EFCDAB713A3680C34</ClientCertificate>  
<ProxyPassword vt="1" />  
<ProxyUsername vt="8">proxyuser</ProxyUsername>  
</CustomProps>  
```