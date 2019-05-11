---
title: 字段填充 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47017036-7d64-4222-b574-d2913bf69358
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4eac7354d7e867ceca759caa40098ef09ed2a2d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388151"
---
# <a name="field-padding"></a>字段填充

## <a name="overview"></a>概述

填充字符分隔和位置记录中的字段中使用的字符或该字段为保留的字节数小于字段中包含的数据。 如果有，这些字符将占用的数据，不需要的字段的部分。 填充字符指定字段的字段使用**填充字符**并**填充字符类型**属性的相应**字段元素**和**字段属性**节点。 如果没有填充字符指定为特定字段，默认填充字符： 空格 ("")，用于表示该字段。  
  
## <a name="inbound-instances"></a>入站的实例
 对于入站的实例消息，而不管特定记录是位置或分隔，平面文件拆装器将放弃前导空格或尾随为指定的实例或默认填充字符的特定字段，因为在实例消息转换为其等效 XML 形式。 无论它是前导空格或尾随的相关的填充字符将被丢弃的实例取决于是否**理由**属性的相应**Field 元素**和**字段特性**节点设置为**右**或**左侧**分别。  

## <a name="outbound-instances"></a>出站实例  
 对于出站实例消息，平面文件组装器会插入适当数量的指定或默认填充字符字段，以便该字段的长度正确。 将插入填充字符之前或之后的数据字符基于是否**理由**属性的相应**Field 元素**和**字段属性**节点设置为**右**或**左侧**分别。  
  
 当要填充的出站实例消息中的字段包含在位置记录**位置偏移量**并**位置长度**的相应属性**字段元素**或**字段属性**节点，结合的数据字段必须包含的字符数确定是否所有填充字符都是必需的以及如果是这样，多少。 要填充的出站实例消息中的字段包含在分隔记录中，填充字符时，仅插入时的值**填充字符的最小长度**的相应属性**字段元素**或**字段属性**节点超过数据字符数。  

## 
这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

## <a name="see-also"></a>请参阅  
 [字段注意事项](../core/field-considerations.md)   
 [字段对齐](../core/field-justification.md)   
 [位置记录中的字段位置规范](../core/specification-of-field-positions-within-positional-records.md)  