---
title: 创建链接 |Microsoft Docs
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
ms.openlocfilehash: 441ae9536dec11f8eead5544e95b7ba7f7814852
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353644"
---
# <a name="creating-links"></a>创建链接
BizTalk 映射器可帮助你自动执行某些链接创建中涉及的元素。 简单链接创建类似于简单数据类型。 有多个类似于编程语言中的结构分配的更复杂的链接创建窗体。 例如，使用指定的数据如何将多个项的从输入的实例消息移动到相应的输出实例消息的单个链接创建。  
  
 创建使用以下方法链接：  
  
-   **简单链接创建。** 在简单链接创建通过拖动生成链接。 将源架构中的字段拖至目标架构中的字段输出实例消息中将导致创建元素或属性，并将元素或属性的值插入消息中。 此类链接可以之间直接进行**记录**并**字段**节点在源和目标架构中，或它们可以包括一个或多个 functoid 之间的链接路径中**记录**并**字段**源和目标架构中的节点。  
  
-   **结构链接。** 在创建结构链接时，你生成多个简单链接在同一时间之间**记录**并**字段**中具有相同的相对结构的源和目标架构的节点。 若要使用结构链接，这两种架构的相关部分的结构必须相同。 有关配置结构链接的详细信息，请参阅[如何自动链接记录](../core/how-to-link-records-automatically.md)。  
  
-   **名称匹配链接。** 当使用此方法时，在同一时间之间创建多个简单链接**记录**并**字段**源和目标架构中的节点上的名称基于**记录**并**字段**节点。 若要使用名称匹配链接，源和目标架构的结构必须非常相似，但又不完全相同。 有关配置名称匹配链接的详细信息，请参阅[如何自动链接记录](../core/how-to-link-records-automatically.md)。  
  
    > [!NOTE]
    >  你还可以看到[如何管理现有链接](../core/how-to-manage-existing-links.md)有关如何更改/修改现有链接的信息。  
  
## <a name="preserving-whitespace-in-a-link"></a>保留链接中的空格  
 如果您想要保留源元素中的空格，映射到目标元素或 functoid 时，需要编写自定义脚本。  
  
 在映射器或运行时系统中，不保留空格。 映射器和运行时系统使用 BTSXslTransform.Transform，它处理大消息转换，并依靠 XmlReader 使用 XPath 数据模型进行导航。  
  
 若要保留空白，可以编写自定义脚本返回所需的数量的空格。 例如，下面的代码始终返回一个包含 5 个空格字符的字符串：  
  
```  
public string Whitespace(string param1)  
{  
  return "     ";  
}  
```  
  
 如果您的源元素时链接到此脚本和目标元素的输入作为输出，在执行映射时，输出元素将包含 5 个空格字符。  
  
> [!NOTE]
>  如果您查看输出使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，该元素将显示为空。 这是因为 XML 查看器将包含空格仅作为空白的元素。 若要查看空格，用鼠标右键单击 XML 视图，然后选择**查看源**。  
  
## <a name="see-also"></a>请参阅  
 [如何编辑链接属性](../core/how-to-edit-link-properties.md)