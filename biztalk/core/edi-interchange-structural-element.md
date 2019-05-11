---
title: EDI 交换结构元素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03f47ae2-fa0f-4d88-a700-85f3d515d2d0
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 416624a6aef721b6d792320aa5a3ac71650fb131
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389226"
---
# <a name="edi-interchange-structural-element"></a>EDI 交换结构元素
交换是 EDI 消息的最高级别的结构元素。 它包含由两个合作伙伴交换的一个或多个组的集合。 交换的目标必须是一个贸易合作伙伴。 交换可能包含一种或多种类型的事务集/消息。  
  
 使用交换时，交换自身以及其中的组和事务集/消息由标头定义。 段、数据元素和子元素由分隔符分隔。 每个分隔符都有一个默认值，但可以为参与方定义其他字符。 在 EDIFACT 交换中，在交换中用作分隔符的所选字符是在单独的 UNA 交换标头中定义的。 而在 X12 交换中，分隔符是在 ISA 交换标头中定义的。 请注意，在 X12 中，数据元素分隔符是位于第四个字符位置的字符，数据段终止符是位于最后一个字符位置的字符。 其他 X12 分隔符和全部 EDIFACT 分隔符由字段定义，例如 X12 组件分隔符由 ISA16 字段定义，EDIFACT 数据元素分隔符由 UNA2 字段定义。  
  
 交换包括一个用于定义 EDI 消息的信封。 该信封必须以交换标头（X12 中的 ISA 或 EDIFACT 中的 UNA/UNB）开头，且必须以交换尾部 (IEA/UNZ) 结束。 交换标头包括定义以下各项的元素：发送方和接收方、日期和时间、版本号、与标头和尾部匹配的控制编号以及其他信息。  
  
 ISA12 和 GS8 字段（对于 X12 交换）和 UNH2 字段（对于 EDIFACT 交换）包含发现架构所必需的版本信息。  
  
 交换尾部具有指示交换中的组数的元素。  
  
> [!NOTE]
>  功能安全标头、功能保证标头、功能安全值段和功能安全尾部段均超出 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI 和 AS2 的范围。 如果收到具有这些段的交换，则会挂起交换并显示错误日志，指示无法识别这些段。