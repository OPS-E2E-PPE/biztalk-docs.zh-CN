---
title: "包含的位置记录的平面文件消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72c17c25-3847-458e-a43e-0dbdc42db749
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26c9e4551abcbd0fba32b21fb8e4205bece6e82f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="flat-file-messages-with-positional-records"></a>带有位置记录的平面文件消息
平面文件实例消息中的位置记录包含的各个字段（数据项）都具有预定义长度。 根据这些长度对字段进行解析。 例如，考虑平面文件实例消息中的以下位置记录，该记录包含发货地址（第一行显示了为每个字段保留的字符数）。  
  
```  
123456789012345678901234567890123456789012345678901234567890123456789012345  
US        Alice Smith         123 Maple Street    Mill Valley    CA 90952  
```  
  
 此记录在平面文件架构中的合理定义可描述为名为“shipTo”的位置记录，其中包含以下字段：  
  
-   名为“country/region”的属性，它的对齐方式是左对齐，长度为 10 个字符，字符偏移量为零。  
  
-   名为“name”的元素，它的对齐方式是左对齐，长度为 20 个字符，字符偏移量为零。  
  
-   名为“street”的元素，它的对齐方式是左对齐，长度为 20 个字符，字符偏移量为零。  
  
-   名为“city”的元素，它的对齐方式是左对齐，长度为 15 个字符，字符偏移量为零。  
  
-   名为“state”的元素，它的对齐方式是左对齐，长度为 2 个字符，字符偏移量为零。  
  
-   名为“zip”的元素，它的对齐方式是左对齐，长度为 5 个字符，字符偏移量为一。  
  
 给定这些记录和字段定义后，平面文件拆分器将生成此记录的 XML 等效项，如下所示：  
  
```  
<shipTo country/region="US">  
    <name>Alice Smith</name>  
    <street>123 Maple Street</street>  
    <city>Mill Valley</city>  
    <state>CA</state>  
    <zip>90952</zip>  
</shipTo>  
  
```  
  
 有一些与位置记录有关的注意事项将会影响记录的分析（接收时）和构造（发送时）方式，包括：  
  
-   用于填充每一字段的未使用部分的字符称为填充字符。 有关详细信息，请参阅[字段填充](../core/field-padding.md)。  
  
-   记录内的可选标记，用于将某记录区别于其他相似的记录。 标记通常出现在记录开头，但也允许在记录的其他地方出现。 有关详细信息，请参阅[位置记录中的标记处理](../core/tag-handling-in-positional-records.md)。 位置记录可定义为具有或不具有标记，但是一旦定义后，就必须根据该定义决定标记的存在与否。  
  
-   固定的长度字段，相对于随附的填充字符中的数据的对齐方式。 有关详细信息，请参阅[字段理由](../core/field-justification.md)。  
  
-   其他位置记录或分隔记录中嵌套的位置记录。 有关详细信息，请参阅[嵌套位置记录](../core/nested-positional-records.md)。  
  
-   其字段长度指定为特定的字节数而非特定的字符数的位置记录。 有关详细信息，请参阅[位置以字节为单位计数](../core/position-counting-in-bytes.md)。  
  
 若要帮助你更好地了解如何使用位置的平面文件，请参阅位于 files\microsoft 的 FlatFileReceive 和 FlatFileSend 文件夹中的示例[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]\SDK\Samples\Pipelines\AssemblerDisassembler\\。  
  
> [!NOTE]
>  如果你平面文件包含分隔和定位记录，则必须设置**结构**的根节点的属性**带分隔符**和**结构**属性从属记录节点为**带分隔符**或**位置**根据。  
  
> [!NOTE]
>  位置记录中的字段最多包含 50000000 个字符。  
  
## <a name="see-also"></a>另请参阅  
 [平面文件消息的结构](../core/structure-of-a-flat-file-message.md)   
 [如何创建平面文件消息架构](../core/how-to-create-schemas-for-flat-file-messages.md)