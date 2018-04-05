---
title: SWIFT 文本 |Microsoft 文档
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
ms.openlocfilehash: c80d8ee0343cbf8ac96d57119ef198d623159b26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="swift-text"></a>SWIFT 文本
消息文本构成财务 (FIN) 消息的负载，并包含所有数据字段包含消息类型，发送方和接收方，字段除外。 这三个字段都包含在标头部分。 有些消息还包含一个可选用户标头，它可能还提供处理信息。  
  
 每个 FIN 消息负载包含的一系列定义的序列中的字段。 这些字段符合以下规则：  
  
-   字段可能必需或可选在序列中。  
  
-   序列可能包含子序列，并且子序列可以重复序列内。  
  
-   你可以使用几种消息类型中的字段。  
  
-   在字段中，可能有元素或子字段。 元素或子字段可能是普遍适用于多个字段。  
  
-   每个重复的序列由组节点表示。  
  
-   每个字段可能本身具有多个 nodal 级别，每个作为记录所述。  
  
-   架构元素表示仅最低的级别子字段。  
  
-   通用记录和元素中定义的通用基础架构，如下所述。  
  
-   某些字段可能在几种格式 （如方字段） 中表示。 此类字段被定义为架构中的选择字段。  
  
 某些字段具有有限组值。 大多数情况下，架构列出了这些值。 架构定义还包括字符集验证。