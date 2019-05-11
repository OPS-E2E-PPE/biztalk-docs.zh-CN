---
title: SMTP 适配器属性架构和属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dcc5e9b1ab3ac9ef5d898c21e0c70638425443a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65270994"
---
# <a name="smtp-adapter-property-schema-and-properties"></a>SMTP 适配器属性架构和属性
下表列出了 SMTP 适配器属性架构中的属性。  
  
 **Namespace**： http://schemas.microsoft.com/BizTalk/2003/smtp-properties  
  
|“属性”|类型|Description|  
|----------|----------|-----------------|  
|**用户名**|xs:string|指定要用于 SMTP 服务器的身份验证的用户名。|  
|**密码**|xs:string|指定要使用的 SMTP 服务器的身份验证的密码。|  
|**SMTPHost**|xs:string|指定要发送消息时使用的 SMTP 服务器的名称。|  
|**From**|xs:string|指定要放置在 SMTP 的电子邮件地址**从**标头。|  
|**CC**|xs:string|指定要将消息的副本发送的电子邮件地址。|  
|**主题**|xs:string|指定消息的使用者标头。|  
|**SMTPAuthenticate**|xs:int|指定要对 SMTP 服务器使用身份验证的类型。|  
|**ReadReceipt**|xs:boolean|指定是否在读取消息时发送一封确认电子邮件。|  
|**DeliveryReceipt**|xs:boolean|指定是否在消息传递后发送确认电子邮件。|  
|**EmailBodyText**|xs:string|指定要用于发送的电子邮件的正文文本。|  
|**EmailBodyTextCharset**|xs:string|指定要使用时要发送的电子邮件的正文进行编码的字符集**EmailBodyText**使用选项。 SMTP 适配器会将转换**EmailBodyText**到由指定的字符集**EmailBodyTextCharset**。|  
|**EmailBodyFile**|xs:string|指定文件的内容将用于要发送电子邮件和文件的完整路径的正文。 在运行时，此路径必须是 SMTP 适配器的主机可访问。|  
|**EmailBodyFileCharset**|xs:string|指定要使用要发送的电子邮件的正文进行编码的字符集**EmailBodyFile**属性设置。 SMTP 适配器将该文件; 不执行任何转换该文件已必须用此字符集进行编码。 如果该文件具有字节顺序标记 (BOM)，SMTP 适配器将其删除。|  
|**Attachments**|xs:string|指定的文件将附加到电子邮件和文件的文件的完整路径。 指定的路径必须是 SMTP 适配器的主机可以访问在运行时。|  
|**MessagePartsAttachments**|xs:unsignedInt|指定 BizTalk 消息部分如何附加到电子邮件。|  
|**ReplyBy**|xs:dateTime|指定一个日期时间值**答复**传出的电子邮件消息中的标头。|  
  
## <a name="see-also"></a>请参阅  
 [配置 SMTP 适配器](../core/configuring-the-smtp-adapter.md)