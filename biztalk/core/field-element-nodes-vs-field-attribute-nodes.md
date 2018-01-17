---
title: "“字段元素”节点与字段属性节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1fffbca-8886-42c0-9214-cd0c5314850c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d90f622e20bbdbace6804b2418cb68fd2ad60da
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="field-element-nodes-vs-field-attribute-nodes"></a><span data-ttu-id="eff46-102">“字段元素”节点与“字段属性”节点</span><span class="sxs-lookup"><span data-stu-id="eff46-102">Field Element Nodes vs. Field Attribute Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="eff46-103">概述</span><span class="sxs-lookup"><span data-stu-id="eff46-103">Overview</span></span>
<span data-ttu-id="eff46-104">使用平面文件架构的控制平面文件反汇编程序入站平面文件实例消息转换为其等效的 XML 格式，和由控制如何出站的平面文件汇编方式 XML 消息转换为其等效的平面文件实例消息。</span><span class="sxs-lookup"><span data-stu-id="eff46-104">Flat file schemas are used by the flat file disassembler to control how inbound flat file instance messages are translated into their equivalent XML form, and are used by the flat file assembler to control how outbound XML messages are translated into their equivalent flat file instance messages.</span></span> <span data-ttu-id="eff46-105">在构造此类架构，你使用 **Field 元素** 节点或 **字段特性** 节点尤其是定位在控制架构是否在平面文件实例消息中的特定字段对应于 XML 元素或等效的 XML 格式的消息中的 XML 属性。</span><span class="sxs-lookup"><span data-stu-id="eff46-105">When constructing such schemas, you use either a **Field Element** node or a **Field Attribute** node in particular positions within the schema to control whether a particular field in the flat file instance message corresponds to an XML element or to an XML attribute in the equivalent XML form of the message.</span></span>  

## <a name="example"></a><span data-ttu-id="eff46-106">示例</span><span class="sxs-lookup"><span data-stu-id="eff46-106">Example</span></span>  
 <span data-ttu-id="eff46-107">例如，左对齐、 星号填充字段值"`red*****`"在平面文件实例消息可以转化为其等效的 XML 表示形式中两个不同的方式取决于架构中的该字段是否 **Field 元素** 节点或 **字段特性** 节点。</span><span class="sxs-lookup"><span data-stu-id="eff46-107">For example, the left-aligned, asterisk-padded field value "`red*****`" in a flat file instance message can be translated into its equivalent XML representation in two different ways depending upon whether that field in the schema is a **Field Element** node or a **Field Attribute** node.</span></span> <span data-ttu-id="eff46-108">当通过架构中表示该字段**Field 元素**节点其**节点名称**属性设置为"color"，且包含**记录**节点都有其**节点名称**属性设置为"shirt"，等效的 XML （以粗体类型显示） 的平面文件字段。</span><span class="sxs-lookup"><span data-stu-id="eff46-108">When that field is represented in the schema by a **Field Element** node with its **Node Name** property set to "color", and the containing **Record** node has its **Node Name** property set to "shirt", the XML equivalent of the flat file field is (shown in bold type).</span></span>  
  
```  
<shirt>  
    <color>red</color>  
</shirt>  
```  
  
 <span data-ttu-id="eff46-109">当通过架构中表示该相同的平面文件字段 **字段特性** 节点其 **节点名称** 属性设置为颜色，且包含 **记录** 节点都有其 **节点名称** 属性设置为 shirt，平面文件显示的字段是 （粗体类型） 的 XML 等效项︰</span><span class="sxs-lookup"><span data-stu-id="eff46-109">When that same flat file field is represented in the schema by a **Field Attribute** node with its **Node Name** property set to color, and the containing **Record** node has its **Node Name** property set to shirt, the XML equivalent of the flat file field is (shown in bold type):</span></span>  
  
```  
<color shirt="red"/>  
```  
  
> [!NOTE]
>  <span data-ttu-id="eff46-110">平面文件架构具有进一步限制，在给定 **记录** 节点，从属 **字段特性** 节点必须早从属 **记录** 节点或 **Field 元素** 节点。</span><span class="sxs-lookup"><span data-stu-id="eff46-110">Flat file schemas have a further restriction that within a given **Record** node, subordinate **Field Attribute** nodes must come before subordinate **Record** nodes or **Field Element** nodes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eff46-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eff46-111">See Also</span></span>  
-  [<span data-ttu-id="eff46-112">字段注意事项</span><span class="sxs-lookup"><span data-stu-id="eff46-112">Field Considerations</span></span>](../core/field-considerations.md)
-  <span data-ttu-id="eff46-113">**节点名称**属性[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="eff46-113">**Node Name** property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>