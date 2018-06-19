---
title: 任何属性节点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa2d25bc-3a8f-4fd9-acad-341b8e80c737
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82490a114149e3d4f71e3598900be5599c8a36e2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964643"
---
# <a name="any-attribute-nodes"></a><span data-ttu-id="121a5-102">“任何属性”节点</span><span class="sxs-lookup"><span data-stu-id="121a5-102">Any Attribute Nodes</span></span>
<span data-ttu-id="121a5-103">在 BizTalk 编辑器中，你可以使用**任何属性**节点以指示可能出现零个或多个未知的属性实例消息中 （已知） 元素。</span><span class="sxs-lookup"><span data-stu-id="121a5-103">In BizTalk Editor, you can use an **Any Attribute** node to indicate a (known) element within an instance message for which zero or more unknown attributes may appear.</span></span> <span data-ttu-id="121a5-104">这适用于以下情况：您知道某特定元素将存在于实例消息中的特定位置，但您不十分确定该元素可能包含哪些属性。</span><span class="sxs-lookup"><span data-stu-id="121a5-104">This accommodates situations in which you know that a particular element will be present at a particular location within an instance message, but you are not sure exactly what attributes that element might include.</span></span> <span data-ttu-id="121a5-105">如果你将放置**任何属性**中的节点**记录**的相关元素与关联的节点，BizTalk 可以处理该元素，与正在任何关联的属性，唯一的要求语法更正 (attributeName ="attributeValue")。</span><span class="sxs-lookup"><span data-stu-id="121a5-105">If you place an **Any Attribute** node within the **Record** node associated with the relevant element, BizTalk can process that element, with the only requirement being that any associated attributes are syntactically correct (attributeName="attributeValue").</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="121a5-106">在 BizTalk 编辑器中，**任何属性**节点表示以字符串\<AnyAttribute\>架构树视图中。</span><span class="sxs-lookup"><span data-stu-id="121a5-106">In BizTalk Editor, the **Any Attribute** node is represented with the string \<AnyAttribute\> in the schema tree view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="121a5-107">你可以控制到未知消息部分进行验证格式正确的 XML 使用程度**过程内容**属性。</span><span class="sxs-lookup"><span data-stu-id="121a5-107">You can control the degree to which the unknown portion of the message is validated as well-formed XML by using the **Process Contents** property.</span></span> <span data-ttu-id="121a5-108">在许多情况下，你可能需要设置**过程内容**属性**跳过**实例消息的位置处的内容**任何属性**要处理的节点.</span><span class="sxs-lookup"><span data-stu-id="121a5-108">In many cases you may need to set the **Process Contents** property to **Skip** for the contents of an instance message at the location of the **Any Attribute** node to be processed.</span></span> <span data-ttu-id="121a5-109">保留的默认值**Strict**为**过程内容**属性将阻止从传递的实例消息验证。</span><span class="sxs-lookup"><span data-stu-id="121a5-109">Retaining the default value of **Strict** for the **Process Contents** property will prevent instance message validation from passing.</span></span>  
>
> <span data-ttu-id="121a5-110">此属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="121a5-110">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="xsd-representation"></a><span data-ttu-id="121a5-111">XSD 表示形式</span><span class="sxs-lookup"><span data-stu-id="121a5-111">XSD representation</span></span>  
 <span data-ttu-id="121a5-112">当**任何属性**节点添加到**记录**节点或**属性组**节点，单个 XML 标记添加到相应的 XML 架构定义 (XSD) 语言架构表示形式。</span><span class="sxs-lookup"><span data-stu-id="121a5-112">When an **Any Attribute** node is added to a **Record** node or to an **Attribute Group** node, a single XML tag is added to the corresponding XML Schema definition (XSD) language representation of the schema.</span></span> <span data-ttu-id="121a5-113">在下面的示例中，新**任何属性**节点，显示其 XSD 表示形式中加粗，并且已添加到现有**记录**已包含的节点**Field 元素**节点。</span><span class="sxs-lookup"><span data-stu-id="121a5-113">In the following example, a new **Any Attribute** node, whose XSD representation is shown in bold, has been added to an existing **Record** node that already contains a **Field Element** node.</span></span>  
  
```  
<xs:element name="ExistingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
        <xs:anyAttribute />  
    </xs:complexType>  
</xs:element  
```  
  
 <span data-ttu-id="121a5-114">在前面的示例中，新的 XSD 表示**任何属性**节点将添加**anyAttribute**到末尾的包含的元素 (**记录**节点) **元素**元素、 外部**序列**元素，就能在**complexType**元素。</span><span class="sxs-lookup"><span data-stu-id="121a5-114">In the preceding example, the XSD representation of the new **Any Attribute** node adds an **anyAttribute** element to the end of the containing (**Record** node) **element** element, outside the **sequence** element and within the **complexType** element.</span></span> <span data-ttu-id="121a5-115">这就是所有**属性**元素，而那些具有非**属性组**节点，添加到其包含**元素**元素。</span><span class="sxs-lookup"><span data-stu-id="121a5-115">This is where all **attribute** elements, other than those with an **Attribute Group** node, are added to their containing **element** elements.</span></span>  
  
 <span data-ttu-id="121a5-116">现在，并假定**过程内容**属性**任何属性**节点设置为**跳过**中实例消息受此架构片段， **ExistingRecord**元素预期行为，而且它可以包含任何属性，只要它们是与 XML 语法格式正确。</span><span class="sxs-lookup"><span data-stu-id="121a5-116">Now, and assuming that the **Process Contents** property of the **Any Attribute** node is set to **Skip**, within an instance message governed by this schema fragment, an **ExistingRecord** element is expected, and it can contain any attributes so long as they are well-formed with respect to XML syntax.</span></span> <span data-ttu-id="121a5-117">(若要符合在此示例中的 XSD 片段，它必须包含**ExistingFieldElement**元素也。)</span><span class="sxs-lookup"><span data-stu-id="121a5-117">(To conform to the XSD fragment in this example, it must also contain the **ExistingFieldElement** element as well.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="121a5-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="121a5-118">See Also</span></span>  
 <span data-ttu-id="121a5-119">[BizTalk 表示形式架构](../core/biztalk-representation-of-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="121a5-119">[BizTalk Representation of Schemas](../core/biztalk-representation-of-schemas.md) </span></span>  
 <span data-ttu-id="121a5-120">[节点属性](../core/node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="121a5-120">[Node Properties](../core/node-properties.md) </span></span>  
 <span data-ttu-id="121a5-121">[如何设置节点属性](../core/how-to-set-node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="121a5-121">[How to Set Node Properties](../core/how-to-set-node-properties.md) </span></span>  
 [<span data-ttu-id="121a5-122">“任何元素”节点</span><span class="sxs-lookup"><span data-stu-id="121a5-122">Any Element Nodes</span></span>](../core/any-element-nodes.md)