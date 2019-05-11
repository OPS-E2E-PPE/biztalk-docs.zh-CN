---
title: 节点名称属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95d9e5bf-7439-4ef4-ad14-e8d3e8eff911
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57d4c558e509cdcd8540795756a3891a286c3fc5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263379"
---
# <a name="node-name-property"></a>节点名称属性
因为你可以使用 BizTalk 编辑器来将节点插入到架构树中，某些节点为了进行重命名，但有些却不。 实质上，可以并应该重命名**记录**节点， **Field 元素**节点，并**字段属性**节点。 向这些节点的名称将成为 XML 元素和在该架构定义的消息中的属性的名称。  
  
 在架构树中，不能重命名的节点所示的 XML 标记，则窗体即，带有小于比 (\<) 和大于号 (\>) 符号。 例如，**架构**节点，**选择组**节点， **Any 元素**节点，以及**任何属性**节点在架构中表示具有名称的树\<架构\>，\<选\>，\<任何\>，并\<AnyAttribute\>分别。 **节点名称**此类节点的属性是只读的。  
  
 在给定**记录**节点，您不能有两个**字段属性**具有相同名称的节点。 但是，有多个**Field 元素**节点或**记录**使用相同的名称相同的子节点的节点**记录**节点，只要它们都具有相同的数据类型(根据其**数据类型**属性**字段元素**节点或其**Data Structure Type**为**记录**节点）。  
  
 当授予名称传递给**记录**节点，**字段元素**节点，并**字段属性**节点，使用具有描述性的角色的该元素或属性内的名称由架构所定义的消息。 例如，名字可能是不错的选择的名称**Field 元素**将用于存储人员名字的地址结构中的节点。 在出现第一个名称 James XML 实例消息中，如以下所示的相应元素。  
  
```  
    <FirstName>James</FirstName>  
```  
  
 当您要重命名**记录**节点，**字段元素**节点，并**字段属性**节点，您应注意，节点名中允许使用不是所有字符。 有关这些不允许的字符的信息，请参阅[的节点名称字符进行编码](../core/which-node-name-characters-get-encoded.md)。 尽管 BizTalk 编辑器允许您通过不允许的字符对它们进行编码，但它通常是更简单，若要完全避免此类字符。 有关如何信息不允许的字符进行编码，请参阅[如何节点名称字符进行编码](../core/how-node-name-characters-get-encoded.md)。  
  
 除了节点名中不允许的字符其进行了编码的架构的 XSD 表示形式，则不应使用C#保留字作为架构树中任何根节点的名称 (除非提供有效**RootNode TypeName**属性值) 或作为架构文件名。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [已编码的节点名称字符](../core/which-node-name-characters-get-encoded.md)  
  
-   [如何对节点名称字符进行编码](../core/how-node-name-characters-get-encoded.md)