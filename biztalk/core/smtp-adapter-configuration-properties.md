---
title: SMTP 适配器配置属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SMTP adapters, properties
- SMTP adapters, code sample
- SMTP adapters, send ports
- send ports, adapters
ms.assetid: 6af287f5-272a-42d7-9878-99a4157c06ce
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 740e3081e9b03dec725b02dd0107d9c8a1363b48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401889"
---
# <a name="smtp-adapter-configuration-properties"></a>SMTP 适配器配置属性
下表列出了发送端口可以设置为 SMTP 适配器的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|DeliveryReceipt|VT_BOOL|指定在传递消息时，应发送确认电子邮件。|有效值为<br /><br /> -   -1 (true)<br />-0 (false)|默认值为 0 (false)。|  
|From|VT_BSTR|指定的电子邮件地址，将 SMTP 从标头。|最小长度：0<br /><br /> 最大长度：256|None|  
|MessagePartsAttachments|VT_UI4|指定 BizTalk 消息部分如何附加到电子邮件。|有效值为<br /><br /> -0 （不附加消息部分）<br />-1 （仅附加正文部分<br />-2 （附加所有部分）|默认值为的 0 （不附加消息部分）。|  
|CC|VT_BSTR|指定要发送邮件的抄送电子邮件地址。|最大长度：1024|可以指定多个地址。|  
|SMTPAuthenticate|VT_UI4|有效值为<br /><br /> -0 （不验证）<br />-1 （基本身份验证）<br />-2 （进程帐户 (NTLM)）|如果未指定此值被应用的 （默认值） 值。|（默认值） 值表示 SMTP 发送端口将使用发送处理程序中指定的配置值。|  
|用户名|VT_BSTR|指定要用于 SMTP 服务器的身份验证的用户名。|此属性不需要一个值，除非 SMTPAuthenticate 属性设置为 1 （基本身份验证）。<br /><br /> 最小长度：0<br /><br /> 最大长度：256|None|  
|EmailBodyFileCharset|VT_BSTR|指定要发送的文件的编码的字符集。|此属性不需要一个值，除非设置 EmailBodyFile 属性。|SMTP 适配器不适用于指定编码的文件，此选项仅用于指定要发送的文件已编码的方式。<br /><br /> 默认值为 utf-8。|  
|EmailBodyText|VT_BSTR|指定要用于发送的电子邮件的正文文本。|最大长度：64Kb|None|  
|ReadReceipt|VT_BOOL|指定当读取消息时，应发送确认电子邮件。|有效值为<br /><br /> -   -1 (true)<br />-0 (false)|默认值为 0 (false)。|  
|若要|VT_BSTR|指定要将消息发送的电子邮件地址。|None|None|  
|EmailBodyFile|VT_BSTR|指定要用于发送电子邮件的正文的文件的路径。|最大路径长度：256 个字符|它是建议的最佳做法，若要指定可从要在生产中使用的 BizTalk Server 组中的所有 BizTalk 服务器访问的文件共享上的路径。|  
|Subject|VT_BSTR|指定消息的使用者标头。|最小长度：0<br /><br /> 最大长度：256|None|  
|Password|VT_NULL|指定要使用的 SMTP 服务器的身份验证的密码。|此属性不需要一个值，除非 SMTPAuthenticate 属性设置为 1 （基本身份验证）。<br /><br /> 此值始终设置为 null 时导出绑定文件。 此字段前，必须手动填充密码与绑定文件导入目标 BizTalk Server 配置。|None|  
|Attachments|VT_BSTR|指定要附加到正在发送的电子邮件的文件的路径。|最大路径长度：256 个字符|None|  
|SMTPHost|VT_BSTR|指定要发送消息时使用的 SMTP 服务器的名称。|URI 发送端口或接收位置不能超过 256 个字符。<br /><br /> 最大路径长度：256 个字符|None|  
|EmailBodyTextCharset|VT_BSTR|指定要使用正在发送的电子邮件正文进行编码的字符集。|此属性不需要一个值，除非设置 EmailBodyText 属性。|默认值为 utf-8。|  
  
 下面的代码显示了使用设置的属性的 XML 字符串的格式：  
  
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