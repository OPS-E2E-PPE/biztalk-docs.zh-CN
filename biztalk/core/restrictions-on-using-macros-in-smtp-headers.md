---
title: 在 SMTP 标头中使用宏的限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], restrictions
- macros, SMTP headers [SMTP adapters]
- SMTP adapters, macros
- SMTP adapters, restrictions
- configuring [SMTP adapters], SMTP headers
- SMTP adapters, SMTP headers
- configuring [SMTP adapters], macros
- SMTP headers
ms.assetid: ceab0917-cb3c-423b-a15f-63747ab1d8da
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5162de289f9c9e7798e5a24aa75fa9305763b401
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977974"
---
# <a name="restrictions-on-using-macros-in-smtp-headers"></a>在 SMTP 标头中使用宏的限制
您可以使用预定义的宏集合动态地在 SMTP 消息标头上构成“主题” 、“收件人” 、“发件人” 和“抄送”  属性。 在发送消息前，SMTP 发送处理程序使用宏的值替代标头中的所有宏。 当形成一个标头时，您可以使用多个不同的宏。  
  
 如果以下项之一为 True，则 SMTP 发送处理程序不会替代“收件人” 、“发件人” 或“抄送”  标头中的宏：  
  
- 未设置相应的系统属性。  
  
- 宏拼写错误。  
  
- 宏的值所包含的符号对于 SMTP 标头无效。  
  
  如果满足下列任一条件，将 SMTP 发送处理程序会将宏它们是，例如， <strong>%sourceparty%@somedomain.com</strong> 或**Message from %sourceparty%**。  
  
  下表列出了可用于生成“收件人” 、“抄送” 和“主题”  标头的宏：  
  
|宏|Description|用于与“收件人”一起使用|用于与“抄送”一起使用|用于与“主题”一起使用|  
|-----------|-----------------|---------------------|---------------------|--------------------------|  
|%MessageID%|BizTalk Server 中消息的全局唯一标识符 (GUID)。 该值来自消息上下文属性 **BTS.MessageID**。|“否”|否|是|  
|%datetime_bts2000%|YYYYMMDDhhmmsss 格式的 UTC 日期时间，其中，sss 表示秒和毫秒（例如，199707121035234 表示 1997/07/12 10:35:23 和 400 毫秒）。|“否”|否|是|  
|%datetime%|YYYY-MM-DDThhmmss 格式的 UTC 日期时间（例如 1997-07-12T103508）。|“否”|否|是|  
|%datetime.tz%|本地日期时间加上 GMT 时区，格式为 YYYY-MM-DDThhmmssTZD（例如 1997-07-12T103508+800）。|“否”|否|是|  
|%time%|hhmmss 格式的 UTC 时间。|“否”|否|是|  
|%time.tz%|本地时间加上 GMT 时区，格式为 hhmmssTZD（例如 124525+530）。|“否”|否|是|  
|%SourceParty%|文件适配器从其接收消息的源参与方的名称。|“否”|否|是|  
|%SourcePartyQualifier%|文件适配器从其接收消息的源参与方的限定符。|“否”|否|是|  
|%DestinationParty%|目标参与方的名称。 该值来自消息上下文属性 **BTS.DestinationParty**。|是|是|是|  
|%DestinationPartyQualifier%|目标参与方的限定符。 该值来自消息上下文属性 **BTS.DestinationPartyQualifier**。|“否”|否|是|  
  
## <a name="see-also"></a>请参阅  
 [配置 SMTP 适配器时的限制](../core/restrictions-when-configuring-the-smtp-adapter.md)
