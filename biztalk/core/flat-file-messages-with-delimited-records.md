---
title: 带有分隔记录的平面文件消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ad7119b-4e39-43df-9dba-a04382eb6db2
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54b700c0239bed2f1c324085195ca37d2ceaa0c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387896"
---
# <a name="flat-file-messages-with-delimited-records"></a>带有分隔记录的平面文件消息
在平面文件实例消息中的分隔的记录包含嵌套的记录和/或通过预定义的字符或一组字符分隔的各个字段 （数据项）。 对字段进行解析根据这些分隔符。 例如，考虑以下分隔的记录从平面文件实例消息，其中包含假设的采购订单中的两个行项目：  
  
```  
  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Electric-120vac,ITEM926-AA|Baby Monitor|1|39.98|Electric-4AA|2004-01-21  
  
```  
  
 此记录在平面文件架构中的合理定义可描述如下：  
  
- 名为具有子分隔符 （，）、 子订单前缀和标记项的项的分隔的记录。  
  
  -   分隔重复记录名为带有子分隔符的项&#124;，子订单中缀和 ITEM 标记。  
  
  -   名为"partNum"的属性。  
  
  -   名为"productName"的元素。  
  
  -   名为"数量"的元素。  
  
  -   名为"USPrice"的元素。  
  
  -   名为"powerSource"的元素。  
  
- 名为"shipDate"的可选元素。  
  
  给定这些记录和字段定义后，平面文件拆装器会生成这些记录的以下 XML 等效项。  
  
```  
  
<items>  
    <item partNum="872-AA">  
        <productName>Lawnmower</productName>  
        <quantity>1</quantity>  
        <USPrice>148.95</USPrice>  
        <powerSource>Electric-120vac</powerSource>  
    </item>  
    <item partNum="926-AA">  
        <productName>Baby Monitor</productName>  
        <quantity>1</quantity>  
        <USPrice>39.98</USPrice>  
        <powerSource>Electric-4AA</powerSource>  
        <shipDate>2004-01-21</shipDate>  
    </item>  
</items>  
  
```  
  
 有多种会影响接收和发送时，构造时记录的分析方式的分隔记录与相关的注意事项包括：  
  
- 用于替代分隔符的解释，以便它们将被视为数据的一部分的字符。 有关详细信息，请参阅[方式解释的特殊字符作为字段值的一部分](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)。  
  
- 用于将某记录区别与其他类似记录的记录的开始处的可选标记。 有关详细信息，请参阅[分隔记录中的标记处理](../core/tag-handling-in-delimited-records.md)。  
  
- 在相对于伴随填充字符的最小长度字段内的数据的对齐方式。 有关详细信息，请参阅[字段填充](../core/field-padding.md)，[字段对齐](../core/field-justification.md)，并[最小字段长度分隔记录中的](../core/minimum-field-lengths-within-delimited-records.md)。  
  
- 位置记录嵌套在其他分隔记录中。 有关详细信息，请参阅[嵌套位置和分隔记录](../core/nested-positional-and-delimited-records.md)。  
  
- 在固定的长度字段，相对于其伴随填充字符中的数据的对齐方式。 有关详细信息，请参阅[字段对齐](../core/field-justification.md)。  
  
- 有关分隔符的位置的注意事项均与所分隔的数据。 有关详细信息，请参阅[子顺序的注意事项](../core/child-order-considerations.md)。  
  
- 保留和取消分隔符时接收和发送平面文件消息。 有关详细信息，请参阅[分隔符保留和取消](../core/delimiter-preservation-and-suppression.md)。  
  
  若要帮助您更好地理解如何处理分隔平面文件，请参阅位于的 FlatFileReceive 和 FlatFileSend 文件夹中的示例[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Pipelines\AssemblerDisassembler\\。  
  
> [!NOTE]
>  如果平面文件中包含分隔和位置记录，则必须设置**结构**属性的根节点**带分隔符**并**结构**属性从属记录节点**带分隔符**或**位置**根据需要。  
  
> [!NOTE]
>  平面文件中的分隔的字段的最多包含 50000000 个字符的限制。  
  
## <a name="see-also"></a>请参阅  
 [平面文件消息的结构](../core/structure-of-a-flat-file-message.md)   
 [如何为平面文件消息创建架构](../core/how-to-create-schemas-for-flat-file-messages.md)   
 [迁移平面文件记录](../core/migrating-flat-file-records.md)