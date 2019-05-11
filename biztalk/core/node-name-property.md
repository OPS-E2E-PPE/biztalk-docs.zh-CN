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
# <a name="node-name-property"></a><span data-ttu-id="a998f-102">节点名称属性</span><span class="sxs-lookup"><span data-stu-id="a998f-102">Node Name Property</span></span>
<span data-ttu-id="a998f-103">因为你可以使用 BizTalk 编辑器来将节点插入到架构树中，某些节点为了进行重命名，但有些却不。</span><span class="sxs-lookup"><span data-stu-id="a998f-103">As you use BizTalk Editor to insert nodes into the schema tree, some nodes are meant to be renamed and others are not.</span></span> <span data-ttu-id="a998f-104">实质上，可以并应该重命名**记录**节点， **Field 元素**节点，并**字段属性**节点。</span><span class="sxs-lookup"><span data-stu-id="a998f-104">Essentially, you can and should rename **Record** nodes, **Field Element** nodes, and **Field Attribute** nodes.</span></span> <span data-ttu-id="a998f-105">向这些节点的名称将成为 XML 元素和在该架构定义的消息中的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="a998f-105">The names that you give to these nodes will become the names of the XML elements and attributes in the message that the schema defines.</span></span>  
  
 <span data-ttu-id="a998f-106">在架构树中，不能重命名的节点所示的 XML 标记，则窗体即，带有小于比 (\<) 和大于号 (\>) 符号。</span><span class="sxs-lookup"><span data-stu-id="a998f-106">In the schema tree, the nodes that you cannot rename are shown in the form of XML tags; that is, with the less than (\<) and greater than (\>) signs.</span></span> <span data-ttu-id="a998f-107">例如，**架构**节点，**选择组**节点， **Any 元素**节点，以及**任何属性**节点在架构中表示具有名称的树\<架构\>，\<选\>，\<任何\>，并\<AnyAttribute\>分别。</span><span class="sxs-lookup"><span data-stu-id="a998f-107">For example, the **Schema** node, **Choice Group** nodes, **Any Element** nodes, and **Any Attribute** nodes are represented in the schema tree with the names \<Schema\>, \<Choice\>, \<Any\>, and \<AnyAttribute\>, respectively.</span></span> <span data-ttu-id="a998f-108">**节点名称**此类节点的属性是只读的。</span><span class="sxs-lookup"><span data-stu-id="a998f-108">The **Node Name** property for such nodes is read-only.</span></span>  
  
 <span data-ttu-id="a998f-109">在给定**记录**节点，您不能有两个**字段属性**具有相同名称的节点。</span><span class="sxs-lookup"><span data-stu-id="a998f-109">Within a given **Record** node, you cannot have two **Field Attribute** nodes with the same name.</span></span> <span data-ttu-id="a998f-110">但是，有多个**Field 元素**节点或**记录**使用相同的名称相同的子节点的节点**记录**节点，只要它们都具有相同的数据类型(根据其**数据类型**属性**字段元素**节点或其**Data Structure Type**为**记录**节点）。</span><span class="sxs-lookup"><span data-stu-id="a998f-110">However, you can have more than one **Field Element** node or **Record** node with the same name as child nodes of the same **Record** node, as long as they all have the same data type (as specified by their **Data Type** property for **Field Element** nodes or their **Data Structure Type** for **Record** nodes).</span></span>  
  
 <span data-ttu-id="a998f-111">当授予名称传递给**记录**节点，**字段元素**节点，并**字段属性**节点，使用具有描述性的角色的该元素或属性内的名称由架构所定义的消息。</span><span class="sxs-lookup"><span data-stu-id="a998f-111">When you give names to **Record** nodes, **Field Element** nodes, and **Field Attribute** nodes, use names that are descriptive of the role of that element or attribute within the message being defined by the schema.</span></span> <span data-ttu-id="a998f-112">例如，名字可能是不错的选择的名称**Field 元素**将用于存储人员名字的地址结构中的节点。</span><span class="sxs-lookup"><span data-stu-id="a998f-112">For example, FirstName is probably a good choice for the name of a **Field Element** node that will be used to store the first name of someone in an address structure.</span></span> <span data-ttu-id="a998f-113">在出现第一个名称 James XML 实例消息中，如以下所示的相应元素。</span><span class="sxs-lookup"><span data-stu-id="a998f-113">In an XML instance message where the first name James occurs, the corresponding element would look like the following.</span></span>  
  
```  
    <FirstName>James</FirstName>  
```  
  
 <span data-ttu-id="a998f-114">当您要重命名**记录**节点，**字段元素**节点，并**字段属性**节点，您应注意，节点名中允许使用不是所有字符。</span><span class="sxs-lookup"><span data-stu-id="a998f-114">When you are renaming **Record** nodes, **Field Element** nodes, and **Field Attribute** nodes, you should be aware that not all characters are allowed in node names.</span></span> <span data-ttu-id="a998f-115">有关这些不允许的字符的信息，请参阅[的节点名称字符进行编码](../core/which-node-name-characters-get-encoded.md)。</span><span class="sxs-lookup"><span data-stu-id="a998f-115">For information about these disallowed characters, see [Which Node Name Characters Get Encoded](../core/which-node-name-characters-get-encoded.md).</span></span> <span data-ttu-id="a998f-116">尽管 BizTalk 编辑器允许您通过不允许的字符对它们进行编码，但它通常是更简单，若要完全避免此类字符。</span><span class="sxs-lookup"><span data-stu-id="a998f-116">Although BizTalk Editor allows you to use disallowed characters by encoding them, it is often simpler to avoid such characters altogether.</span></span> <span data-ttu-id="a998f-117">有关如何信息不允许的字符进行编码，请参阅[如何节点名称字符进行编码](../core/how-node-name-characters-get-encoded.md)。</span><span class="sxs-lookup"><span data-stu-id="a998f-117">For information about how disallowed characters are encoded, see [How Node Name Characters Get Encoded](../core/how-node-name-characters-get-encoded.md).</span></span>  
  
 <span data-ttu-id="a998f-118">除了节点名中不允许的字符其进行了编码的架构的 XSD 表示形式，则不应使用C#保留字作为架构树中任何根节点的名称 (除非提供有效**RootNode TypeName**属性值) 或作为架构文件名。</span><span class="sxs-lookup"><span data-stu-id="a998f-118">In addition to the characters that are disallowed in node names, unless they are encoded in the XSD representation of the schema, you should not use C# reserved words as the names of any root nodes in the schema tree (unless you provide a valid **RootNode TypeName** property value) or as schema file names.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a998f-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="a998f-119">In This Section</span></span>  
  
-   [<span data-ttu-id="a998f-120">已编码的节点名称字符</span><span class="sxs-lookup"><span data-stu-id="a998f-120">Which Node Name Characters Get Encoded</span></span>](../core/which-node-name-characters-get-encoded.md)  
  
-   [<span data-ttu-id="a998f-121">如何对节点名称字符进行编码</span><span class="sxs-lookup"><span data-stu-id="a998f-121">How Node Name Characters Get Encoded</span></span>](../core/how-node-name-characters-get-encoded.md)