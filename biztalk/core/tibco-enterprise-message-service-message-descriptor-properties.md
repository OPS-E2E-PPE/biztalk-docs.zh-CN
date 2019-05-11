---
title: TIBCO EMS 消息描述符属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc164c12-6dc3-4b74-9aa9-024e18faf80a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3684b21f7e37757a9d6ab3bf66e352d4518d33bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379902"
---
# <a name="tibco-enterprise-message-service-message-descriptor-properties"></a>TIBCO Enterprise Message Service 消息描述符属性

## <a name="descriptor-properties-and-values"></a>描述符属性和值
下表显示了可用的消息描述符 （TibcoEMSMD 结构） 属性及其相应的类型和值的完整集。  
  
|“属性”|类型|ReplTest1|说明|  
|----------|----------|-----------|-----------|  
|TibcoEMS。相关 Id|string|||  
|TibcoEMS .DelieveryMode|string|一个 PERSISENT 或 NON-PERSISTENT||  
|TibcoEMS。目标|string||只读|  
|TibcoEMS。过期|long|||  
|TibcoEMS。消息 Id|string||只读|  
|TibcoEMS。优先级|integer|从 0 到 9||  
|TibcoEMS。被重新传送|boolean||只读|  
|TibcoEMS。ReplyTo|string|类似于目标||  
|TibcoEMS。时间戳|long||只读|  
  
 只读属性是在用于 TIBCO EMS 的 Microsoft BizTalk 适配器传递消息时由 TIBCO Enterprise Message Service 设置这些属性。 更改此值，但也可以在消息赋值形状中，表达式中不会影响该消息。  
  
 有关必须从 EMS 消息移动到 BizTalk Server 消息的其他属性，必须创建一个属性 DLL 并在项目中使用。  
  
 以下示例属性架构使业务流程，以使用`JMSXDeliveryCount`消息属性。  
  
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
  
 请确保使用目标命名空间;仅使用此命名空间的属性复制到 BizTalk Server 消息或 EMS 消息。 请参阅有关消息上下文属性的详细信息的 BizTalk Server 文档。  
  
## <a name="see-also"></a>请参阅  
[TIBCO EMS 消息上下文属性](../core/message-context-properties-in-biztalk-server.md)