---
title: 创建链接 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, links
- BizTalk Mapper, links
ms.assetid: e8596c50-62e9-40a7-ad61-29cbdb4f4fc9
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87570b82dc63a02c629e0fc024c2e44d57df1401
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238565"
---
# <a name="creating-links"></a>创建链接
BizTalk 映射器可帮助您自动化在创建链接过程中所涉及的一些元素。 简单链接创建类似于简单数据类型。 还有一些较为复杂的链接创建形式，类似于编程语言中的结构分配。 例如，使用单个链接创建指定如何将多个数据项从输入实例消息移至相应的输出实例消息。  
  
 可以使用以下方法来创建链接：  
  
-   **简单链接创建。** 在简单链接创建中，通过拖动即可生成链接。 将源架构中的字段拖至目标架构中的字段将在输出实例消息中创建元素或属性，并在消息中插入元素或属性的值。 直接之间可以进行此类链接**记录**和**字段**节点在源和目标架构中，或它们可以在之间的链接路径中包含一个或多个 functoid**记录**和**字段**源和目标架构中的节点。  
  
-   **结构的链接。** 在创建结构链接，你生成多个简单的链接在同一时间之间**记录**和**字段**具有相同的相对结构的源和目标架构中的节点。 若要使用结构链接，两个架构的相关部分的结构必须相同。 有关配置结构链接的详细信息，请参阅[如何自动链接记录](../core/how-to-link-records-automatically.md)。  
  
-   **名称匹配的链接。** 当你使用此方法时，你将在同一时间之间创建多个简单链接**记录**和**字段**源和目标架构中的节点的名称基于**记录**和**字段**节点。 若要使用名称匹配链接，源架构和目标架构的结构必须非常相似，但无需完全相同。 有关配置名称匹配的链接的详细信息，请参阅[如何自动链接记录](../core/how-to-link-records-automatically.md)。  
  
    > [!NOTE]
    >  你还可以看到[如何管理现有链接](../core/how-to-manage-existing-links.md)有关如何更改/修改的现有链接的信息。  
  
## <a name="preserving-whitespace-in-a-link"></a>保留链接中的空格  
 如果在将源元素映射到目标元素或 functoid 时，想要保留源元素中的空格，则需要编写自定义脚本。  
  
 在映射器或运行时系统中不保留空格。 映射器和运行时系统都使用 BTSXslTransform.Transform，它处理大消息转换，并依靠 XmlReader 通过 XPath 数据模型进行定位。  
  
 若要保留空格，可编写能返回所需数量的空格的自定义脚本。 例如，以下代码始终返回包含 5 个空格字符的字符串：  
  
```  
public string Whitespace(string param1)  
{  
  return "     ";  
}  
```  
  
 如果你源元素链接到此脚本和目标元素的输入作为输出，执行映射时，输出元素将包含 5 空白字符。  
  
> [!NOTE]
>  如果您查看输出使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，元素将显示为空。 这是因为 XML 查看器将包含空格的元素仅作为空白处理。 若要查看空白，右键单击 XML 视图，然后选择**查看源**。  
  
## <a name="see-also"></a>另请参阅  
 [如何编辑链接属性](../core/how-to-edit-link-properties.md)