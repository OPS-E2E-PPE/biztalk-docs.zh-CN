---
title: 表驱动循环示例 |Microsoft Docs
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 505738960cb47930c210398dd76ffe394fe71637
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291667"
---
# <a name="table-driven-looping-example"></a>表驱动循环示例
本部分简要介绍的映射使用**表循环**并**表提取程序**functoid。 有关选择的详细信息，放置、 链接和配置这些 functoid，请参阅[如何添加表循环和向映射表提取程序 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)。  
  
 假设您有需要在该文档需要单独的发货和帐单邮寄地址中使用的地址的列表。 这些地址可能如以下代码。  
  
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
  
 一种形式采用的输出将是以下代码中，复制这些地址，但将其标记具有属性。  
  
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
  
 `The following figure shows a map using the`  **表****循环**`functoid and`**表****提取程序**   `functoids to generate the desired output instance message.`  
  
 ![映射表循环和表提取程序 functoid](../core/media/tableloopingextractorfunctoid.gif "tableloopingextractorfunctoid")  
TableLooping 和提取程序 Functoid  
  
 请注意，**表循环**functoid 链接到输入和输出架构中的记录级别元素。 该链接可以确保创建封闭的结构，因此创建的记录中的元素。 另外还要注意，有一个**表提取程序**functoid 的输出架构中每个字段。  
  
 指向输入架构中记录的链接是中的第一个参数**配置\<Functoid\> Functoid**对话框。  
  
 第二个参数是 functoid 的网格表中的列数： 一列分别表示地址类型、 名称、 街道、 城市、 州和邮政编码。 后面的第二个参数是所有可能会显示在网格表中的值的列表。 这些包括地址类型 （"ShipTo"、"BillTo"） 的字符串常量，以及指向地址的字段。 请注意，指向地址字段的名称。 命名在映射中的链接可以简化构造表。 否则，完整路径将显示在**配置表循环 Functoid**对话框。  
  
 配置后**表循环**functoid，您可以构造表使用**配置表循环 Functoid**对话框。 单击省略号，此时将显示对话框 (**...**) 按钮与相关联**表循环网格**中的属性**属性**窗口。  
  
 请注意，共有六个列中的规定**配置表循环 Functoid**对话框： 一列对应输出架构中每个字段。 下拉列表中显示的字段，还为指定的在第三个以及其后的参数的可能值**配置表循环 Functoid**对话框。 表中的两个行，一个用于每种类型的输出架构中的记录。 因为有两个行，此映射生成每个输入记录的两个的记录。 如果有四个行，将有每个输入记录的四个输出记录。  
  
 作为**表循环**functoid 不需要每条记录，它记录中的值表中填充，然后将一行发送到的一次**表提取程序**functoid。 **表提取程序**functoid 每个表行中提取一个值，并将其传递到输出实例消息中的链接字段。  
  
## <a name="see-also"></a>请参阅  
 [表循环 Functoid](../core/table-looping-functoid.md)   
 [表提取程序 Functoid](../core/table-extractor-functoid.md)   
 [表驱动循环配置](../core/table-driven-looping-configuration.md)   
 [如何添加表循环和表提取程序 Functoid 映射](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)   
 [高级的 Functoid](../core/advanced-functoids.md)   
 [索引 Functoid](../core/index-functoid.md)   
 [迭代 Functoid](../core/iteration-functoid.md)   
 [循环 Functoid](../core/looping-functoid.md)   
 [记录计数 Functoid](../core/record-count-functoid.md)