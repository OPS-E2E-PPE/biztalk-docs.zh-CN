---
title: 分隔记录的平面文件消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ad7119b-4e39-43df-9dba-a04382eb6db2
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5dc9eb0253e2bfe8824f6395e1c619c23f0e551
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="flat-file-messages-with-delimited-records"></a>带有分隔记录的平面文件消息
平面文件实例消息中的分隔记录包含嵌套记录和/或使用预定义的字符或一组字符分隔的各个字段（数据项）。 根据这些分隔符对字段进行解析。 例如，下面是某个平面文件实例消息中的分隔记录，其中包含假设的采购订单中的两个行项目：  
  
```  
  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Electric-120vac,ITEM926-AA|Baby Monitor|1|39.98|Electric-4AA|2004-01-21  
  
```  
  
 此记录在平面文件架构中的合理定义可描述如下：  
  
-   名为“items”的分隔记录带有子分隔符 (,)、子订单前缀和 ITEMS 标记。  
  
    -   分隔，一个名为具有子分隔符 &#124;项的重复记录;，子顺序中缀，并标记项。  
  
    -   名为“partNum”的属性。  
  
    -   名为“productName”的元素。  
  
    -   名为“quantity”的元素。  
  
    -   名为“USPrice”的元素。  
  
    -   名为“powerSource”的元素。  
  
-   名为“shipDate”的可选元素。  
  
 给定这些记录和字段定义后，平面文件拆分器将生成这些记录的 XML 等效项，如下所示：  
  
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
  
 有一些与分隔记录有关的注意事项将会影响记录的分析（接收时）和构造（发送时）方式，包括：  
  
-   用于替代分隔符的解释以将其作为数据的一部分进行处理的字符。 有关详细信息，请参阅[如何解释的特殊字符作为字段值的一部分](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)。  
  
-   位于记录开始位置、用于将该记录与其他类似记录区分开的可选标记。 有关详细信息，请参阅[中分隔记录的标记处理](../core/tag-handling-in-delimited-records.md)。  
  
-   数据在最小长度字段中相对于伴随填充字符的对齐方式。 有关详细信息，请参阅[字段填充](../core/field-padding.md)，[字段理由](../core/field-justification.md)，和[最小值字段长度内分隔记录](../core/minimum-field-lengths-within-delimited-records.md)。  
  
-   其他分隔记录中嵌套的位置记录。 有关详细信息，请参阅[嵌套位置和分隔记录](../core/nested-positional-and-delimited-records.md)。  
  
-   数据在固定长度字段中相对于其伴随填充字符的对齐方式。 有关详细信息，请参阅[字段理由](../core/field-justification.md)。  
  
-   有关分隔符相对于所分隔数据的位置的注意事项。 有关详细信息，请参阅[子顺序注意事项](../core/child-order-considerations.md)。  
  
-   在接收和发送平面文件消息时分隔符的保留和取消。 有关详细信息，请参阅[分隔符保留和抑制](../core/delimiter-preservation-and-suppression.md)。  
  
 若要帮助你更好地了解如何使用带分隔符的平面文件，请参阅位于的 FlatFileReceive 和 FlatFileSend 文件夹中的示例[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Pipelines\AssemblerDisassembler\\。  
  
> [!NOTE]
>  如果你平面文件包含分隔和定位记录，则必须设置 **结构** 的根节点的属性 **带分隔符** 和 **结构** 属性为从属记录节点 **带分隔符** 或 **位置** 根据。  
  
> [!NOTE]
>  平面文件中的分隔字段最多包含 50000000 个字符。  
  
## <a name="see-also"></a>另请参阅  
 [平面文件消息的结构](../core/structure-of-a-flat-file-message.md)   
 [如何创建平面文件消息架构](../core/how-to-create-schemas-for-flat-file-messages.md)   
 [迁移平面文件记录](../core/migrating-flat-file-records.md)