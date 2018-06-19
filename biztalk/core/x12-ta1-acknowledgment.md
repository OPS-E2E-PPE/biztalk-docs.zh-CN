---
title: X12 TA1 确认 |Microsoft 文档
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
ms.openlocfilehash: f6a3de45744b40335999c1471165ff851ec60664
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "25973699"
---
# <a name="x12-ta1-acknowledgment"></a>X12 TA1 确认
X12 TA1 技术确认通过地址接收方报告交换标头和尾部的处理状态。 无论其他内容的状态如何，当 X12 编码消息的 ISA 和 IEA 有效时，将会发送肯定的 TA1 确认。 否则，将发送带有错误代码的 TA1 确认。  
  
 X12 TA1 确认符合 X12_\<版本号\>_TA1.xsd 架构。 TA1 确认是在 ISA/IEA 信封内部发送的。 ISA 和 IEA 与其他任何交换没有任何区别。  
  
 下表显示了 TA1 确认交换内部的分段。  
  
|TA1 中的字段|字段的名称|映射到传入交换|“值”|  
|------------------|-------------------|------------------------------------|-----------|  
|TA101|交换控制编号|ISA13 - 交换控制编号|-|  
|TA102|交换日期|ISA09 交换日期|-|  
|TA103|交换时间|ISA10 – 交换时间|-|  
|TA104|交换确认代码*|N/A|引擎行为︰ A、 E 或 R<br /><br /> A = 接受<br /><br /> E = 已接受但存在错误的交换<br /><br /> R = 已拒绝/已挂起的交换|  
|TA105|交换注释代码|N/A|处理结果错误代码。 **注意：** 中的，请参阅表[X12 TA1 确认错误代码](../core/x12-ta1-acknowledgment-error-codes.md)。|  
  
 \* 引擎行为基于数据元素验证;除了安全和身份验证信息，将关闭中配置信息的字符串比较基于其。