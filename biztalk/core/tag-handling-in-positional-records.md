---
title: "位置记录中标记处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c85d695-6dc9-4200-a453-dc576832adca
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 804647b3cf43b9b6747b2e5f50e05e38313b03d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tag-handling-in-positional-records"></a>处理位置记录中的标记

## <a name="overview"></a>概述
位置记录可以包括一种称为标记的已知字符序列，使用标记可以消除一种类型的记录与其他类型的记录之间的歧义。 这样，平面文件拆装器正确地标识相应**记录**包含正确分析的平面文件记录所需的信息的架构中的节点。  
  
 你可以使用**[标记标识符**和**标记偏移量**属性在一起以指定的标记，并在位置记录其位置。 请注意，这会允许要出现在任何地方中位置的记录，具体取决于你设置的标记**位置长度**和**位置偏移量**内的各个字段的属性该记录，该标记可以解释为与某一关联的数据的一部分或多个这些字段。  
  
 **位置偏移量**属性还允许你以从记录中的数据单独处理标记。 例如，如果标签在记录的开始处出现，它是四个字符的长度，则可设置的值**位置偏移量**到四个，从而有效地跳过的记录中的第一个字段的属性位置记录标记时的第一个字段的值转换为等效的 XML 格式的记录。  

这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 
  
## <a name="see-also"></a>另请参阅  
 [位置记录注意事项](../core/positional-record-considerations.md)   
