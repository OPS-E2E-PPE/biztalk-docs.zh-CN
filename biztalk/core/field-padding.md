---
title: "字段填充 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 47017036-7d64-4222-b574-d2913bf69358
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56aa8490bd9e72677c9c8eefa73e7f6bd8438dfd
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="field-padding"></a>字段填充

## <a name="overview"></a>概述

分隔记录和位置记录中字段包含的数据小于为该字段保留的字符或字节数时，这些字段将使用填充字符。 这些字符将占用数据不需要的字段部分（如果有的话）。 按字段基础使用指定的填充字符**填充字符**和**填充字符类型**的相应属性**Field 元素**和**字段特性**节点。 如果没有为特定字段指定填充字符，该字段将使用默认填充字符：空格 (" ")。  
  
## <a name="inbound-instances"></a>入站的实例
 对于入站实例消息，不管特定记录是位置记录还是分隔记录，在实例消息翻译成其等效 XML 形式时，平面文件拆装器都会丢弃特定字段的指定或默认填充字符的前导或尾部实例。 是否它是前导空格或尾随的相关的填充字符将被丢弃的实例取决于是否**理由**相应属性**Field 元素**和**字段属性**节点设置为**右**或**左**分别。  

## <a name="outbound-instances"></a>出站实例  
 对于出站实例消息，平面文件组装器将适当数量的指定或默认填充字符插入到字段中，以使字段的长度正确。 将插入填充字符，之前或之后的数据字符基于是否 **理由** 的相应属性 **Field 元素** 和 **字段特性** 节点设置为 **右** 或 **左**, 分别。  
  
 当要填充的出站实例消息中的字段包含在一个位置的记录，**位置偏移量**和**位置长度**的相应属性**字段元素**或**字段特性**节点，加上数据的字符数的字段必须包含，确定是否任何填充字符是必需的如果是，多少。 要填充的出站实例消息中的字段包含在分隔记录，填充字符时仅插入时的值**填充字符的最小长度**的相应属性**字段元素**或**字段特性**节点超过数据字符数。  

## 
这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

## <a name="see-also"></a>另请参阅  
 [字段注意事项](../core/field-considerations.md)   
 [字段理由](../core/field-justification.md)   
 [位置记录中的字段位置规范](../core/specification-of-field-positions-within-positional-records.md)  