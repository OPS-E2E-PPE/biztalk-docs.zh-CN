---
title: 分隔符保留和取消 |Microsoft Docs
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
ms.openlocfilehash: 9bb92d9784fb9e12494757407898388d6f52725e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975470"
---
# <a name="delimiter-preservation-and-suppression"></a>分隔符保留和取消

## <a name="overview"></a>概述
有两个属性可应用于分隔记录：**为空数据保留分隔符**并**取消尾部分隔符**。 使用这些属性来控制平面文件组装器如何处理与不存在的数据和尾部分隔符的分隔符。 当您将设置**为空数据保留分隔符**属性设置为**是**（这是默认设置），在翻译后的平面文件消息中包括分隔符：  
  
- 没有数据的字段。  
  
- 没有相关联的标记且没有数据的直接从属记录。  
  
  当您将设置**为空数据保留分隔符**属性设置为**否**，记录和字段不包含数据的已翻译平面文件中不包括分隔符。 此外，而不考虑的设置**为空数据保留分隔符**属性，而无需为其定义标记的数据的直接从属记录在翻译后的平面文件消息中不会包含分隔符。  
  
  当您将设置**取消尾部分隔符**属性设置为**否**（这是默认设置），可能会在翻译后的平面文件消息中包含一个或多个尾部分隔符。 当您将设置**取消尾部分隔符**属性设置为**是**、 尾随翻译后的平面文件消息中不包含分隔符。  

## <a name="special-scenarios"></a>特殊的方案  
 行为引起的设置的其中某些特殊情况下**为空数据保留分隔符**并**取消尾部分隔符**属性可能会发生冲突。 在这种情况下后, 一种属性，与关联的行为**取消尾部分隔符**，将优先。 此外，在某些特殊情况，系统将警告您为这两个属性选择的设置存在潜在冲突。  
  
 例如，考虑**记录**定义具有以下属性值的节点：  
  
- 节点名称为 MyRec  
  
- 标记标识符为 Rec  
  
- 子分隔符为 ,  
  
- 子顺序为中缀  
  
  并定义包含五个**字段元素**具有以下名称的节点 (它们也可能是**Field 特性**节点或从属**记录**节点):  
  
- FieldElem1  
  
- FieldElem2  
  
- FieldElem3  
  
- FieldElem4  
  
- FieldElem5  
  
  接下来，假定，以下主要空 XML 片段，表示此**记录**节点中，传递给平面文件组装器。  
  
```  
<MyRec>  
    <FieldElem1 />  
    <FieldElem2 />  
    <FieldElem3>Val</FieldElem3>  
    <FieldElem4 />  
    <FieldElem5 />  
</MyRec>  
  
```  
  
 下表显示产生的输出和关联的其他属性设置的相关架构节点，根据不同的设置要求**为空数据保留分隔符**(PDFED) 和**取消尾部分隔符**(STD) 属性。  
  
|PDFED 设置|STD 设置|“输出”|其他节点要求|  
|---|---|---|---|  
|是|“否”|Rec,,,Val,,|无。|  
|“否”|是|Rec,Val|所有**Field 元素**节点必须配置为可选。|  
|是|是|Rec,,,Val|节点名分别为**fieldelem4**并**FieldElem5**必须配置为可选。|  
|“否”|“否”|Rec,Val,,|所有**Field 元素**节点必须配置为可选。|  
  
 当这些属性设置指定应不保留分隔符或应取消分隔符时，在以下两种情况下将发出一条消息，警告您可能无法使用同一架构解析序列化平面文件数据：  
  
-   当**记录**为其节点**为空数据保留分隔符**属性设置为**否**和/或**取消尾部分隔符**属性设置为**是**分别包含从属**字段元素**节点，**字段属性**节点，或**记录**节点未指定任何标记。  
  
-   当从属**字段元素**节点，**字段属性**节点，并**记录**未指定任何标记的节点未配置为 optional (通过设置**最小出现次数**属性设置为零) 架构中。 当**取消尾部分隔符**属性设置为**是**，只有最后一个这样的从属节点需要配置为可选。 当**为空数据保留分隔符**属性设置为**否**、 所有尾部从属节点需要配置为可选。  
  
> [!NOTE]
>  当与 （可能可选） 相关联的 XML 元素，则始终保留分隔符**记录**， **Field 元素**，或**字段属性**节点是根本没有从除一条记录时遵循缺失的可选字段的业务文档的 XML 表示形式。 换句话说，如果数据及其前后的 XML 标记都丢失，则在业务文档的平面文件表示形式中将始终包含相应的分隔符。  
  
 现在将该架构更改为紧随缺少的“字段元素”之后包含一个带有两个“字段元素”的子记录。 将该子记录元素配置为使用&#124;（管道） 字符作为分隔符。  
  
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
  
## <a name="see-also"></a>请参阅  
- [分隔记录注意事项](../core/delimited-record-considerations.md)   
- **为空数据 （平面文件架构的节点属性） 保留分隔符**和**取消尾部分隔符 （平面文件架构的节点属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
