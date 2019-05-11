---
title: 字段对齐 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04380208-9bfd-43cf-a279-104daea2b978
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f6ddea01774cdae6fb17c27212f2d53351fa072
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345566"
---
# <a name="field-justification"></a>字段对齐

## <a name="overview"></a>概述
字段对齐问题是否之前出现的字段中的数据字符 （左对齐） 还是之后 （右对齐） 任何伴随的填充字符。  
  
 有时字段中包含的数据字符不需要的所有空间专用于该字段。 这是最常在位置记录，其中的字节数或专用于字段的字符数固定的则返回 true，由**位置长度**并**位置偏移量**属性。 很常见的项的数据小于字段长度，以填充字符来填充字段的未使用部分此类方案中。  
  
 此类填充也可能发生在分隔记录时的值**填充字符的最小长度**属性超过存储相关数据项所需的空间。  
  
 在这两个此类情况下，值**理由**属性 (**左侧**或**右**) 的相关**字段元素**或**字段属性**节点确定是否填充字符将后面 （左对齐） 的数据字符或是否填充字符将前面 （右对齐） 的数据字符。  
  
 当平面文件拆装器将平面文件实例消息转换成等效的 XML 实例消息，**理由**属性解析相应的字段时使用。 当平面文件组装器将 XML 实例消息转换成等效的平面文件实例消息，**理由**属性用于确定当关联的填充字符与特定字段中，如果有的话，应添加到数据流： 之前或之后的相应数据字符。  
  
## <a name="see-also"></a>请参阅  
- [字段注意事项](../core/field-considerations.md)   
- 以下属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:  
    - 对齐 （平面文件架构的节点属性）  
    - 位置偏移量 （平面文件架构的节点属性）  
    - 位置长度 （平面文件架构的节点属性）