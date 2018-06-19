---
title: 根节点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2161f877-835e-434d-a8d1-2426f977d60e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2070982a6bca09e8bffb2bcc88e5997360c86851
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268965"
---
# <a name="root-nodes"></a><span data-ttu-id="e50ec-102">根节点</span><span class="sxs-lookup"><span data-stu-id="e50ec-102">Root Nodes</span></span>
<span data-ttu-id="e50ec-103">在 BizTalk 编辑器中，子节点的**架构**节点称为**根**节点。</span><span class="sxs-lookup"><span data-stu-id="e50ec-103">In BizTalk Editor, child nodes of the **Schema** node are known as **Root** nodes.</span></span> <span data-ttu-id="e50ec-104">**根**节点是特殊类型的**记录**节点，并且具有比常规的几个更多属性**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="e50ec-104">**Root** nodes are a special type of **Record** node, and have a few more properties than regular **Record** nodes.</span></span> <span data-ttu-id="e50ec-105">**根**节点表示的类型的文档所述的架构，并可以重命名为相应。</span><span class="sxs-lookup"><span data-stu-id="e50ec-105">The **Root** node represents the type of document described by the schema, and can be renamed as appropriate.</span></span> <span data-ttu-id="e50ec-106">例如，你可以重命名**根**节点，以使其描述的架构表示，如 purchaseOrder、 orderAcknowledgment 或 shipNotice 消息的类型。</span><span class="sxs-lookup"><span data-stu-id="e50ec-106">For example, you can rename the **Root** node so that it describes the type of message that the schema represents, such as purchaseOrder, orderAcknowledgment, or shipNotice.</span></span>  
  
 <span data-ttu-id="e50ec-107">在 BizTalk 编辑器中，创建新的 XML 架构时**架构**节点和一个**根**自动创建的节点。</span><span class="sxs-lookup"><span data-stu-id="e50ec-107">When you create a new XML schema in BizTalk Editor, the **Schema** node and one **Root** node are created automatically.</span></span> <span data-ttu-id="e50ec-108">你可以创建其他**根**节点的子级**架构**节点; 这使你可以创建单个的 XML 架构定义 (XSD) 语言表示中的架构的库。</span><span class="sxs-lookup"><span data-stu-id="e50ec-108">You can create additional **Root** nodes as children of the **Schema** node; this enables you to create a library of schemas within a single XML Schema definition (XSD) language representation.</span></span> <span data-ttu-id="e50ec-109">例如，可以创建一个架构库以描述与发送采购订单相关的消息的各种架构，并将多个根节点分别命名为 purchaseOrder、orderAcknowledgment 和 shipNotice。</span><span class="sxs-lookup"><span data-stu-id="e50ec-109">For example, you can create a library of schemas to describe the various schemas of messages related to sending purchase orders, naming the various root nodes purchaseOrder, orderAcknowledgment, and shipNotice.</span></span>  
  
## <a name="xsd-representation"></a><span data-ttu-id="e50ec-110">XSD 表示形式</span><span class="sxs-lookup"><span data-stu-id="e50ec-110">XSD representation</span></span>  
 <span data-ttu-id="e50ec-111">下面的示例显示中对应的架构的 XSD 表示行**根**架构的树视图中的节点。</span><span class="sxs-lookup"><span data-stu-id="e50ec-111">The following example shows the lines in the XSD representation of the schema that correspond to the **Root** node in the tree view of the schema.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16" ?>  
<xs:schema xmlns="http://BizTalk_Server_Project1.Schema2"  
    xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
    targetNamespace="http://BizTalk_Server_Project1.Schema2"  
    xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name="Root">  
        <xs:complexType />   
    </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="e50ec-112">**根**节点在 BizTalk 编辑器代表所涉及的消息的相应 XML 实例中的主要元素。</span><span class="sxs-lookup"><span data-stu-id="e50ec-112">**Root** nodes in BizTalk Editor represent the main element in a corresponding XML instance of the message in question.</span></span> <span data-ttu-id="e50ec-113">例如，如果**根**的特定架构的节点已重命名为 purchaseOrder、 相应的 XSD 表示形式具有以下的高级结构。</span><span class="sxs-lookup"><span data-stu-id="e50ec-113">For example, if the **Root** node of a particular schema is renamed to purchaseOrder, the corresponding XSD representation has the following high-level structure.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16" ?>  
<xs:schema xmlns="http://BizTalk_Server_Project1.Schema2"  
    xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
    targetNamespace="http://BizTalk_Server_Project1.Schema2"  
    xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name="">  
        <xs:complexType>   
            ...  
        </xs:complexType>   
    </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="e50ec-114">相应的 XML 实例消息必须具有以下基本结构：</span><span class="sxs-lookup"><span data-stu-id="e50ec-114">A corresponding XML instance message must have the following basic structure.</span></span>  
  
```  
<?xml version="1.0"?>  
<purchaseOrder ...>  
    ...  
</purchaseOrder>  
```  
  
> [!NOTE]
>  <span data-ttu-id="e50ec-115">根节点可能没有**字段**属性。</span><span class="sxs-lookup"><span data-stu-id="e50ec-115">Root nodes may not have **Field** attributes.</span></span> <span data-ttu-id="e50ec-116">**字段**属性附加到**根**节点不会保存具有架构。</span><span class="sxs-lookup"><span data-stu-id="e50ec-116">**Field** attributes attached to the **Root** node are not saved with the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e50ec-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e50ec-117">See Also</span></span>  
-  [<span data-ttu-id="e50ec-118">BizTalk 表示形式架构</span><span class="sxs-lookup"><span data-stu-id="e50ec-118">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
-  [<span data-ttu-id="e50ec-119">节点属性</span><span class="sxs-lookup"><span data-stu-id="e50ec-119">Node Properties</span></span>](../core/node-properties.md)   
-  <span data-ttu-id="e50ec-120">**记录节点属性**  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="e50ec-120">**Record Node Properties**  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
-  [<span data-ttu-id="e50ec-121">如何设置节点属性</span><span class="sxs-lookup"><span data-stu-id="e50ec-121">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)