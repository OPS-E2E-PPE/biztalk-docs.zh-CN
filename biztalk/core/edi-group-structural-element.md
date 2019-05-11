---
title: EDI 组结构元素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 100a7118-9c02-474e-8685-9e4bb6f52e81
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c05591419e83063d8ebd8f4f79dffe801eeb2a76
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350482"
---
# <a name="edi-group-structural-element"></a>EDI 组结构元素
组包含一个或多个事务集。 一个 EDIFACT 组必须包含相同类型的事务集。 X12 组可能包含类似类型的事务集 （基于事务集-组 (GS01-ST01) 映射） 或相同类型的事务集。 下面列出了类似 X12 事务集 (ST01) 可能会一起发生在单个组 (GS01) 表。  
  
|GS01|ST01|  
|----------|----------|  
|CF|844|  
|CF|849|  
|DX|894|  
|DX|895|  
|FR|821|  
|FR|827|  
|GC|920|  
|GC|924|  
|GC|925|  
|GC|926|  
|HC|837|  
|HC|837_D|  
|HC|837_I|  
|HC|837_P|  
|IA|110|  
|IA|980|  
|IO|310|  
|IO|312|  
|ME|198|  
|ME|200|  
|ME|201|  
|ME|245|  
|ME|261|  
|ME|262|  
|ME|263|  
|ME|833|  
|ME|872|  
|MG|203|  
|MG|206|  
|MG|259|  
|MG|260|  
|MG|264|  
|MG|266|  
|OG|875|  
|OG|876|  
|PK|196|  
|PK|839|  
|QG|878|  
|QG|879|  
|QG|888|  
|QG|889|  
|QG|896|  
|QO|313|  
|QO|315|  
|RO|300|  
|RO|301|  
|RO|303|  
|RQ|836|  
|RQ|840|  
|RS|869|  
|RS|870|  
|SL|135|  
|SL|139|  
|SO|302|  
|SO|311|  
|SO|317|  
|SO|319|  
|SO|322|  
|SO|323|  
|SO|324|  
|SO|325|  
|SO|326|  
|SO|361|  
|TO|197|  
|TO|199|  
|TO|265|  
|TO|485|  
|TO|486|  
|TP|460|  
|TP|463|  
|TP|466|  
|TP|468|  
|TP|490|  
|TP|492|  
|TP|494|  
|WA|140|  
|WA|141|  
|WA|142|  
|WA|143|  
  
> [!NOTE]
>  HIPAA 5010 组还允许单个组中的不同版本的事务集。  
  
 如果处理事务集时遇到异常，则挂起 EDI 参与方属性用于确定是否设置整个交换还是仅失败的事务。  
  
 组必须使用功能组标头 (GS 在 X12 中) 或在 EDIFACT 中，UNG 开头，它必须以功能组尾部 (X12 中的 GE) 或 EDIFACT 中的 UNE 结尾。 组标头包含发送方和接收方代码、 日期和时间、 与标头和尾部，定义可能会包含在功能组和其他信息的事务集的集合的组标识符相匹配的控制编号。 组尾部具有指示组内事务集数目的元素。  
  
 组是可选的 EDIFACT 交换中。 EDIFACT 交换可以包含多个事务集，即使不不存在任何组 （UNG 段不存在）。 在这种情况下，的事务集必须均为相同的类型，如单个组中的事务集必须属于同一类型。 例如，APERAK 和 ORDERS 事务集可能不能同时是存在于单个组或不具有多个组的交换中。  
  
 一组需要在 X12 交换。