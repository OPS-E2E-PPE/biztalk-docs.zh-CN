---
title: 节点直接对应于消息实例数据和结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18cf721c-2972-43c6-8ae4-f2f8f83ba2c5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eef4c9c8ae710aa75b1cb05ad8f5b4732f06bd30
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323632"
---
# <a name="nodes-that-correspond-directly-to-message-instance-data-and-structure"></a><span data-ttu-id="ec0d4-102">直接对应于消息实例数据和结构的节点</span><span class="sxs-lookup"><span data-stu-id="ec0d4-102">Nodes That Correspond Directly to Message Instance Data and Structure</span></span>
<span data-ttu-id="ec0d4-103">使用 BizTalk 编辑器中创建架构的节点类型的一些直接对应于该架构控制的实例消息的 XML 表示形式中元素和属性 (用于其他实例消息格式，如平面文件格式，这对应关系只存在从其他格式和之前转换为其他格式的转换后）。</span><span class="sxs-lookup"><span data-stu-id="ec0d4-103">Some of the node types that you use to create schemas in BizTalk Editor correspond directly to elements and attributes in XML representation of instance messages governed by the schema (for other instance message formats, such as flat file formats, this correspondence only exists after translation from the other format and before translation to the other format).</span></span> <span data-ttu-id="ec0d4-104">这些节点类型是**记录**节点 (包括根**记录**节点)，**字段元素**节点，以及**字段属性**节点。</span><span class="sxs-lookup"><span data-stu-id="ec0d4-104">These node types are **Record** nodes (including root **Record** nodes), **Field Element** nodes, and **Field Attribute** nodes.</span></span>  
  
 <span data-ttu-id="ec0d4-105">提供给的值**节点名称**的属性**记录**并**字段元素**节点控制的 XML 实例消息中指定的相应元素的名称架构。</span><span class="sxs-lookup"><span data-stu-id="ec0d4-105">The values you give to the **Node Name** property of **Record** and **Field Element** nodes specify the name of the corresponding element in XML instance messages governed by the schema.</span></span> <span data-ttu-id="ec0d4-106">同样，值提供给**节点名称**的属性**字段属性**节点在该架构控制的 XML 实例消息中指定的相应属性的名称。</span><span class="sxs-lookup"><span data-stu-id="ec0d4-106">Likewise, the values you give to the **Node Name** property of **Field Attribute** nodes specify the name of the corresponding attribute in XML instance messages governed by the schema.</span></span> <span data-ttu-id="ec0d4-107">此属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="ec0d4-107">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="ec0d4-108">本部分的其余部分提供了有关此类具有根节点的详细信息**记录**节点在架构中接收由于其特殊的角色进行单独处理。</span><span class="sxs-lookup"><span data-stu-id="ec0d4-108">The remainder of this section provides more information about this class of nodes, with root **Record** nodes receiving separate treatment due to their special role in schemas.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ec0d4-109">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ec0d4-109">Next steps</span></span> 
  
-   [<span data-ttu-id="ec0d4-110">根节点</span><span class="sxs-lookup"><span data-stu-id="ec0d4-110">Root Nodes</span></span>](../core/root-nodes.md)  
  
-   [<span data-ttu-id="ec0d4-111">“记录”节点</span><span class="sxs-lookup"><span data-stu-id="ec0d4-111">Record Nodes</span></span>](../core/record-nodes.md)  
  
-   [<span data-ttu-id="ec0d4-112">“字段元素”节点</span><span class="sxs-lookup"><span data-stu-id="ec0d4-112">Field Element Nodes</span></span>](../core/field-element-nodes.md)  
  
-   [<span data-ttu-id="ec0d4-113">“字段属性”节点</span><span class="sxs-lookup"><span data-stu-id="ec0d4-113">Field Attribute Nodes</span></span>](../core/field-attribute-nodes.md)