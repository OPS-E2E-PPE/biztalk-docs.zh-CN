---
title: "EDI 组结构化元素 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 100a7118-9c02-474e-8685-9e4bb6f52e81
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 555d7b86e069adda4f7761b698793fd4ec2af721
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edi-group-structural-element"></a>EDI 组结构元素
组包含一个或多个事务集。 一个 EDIFACT 组必须包含同一类型的事务集。 一个 X12 组可能包含类似类型的事务集（基于事务集 - 组 (GS01-ST01) 映射）或相同类型的事务集。 列表类似 X12 事务集 (ST01)，可以在一个组 (GS01) 一起发生这种情况下表。  
  
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
>  HIPAA 5010 组还允许单一组内存在不同版本的事务集。  
  
 如果在处理事务集时遇到异常，将使用 EDI 参与方属性来确定是挂起整个交换还是仅挂起失败的事务集。  
  
 一个组必须以功能组标头（X12 中的 GS 或 EDIFACT 中的 UNG），且必须以功能组尾部（X12 中的 GE 或 EDIFACT 中的 UNE）结束。 组标头包含发送方和接收方代码、日期和时间、与标头和尾部匹配的控制编号、可能包括在功能组内的用于定义事务集的集合的组标识符以及其他信息。 组尾部具有指示组内事务集数目的元素。  
  
 组在 EDIFACT 交换内是可选的。 即使不存在组（不存在 UNG 段），一个 EDIFACT 交换也可包含多个事务集。 在此情况下，所有事务集都必须具有同一类型，因为一个组中的事务集的类型必须相同。 例如，APERAK 和 ORDERS 事务集不能同时出现在一个组或不具有多个组的交换中。  
  
 组在 X12 交换内是必需的。