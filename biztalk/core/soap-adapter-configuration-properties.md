---
title: SOAP 适配器配置属性 |Microsoft 文档
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
ms.openlocfilehash: f52fde9d80717d192d3a5b90548ccc01e87d2044
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279813"
---
# <a name="soap-adapter-configuration-properties"></a>SOAP 适配器配置属性
下表列出了可为 SOAP 适配器接收位置设置的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|UseSSO|VT_BOOL|指定是否使用单一登录。|-有效值为：<br />--1 (true)<br />-0 (false)|默认值为 0 (false)。|  
  
 下面的代码演示使用设置的属性的 XML 字符串的格式：  
  
```  
<CustomProps>  
<UseSSO vt="11">0</UseSSO>  
</CustomProps>  
```  
  
 下表列出了可为 SOAP 适配器发送端口设置的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|友好|VT_I4|指定此发送端口的代理服务器端口。|无|除非 UseProxy 属性设置为 -1 (true)，否则此属性不需要值。<br /><br /> 默认值为 80。|  
|AuthenticationScheme|VT_BSTR|指定目标服务器使用的验证类型。|有效值为<br /><br /> 匿名<br />-基本<br />-摘要<br />-NTLM|默认值为“匿名”。|  
|用户名|VT_BSTR|指定用于目标服务器验证的用户名。|最小长度：0<br /><br /> 最大长度：256|除非 AuthenticationScheme 属性设置为“基本”或“摘要”，并且 UseSSO 属性设置为 0 (false)，否则此属性不需要值。|  
|UseProxy|VT_BOOL|指定 SOAP 发送处理程序是否使用代理服务器。|有效值为<br /><br /> --1 (true)<br />-0 (false)|默认值为 0 (false)。|  
|UseSoap12|VT_BOOL|指定此项可生成将支持 SOAP 1.2 协议的代理代码。|如果不选择此选项，将生成 SOAP 1.1 符合代理代码。<br /><br /> 有效值为<br /><br /> --1 (true)<br />-0 (false)|默认值为 0 (false)。|  
|UsingOrchestration|VT_BOOL|指定是否使用与此发送端口地址相关联的 Web Services 代理。|有效值为<br /><br /> --1 (true)<br />-0 (false)|默认值为 -1 (true)。|  
|UseSSO|VT_BOOL|指定是否使用企业单一登录。|有效值为<br /><br /> --1 (true)<br />-0 (false)|默认值为 0 (false)。|  
|ProxyAddress|VT_BSTR|指定代理服务器的名称。|只有 UseProxy 属性设置为 -1 (true) 时，此属性才是有效的。|无|  
|密码|VT_NULL|指定用于目标服务器验证的密码。|此值在导出绑定文件时始终设置为空。 在将绑定文件导入目标 BizTalk Server 配置前，必须手动在此字段中填充密码。|除非 AuthenticationScheme 属性设置为“基本”或“摘要”，并且 UseSSO 属性设置为 0 (false)，否则此属性不需要值。|  
|AssemblyPath|VT_BSTR|指定包含 Web 服务代理的程序集的路径。|无|无|  
|TypeName|VT_BSTR|指定包含要调用的 Web 方法的类的名称。|无|无|  
|MethodName|VT_BSTR|指定要调用的类的方法。|无|无|  
|UseHandlerSetting|VT_BOOL|指定是否使用 SOAP 发送处理程序的默认代理配置。|有效值为<br /><br /> --1 (true)<br />-0 (false)|默认值为 -1 (true)。|  
|ClientCertificate|VT_BSTR|指定用于建立连接的客户端证书的指纹。|最小长度：0<br /><br /> 最大长度： 59|无|  
|ProxyPassword|VT_NULL|指定用于代理服务器验证的密码。|此值在导出绑定文件时始终设置为空。 在将绑定文件导入目标 BizTalk Server 配置前，必须手动在此字段中填充密码。|如果 UseProxy 设置为 0 (false)，则此属性不需要值。|  
|ProxyUsername|VT_BSTR|指定用于代理服务器验证的用户名。|无|除非 UseProxy 属性设置为 -1 (true)，否则此属性不需要值。|  
  
 下面的代码演示使用设置的属性的 XML 字符串的格式：  
  
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