---
title: "节点名称属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95d9e5bf-7439-4ef4-ad14-e8d3e8eff911
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 155ad9ac5310b5084a94eb59a225e4d40e552bb9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="node-name-property"></a>“节点名称”属性
在使用 BizTalk 编辑器向架构树中插入节点时，需要对某些节点进行重命名，而另外一些节点则不需要。 实质上，你可以和应该重命名**记录**节点， **Field 元素**节点，和**字段特性**节点。 您为这些节点指定的名称将成为架构所定义的消息中的 XML 元素和属性的名称。  
  
 在架构树中，不能重命名的节点所示的 XML 标记，则窗体也就是说，以小于比 (\<) 和大于号 (>)。 例如，**架构**节点，**选项组**节点， **Any 元素**节点，和**任何属性**节点表示架构中具有名称的树\<架构 >，\<选择 >，\<任何 >，和\<AnyAttribute > 分别。 **节点名称**这样的节点的属性是只读的。  
  
 在给定**记录**节点，你不能有两个**字段特性**具有相同名称的节点。 但是，有多个**Field 元素**节点或**记录**具有相同名称的相同的子节点的节点**记录**节点，只要它们都具有相同的数据类型(由指定其**数据类型**属性**Field 元素**节点或其**数据结构类型**为**记录**节点）。  
  
 当你提供名称，到**记录**节点， **Field 元素**节点，和**字段特性**节点，使用具有描述性的角色的该元素或属性中的名称正在定义的架构的消息。 例如，名字可能是一个不错的选择的名称**Field 元素**将用于存储的某人的名字地址结构中的节点。 在包含名字 James 的 XML 实例消息中，相应的元素应与下面所列相似：  
  
```  
    <FirstName>James</FirstName>  
```  
  
 当你正在重命名**记录**节点， **Field 元素**节点，和**字段特性**节点，你应注意，节点名称中允许使用不是所有字符。 有关这些不允许的字符的信息，请参阅[的节点名称字符获取编码](../core/which-node-name-characters-get-encoded.md)。 虽然 BizTalk 编辑器允许您通过编码来使用不允许的字符，但彻底避免使用此类字符通常更为简单。 有关如何信息不允许的字符进行编码，请参阅[节点名称字符获取编码方式](../core/how-node-name-characters-get-encoded.md)。  
  
 除了在节点名称中允许的字符除非它们进行编码的架构的 XSD 表示中，你不应使用 C# 保留字作为架构树中的所有根节点的名称 (除非你提供有效**RootNodeTypeName**属性值) 或架构文件的名称。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [节点名称字符获取编码](../core/which-node-name-characters-get-encoded.md)  
  
-   [节点名称字符获取编码方式](../core/how-node-name-characters-get-encoded.md)