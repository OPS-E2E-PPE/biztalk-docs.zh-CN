---
title: 带有位置记录的平面文件消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72c17c25-3847-458e-a43e-0dbdc42db749
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3cee44a9fbb3cdce4b75da765caf3fbf8f265d8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990750"
---
# <a name="flat-file-messages-with-positional-records"></a>带有位置记录的平面文件消息
平面文件实例消息中的位置记录包含的各个字段（数据项）都具有预定义长度。 根据这些长度对字段进行解析。 例如，考虑平面文件实例消息中的以下位置记录，该记录包含发货地址（第一行显示了为每个字段保留的字符数）。  
  
```  
123456789012345678901234567890123456789012345678901234567890123456789012345  
US        Alice Smith         123 Maple Street    Mill Valley    CA 90952  
```  
  
 此记录在平面文件架构中的合理定义可描述为名为“shipTo”的位置记录，其中包含以下字段：  
  
- 名为“country/region”的属性，它的对齐方式是左对齐，长度为 10 个字符，字符偏移量为零。  
  
- 名为“name”的元素，它的对齐方式是左对齐，长度为 20 个字符，字符偏移量为零。  
  
- 名为“street”的元素，它的对齐方式是左对齐，长度为 20 个字符，字符偏移量为零。  
  
- 名为“city”的元素，它的对齐方式是左对齐，长度为 15 个字符，字符偏移量为零。  
  
- 名为“state”的元素，它的对齐方式是左对齐，长度为 2 个字符，字符偏移量为零。  
  
- 名为“zip”的元素，它的对齐方式是左对齐，长度为 5 个字符，字符偏移量为一。  
  
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
  
- 用于填充每一字段的未使用部分的字符称为填充字符。 有关详细信息，请参阅[字段填充](../core/field-padding.md)。  
  
- 记录内的可选标记，用于将某记录区别于其他相似的记录。 标记通常出现在记录开头，但也允许在记录的其他地方出现。 有关详细信息，请参阅[位置记录中的标记处理](../core/tag-handling-in-positional-records.md)。 位置记录可定义为具有或不具有标记，但是一旦定义后，就必须根据该定义决定标记的存在与否。  
  
- 在固定的长度字段，相对于伴随填充字符中的数据的对齐方式。 有关详细信息，请参阅[字段对齐](../core/field-justification.md)。  
  
- 其他位置记录或分隔记录中嵌套的位置记录。 有关详细信息，请参阅[嵌套位置记录](../core/nested-positional-records.md)。  
  
- 其字段长度指定为特定的字节数而非特定的字符数的位置记录。 有关详细信息，请参阅[以字节为单位为单位计算位置](../core/position-counting-in-bytes.md)。  
  
  若要帮助您更好地理解如何处理位置平面文件，请参阅位于 \Program Files\Microsoft BizTalk Server\SDK\Samples\Pipelines\AssemblerDisassembler 的 FlatFileReceive 和 FlatFileSend 文件夹中的示例\\。  
  
> [!NOTE]
>  如果平面文件中包含分隔和位置记录，则必须设置**结构**属性的根节点**带分隔符**并**结构**属性从属记录节点**带分隔符**或**位置**根据需要。  
  
> [!NOTE]
>  位置记录中的字段最多包含 50000000 个字符。  
  
## <a name="see-also"></a>请参阅  
 [平面文件消息的结构](../core/structure-of-a-flat-file-message.md)   
 [如何为平面文件消息创建架构](../core/how-to-create-schemas-for-flat-file-messages.md)