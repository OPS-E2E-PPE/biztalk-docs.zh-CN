---
title: 其他平面文件属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c88ad2f-b5a8-46e6-b1b8-61ce6ba910d1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9989d29eadf2487b84e2520755e879cd201b1798
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230037"
---
# <a name="additional-flat-file-properties"></a>其他平面文件属性

## <a name="hidden-properties"></a>隐藏的属性
下表列出了在架构编辑器中未显示的其他平面文件节点属性。 使用这些属性需要在文本编辑器中手动编辑架构文件。  
  
|属性|值|默认值|Description|  
|--------------|------------|-------------------|-----------------|  
|suppress_empty_nodes|**true** 或 **false**|**false**|指示是否在解析程序生成 XML 实例数据后删除空 XML 节点。|  
|generate_empty_nodes|**true** 或 **false**|**true**|为 XML 实例数据中的现有记录生成空节点。|  
|parser_optimization|**速度**或**复杂性**|**速度**|针对速度进行优化可缩短解析时间，但需要处理某些数据多义性问题。 针对复杂度进行优化可处理更广泛的多义性问题，但会影响处理速度。|  
|lookahead_depth|任何正整数；0 表示 lookahead 无限制。|3|在查找匹配数据时向前查找的深度。|  
|allow_early_termination|**true** 或 **false**|**false**|指示位置的记录是否可以提前终止 (**true**) 或必须包含所有记录的字段的数据 (**false**)。|  
|early_terminate_optional_fields|**true** 或 **false**|**false**|启用的可选的尾随字段提前终止 (**true**)。 如果在 BizTalk 编辑器中打开现有架构无此批注，则将默认值设置为添加到它此批注 (**false**)。 **注意：** early_terminate_optional_fields 批注才能起作用，如果 allow_early_termination 设置为"true"。|  
  
 所有这些属性是属性的 **/annotation/appinfo/schemaInfo**元素。  
  
 当**parser_optimization**设置为**复杂性**，相同的组或记录中的多个可选节点时，您可能必须针对架构验证失败。 你可能需要设置**lookahead_depth**为零 (0)，以避免验证错误。  
  
## <a name="see-also"></a>另请参阅  
-  [节点属性](../core/node-properties.md)   
-  **补充节点属性平面文件架构**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]