---
title: "SMTP 适配器属性架构和属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UserName property, SMTP adapters
- EmailBodyTextCharset property [SMTP adapters]
- configuring [SMTP adapters], properties
- Subject property [SMTP adapters]
- EmailBodyFileCharset property [SMTP adapters]
- Attachments property [SMTP adapters]
- SMTP adapters, schemas
- EmailBodyText property [SMTP adapters]
- configuring [SMTP adapters], schemas
- CC property [SMTP adapters]
- ReadReceipt property [SMTP adapters]
- Password property [SMTP adapters]
- ReplyBy property [SMTP adapters]
- DeliveryReceipt property [SMTP adapters]
- SMTP adapters, properties
- SMTPAuthenticate property [SMTP adapters]
- EmailBodyFile property [SMTP adapters]
- schemas, SMTP adapters
- SMTPHost property [SMTP adapters]
- From property [SMTP adapters]
- MessagePartsAttachments property [SMTP adapters]
ms.assetid: 6d062fb6-d728-4525-8f0d-bd3f0f8ff7ca
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09f7dfa67bfad53e43a4a6678ff6ad67705e0e27
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="smtp-adapter-property-schema-and-properties"></a>SMTP 适配器属性架构和属性
下表列出了 SMTP 适配器属性架构中的属性：  
  
 **Namespace:** http://schemas.microsoft.com/BizTalk/2003/smtp-properties  
  
|Name|类型|Description|  
|----------|----------|-----------------|  
|**用户名**|xs:string|指定对 SMTP 服务器进行验证所使用的用户名。|  
|**密码**|xs:string|指定对 SMTP 服务器进行验证所使用的密码。|  
|**SMTPHost**|xs:string|指定发送邮件时要使用的 SMTP 服务器的名称。|  
|**From**|xs:string|指定要放入 SMTP 的电子邮件地址**从**标头。|  
|**抄送**|xs:string|指定要将邮件的副本发送到的电子邮件地址。|  
|**主题**|xs:string|指定邮件的主题。|  
|**SMTPAuthenticate**|xs:int|指定对 SMTP 服务器使用的验证类型。|  
|**ReadReceipt**|xs:boolean|指定在阅读邮件后是否发送确认电子邮件。|  
|**DeliveryReceipt**|xs:boolean|指定在送达邮件后是否发送确认电子邮件。|  
|**EmailBodyText**|xs:string|指定将用于要发送的电子邮件正文的文本。|  
|**EmailBodyTextCharset**|xs:string|指定要用于编码时要发送电子邮件的正文的字符集**EmailBodyText**使用选项。 SMTP 适配器会将转换**EmailBodyText**为设置指定的字符**EmailBodyTextCharset**。|  
|**EmailBodyFile**|xs:string|指定将使用一个文件的内容作为要发送的电子邮件的正文，并指定该文件的完整路径。 在运行时，SMTP 适配器所在的主机必须能够访问此路径。|  
|**EmailBodyFileCharset**|xs:string|指定要用于编码如果正在发送的电子邮件正文的字符集**EmailBodyFile**属性设置。 SMTP 适配器将不对该文件执行任何转换；该文件必须已用此字符集进行编码。 如果该文件具有字节顺序标记 (BOM)，则 SMTP 适配器将删除该标记。|  
|**Attachments**|xs:string|指定将向电子邮件附加一个或多个文件，并指定所附加的文件的完整路径。 在运行时，SMTP 适配器所在的主机必须能够访问所指定的路径。|  
|**MessagePartsAttachments**|xs:unsignedInt|指定 BizTalk 消息部分如何附加到电子邮件。|  
|**ReplyBy**|xs:dateTime|指定的日期时间值**答复到**传出的电子邮件消息中的标头。|  
  
## <a name="see-also"></a>另请参阅  
 [配置 SMTP 适配器](../core/configuring-the-smtp-adapter.md)