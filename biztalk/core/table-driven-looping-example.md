---
title: 表驱动循环示例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Table Extractor functoids, code sample
- Table Looping functoids
- Table Extractor functoids
- Table Looping functoids, about Table Looping functoids
- Table Extractor functoids, about Table Extractor functoids
- code samples, Table Looping functoids
- Table Looping functoids, code sample
- code samples, Table Extractor functoids
ms.assetid: d890bdb1-12a6-4001-9748-737b1f2bab79
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6989ac7e64cf28784d08f26aaf9e7af3a166a28
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="table-driven-looping-example"></a>表驱动循环示例
本部分简要介绍映射使用 **表循环** 和 **表提取程序** functoid。 有关选择的详细信息，将放置、 链接和配置 functoid，请参阅[如何添加表循环和一个映射到表提取程序 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)。  
  
 假设您有一个需要在文档中使用的地址的列表，该文档需要单独的发货地址和帐单邮寄地址。 这些地址可能如以下代码所示：  
  
```  
<ns0:Root xmlns:ns0="http://TableLoopingSample.Addresses">  
    <Address>  
        <Name>Kelly Focht</Name>  
        <Street>456 1st Ave</Street>  
        <City>Miami</City>  
        <State>FL</State>  
        <PostalCode>81406</PostalCode>  
    </Address>  
    <Address>  
        <Name>Wendy Wheeler</Name>  
        <Street>7890 Broadway</Street>  
        <City>Columbus</City>  
        <State>OH</State>  
        <PostalCode>46290</PostalCode>  
    </Address>  
</ns0:Root>  
```  
  
 可采用的输出形式之一如以下代码所示，可复制这些地址但使用属性对其进行标记：  
  
```  
<ns0:Root xmlns:ns0="http://TableLoopingSample.POAddresses">  
    <Address Type="ShipTo">  
        <Name>Kelly Focht</Name>  
        <Street>456 1st Ave</Street>  
        <City>Miami</City>  
        <State>FL</State>  
        <PostalCode>81406</PostalCode>  
    </Address>  
    <Address Type="BillTo">  
        <Name>Kelly Focht</Name>  
        <Street>456 1st Ave</Street>  
        <City>Miami</City><State>FL</State>  
        <PostalCode>81406</PostalCode>  
    </Address>  
    <Address Type="ShipTo">  
        <Name>Wendy Wheeler</Name>  
        <Street>7890 Broadway</Street>  
        <City>Columbus</City>  
        <State>OH</State>  
        <PostalCode>46290</PostalCode>  
    </Address>  
    <Address Type="BillTo">  
        <Name>Wendy Wheeler</Name>  
        <Street>7890 Broadway</Street>  
        <City>Columbus</City>  
        <State>OH</State>  
        <PostalCode>46290</PostalCode>  
    </Address>  
</ns0:Root>  
```  
  
 `The following figure shows a map using the`  **表** **循环**  `functoid and`  **表** **提取器**  `functoids to generate the desired output instance message.`  
  
 ![映射表循环和表提取程序 functoid](../core/media/tableloopingextractorfunctoid.gif "tableloopingextractorfunctoid")  
“表循环”和“表提取程序”Functoid  
  
 请注意， **表循环** functoid 指向输入和输出架构中的记录级别元素。 此链接可确保创建封闭的结构，从而确保在记录内创建元素。 此外请注意，有一个 **表提取程序** functoid 输出架构中每个字段。  
  
 输入架构中的记录的链接是中的第一个参数**配置\<Functoid\> Functoid**对话框。  
  
 第二个参数是 functoid 网格表中的列数︰ 以一个列的每个地址类型、 名称、 街道、 城市、 州和邮政编码。 紧随第二个参数之后是在该网格表中可能显示的所有值的列表。 这些值包括地址类型的字符串常数（“ShipTo”、“BillTo”），以及指向地址的字段的链接。 请注意，指向地址字段的链接都具有名称。 对映射中的链接进行命名，可以简化构造表的过程。 否则，完整路径出现在 **配置表循环 Functoid** 对话框。  
  
 配置后 **表循环** functoid，您可以构造表使用 **配置表循环 Functoid** 对话框。 单击省略号，此时将显示对话框 (**...**) 与关联的按钮 **表循环网格** 中的属性 **属性** 窗口。  
  
 请注意，有六个列中指定 **配置表循环 Functoid** 对话框︰ 输出架构中每个字段的一列。 下拉列表中显示的字段，还为指定的中的第三个和以下参数的可能值 **配置表循环 Functoid** 对话框。 表包含两行，分别对应于输出架构中的每个记录类型。 因为存在两行，所以此映射将为每个输入记录生成两个记录。 如果存在四行，则每个输入记录将有四个输出记录。  
  
 作为 **表循环** functoid 采用每个记录，它在表中记录的值填充，然后将一个行发送到的一次 **表提取程序** functoid。 **表提取程序** functoid 每个表行中提取一个值，并将其传递到输出实例消息中链接的字段。  
  
## <a name="see-also"></a>另请参阅  
 [表循环 Functoid](../core/table-looping-functoid.md)   
 [表提取程序 Functoid](../core/table-extractor-functoid.md)   
 [表驱动循环配置](../core/table-driven-looping-configuration.md)   
 [如何添加表循环以及到地图表提取程序 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)   
 [高级的 Functoid](../core/advanced-functoids.md)   
 [索引 Functoid](../core/index-functoid.md)   
 [迭代 Functoid](../core/iteration-functoid.md)   
 [循环 Functoid](../core/looping-functoid.md)   
 [“记录计数”Functoid](../core/record-count-functoid.md)