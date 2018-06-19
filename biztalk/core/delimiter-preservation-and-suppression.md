---
title: 分隔符保留和抑制 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30985b94-625e-411a-8137-1c129bc197bf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0b5a5c60d42892479feacc93aedb3802b11308c
ms.sourcegitcommit: d572ae5c887898adedcb3dfc5f83841beedd3434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/06/2017
ms.locfileid: "26335497"
---
# <a name="delimiter-preservation-and-suppression"></a>分隔符保留和抑制

## <a name="overview"></a>概述
有两个属性应用于分隔记录：**空数据的保留分隔符**和**禁止显示尾随分隔符**。 使用这些属性控制的平面文件汇编如何处理尾随分隔符不存在的数据与关联的分隔符。 当你将设置**空数据的保留分隔符**属性**是**（这是默认设置） 中的已翻译的平面文件消息包括分隔符：  
  
-   没有数据的字段。  
  
-   没有相关联的标记且没有数据的直接从属记录。  
  
 当你将设置**空数据的保留分隔符**属性**否**，记录和字段不包含数据的已翻译平面文件中未包含分隔符。 此外，不管如何设置**空数据的保留分隔符**属性，分隔符将不包含在立即从属的记录，而无需为其定义一个标记的数据的已翻译的平面文件消息。  
  
 当你将设置**禁止显示尾随分隔符**属性**否**（这是默认设置），已转换的平面文件消息中可能包含一个或多个尾随分隔符。 当你将设置**禁止显示尾随分隔符**属性**是**、 尾随分隔符不包括在已转换的平面文件消息。  

## <a name="special-scenarios"></a>特殊的方案  
 在某些特殊的情况下，其中行为引起的设置**空数据的保留分隔符**和**禁止显示尾随分隔符**属性可能会发生冲突。 在这种情况下后, 一个属性，与关联的行为**禁止显示尾随分隔符**，将优先。 此外，在某些特殊情况，系统将警告您为这两个属性选择的设置存在潜在冲突。  
  
 例如，考虑**记录**定义具有以下属性值的节点：  
  
-   节点名称为 MyRec  
  
-   标记标识符为 Rec  
  
-   子分隔符为 ,  
  
-   子顺序为中缀  
  
 和定义包含五个**Field 元素**具有以下名称的节点 (它们可能是**字段特性**节点或从属**记录**节点):  
  
-   FieldElem1  
  
-   FieldElem2  
  
-   FieldElem3  
  
-   FieldElem4  
  
-   FieldElem5  
  
 接下来，假定，以下主要空 XML 片段，表示此**记录**节点，传递到的平面文件汇编。  
  
```  
<MyRec>  
    <FieldElem1 />  
    <FieldElem2 />  
    <FieldElem3>Val</FieldElem3>  
    <FieldElem4 />  
    <FieldElem5 />  
</MyRec>  
  
```  
  
 下表显示生成的输出和关联的其他属性设置为根据不同的设置相关的架构节点的要求**空数据的保留分隔符**(PDFED) 和**禁止显示尾随分隔符**(STD) 属性。  
  
|PDFED 设置|STD 设置|“输出”|其他节点要求|  
|---|---|---|---|  
|是|是|Rec,,,Val,,|无。|  
|是|是|Rec,Val|所有**Field 元素**节点必须配置为可选。|  
|是|是|Rec,,,Val|节点名为**FieldElem4**和**FieldElem5**必须配置为可选。|  
|是|是|Rec,Val,,|所有**Field 元素**节点必须配置为可选。|  
  
 当这些属性设置指定应不保留分隔符或应取消分隔符时，在以下两种情况下将发出一条消息，警告您可能无法使用同一架构解析序列化平面文件数据：  
  
-   当**记录**为其节点**空数据的保留分隔符**属性设置为**否**和/或**禁止显示尾随分隔符**属性设置为**是**分别包含从属**Field 元素**节点，**字段特性**节点，或**记录**为其指定没有标记的节点。  
  
-   当从属**Field 元素**节点，**字段特性**节点，和**记录**未配置为其指定没有标记的节点是可选 (通过设置**最小出现次数**属性设置为零) 架构中。 当**禁止显示尾随分隔符**属性设置为**是**，只有的最后一个这样的从属节点需要将配置为可选。 当**空数据的保留分隔符**属性设置为**否**、 所有尾随从属节点需要将配置为可选。  
  
> [!NOTE]
>  与 （大概可选） 关联的 XML 元素时，将始终保留分隔符**记录**， **Field 元素**，或**字段特性**完全节点未显示从 XML 文档的表示形式业务除一条记录时遵循缺失的可选字段。 换句话说，如果数据及其前后的 XML 标记都丢失，则在业务文档的平面文件表示形式中将始终包含相应的分隔符。  
  
 现在将该架构更改为紧随缺少的“字段元素”之后包含一个带有两个“字段元素”的子记录。 子记录元素配置为使用 &#124;（竖线） 作为分隔符的字符。  
  
```  
<MyRec>  
    <FieldElem1 />  
    <FieldElem2 />  
    <FieldElem3>Val</FieldElem3>  
    <!-- <FieldElem4 /> -->  
    <ChildRec>  
        <InnerFieldElement1>Inner1</InnerFieldElement1>   
        <InnerFieldElement2>Inner2</InnerFieldElement1>  
    </ChildRec>  
    <FieldElem5 />  
</MyRec>  
  
```  
  
 如果将其传递给平面文件拆装器，则不会保留“FieldElem4”的分隔符，但后面的记录将按预期进行分隔。  
  
```  
,,Val,,Inner1,Inner2,,  
```  
  
## <a name="see-also"></a>另请参阅  
-  [分隔记录注意事项](../core/delimited-record-considerations.md)   
-  **为空数据 （的平面文件架构的节点属性） 保留分隔符**和**禁止显示尾部分隔符 （节点属性的平面文件架构）**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
