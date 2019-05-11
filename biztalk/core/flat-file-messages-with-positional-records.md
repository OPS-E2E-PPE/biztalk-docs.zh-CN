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
ms.openlocfilehash: e3b780953c9a1f2c538b63f47942eae5f4ce60df
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345320"
---
# <a name="flat-file-messages-with-positional-records"></a>带有位置记录的平面文件消息
位置记录在平面文件实例消息中的包含的各个字段 （数据项），每个预定义长度。 根据这些长度，对字段进行解析。 例如，考虑平面文件实例消息，其中包含发货地址 （第一行显示为每个字段保留的字符数） 中的以下位置记录。  
  
```  
123456789012345678901234567890123456789012345678901234567890123456789012345  
US        Alice Smith         123 Maple Street    Mill Valley    CA 90952  
```  
  
 此记录在平面文件架构中的合理定义可描述为位置记录名为 shipTo 包含以下字段：  
  
- 名为的属性，它是左对齐，国家/地区的长度，具有零个字符的偏移量的 10 个字符。  
  
- 名为名称为左对齐的元素，长度为 20 个字符的零个字符的偏移量。  
  
- 名为街道是左对齐的元素，长度为 20 个字符的零个字符的偏移量。  
  
- 名为 city，它是左对齐的元素，偏移量为 15 个字符长度，以零个字符。  
  
- 名为状态，它是左对齐的元素，2 个字符的长度，零字符偏移量。  
  
- 名为 zip，它是左对齐的元素，5 个字符的长度，一个字符偏移量。  
  
  给定这些记录和字段定义后，平面文件拆装器将生成此记录的以下 XML 等效项。  
  
```  
<shipTo country/region="US">  
    <name>Alice Smith</name>  
    <street>123 Maple Street</street>  
    <city>Mill Valley</city>  
    <state>CA</state>  
    <zip>90952</zip>  
</shipTo>  
  
```  
  
 有数个会影响接收和发送时，构造时记录的分析方式的位置记录相关的注意事项包括：  
  
- 用来填充名为的填充字符的每个字段的未使用的部分的字符。 有关详细信息，请参阅[字段填充](../core/field-padding.md)。  
  
- 记录中的可选标记用于将记录与其他相似的记录区分开来。 标记通常出现在的记录，但是允许任意位置的开头。 有关详细信息，请参阅[位置记录中的标记处理](../core/tag-handling-in-positional-records.md)。 位置记录可以定义为具有或不具有标记，但定义后，该标记必须存在与否，基于所定义。  
  
- 在固定的长度字段，相对于伴随填充字符中的数据的对齐方式。 有关详细信息，请参阅[字段对齐](../core/field-justification.md)。  
  
- 位置记录嵌套在其他位置或分隔记录。 有关详细信息，请参阅[嵌套位置记录](../core/nested-positional-records.md)。  
  
- 字段长度指定为特定的字节数，而不是特定数目的字符的位置记录。 有关详细信息，请参阅[以字节为单位为单位计算位置](../core/position-counting-in-bytes.md)。  
  
  若要帮助您更好地理解如何处理位置平面文件，请参阅位于 \Program Files\Microsoft BizTalk Server\SDK\Samples\Pipelines\AssemblerDisassembler 的 FlatFileReceive 和 FlatFileSend 文件夹中的示例\\。  
  
> [!NOTE]
>  如果平面文件中包含分隔和位置记录，则必须设置**结构**属性的根节点**带分隔符**并**结构**属性从属记录节点**带分隔符**或**位置**根据需要。  
  
> [!NOTE]
>  位置记录中的字段具有最多包含 50000000 个字符的限制。  
  
## <a name="see-also"></a>请参阅  
 [平面文件消息的结构](../core/structure-of-a-flat-file-message.md)   
 [如何为平面文件消息创建架构](../core/how-to-create-schemas-for-flat-file-messages.md)