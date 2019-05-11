---
title: 其他平面文件属性 |Microsoft Docs
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
ms.openlocfilehash: cab0391fd8ffb8388d113301f7a3655f703c2c77
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360734"
---
# <a name="additional-flat-file-properties"></a>其他平面文件属性

## <a name="hidden-properties"></a>隐藏的属性
下表列出了不会出现在架构编辑器中的其他平面文件节点属性。 使用这些属性需要手动编辑在文本编辑器中的架构文件。  

|属性|值|默认值|Description|  
|--------------|------------|-------------------|-----------------|  
|suppress_empty_nodes|**true** 或 **false**|**false**|指示在解析程序生成的 XML 实例数据后删除空 XML 节点。|  
|generate_empty_nodes|**true** 或 **false**|**true**|在 XML 实例数据中生成空节点的现有记录。|  
|parser_optimization|**速度**或**复杂性**|**speed**|优化速度缩短解析时间有关，但需要处理某些数据多义性问题。 针对复杂度进行优化处理更广泛的多义性问题，但会影响处理速度。|  
|lookahead_depth|任何正整数;零 (0) 表示 lookahead 无限制。|3|向前查找匹配的数据的方式。|  
|allow_early_termination|**true** 或 **false**|**false**|指示位置记录是否可以提前终止 (**，则返回 true**) 或必须包含所有记录的字段的数据 (**false**)。|  
|early_terminate_optional_fields|**true** 或 **false**|**false**|允许提前终止可选尾部字段 (**，则返回 true**)。 如果在 BizTalk 编辑器中打开现有架构无此批注，则将使用默认值设置为添加到它此批注 (**false**)。 **注意：** 时，early_terminate_optional_fields 批注才会生效在 allow_early_termination 设置为"true"。|  

 所有这些属性是属性**是 /annotation/appinfo/schemaInfo**元素。  

 当**parser_optimization**设置为**复杂性**，同一个组或记录中的许多可选节点时，您可能必须根据架构验证失败。 可能需要设置**lookahead_depth**为零 (0) 以避免出现验证错误。  

## <a name="see-also"></a>请参阅  
- [节点属性](../core/node-properties.md)   
- **平面文件架构的补充节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
