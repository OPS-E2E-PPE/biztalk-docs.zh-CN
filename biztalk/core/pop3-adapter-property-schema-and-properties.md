---
title: POP3 适配器属性架构和属性 |Microsoft Docs
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
ms.openlocfilehash: 4bfd98117254686f69a590430f46fbd07a4d0b03
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394907"
---
# <a name="pop3-adapter-property-schema-and-properties"></a>POP3 适配器属性架构和属性
下表列出了 POP3 适配器属性架构中的属性。  
  
 **Namespace**： http://schemas.microsoft.com/BizTalk/2003/pop3-properties  
  
|**名称**|**类型**|**说明**|  
|--------------|--------------|---------------------|  
|**主题**|xs:string|指定上放置的内容**使用者**消息标头|  
|**From**|xs:string|指定上放置的电子邮件地址**从**电子邮件消息的标头字段。|  
|**若要**|xs:string|指定的电子邮件地址或地址上放置**到**电子邮件消息的标头字段。|  
|ReplyTo|xs:string|指定上放置的电子邮件地址**ReplyTo**电子邮件消息的标头字段。|  
|**CC**|xs:string|指定的电子邮件地址或地址上放置**CC**电子邮件消息的标头字段。|  
|**Date**|xs:string|指定上放置的内容**日期**电子邮件消息的标头字段。|  
|**DispositionNotificationTo**|xs:string|指定上放置的内容**DispositionNotificationTo**电子邮件消息的标头字段。|  
|**标头**|xs:string|指定的所有电子邮件消息的标头字段的内容。|  
  
## <a name="see-also"></a>请参阅  
 [配置 POP3 适配器](../core/configuring-the-pop3-adapter.md)