---
title: SWIFT 文本 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SWIFT, text
ms.assetid: 90851d38-7789-4b1b-813b-7943f77ab984
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06e46c8be5da2f62f2b59ce2591e0559367adf08
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990926"
---
# <a name="swift-text"></a>SWIFT 文本
消息文本构成消息负载的财务 (FIN)，并且包含的所有数据字段包含发件人、 收件人和消息类型的字段除外。 这三个字段都包含在标头部分。 有些消息还包含一个可选用户标头，它还可能提供处理信息。  
  
 每个 FIN 消息有效负载包含一系列定义序列中的字段。 这些字段符合以下规则：  
  
- 字段是必需或可选序列中。  
  
- 序列可能包含子序列，并在序列内重复子序列可能。  
  
- 可以使用几种消息类型中的字段。  
  
- 在字段中可能有元素或子字段。 元素或子字段可能是普遍适用于多个字段。  
  
- 组节点表示每个重复的序列。  
  
- 每个字段可能本身具有多个 nodal 级别，每个描述为一条记录。  
  
- 架构元素表示只能最低的级别子字段。  
  
- 通用记录和元素中定义的通用基础架构，如下所述。  
  
- 某些字段可能会出现在几种格式 （如参与方字段）。 此类字段定义为架构中选择字段。  
  
  某些字段具有有限的值集。 大多数情况下，该架构还列出了这些值。 架构定义还包括字符集验证。