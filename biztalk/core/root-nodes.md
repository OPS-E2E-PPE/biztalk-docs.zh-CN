---
title: 根节点 |Microsoft Docs
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
ms.openlocfilehash: 0886e1098c3cdc561f878c0a99615f197f937ef5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254761"
---
# <a name="root-nodes"></a><span data-ttu-id="ba8cb-102">根节点</span><span class="sxs-lookup"><span data-stu-id="ba8cb-102">Root Nodes</span></span>
<span data-ttu-id="ba8cb-103">在 BizTalk 编辑器中的子节点**架构**节点被称为**根**节点。</span><span class="sxs-lookup"><span data-stu-id="ba8cb-103">In BizTalk Editor, child nodes of the **Schema** node are known as **Root** nodes.</span></span> <span data-ttu-id="ba8cb-104">**根**节点是特殊类型的**记录**节点，并且具有了几个属性比常规**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="ba8cb-104">**Root** nodes are a special type of **Record** node, and have a few more properties than regular **Record** nodes.</span></span> <span data-ttu-id="ba8cb-105">**根**节点表示架构所描述的文档类型，可以重命名是根据需要。</span><span class="sxs-lookup"><span data-stu-id="ba8cb-105">The **Root** node represents the type of document described by the schema, and can be renamed as appropriate.</span></span> <span data-ttu-id="ba8cb-106">例如，你可以重命名**根**节点，以使其描述架构表示的诸如 purchaseOrder、 orderAcknowledgment 或 shipnotice 等消息的类型。</span><span class="sxs-lookup"><span data-stu-id="ba8cb-106">For example, you can rename the **Root** node so that it describes the type of message that the schema represents, such as purchaseOrder, orderAcknowledgment, or shipNotice.</span></span>  

 <span data-ttu-id="ba8cb-107">在 BizTalk 编辑器中，创建新的 XML 架构时**架构**节点和一个**根**自动创建节点。</span><span class="sxs-lookup"><span data-stu-id="ba8cb-107">When you create a new XML schema in BizTalk Editor, the **Schema** node and one **Root** node are created automatically.</span></span> <span data-ttu-id="ba8cb-108">您可以创建其他**根**节点的子级作为节点**架构**节点; 这使您可以创建一个库中的单个 XML 架构定义 (XSD) 语言表示形式的架构。</span><span class="sxs-lookup"><span data-stu-id="ba8cb-108">You can create additional **Root** nodes as children of the **Schema** node; this enables you to create a library of schemas within a single XML Schema definition (XSD) language representation.</span></span> <span data-ttu-id="ba8cb-109">例如，可以创建一个架构来描述与发送采购订单相关的消息的各种架构库命名不同的根节点 purchaseOrder、 orderAcknowledgment 和 shipnotice 等。</span><span class="sxs-lookup"><span data-stu-id="ba8cb-109">For example, you can create a library of schemas to describe the various schemas of messages related to sending purchase orders, naming the various root nodes purchaseOrder, orderAcknowledgment, and shipNotice.</span></span>  

## <a name="xsd-representation"></a><span data-ttu-id="ba8cb-110">XSD 表示形式</span><span class="sxs-lookup"><span data-stu-id="ba8cb-110">XSD representation</span></span>  
 <span data-ttu-id="ba8cb-111">下面的示例显示行中对应于架构的 XSD 表示形式**根**架构的树视图中的节点。</span><span class="sxs-lookup"><span data-stu-id="ba8cb-111">The following example shows the lines in the XSD representation of the schema that correspond to the **Root** node in the tree view of the schema.</span></span>  

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

 <span data-ttu-id="ba8cb-112">**根**节点在 BizTalk 编辑器中表示所涉及的消息的相应 XML 实例中的主要元素。</span><span class="sxs-lookup"><span data-stu-id="ba8cb-112">**Root** nodes in BizTalk Editor represent the main element in a corresponding XML instance of the message in question.</span></span> <span data-ttu-id="ba8cb-113">例如，如果**根**特定架构的节点已重命名为 purchaseOrder，相应的 XSD 表示形式具有以下高级结构。</span><span class="sxs-lookup"><span data-stu-id="ba8cb-113">For example, if the **Root** node of a particular schema is renamed to purchaseOrder, the corresponding XSD representation has the following high-level structure.</span></span>  

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

 <span data-ttu-id="ba8cb-114">相应的 XML 实例消息必须具有以下基本结构。</span><span class="sxs-lookup"><span data-stu-id="ba8cb-114">A corresponding XML instance message must have the following basic structure.</span></span>  

```  
<?xml version="1.0"?>  
<purchaseOrder ...>  
    ...  
</purchaseOrder>  
```  

> [!NOTE]
>  <span data-ttu-id="ba8cb-115">根节点可能没有**字段**属性。</span><span class="sxs-lookup"><span data-stu-id="ba8cb-115">Root nodes may not have **Field** attributes.</span></span> <span data-ttu-id="ba8cb-116">**字段**特性附加到**根**节点将不与架构一起保存。</span><span class="sxs-lookup"><span data-stu-id="ba8cb-116">**Field** attributes attached to the **Root** node are not saved with the schema.</span></span>  

## <a name="see-also"></a><span data-ttu-id="ba8cb-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba8cb-117">See Also</span></span>  
- [<span data-ttu-id="ba8cb-118">架构的 BizTalk 表示形式</span><span class="sxs-lookup"><span data-stu-id="ba8cb-118">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
- [<span data-ttu-id="ba8cb-119">节点属性</span><span class="sxs-lookup"><span data-stu-id="ba8cb-119">Node Properties</span></span>](../core/node-properties.md)   
- <span data-ttu-id="ba8cb-120">**记录节点属性**  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="ba8cb-120">**Record Node Properties**  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
- [<span data-ttu-id="ba8cb-121">如何设置节点属性</span><span class="sxs-lookup"><span data-stu-id="ba8cb-121">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)
