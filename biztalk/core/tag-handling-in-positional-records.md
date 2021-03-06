---
title: 在位置记录中标记处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c85d695-6dc9-4200-a453-dc576832adca
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fe1ec096926dc8737c6657ca99fb3cb90b59673
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291624"
---
# <a name="tag-handling-in-positional-records"></a>位置记录中的标记处理

## <a name="overview"></a>概述
位置记录可以包含的已知字符序列，称为一个标记，它可用于消除从另一个记录的一种类型的歧义。 这样，平面文件拆装器以便正确标识适当**记录**中包含正确解析平面文件记录所需的信息的架构的节点。  
  
 可以使用 **[标记标识符**并**标记偏移量**属性一起以指定的标记，并在位置记录其位置。 请注意，这会允许标记可以根据你设置的位置记录中任意位置出现**位置长度**并**位置偏移量**内的各字段的属性该记录，该标记可以解释为与某个关联的数据的一部分或多个字段。  
  
 **位置偏移量**属性还允许您从记录中的数据单独处理标记。 例如，如果标签的记录开始时，它是长度为四个字符，则可以设置的值**位置偏移量**到四个，从而有效地跳过的记录中的第一个字段的属性位置记录标记中的记录的等效 XML 格式翻译第一个字段的值时。  

这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 
  
## <a name="see-also"></a>请参阅  
 [位置记录注意事项](../core/positional-record-considerations.md)   
