---
title: "SMTP 适配器配置属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SMTP adapters, properties
- SMTP adapters, code sample
- SMTP adapters, send ports
- send ports, adapters
ms.assetid: 6af287f5-272a-42d7-9878-99a4157c06ce
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8b8bb0c5562c07260a9d411b8144bd7a576eb3a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="smtp-adapter-configuration-properties"></a>SMTP 适配器配置属性
下表列出了可为 SMTP 适配器发送端口设置的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|DeliveryReceipt|VT_BOOL|指定在送达邮件后应发送确认电子邮件。|有效值为<br /><br /> --1 (true)<br />-0 (false)|默认值为 0 (false)。|  
|From|VT_BSTR|指定在 SMTP“发件人”标题上显示的电子邮件地址。|最小长度：0<br /><br /> 最大长度：256|无|  
|MessagePartsAttachments|VT_UI4|指定 BizTalk 消息部分如何附加到电子邮件。|有效值为<br /><br /> -0 （不附加任何消息部分）<br />-1 （附加唯一正文部分<br />-2 （附加所有部分）|默认值为 0（不附加消息部分）。|  
|CC|VT_BSTR|指定邮件的抄送副本要发送到的电子邮件地址。|最大长度： 1024年|您可以指定多个地址。|  
|SMTPAuthenticate|VT_UI4|有效值为<br /><br /> -0 （不验证）<br />-1 （基本身份验证）<br />-2 （进程帐户 (NTLM)）|如果未指定此值，则使用默认值。|默认值表示 SMTP 发送端口将使用发送处理程序中指定的配置值。|  
|用户名|VT_BSTR|指定对 SMTP 服务器进行验证所使用的用户名。|除非 SMTPAuthenticate 属性设置为 -1（基本验证），否则此属性不需要值。<br /><br /> 最小长度：0<br /><br /> 最大长度：256|无|  
|EmailBodyFileCharset|VT_BSTR|指定要发送的文件的字符集编码。|除非设置 EmailBodyFile 属性，否则此属性不需要值。|SMTP 适配器不将指定的编码应用于文件，此选项只用于指定发送的文件已经使用的编码方式。<br /><br /> 默认值为 utf-8。|  
|EmailBodyText|VT_BSTR|指定将用于要发送的电子邮件正文的文本。|最大长度：64KB|无|  
|ReadReceipt|VT_BOOL|指定在读取邮件后应发送确认电子邮件。|有效值为<br /><br /> --1 (true)<br />-0 (false)|默认值为 0 (false)。|  
|若要|VT_BSTR|指定邮件要发送到的电子邮件地址。|无|无|  
|EmailBodyFile|VT_BSTR|指定用于要发送的电子邮件的正文的文件的路径。|最大路径长度：256 个字符|它是建议的最佳做法来从要在生产中使用的 BizTalk Server 组中的所有 BizTalk 服务器可访问的文件共享上指定的路径。|  
|主题|VT_BSTR|指定邮件的主题。|最小长度：0<br /><br /> 最大长度：256|无|  
|密码|VT_NULL|指定对 SMTP 服务器进行验证所使用的密码。|此属性不需要一个值，除非 SMTPAuthenticate 属性设置为 1 （基本身份验证）。<br /><br /> 此值在导出绑定文件时始终设置为空。 在将绑定文件导入目标 BizTalk Server 配置前，必须手动在此字段中填充密码。|无|  
|Attachments|VT_BSTR|指定附加到要发送的电子邮件的文件的路径。|最大路径长度：256 个字符|无|  
|SMTPHost|VT_BSTR|指定发送邮件时要使用的 SMTP 服务器的名称。|发送端口或接收位置的 URI 不能超过 256 个字符。<br /><br /> 最大路径长度：256 个字符|无|  
|EmailBodyTextCharset|VT_BSTR|指定将用于要发送的电子邮件正文编码的字符集。|除非设置 EmailBodyText 属性，否则此属性不需要值。|默认值为 utf-8。|  
  
 下面的代码演示使用设置的属性的 XML 字符串的格式：  
  
```  
<CustomProps>  
<DeliveryReceipt vt="11">-1</DeliveryReceipt>  
<From vt="8">someone@microsoft.com</From>  
<MessagePartsAttachments vt="19">0</MessagePartsAttachments>  
<CC vt="8">someoneelse@microsoft.com</CC>  
<SMTPAuthenticate vt="19">1</SMTPAuthenticate>  
<Username vt="8">OverrideUsername</Username>  
<EmailBodyFileCharset vt="8">utf-8</EmailBodyFileCharset>  
<EmailBodyText vt="8">Email Body Text</EmailBodyText>  
<ReadReceipt vt="11">-1</ReadReceipt>  
<To vt="8">recipient@microsoft.com</To>  
<EmailBodyFile vt="8">C:\emailbodyfile.xml</EmailBodyFile>  
<Subject vt="8">test mail</Subject>  
<Password vt="1" />  
<Attachments vt="8">C:\attachment.txt</Attachments>  
<SMTPHost vt="8">emailhost</SMTPHost>  
<EmailBodyTextCharset vt="8">utf-8</EmailBodyTextCharset>  
</CustomProps>  
```