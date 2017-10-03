---
title: "为技术确认 EDIFACT CONTRL 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f2a7564-dbd3-48d0-b0a6-a77a0560459f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8376e3249a102486c1bef4d92a7512c8aa29636c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edifact-contrl-message-as-technical-acknowledgment"></a>作为技术确认的 EDIFACT CONTRL 消息
如果已在业务配置文件设置或贸易合作伙伴协议（或者没有在两个业务配置文件之间定义协议时在后备协议）中选择生成技术确认，或者如果消息中的 UNB9 字段设置为“2”，则会生成 CONTRL 消息作为技术确认。 此确认会报告交换回执的结果。  
  
 CONTRL 技术确认包括以下段：  
  
-   UNH 消息标头（必需）  
  
-   UCI 交换响应，用于标识交换主题并指示交换回执的性质（必需）。 UCI 段的最大出现次数为 1；因此，它将报告在一个控制段中遇到的第一个错误。  
  
-   UNT 消息尾部（必需）。  
  
 错误在 UCI5“语法错误代码”数据元素中报告。 与 X12 编码的交换不同，EDIFACT 编码的交换没有“已接受但存在错误”条件。  
  
> [!NOTE]
>  仅当传入的 EDIFACT 消息重复或信封中存在错误（例如，字符集存在问题）时，CONTRL 回执（EDIFACT 技术确认）才报告“已拒绝”状态。 与 X12 在 TA1 确认的 TA104 字段中报告“已接受交换但存在错误”不同，EDIFACT 不在 CONTRL 技术确认中报告这一状态。 如果接受了 EDIFACT 消息的一部分，CONTRL 技术确认将报告“已接受”。 在某些情况下，虽然消息的一部分将被拒绝，但 CONTRL 确认仍将报告“已接受”状态。 在这种情况下，UCI5 元素可能报告错误。  
  
 CONTRL 技术确认包括以下数据元素：  
  
|Data 元素|Name|用法|  
|------------------|----------|-----------|  
|UNH1|消息参考编号|-|  
|UNH2|消息标识符子组件|这些子组件为：<br /><br /> -1 = CONTRL<br /><br /> - 2 = 4<br /><br /> - 3 = 1<br /><br /> -4 = 取消|  
|UCI1|交换控制编号|映射自已接收消息的 UNB5 字段。|  
|UCI2|交换发送方|映射自已接收消息的 UNB2 字段。 第一个子组件（标识）是必需的。 第二个子组件（代码限定符）和第三个组件（反向路由地址）是可选的。|  
|UCI3|交换接收方|映射自已接收消息的 UNB3 字段。 第一个子组件（标识）是必需的。 第二个子组件（代码限定符）是可选的。|  
|UCI4|操作代码|这些操作代码为：<br /><br /> -如果接受交换的 8<br /><br /> -如果接受交换的 7，但某些事务集将被拒绝<br /><br /> -如果该交换拒绝由于 UNA 或 UNB 段中出现错误的 4<br /><br /> 这是一个必需的数据元素。|  
|UCI5|语法错误代码|标识错误情况（如果有）。 有关详细信息，请参阅[EDIFACT CONTRL 确认错误代码](../core/edifact-contrl-acknowledgment-error-codes.md)。<br /><br /> 此数据元素为条件可选。|  
|UCI6|服务段标记|标识在 UCI.5 数据元素中确定了错误情况的段。<br /><br /> 此数据元素为条件可选。|  
|UCI7|数据元素标识|标识在 UCI.5 数据元素中确定了错误情况的数据元素。 UCI7 的子组件为：<br /><br /> 元素的位置错误的数据段 （必需） 中<br /><br /> -错误组件数据元素中位置段 (条件 optionality)<br /><br /> 的段 (条件 optionality) 中的错误的数据元素匹配项|  
|UCI8|-|-|  
|UNT1|段计数|-|  
|UNT2|消息参考编号|-|