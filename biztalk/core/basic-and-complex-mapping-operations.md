---
title: 基本和复杂映射操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: da864b48-6255-4847-9a6f-13e489e8658d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3ca1e0819de255e70d4f66064f52cdc70f7189c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529159"
---
# <a name="basic-and-complex-mapping-operations"></a>基本和复杂映射操作
BizTalk 映射器为各种映射方案范围从简单的父子树类型操作到包含循环记录和层次结构的详细又复杂的操作提供解决方案。 映射方案的复杂性取决于您的首选项和业务需求 — XML 架构定义 (XSD) 语言提供了相当大的灵活性，在定义结构化的格式。 几乎所有映射方案都分为两个类别之一： 基本映射和复杂映射。  
  
## <a name="basic-mapping"></a>基本映射  
 基本映射是映射的最常见的可以创建类型。 在基本映射中，输入和输出项具有一对一的关系。 输入的项映射到一个且只有一个输出项。 尽管许多类型的转换和转换都使用基本映射，例如，使用多个可能*functoid*和级联 functoid 来处理要复制的值，基础方案仍保持相对简单。 基本映射操作还包括来自两个不同父记录 （仅出现一次） 到目标架构中的单个父记录下的字段的字段映射。  
  
## <a name="complex-mapping"></a>复杂的映射  
 复杂映射涉及记录或字段的单个实例出现多次**记录**或**Field 元素**架构树中的节点。 这些节点将其**Max Occurs**属性设置为一个值大于一 (1)，该值指示实例消息中可能有多个相应元素。 当 BizTalk 映射使用此类型的可变计数映射 (也称为*循环*)，可扩展样式表语言 (XSL) 样式表编译器必须能够确定要对其进行循环访问以生成的适当循环路径所需的输出。  
  
 一般情况下，可以将源架构中的循环记录中的字段链接到目标架构中的循环记录中的字段。 输入的实例消息中的相应元素数决定创建输出实例消息中的元素数。 源和目标架构，请考虑从示例具有以下 XSD 片断。  
  
### <a name="source-schema-fragment"></a>源架构片断  
  
```  
<xs:element minOccurs="1" maxOccurs="5"  
            name="SrcLoopingRecord">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="" type="xs:string" />   
      <xs:element name="" type="xs:integer" />   
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
  
```  
  
### <a name="destination-schema-fragment"></a>目标架构片断  
  
```  
<xs:element minOccurs="0" maxOccurs="unbounded"  
            name="DstLoopingRecord">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="" type="xs:string" />   
      <xs:element name="" type="xs:integer" />   
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
  
```  
  
 在这些片断中：  
  
- **SrcLoopingRecord**、 一个**记录**输入的实例消息中的节点可出现一到五次。 它还包含子级**Field 元素**节点**Field1** （字符串） 和**Field2** （整数） 出现一次为其父级的每个实例。  
  
- **DstLoopingRecord**、 一个**记录**输出实例消息中的节点可以出现零 (0) 或时间，不受限制的详细信息。 它还包含子级**Field 元素**节点**FieldA** （字符串） 和**FieldB** （整数） 出现一次为其父级的每个实例。  
  
  假定 Field1 映射到 FieldA、 将 Field2 映射到 FieldB，并且以下片段中的输入的实例消息已处理相应的映射，将生成的以下片段中的输出实例消息。  
  
### <a name="input-instance-message-fragment"></a>输入的实例消息片断  
  
```  
<SrcLoopingRecord>  
    <Field1>A string</Field1>  
    <Field2>10</Field2>  
</SrcLoopingRecord>  
<SrcLoopingRecord>  
    <Field1>Another string</Field1>  
    <Field2>11</Field2>  
</SrcLoopingRecord>  
<SrcLoopingRecord>  
    <Field1>A ball of string</Field1>  
    <Field2>12</Field2>  
</SrcLoopingRecord>  
```  
  
### <a name="output-instance-message-fragment"></a>输出实例消息片断  
  
```  
<DstLoopingRecord>  
    <FieldA>A string</FieldA>  
    <FieldB>10</FieldB>  
</DstLoopingRecord>  
<DstLoopingRecord>  
  <FieldA>Another string</FieldA>  
  <FieldB>11</FieldB>  
</DstLoopingRecord>  
<DstLoopingRecord>  
    <FieldA>A ball of string</FieldA>  
    <FieldB>12</FieldB>  
</DstLoopingRecord>  
```  
  
 次数**SrcLoopingRecord**输入的实例消息 (3) 中的元素可确定的次数**DstLoopingRecord**输出实例消息中的元素。  
  
 映射的 BizTalk 映射器不支持的类型是使用多个循环路径。 此类型的映射涉及源架构映射到目标架构中的单个循环记录中的字段中的两个或多个循环记录中的字段。 这会带来一个问题 — 没有有效的方法可确定要生成输出实例消息中的元素数。 多个循环路径会导致映射编译警告，指出目标节点具有多个源循环路径。 但是，这只是一个警告，并且第一个源循环路径中的迭代数用于确定生成输出实例消息中的元素数量。 可能需要显式控制循环行为，通过使用**循环**functoid。  
  
 Microsoft BizTalk Server 引入了一种新的循环调用表驱动循环。 表驱动循环时，输出实例消息需要基于输入的实例消息中的数据，结合一个或多个常数、 来自源架构或 functoid 的链接。 在这种情况下，输出实例消息可以有根据是组合使用不同的常量，或根据从输入的实例消息中的多个记录的数据的输入的实例消息中的单个记录中的数据的多个记录。 有关表驱动循环使用**表循环**并**表提取程序**functoid，请参阅[表循环和表提取程序 Functoid](../core/table-looping-and-table-extractor-functoids.md)。  
  
## <a name="see-also"></a>请参阅  
 [映射](../core/maps.md)   
 [使用 BizTalk 映射器创建映射](../core/creating-maps-using-biztalk-mapper.md)