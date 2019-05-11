---
title: X12 TA1 确认 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68568a1a-3669-46f4-8edc-8d057b012544
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a168a4112e861ea6b33b232883d320be2aa1ba82
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394754"
---
# <a name="x12-ta1-acknowledgment"></a>X12 TA1 确认
X12 TA1 技术确认报告的交换标头和尾部地址接收方处理的状态。 有效，发送肯定的 TA1 确认的 ISA 和 IEA 的 X12 编码消息时，任何其他内容的状态。 否则，发送并返回错误代码的 TA1 确认。  
  
 X12 TA1 确认遵循到 X12_\<版本号\>_TA1.xsd 架构。 在 ISA/IEA 信封内部发送 TA1 确认。 ISA 和 IEA 与其他任何交换没有什么不同。  
  
 下表中显示了 TA1 确认交换内部的分段。  
  
|TA1 中的字段|字段的名称|映射到传入的交换|ReplTest1|  
|------------------|-------------------|------------------------------------|-----------|  
|TA101|交换控制编号|ISA13-交换控制编号|-|  
|TA102|交换日期|ISA09 Interchange Date|-|  
|TA103|交换时间|ISA10 – 交换时间|-|  
|TA104|交换确认代码 *|不可用|引擎行为：A、 E 或 R<br /><br /> A = 接受<br /><br /> E = 接受存在错误的交换<br /><br /> R = 交换被拒绝/已挂起|  
|TA105|交换注释代码|不可用|处理结果错误代码。 **注意：** 请参阅中的表[X12 TA1 确认错误代码](../core/x12-ta1-acknowledgment-error-codes.md)。|  
  
 \* 引擎行为基于数据元素验证;除了安全和身份验证信息，这将基于配置信息中的字符串比较。