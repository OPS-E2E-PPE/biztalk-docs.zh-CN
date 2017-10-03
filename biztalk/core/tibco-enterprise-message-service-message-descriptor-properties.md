---
title: "TIBCO 企业消息服务消息描述符属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: message descriptor properties
ms.assetid: fc164c12-6dc3-4b74-9aa9-024e18faf80a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80c75875c44c4d082089fc9394fef390a0f91571
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tibco-enterprise-message-service-message-descriptor-properties"></a>TIBCO Enterprise Message Service 消息描述符属性
下表显示了可用的消息描述符（TibcoEMSMD 结构）属性的完整集以及其对应的类型和值：  
  
|Name|类型|值|说明|  
|----------|----------|-----------|-----------|  
|TibcoEMS .CorrelationID|string|||  
|TibcoEMS .DelieveryMode|string|一个 PERSISENT 或 NON-PERSISTENT||  
|TibcoEMS .Destination|string||只读|  
|TibcoEMS .Expiration|long|||  
|TibcoEMS .MessageID|string||只读|  
|TibcoEMS .Priority|integer|从 0 到 9||  
|TibcoEMS .Redelivered|boolean||只读|  
|TibcoEMS .ReplyTo|string|类似于目标||  
|TibcoEMS .Timestamp|long||只读|  
  
 只读属性是在向用于 TIBCO EMS 的 Microsoft BizTalk 适配器发送消息时由 TIBCO Enterprise 消息服务设置的属性。 更改此值，尽管可能在消息分配形状的表达式中，但不影响消息。  
  
 对于必须从 EMS 消息移动到 BizTalk Server 消息的其他属性，必须创建一个属性 DLL 并在该项目中使用它。  
  
 以下示例属性架构使业务流程能够使用 `JMSXDeliveryCount` 消息属性。  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" targetNamespace="http://schemas.microsoft.com/BizTalk/TibcoEMS-properties" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:annotation>  
        <xs:appinfo>  
            <b:schemaInfo schema_type="property" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" />  
        </xs:appinfo>  
    </xs:annotation>  
    <xs:element name="JMSXDeliveryCount" type="xs:long">  
        <xs:annotation>  
            <xs:appinfo>  
                <b:fieldInfo propertyGuid="f62f1a4b-a528-45fb-b1f8-bd880e9f46db" />  
            </xs:appinfo>  
        </xs:annotation>  
    </xs:element>  
</xs:schema>   
```  
  
 确保使用目标命名空间；仅将使用该命名空间的属性复制到 BizTalk Server 消息或复制到 EMS 消息。 有关消息上下文属性的详细信息，请参阅 BizTalk Server 文档。  
  
## <a name="see-also"></a>另请参阅  
 [消息上下文属性](../core/message-context-properties2.md)