---
title: POP3 适配器配置属性 |Microsoft Docs
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
ms.openlocfilehash: b3ca7c44230e47e1aeccd415630d4153ae5f4eb6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394929"
---
# <a name="pop3-adapter-configuration-properties"></a>POP3 适配器配置属性
下表列出了可以设置为 POP3 适配器的配置属性接收位置：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|mailServer|VT_BSTR|指定 POP3 适配器将要轮询的邮箱所在的 POP3 邮件服务器。|None|None|  
|serverPort|VT_BSTR|指定 POP3 邮件服务器的端口。|有效值为从 0 到 65535 之间。|值为 0 指示如果则设置为 false，请使用默认 POP3 端口 110 或端口 995 如果 sslRrequired 属性设置为 true。<br /><br /> 默认值为 0。|  
|userName|VT_BSTR|指定要用于 POP3 服务器的身份验证的用户名。|None|None|  
|password|VT_BSTR|指定要用于 POP3 服务器的身份验证的用户密码。|导出绑定文件时，此值始终会被屏蔽。 此字段前，必须手动填充密码与绑定文件导入目标 BizTalk Server 配置。|None|  
|authenticationScheme|VT_BSTR|指定要对目标服务器使用身份验证的类型。|有效值为<br /><br /> -基本<br />-摘要<br />-   SPA|没有此属性的默认值。|  
|sslRequired|VT_BSTR|指定是否使用 SSL 与目标服务器进行通信。|有效值为<br /><br /> -true<br />-false|默认值是 False。|  
|applyMIME|VT_BSTR|指定是否要应用 MIME 解码通过 POP3 适配器接收到消息。|有效值为<br /><br /> -true<br />-false|默认值为 true。|  
|bodyPartContentType|VT_BSTR|指定要提交到 BizTalk Server 的传入电子邮件的正文部分内容类型。|有效值为<br /><br /> -   body<br />-   text/xml<br />-   text/plain<br />-文本 /|没有此属性的默认值。|  
|bodyPartIndex|VT_BSTR|指定要提交到 BizTalk Server 的传入电子邮件的正文部分。|有效值为从 0 到 128。|默认值为 0。|  
|errorThreshold|VT_BSTR|指定的最大网络或协议错误，关闭适配器前等待数。|有效值为从 0 到 4294967295。|指定值 0 可以防止适配器关闭。<br /><br /> 默认值为 10。|  
|pollingInterval|VT_BSTR|指定两次尝试从 POP3 服务器检索消息之间的间隔。|有效值为<br /><br /> -从 1 到 120 如果 pollingUnitOfMeasure 值为天。<br />-从 1 到 2880年如果 pollingUnitOfMeasure 值为小时。<br />-从 1 到 172800 如果 pollingUnitOfMeasure 值为分钟。<br />-从 2 到 10368000 如果 pollingUnitOfMeasure 值为秒。|默认值为 5。|  
|pollingUnitOfMeasure|VT_BSTR|指定度量的单位的 pollingInterval 的值一起使用。|有效值为<br /><br /> -天<br />小时数<br />-分钟<br />/ 字节秒|默认值为分钟。|  
|uri|VT_BSTR|指定接收位置监视的邮箱的完整路径。|URI 发送端口或接收位置不能超过 256 个字符。|None|  
  
 下面的代码显示了使用设置的属性的字符串的格式：  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><mailServer>test.microsoft.com</mailServer><serverPort>0</serverPort><userName>testuser</userName><password>******</password><authenticationScheme>Basic</authenticationScheme><sslRequired>false</sslRequired><applyMIME>true</applyMIME><bodyPartContentType>text/xml</bodyPartContentType><bodyPartIndex>1</bodyPartIndex><errorThreshold>10</errorThreshold><pollingInterval>5</pollingInterval><pollingUnitOfMeasure>Minutes</pollingUnitOfMeasure><uri>POP3://test.microsoft.com#testuser</uri></Config></AdapterConfig></CustomProps>  
```  
  
> [!NOTE]
>  当指定为使用适配器框架生成的适配器的 TransportTypeData 配置数据，使用的名称/值对必须全部存储到\<AdapterConfig > 元素。 由于\<AdapterConfig > 元素指定 VT_BSTR (vt ="8") 数据类型然后\<\>必须对数据中的字符进行转义。