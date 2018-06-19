---
title: POP3 适配器配置属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, adapters
- POP3 adapters, receive locations
- POP3 adapters, code sample
- POP3 adapters, properties
ms.assetid: e30c848d-afff-42f3-8162-c7ea8c7e3b9a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bf7aa17f36143f80a82f664dbabd257d7b924db
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972435"
---
# <a name="pop3-adapter-configuration-properties"></a>POP3 适配器配置属性
下表列出了可为 POP3 适配器接收位置设置的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|mailServer|VT_BSTR|指定 POP3 适配器将要轮询的邮箱所在的 POP3 邮件服务器。|无|无|  
|serverPort|VT_BSTR|指定 POP3 邮件服务器的端口。|有效值为从 0 到 65535 之间。|值为 0 表示：如果 sslRequired 属性设置为 False，则使用默认的 POP3 端口 110；如果 sslRrequired 属性设置为 True，则使用端口 995。<br /><br /> 默认值为 0。|  
|userName|VT_BSTR|指定对 POP3 服务器进行验证所使用的用户名。|无|无|  
|password|VT_BSTR|指定对 POP3 服务器进行验证所使用的用户密码。|在导出绑定文件时此值始终会被屏蔽。 在将绑定文件导入目标 BizTalk Server 配置前，必须手动在此字段中填充密码。|无|  
|authenticationScheme|VT_BSTR|指定目标服务器使用的验证类型。|有效值为<br /><br /> -基本<br />-摘要<br />-SPA|此属性没有默认值。|  
|sslRequired|VT_BSTR|指定是否使用 SSL 与目标服务器进行通信。|有效值为<br /><br /> -true<br />-false|默认值为 false。|  
|applyMIME|VT_BSTR|指定是否将 MIME 解码应用于通过 POP3 适配器接收的消息。|有效值为<br /><br /> -true<br />-false|默认值为 true。|  
|bodyPartContentType|VT_BSTR|指定要提交到 BizTalk Server 的传入电子邮件的正文部分内容类型。|有效值为<br /><br /> 正文<br />-文本/xml<br />-文本/无格式<br />-文本 /|此属性没有默认值。|  
|bodyPartIndex|VT_BSTR|指定要提交到 BizTalk Server 的传入电子邮件的正文部分。|有效值为从 0 到 128。|默认值为 0。|  
|errorThreshold|VT_BSTR|指定在关闭适配器前允许的最大网络错误或协议错误数。|有效的值是 0 到 4294967295。|指定为 0 以防止适配器关闭。<br /><br /> 默认值为 10。|  
|pollingInterval|VT_BSTR|指定尝试从 POP3 服务器检索消息的时间间隔。|有效值为<br /><br /> -从 1 到 120 如果 pollingUnitOfMeasure 值为天。<br />-从 1 到 2880年如果 pollingUnitOfMeasure 值为小时。<br />-从 1 到 172800 如果 pollingUnitOfMeasure 值为分钟。<br />-从 2 到 10368000 如果 pollingUnitOfMeasure 值为秒。|默认值为 5。|  
|pollingUnitOfMeasure|VT_BSTR|指定与 pollingInterval 的值联合使用的度量单位。|有效值为<br /><br /> -天数<br />-小时数<br />-分钟<br />-秒|默认值为“分钟”。|  
|URI|VT_BSTR|指定接收位置所监视邮箱的完整路径。|发送端口或接收位置的 URI 不能超过 256 个字符。|无|  
  
 以下代码显示用于设置这些属性的字符串的格式：  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><mailServer>test.microsoft.com</mailServer><serverPort>0</serverPort><userName>testuser</userName><password>******</password><authenticationScheme>Basic</authenticationScheme><sslRequired>false</sslRequired><applyMIME>true</applyMIME><bodyPartContentType>text/xml</bodyPartContentType><bodyPartIndex>1</bodyPartIndex><errorThreshold>10</errorThreshold><pollingInterval>5</pollingInterval><pollingUnitOfMeasure>Minutes</pollingUnitOfMeasure><uri>POP3://test.microsoft.com#testuser</uri></Config></AdapterConfig></CustomProps>  
```  
  
> [!NOTE]
>  在指定的适配器，使用适配器框架构建的 TransportTypeData 配置数据时，使用的名称/值对必须全部存储到\<AdapterConfig > 元素。 由于\<AdapterConfig > 元素指定 VT_BSTR (vt ="8") 数据类型则\<\>数据中的字符必须进行转义。