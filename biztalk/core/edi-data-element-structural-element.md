---
title: "EDI 数据元素结构化元素 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 775e8b87-b952-46d2-a506-5174d216a9aa
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 600edb30ff157a520ac67eebce58428a62e27c8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edi-data-element-structural-element"></a>EDI 数据元素：结构元素
数据元素是消息中的基本数据单元。 数据元素由数据元素分隔符分隔，默认情况下 X12 是星号，EDIFACT 是加号。 数据元素的可行性定义为：必需、可选或条件。  
  
 数据元素可以是简单或复合。 简单数据元素为数值型，它们是最低级别的数据。 复合数据元素是一串子元素，这些子元素是由复合元素分隔符分隔的简单数据元素。 默认状态下，复合元素分隔符对于 x12 和 EDIFACT 是冒号。  
  
 对于 EDIFACT 编码的消息，如果经由 EDI 发送的数据需要发送任何定义用作分隔符的字符，则需要使用转义符来指明后面的字符不是分隔符，而是数据的一部分。 默认情况下，转义符为问号 (?)。  
  
> [!NOTE]
>  X12 不支持转义符。 如果遇到作为 X12 编码的交换数据一部分的分隔符，则交换将在接收方或发送方挂起。