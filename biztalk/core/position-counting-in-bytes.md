---
title: "以字节为单位计数的位置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5cf666ec-d15e-4d2d-9df9-49189f352c65
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3cdb7bbf1f0d6af04f0cc28ed1bdb7477b259de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="position-counting-in-bytes"></a>以字节为单位计数的位置

## <a name="overview"></a>概述

你可以使用**计数位置中字节**属性**架构**节点： 

* 指定如何值你输入**位置长度**和**位置偏移量**解释的位置记录中的各个字段的属性
* 指定如何值你输入**标记偏移量**解释的位置记录本身的属性

默认情况下，这些值被解释为字符数。 但当**计数位置中字节**属性设置为**True**，这些值都会被解释为字节数。  
  
 设置**计数位置中字节**属性**True**可能需要处理多字节字符时设置 （MBCS 或 DBCS） 的数据，或当平面文件消息源自 SAP，大型机，或其他可能计数以字节为单位的位置的系统。  
  
 当用于对字符进行编码的字节数是变量时，以字节为单位计算字段长度可能十分复杂，并可能引发有关确定字段边界的一些问题。 在这种情况下,如果平面文件拆装器对平面文件进行解析，则它将尝试根据所使用的字符编码的相关知识，进行相应的解析决策。  
  
 此类型的解析决策示例涉及 MBCS 字符编码中的前导字节。 前导字节是已知字节值，用于开始对多字节字符编码并永远不会单独出现。 在使用字节而非字符指定字段长度时，可能会出现以下情况：字段中最后的字节是前导字节，而前导字节本身不能构成完整字符。 在这种情况下，平面文件拆装器将该前导字节的上一字符视为前一字段中的最后的字符，并从该前导字节开始解析下一字段。  

这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 
  
## <a name="see-also"></a>另请参阅  
 [位置记录注意事项](../core/positional-record-considerations.md)   
