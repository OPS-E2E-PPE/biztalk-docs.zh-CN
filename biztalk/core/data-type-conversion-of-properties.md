---
title: "数据类型的属性转换 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, data type conversion
- MQBYTE property [MQSeries adapters]
- MQLONG property [MQSeries adapters]
- MQCHAR property [MQSeries adapters]
- configuring [MQSeries adapters], data type conversion
ms.assetid: 5b81eab0-f7a1-42f3-b212-a211b2893fd5
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3705f1d0a20a48f0683a15588891ef3fe60889cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="data-type-conversion-of-properties"></a>数据类型转换的属性
MQSeries 消息中的标头属性即为消息本身所包含的数据结构。 在发送和接收消息时，MQSeries 适配器会自动对 MQSeries 消息头中的某些值进行验证和转换。  
  
 下表介绍了 MQSeries 数据类型以及这些类型的验证和转换：  
  
|MQSeries 数据类型|验证和转换|  
|------------------------|-------------------------------|  
|MQLONG|MQSeries 执行验证。 转换为长整型。 如果值无效，则将阻止将消息传至 MQSeries 队列中。|  
|MQCHAR|转换为字符串。|  
|MQBYTE|转换为包含字符 0-9 和 a-f 或 A-F 的字符串，表示该数字的十六进制值。|  
  
 许多 MQSeries 属性是 32 位（4 字节）无符号整数。 因为**uint**不是公共语言规范 (CLS) 的符合标准的类型，你必须将它们分配给**对象**之前在.NET 方法中使用这些类型。  
  
## <a name="see-also"></a>另请参阅  
 [MQSeries 适配器属性](../core/mqseries-adapter-properties.md)   
 [与 BizTalk Server 相关的属性](../core/properties-related-to-biztalk-server.md)   
 [MQSeries 上下文属性](../core/mqseries-context-properties.md)