---
title: 字段元素节点与字段属性节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1fffbca-8886-42c0-9214-cd0c5314850c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50bb60f66b6de00510e973357bec43d0af506f4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345586"
---
# <a name="field-element-nodes-vs-field-attribute-nodes"></a><span data-ttu-id="84bef-102">字段元素节点与字段属性节点</span><span class="sxs-lookup"><span data-stu-id="84bef-102">Field Element Nodes vs. Field Attribute Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="84bef-103">概述</span><span class="sxs-lookup"><span data-stu-id="84bef-103">Overview</span></span>
<span data-ttu-id="84bef-104">使用平面文件架构的控制平面文件拆装器如何入站平面文件实例消息转换为其等效的 XML 格式，并将它们来控制出站平面文件组装器使用 XML 消息转换为其等效项平面文件实例消息。</span><span class="sxs-lookup"><span data-stu-id="84bef-104">Flat file schemas are used by the flat file disassembler to control how inbound flat file instance messages are translated into their equivalent XML form, and are used by the flat file assembler to control how outbound XML messages are translated into their equivalent flat file instance messages.</span></span> <span data-ttu-id="84bef-105">当构造此类架构，您将使用两个**Field 元素**节点或**字段属性**节点特别是定位在控制架构是否在平面文件实例中的特定字段消息相对应的 XML 元素或等效的 XML 格式的消息中的 XML 属性。</span><span class="sxs-lookup"><span data-stu-id="84bef-105">When constructing such schemas, you use either a **Field Element** node or a **Field Attribute** node in particular positions within the schema to control whether a particular field in the flat file instance message corresponds to an XML element or to an XML attribute in the equivalent XML form of the message.</span></span>  

## <a name="example"></a><span data-ttu-id="84bef-106">示例</span><span class="sxs-lookup"><span data-stu-id="84bef-106">Example</span></span>  
 <span data-ttu-id="84bef-107">例如，左对齐，星号填充的字段值"`red*****`"中的平面文件实例消息，可以转化为其等效的 XML 表示形式中两个不同的方式取决于架构中的该字段是否**字段元素**节点或**字段属性**节点。</span><span class="sxs-lookup"><span data-stu-id="84bef-107">For example, the left-aligned, asterisk-padded field value "`red*****`" in a flat file instance message can be translated into its equivalent XML representation in two different ways depending upon whether that field in the schema is a **Field Element** node or a **Field Attribute** node.</span></span> <span data-ttu-id="84bef-108">当该字段表示架构中的**字段元素**节点，其**节点名称**属性设置为"color"，并包含**记录**节点都有其**节点名称**属性设置为"shirt"，等效的 XML （以粗体显示） 的平面文件字段。</span><span class="sxs-lookup"><span data-stu-id="84bef-108">When that field is represented in the schema by a **Field Element** node with its **Node Name** property set to "color", and the containing **Record** node has its **Node Name** property set to "shirt", the XML equivalent of the flat file field is (shown in bold type).</span></span>  

```  
<shirt>  
    <color>red</color>  
</shirt>  
```  

 <span data-ttu-id="84bef-109">当该相同的平面文件字段表示架构中的**字段属性**具有节点其**节点名称**属性设置为颜色和包含**记录**节点都有其**节点名称**属性设置为 shirt，（以粗体显示） 的平面文件字段的 XML 等效项：</span><span class="sxs-lookup"><span data-stu-id="84bef-109">When that same flat file field is represented in the schema by a **Field Attribute** node with its **Node Name** property set to color, and the containing **Record** node has its **Node Name** property set to shirt, the XML equivalent of the flat file field is (shown in bold type):</span></span>  

```  
<color shirt="red"/>  
```  

> [!NOTE]
>  <span data-ttu-id="84bef-110">平面文件架构还具有其他限制，在给定**记录**节点中，从属**字段属性**节点必须在从属之前**记录**或节点**字段元素**节点。</span><span class="sxs-lookup"><span data-stu-id="84bef-110">Flat file schemas have a further restriction that within a given **Record** node, subordinate **Field Attribute** nodes must come before subordinate **Record** nodes or **Field Element** nodes.</span></span>  

## <a name="see-also"></a><span data-ttu-id="84bef-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="84bef-111">See Also</span></span>  
- [<span data-ttu-id="84bef-112">字段注意事项</span><span class="sxs-lookup"><span data-stu-id="84bef-112">Field Considerations</span></span>](../core/field-considerations.md)
- <span data-ttu-id="84bef-113">**节点名称**属性 [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="84bef-113">**Node Name** property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
