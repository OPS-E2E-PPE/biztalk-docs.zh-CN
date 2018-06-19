---
title: POP3 适配器属性架构和属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, POP3 adapters
- Subject properties [POP3 adapters]
- Date properties [POP3 adapters]
- From properties [POP3 adapters]
- To properties [POP3 adapters]
- POP3 adapters, properties
- configuring [POP3 adapters], schemas
- configuring [POP3 adapters], properties
- CC properties [POP3 adapters]
- Headers properties [POP3 adapters]
- ReplyTo properties [POP3 adapters]
- DispositionNotificationTo properties [POP3 adapters]
ms.assetid: 7a10ae1f-dbcf-4c05-9a50-2503895960f9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b976aba7161272ebdc65da2b5bcd2067c8cd3a5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264165"
---
# <a name="pop3-adapter-property-schema-and-properties"></a>POP3 适配器属性架构和属性
下表列出了 POP3 适配器属性架构中的属性：  
  
 **Namespace:** http://schemas.microsoft.com/BizTalk/2003/pop3-properties  
  
|**名称**|**类型**|**Description**|  
|--------------|--------------|---------------------|  
|**主题**|xs:string|指定的内容放入**主题**消息标头|  
|**From**|xs:string|指定放置在上的电子邮件地址**从**电子邮件消息的标头字段。|  
|**若要**|xs:string|指定的电子邮件地址或地址放置在**到**电子邮件消息的标头字段。|  
|**ReplyTo**|xs:string|指定放置在上的电子邮件地址**ReplyTo**电子邮件消息的标头字段。|  
|**抄送**|xs:string|指定的电子邮件地址或地址放置在**CC**电子邮件消息的标头字段。|  
|**日期**|xs:string|指定的内容放入**日期**电子邮件消息的标头字段。|  
|**DispositionNotificationTo**|xs:string|指定的内容放入**DispositionNotificationTo**电子邮件消息的标头字段。|  
|**标头**|xs:string|指定电子邮件的所有标头字段的内容。|  
  
## <a name="see-also"></a>另请参阅  
 [配置 POP3 适配器](../core/configuring-the-pop3-adapter.md)