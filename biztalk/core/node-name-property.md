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
ms.openlocfilehash: c1d39c71a425e20c5a9228e418cfa86acb579fa5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="node-name-property"></a><span data-ttu-id="03475-102">“节点名称”属性</span><span class="sxs-lookup"><span data-stu-id="03475-102">Node Name Property</span></span>
<span data-ttu-id="03475-103">在使用 BizTalk 编辑器向架构树中插入节点时，需要对某些节点进行重命名，而另外一些节点则不需要。</span><span class="sxs-lookup"><span data-stu-id="03475-103">As you use BizTalk Editor to insert nodes into the schema tree, some nodes are meant to be renamed and others are not.</span></span> <span data-ttu-id="03475-104">实质上，你可以和应该重命名**记录**节点， **Field 元素**节点，和**字段特性**节点。</span><span class="sxs-lookup"><span data-stu-id="03475-104">Essentially, you can and should rename **Record** nodes, **Field Element** nodes, and **Field Attribute** nodes.</span></span> <span data-ttu-id="03475-105">您为这些节点指定的名称将成为架构所定义的消息中的 XML 元素和属性的名称。</span><span class="sxs-lookup"><span data-stu-id="03475-105">The names that you give to these nodes will become the names of the XML elements and attributes in the message that the schema defines.</span></span>  
  
 <span data-ttu-id="03475-106">在架构树中，不能重命名的节点所示的 XML 标记，则窗体也就是说，以小于比 (\<) 和大于 (\>) 符号。</span><span class="sxs-lookup"><span data-stu-id="03475-106">In the schema tree, the nodes that you cannot rename are shown in the form of XML tags; that is, with the less than (\<) and greater than (\>) signs.</span></span> <span data-ttu-id="03475-107">例如，**架构**节点，**选项组**节点， **Any 元素**节点，和**任何属性**节点表示架构中具有名称的树\<架构\>，\<选择\>，\<任何\>，和\<AnyAttribute\>分别。</span><span class="sxs-lookup"><span data-stu-id="03475-107">For example, the **Schema** node, **Choice Group** nodes, **Any Element** nodes, and **Any Attribute** nodes are represented in the schema tree with the names \<Schema\>, \<Choice\>, \<Any\>, and \<AnyAttribute\>, respectively.</span></span> <span data-ttu-id="03475-108">**节点名称**这样的节点的属性是只读的。</span><span class="sxs-lookup"><span data-stu-id="03475-108">The **Node Name** property for such nodes is read-only.</span></span>  
  
 <span data-ttu-id="03475-109">在给定**记录**节点，你不能有两个**字段特性**具有相同名称的节点。</span><span class="sxs-lookup"><span data-stu-id="03475-109">Within a given **Record** node, you cannot have two **Field Attribute** nodes with the same name.</span></span> <span data-ttu-id="03475-110">但是，有多个**Field 元素**节点或**记录**具有相同名称的相同的子节点的节点**记录**节点，只要它们都具有相同的数据类型(由指定其**数据类型**属性**Field 元素**节点或其**数据结构类型**为**记录**节点）。</span><span class="sxs-lookup"><span data-stu-id="03475-110">However, you can have more than one **Field Element** node or **Record** node with the same name as child nodes of the same **Record** node, as long as they all have the same data type (as specified by their **Data Type** property for **Field Element** nodes or their **Data Structure Type** for **Record** nodes).</span></span>  
  
 <span data-ttu-id="03475-111">当你提供名称，到**记录**节点， **Field 元素**节点，和**字段特性**节点，使用具有描述性的角色的该元素或属性中的名称正在定义的架构的消息。</span><span class="sxs-lookup"><span data-stu-id="03475-111">When you give names to **Record** nodes, **Field Element** nodes, and **Field Attribute** nodes, use names that are descriptive of the role of that element or attribute within the message being defined by the schema.</span></span> <span data-ttu-id="03475-112">例如，名字可能是一个不错的选择的名称**Field 元素**将用于存储的某人的名字地址结构中的节点。</span><span class="sxs-lookup"><span data-stu-id="03475-112">For example, FirstName is probably a good choice for the name of a **Field Element** node that will be used to store the first name of someone in an address structure.</span></span> <span data-ttu-id="03475-113">在包含名字 James 的 XML 实例消息中，相应的元素应与下面所列相似：</span><span class="sxs-lookup"><span data-stu-id="03475-113">In an XML instance message where the first name James occurs, the corresponding element would look like the following.</span></span>  
  
```  
    <FirstName>James</FirstName>  
```  
  
 <span data-ttu-id="03475-114">当你正在重命名**记录**节点， **Field 元素**节点，和**字段特性**节点，你应注意，节点名称中允许使用不是所有字符。</span><span class="sxs-lookup"><span data-stu-id="03475-114">When you are renaming **Record** nodes, **Field Element** nodes, and **Field Attribute** nodes, you should be aware that not all characters are allowed in node names.</span></span> <span data-ttu-id="03475-115">有关这些不允许的字符的信息，请参阅[的节点名称字符获取编码](../core/which-node-name-characters-get-encoded.md)。</span><span class="sxs-lookup"><span data-stu-id="03475-115">For information about these disallowed characters, see [Which Node Name Characters Get Encoded](../core/which-node-name-characters-get-encoded.md).</span></span> <span data-ttu-id="03475-116">虽然 BizTalk 编辑器允许您通过编码来使用不允许的字符，但彻底避免使用此类字符通常更为简单。</span><span class="sxs-lookup"><span data-stu-id="03475-116">Although BizTalk Editor allows you to use disallowed characters by encoding them, it is often simpler to avoid such characters altogether.</span></span> <span data-ttu-id="03475-117">有关如何信息不允许的字符进行编码，请参阅[节点名称字符获取编码方式](../core/how-node-name-characters-get-encoded.md)。</span><span class="sxs-lookup"><span data-stu-id="03475-117">For information about how disallowed characters are encoded, see [How Node Name Characters Get Encoded](../core/how-node-name-characters-get-encoded.md).</span></span>  
  
 <span data-ttu-id="03475-118">除了在节点名称中允许的字符除非它们进行编码的架构的 XSD 表示中，你不应使用 C# 保留字作为架构树中的所有根节点的名称 (除非你提供有效**RootNodeTypeName**属性值) 或架构文件的名称。</span><span class="sxs-lookup"><span data-stu-id="03475-118">In addition to the characters that are disallowed in node names, unless they are encoded in the XSD representation of the schema, you should not use C# reserved words as the names of any root nodes in the schema tree (unless you provide a valid **RootNode TypeName** property value) or as schema file names.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="03475-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="03475-119">In This Section</span></span>  
  
-   [<span data-ttu-id="03475-120">已编码的节点名称字符</span><span class="sxs-lookup"><span data-stu-id="03475-120">Which Node Name Characters Get Encoded</span></span>](../core/which-node-name-characters-get-encoded.md)  
  
-   [<span data-ttu-id="03475-121">如何对节点名称字符进行编码</span><span class="sxs-lookup"><span data-stu-id="03475-121">How Node Name Characters Get Encoded</span></span>](../core/how-node-name-characters-get-encoded.md)