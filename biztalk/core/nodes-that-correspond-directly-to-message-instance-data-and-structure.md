---
title: "直接对应消息的节点实例数据和结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18cf721c-2972-43c6-8ae4-f2f8f83ba2c5
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d5ed1aae517bb81e5a6cfb888300015e99ec017
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="nodes-that-correspond-directly-to-message-instance-data-and-structure"></a>直接对应于消息实例数据和结构的节点
一些用于创建 BizTalk 编辑器中的架构的节点类型与直接对应的实例消息受架构的 XML 表示形式中元素和属性 (其他实例的消息格式，如平面文件格式对应关系仅存在翻译从其他格式和之前为其他格式转换后）。 这些节点类型是**记录**节点 (包括根**记录**节点)， **Field 元素**节点，和**字段特性**节点。  
  
 在向提供的值**节点名称**属性**记录**和**Field 元素**节点受 XML 实例消息中指定的相应元素的名称架构。 同样，值为**节点名称**属性**字段特性**节点受架构的 XML 实例消息中指定相应的属性的名称。 此属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
 本部分的其余部分提供了有关此类具有根节点的详细信息**记录**节点在架构中接收由于其特殊角色的单独处理。  
  
## <a name="next-steps"></a>后续步骤 
  
-   [根节点](../core/root-nodes.md)  
  
-   [记录节点](../core/record-nodes.md)  
  
-   [字段元素节点](../core/field-element-nodes.md)  
  
-   [字段属性节点](../core/field-attribute-nodes.md)