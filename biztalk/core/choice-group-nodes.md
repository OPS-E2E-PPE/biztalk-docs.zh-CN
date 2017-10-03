---
title: "选择组节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 466b525d-4d8c-4b8e-830d-eee27845c0dc
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec6edafcb01e2c0ce155585e4fbe2f9d61b1cf1c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="choice-group-nodes"></a><span data-ttu-id="4e089-102">“选择组”节点</span><span class="sxs-lookup"><span data-stu-id="4e089-102">Choice Group Nodes</span></span>
<span data-ttu-id="4e089-103">在 BizTalk 编辑器中，你可以插入**选项组**节点包含其他节点 （或整个子树的节点），只有一个可以出现在实例消息中。</span><span class="sxs-lookup"><span data-stu-id="4e089-103">In BizTalk Editor, you can insert a **Choice Group** node to contain other nodes (or entire subtrees of nodes), only one of which can appear in an instance message.</span></span> <span data-ttu-id="4e089-104">给定的实例消息（如果有效）将仅显示这些选择之一。</span><span class="sxs-lookup"><span data-stu-id="4e089-104">A given instance message, if valid, will have only one of the choices present.</span></span> <span data-ttu-id="4e089-105">包含的节点必须是与 XML 元素对应的节点，但不能是与 XML 属性对应的节点。</span><span class="sxs-lookup"><span data-stu-id="4e089-105">The contained nodes must be nodes that correspond to XML elements, but cannot be nodes that correspond to XML attributes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e089-106">在 BizTalk 编辑器中，**选项组**节点表示以字符串\<选择 > 架构树视图中。</span><span class="sxs-lookup"><span data-stu-id="4e089-106">In BizTalk Editor, the **Choice Group** node is represented with the string \<Choice> in the schema tree view.</span></span> <span data-ttu-id="4e089-107">如果引用设置为**选项组**节点，如 x，则它会表示为\<组： x > 架构树视图中。</span><span class="sxs-lookup"><span data-stu-id="4e089-107">If you set a reference to a **Choice Group** node, such as x, it is represented as \<Group:x> in the schema tree view.</span></span>  
  
## <a name="xsd-representation"></a><span data-ttu-id="4e089-108">XSD 表示形式</span><span class="sxs-lookup"><span data-stu-id="4e089-108">XSD representation</span></span>  
 <span data-ttu-id="4e089-109">当**选项组**节点插入到**记录**节点，它将在任何其他子节点的末尾插入**序列**，**选择**，或**所有**中的元素**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="4e089-109">When a **Choice Group** node is inserted into a **Record** node, it is inserted at the end of any other child nodes within the **sequence**, **choice**, or **all** element in the **Record** node.</span></span> <span data-ttu-id="4e089-110">下面的示例显示，粗体类型如何新**选项组**节点表示 XML 架构定义 (XSD) 语言**选择**末尾插入元素**序列**中的元素**记录**节点 （带有名为以阐明其标识的节点）。</span><span class="sxs-lookup"><span data-stu-id="4e089-110">The following example shows, in bold type, how a new **Choice Group** node is represented in the XML Schema definition (XSD) language as a **choice** element inserted at the end of the **sequence** element in a **Record** node (with nodes named to clarify their identity).</span></span>  
  
```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  
  
```  
  
 <span data-ttu-id="4e089-111">默认情况下，**选择**给定元素**minOccurs**属性值为零 (0)，表示的选项需要出现。</span><span class="sxs-lookup"><span data-stu-id="4e089-111">By default, the **choice** element is given a **minOccurs** attribute value of zero (0), indicating that none of the choices need occur.</span></span> <span data-ttu-id="4e089-112">你可以更改此值在 Visual Studio 属性窗口中的时**选项组**架构树视图中选择节点。</span><span class="sxs-lookup"><span data-stu-id="4e089-112">You can change this value in the Visual Studio Properties window when the **Choice Group** node is selected in the schema tree view.</span></span>  
  
 <span data-ttu-id="4e089-113">下面的示例演示如何将相同**选择**的 xsd 元素**元素**元素对应于两个从属**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="4e089-113">The following example shows the same **choice** element with the XSD **element** elements corresponding to two subordinate **Record** nodes.</span></span>  
  
```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
            <xs:choice minOccurs="1" maxOccurs="1">  
                <xs:element name="usAddress">  
                    <xs:complexType>  
                        <xs:sequence>  
                        </xs:sequence>  
                    </xs:complexType>  
                </xs:element>  
                <xs:element name="foreignAddress">  
                    <xs:complexType>  
                        <xs:sequence>  
                        </xs:sequence>  
                    </xs:complexType>  
                </xs:element>  
            </xs:choice>  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="4e089-114">在此示例中，两个同级**记录**节点用于描述这一事实，实例消息将具有在其中，美国地址信息的记录或在其中的全球范围内的地址信息的记录。</span><span class="sxs-lookup"><span data-stu-id="4e089-114">In this example, two sibling **Record** nodes are used to describe the fact that an instance message will either have a record with United States address information in it, or a record with worldwide address information in it.</span></span> <span data-ttu-id="4e089-115">此外， **minOccurs**和**maxOccurs**属性**选项组**节点都已设置为一 (1) 在 Visual Studio 属性窗口中，从而导致*minOccurs*和*maxOccurs*属性**选择**被设置为一 (1) 中的 XSD 表示的元素。</span><span class="sxs-lookup"><span data-stu-id="4e089-115">Further, the **minOccurs** and **maxOccurs** properties of the **Choice Group** node have both been set to one (1) in the Visual Studio Properties window, resulting in the *minOccurs* and *maxOccurs* attributes of the **choice** element being set to one (1) in the XSD representation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e089-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e089-116">See Also</span></span>  
-  [<span data-ttu-id="4e089-117">BizTalk 表示形式架构</span><span class="sxs-lookup"><span data-stu-id="4e089-117">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
-  [<span data-ttu-id="4e089-118">节点属性</span><span class="sxs-lookup"><span data-stu-id="4e089-118">Node Properties</span></span>](../core/node-properties.md)   
-  <span data-ttu-id="4e089-119">**序列组节点属性**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="4e089-119">**Sequence Group Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>     
-  [<span data-ttu-id="4e089-120">如何设置节点属性</span><span class="sxs-lookup"><span data-stu-id="4e089-120">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)