---
title: 作为技术确认的 EDIFACT CONTRL 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f2a7564-dbd3-48d0-b0a6-a77a0560459f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8048578c18c68dd424e23a0454d77a821e701ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350121"
---
# <a name="edifact-contrl-message-as-technical-acknowledgment"></a>作为技术确认的 EDIFACT CONTRL 消息
如果您已选择在业务配置文件设置或贸易合作伙伴协议 （或如果两个业务配置文件之间不定义任何协议的后备协议），生成技术确认，或消息中的 UNB9 字段设置为"2"，将 CONTRL将生成消息作为技术确认。 此确认会报告交换回执的结果。  
  
 CONTRL 技术确认包括以下段：  
  
- UNH 消息标头 （必需）  
  
- UCI 交换响应，用于标识交换主题并指示交换回执 （必需） 的性质。 UCI 段具有 1; 最大出现次数因此，它报告在一个控制段中遇到的第一个错误。  
  
- UNT 消息尾部 （必需）。  
  
  在 UCI5"语法错误代码"、 数据元素中报告错误。 没有与 X12 编码的交换为 EDIFACT 编码的交换，没有"已接受但存在错误"条件。  
  
> [!NOTE]
>  仅当传入的 EDIFACT 消息重复或信封 （例如，问题的字符集） 中有错误时，CONTRL 回执 （EDIFACT 技术确认） 报告的状态为"已拒绝"。 EDIFACT 不在 CONTRL 技术确认中报告的状态为"已接受交换但出现错误"，如 X12 在 TA1 确认的 TA104 字段中作用。 如果接受 EDIFACT 消息的一部分，CONTRL 技术确认将报告"已接受"。 在某些情况下，将被拒绝消息的一部分，但 CONTRL 确认仍将报告的状态为"已接受"。 在这种情况下，UCI5 元素可能报告错误。  
  
 CONTRL 技术确认包括以下数据元素：  
  
|数据元素|“属性”|用法|  
|------------------|----------|-----------|  
|UNH1|消息参考编号|-|  
|UNH2|消息标识符子组件|子组件为：<br /><br /> -1 = CONTRL<br /><br /> - 2 = 4<br /><br /> - 3 = 1<br /><br /> -4 = 取消|  
|UCI1|交换控制编号|映射自已接收消息的 UNB5 字段。|  
|UCI2|交换发送方|映射自已接收消息的 UNB2 字段。 第一个子组件 （标识） 是必需的。 第二个子组件 （代码限定符） 和第三个组件 （反向路由地址） 是可选的。|  
|UCI3|交换接收方|映射自已接收消息的 UNB3 字段。 第一个子组件 （标识） 是必需的。 第二个子组件 （代码限定符） 是可选的。|  
|UCI4|操作代码|这些操作代码为：<br /><br /> -8 如果交换被接受<br /><br /> -7 如果交换被接受，但某些事务集将被拒绝<br /><br /> -4 如果交换被拒绝由于 UNA 或 UNB 段中出现错误<br /><br /> 这是必需的数据元素。|  
|UCI5|语法错误代码|标识错误条件 （如果有）。 有关详细信息，请参阅[EDIFACT CONTRL 确认错误代码](../core/edifact-contrl-acknowledgment-error-codes.md)。<br /><br /> 此数据元素为条件可选。|  
|UCI6|服务段标记|标识在 UCI.5 数据元素中确定了错误情况的段。<br /><br /> 此数据元素为条件可选。|  
|UCI7|数据元素标识|标识在 UCI.5 数据元素中确定了错误情况的数据元素。 UCI7 的子组件为：<br /><br /> -中的位置错误数据元素的段 （必需）<br /><br /> -错误组件数据元素的位置中段 （条件可选）<br /><br /> 的错误数据元素在段 （条件可选） 中匹配项|  
|UCI8|-|-|  
|UNT1|段的计数|-|  
|UNT2|消息参考编号|-|