---
title: "基本和复杂的映射操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: da864b48-6255-4847-9a6f-13e489e8658d
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82876310cfa497f8002e7df680281122e90884af
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="basic-and-complex-mapping-operations"></a>基本和复杂的映射操作
BizTalk 映射器为各种映射方案提供解决方案，这些映射方案包括从简单的父子树类型操作到包含循环记录和层次结构的详细又复杂的操作。 映射方案的复杂程度取决于你的首选项和业务需求-XML 架构定义 (XSD) 语言提供在定义结构化的格式相当大的灵活性。 几乎所有映射方案均属于这两个类别之一：基本映射和复杂映射。  
  
## <a name="basic-mapping"></a>基本映射  
 基本映射是最常见的可创建的映射类型。 在基本映射中，输入项与输出项具有一对一的关系。 一个输入项将映射到一个并且只能映射到一个输出项。 尽管可以使用基本的映射，如使用多个有许多类型的转换和翻译 *functoid* 并且级联 functoid 来操作正在复制的值，该基础方案保持相对简单。 基本映射操作还包括将两个不同父记录（仅出现一次）中的字段映射到目标架构中单个父记录下的字段。  
  
## <a name="complex-mapping"></a>复杂映射  
 复杂映射涉及记录或字段的单个实例中发生多次 **记录** 或 **Field 元素** 架构树中的节点。 此类节点具有其 **Max Occurs** 属性设置为一个值大于一 (1)，该值指示实例消息中可能有多个相应元素。 BizTalk 映射时使用此类型的变量计数映射 (也称为 *循环*)，可扩展样式表语言 (XSL) 样式表编译器必须能够确定要对其进行循环以生成所需的输出的正确循环路径。  
  
 通常，可以将源架构的循环记录中的字段链接到目标架构的循环记录中的字段。 输入实例消息中的对应元素数将决定输出实例消息中创建的元素数。 假设示例源架构和目标架构中具有以下 XSD 片断：  
  
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
  
-   **SrcLoopingRecord**, 、 **记录** 输入的实例消息中的节点会从 1 到五次。 它还包含子 **Field 元素** 节点 **Field1** （字符串） 和 **Field2** （整数） 出现一次为每个其父实例。  
  
-   **DstLoopingRecord**, 、 **记录** 输出实例消息中的节点可以出现零 (0) 或时间，不受限制的详细信息。 它还包含子 **Field 元素** 节点 **FieldA** （字符串） 和 **FieldB** （整数） 出现一次为每个其父实例。  
  
 假定将 Field1 映射到 FieldA、将 Field2 映射到 FieldB，并且输入实例消息中的以下片断已对这些映射进行了处理，这样将生成输出实例消息中的以下片断：  
  
### <a name="input-instance-message-fragment"></a>输入实例消息片断  
  
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
  
 出现次数的 **SrcLoopingRecord** 输入的实例消息 (3) 中的元素确定的出现次数的 **DstLoopingRecord** 输出实例消息中的元素。  
  
 BizTalk 映射器不支持使用多个循环路径的映射类型。 此类型的映射涉及源架构的两个或多个循环记录中要映射到目标架构的单个循环记录中字段的字段。 这会带来问题-没有有效方法来确定要在输出的实例消息生成的元素数。 多个循环路径将导致映射编译警告，该警告将指出目标节点具有多个源循环路径。 不过，这仅是警告而已，而第一个源循环路径中的迭代数将用于确定输出实例消息中生成的元素数量。 你可以显式控制循环行为，通过使用 **循环** functoid。  
  
 Microsoft BizTalk Server 引入了一种新的循环调用表驱动循环。 如果输出实例消息需要基于输入实例消息中的数据并且该输入实例消息与一个或多个常数、来自源架构的链接或 functoid 结合在一起，则表驱动循环十分有用。 在这种情况下，该输出实例消息可以具有多个记录，这些记录基于与其他常数相结合的输入实例消息的单个记录中的数据，或基于来自输入实例消息中多个记录的数据。 有关表驱动循环使用**表循环**和**表提取程序**functoid，请参阅[表循环和表提取程序 Functoid](../core/table-looping-and-table-extractor-functoids.md)。  
  
## <a name="see-also"></a>另请参阅  
 [地图](../core/maps.md)   
 [创建使用 BizTalk 映射程序图](../core/creating-maps-using-biztalk-mapper.md)