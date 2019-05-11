---
title: 数据类型属性的转换 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, data type conversion
- MQBYTE property [MQSeries adapters]
- MQLONG property [MQSeries adapters]
- MQCHAR property [MQSeries adapters]
- configuring [MQSeries adapters], data type conversion
ms.assetid: 5b81eab0-f7a1-42f3-b212-a211b2893fd5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3846fa8cb6fe30e1cae561f7652aba0a02944a28
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353035"
---
# <a name="data-type-conversion-of-properties"></a>属性的数据类型转换
MQSeries 消息中的标头属性是消息本身中包含的数据结构。 MQSeries 适配器会自动验证，并将转换时发送和接收消息的 MQSeries 消息标头中的某些值。  
  
 下表介绍了 MQSeries 数据类型及其验证和转换。  
  
|MQSeries 数据类型|验证和转换|  
|------------------------|-------------------------------|  
|MQLONG|MQSeries 执行验证。 将转换为长整型。 不是有效的值将阻止消息转到 MQSeries 队列。|  
|MQCHAR|将转换为字符串。|  
|MQBYTE|将转换为包含字符 0-9 和 a-f 或 A-F，表示数字的十六进制值的字符串。|  
  
 许多 MQSeries 属性是 32 位 （4 字节） 无符号的整数。 因为**uint**不是公共语言规范 (CLS) 的符合标准的类型，您必须将其分配给**对象**之前使用它们在.NET 方法中的类型。  
  
## <a name="see-also"></a>请参阅  
 [MQSeries 适配器属性](../core/mqseries-adapter-properties.md)   
 [与 BizTalk Server 相关的属性](../core/properties-related-to-biztalk-server.md)   
 [MQSeries 上下文属性](../core/mqseries-context-properties.md)