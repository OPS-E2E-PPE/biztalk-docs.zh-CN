---
title: "在 SMTP 标头中使用宏的限制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5bf13f97d3cee4bf5930c448c3444aead898624
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="restrictions-on-using-macros-in-smtp-headers"></a>在 SMTP 标头中使用宏的限制
您可以使用预定义的宏集合动态地在 SMTP 消息标头上构成“主题” 、“收件人” 、“发件人” 和“抄送”  属性。 在发送消息前，SMTP 发送处理程序使用宏的值替代标头中的所有宏。 当形成一个标头时，您可以使用多个不同的宏。  
  
 如果以下项之一为 Ture，则 SMTP 发送处理程序不会替代“收件人” 、“发件人” 或“抄送”  标头中的宏：  
  
-   未设置相应的系统属性。  
  
-   宏拼写错误。  
  
-   宏的值所包含的符号对于 SMTP 标头无效。  
  
 如果满足这些条件，SMTP 发送处理程序使宏不变，例如， **%sourceparty%@somedomain.com** 或**消息从 %sourceparty%**。  
  
 下表列出了可用于生成“收件人” 、“抄送” 和“主题”  标头的宏：  
  
|宏|说明|用于与“收件人”一起使用|用于与“抄送”一起使用|用于与“主题”一起使用|  
|-----------|-----------------|---------------------|---------------------|--------------------------|  
|%MessageID%|BizTalk Server 中消息的全局唯一标识符 (GUID)。 该值来自消息上下文属性 **BTS.MessageID**。|否|是|是|  
|%datetime_bts2000%|YYYYMMDDhhmmsss 格式的 UTC 日期时间，其中，sss 表示秒和毫秒（例如，199707121035234 表示 1997/07/12 10:35:23 和 400 毫秒）。|否|是|是|  
|%datetime%|YYYY-MM-DDThhmmss 格式的 UTC 日期时间（例如 1997-07-12T103508）。|否|是|是|  
|%datetime.tz%|本地日期时间加上 GMT 时区，格式为 YYYY-MM-DDThhmmssTZD（例如 1997-07-12T103508+800）。|否|是|是|  
|%time%|hhmmss 格式的 UTC 时间。|否|是|是|  
|%time.tz%|本地时间加上 GMT 时区，格式为 hhmmssTZD（例如 124525+530）。|否|是|是|  
|%SourceParty%|文件适配器从其接收消息的源参与方的名称。|否|是|是|  
|%SourcePartyQualifier%|文件适配器从其接收消息的源参与方的限定符。|否|是|是|  
|%DestinationParty%|目标参与方的名称。 该值来自消息上下文属性 **BTS.DestinationParty**。|是|是|是|  
|%DestinationPartyQualifier%|目标参与方的限定符。 该值来自消息上下文属性 **BTS.DestinationPartyQualifier**。|否|是|是|  
  
## <a name="see-also"></a>另请参阅  
 [配置 SMTP 适配器时的限制](../core/restrictions-when-configuring-the-smtp-adapter.md)