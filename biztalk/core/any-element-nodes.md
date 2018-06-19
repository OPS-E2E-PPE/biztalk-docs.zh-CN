---
title: 任何元素节点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7e30fcf-31bc-4d48-9bc7-0be90e927127
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f556a5629fd98d910cbbbd83632ac1a6a1702e74
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963691"
---
# <a name="any-element-nodes"></a><span data-ttu-id="ae9ca-102">“任何元素”节点</span><span class="sxs-lookup"><span data-stu-id="ae9ca-102">Any Element Nodes</span></span>
<span data-ttu-id="ae9ca-103">在 BizTalk 编辑器中，你可以使用**Any 元素**节点以指示实例消息中的未知的元素可能出现的位置。</span><span class="sxs-lookup"><span data-stu-id="ae9ca-103">In BizTalk Editor, you can use an **Any Element** node to indicate a location within an instance message where unknown elements may appear.</span></span> <span data-ttu-id="ae9ca-104">这适用于以下情况：您知道某个元素可能会出现在实例消息内的特定位置，但不知道该元素的名称或其可能的复杂程度。</span><span class="sxs-lookup"><span data-stu-id="ae9ca-104">This accommodates situations in which you know that some element might appear at a particular location within an instance message, but you do not know the name of the element, or how complicated it might be.</span></span> <span data-ttu-id="ae9ca-105">如果你将放置**Any 元素**在架构中，BizTalk 适当的位置的节点可以处理此类未知的部分消息。</span><span class="sxs-lookup"><span data-stu-id="ae9ca-105">If you place an **Any Element** node at the appropriate location within the schema, BizTalk can process such unknown portions of a message.</span></span> <span data-ttu-id="ae9ca-106">唯一的要求是相应的 XML 应具有正确的格式。</span><span class="sxs-lookup"><span data-stu-id="ae9ca-106">The only requirement is that the corresponding XML is well-formed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae9ca-107">在 BizTalk 编辑器中， **Any 元素**节点表示以字符串\<任何\>架构树视图中。</span><span class="sxs-lookup"><span data-stu-id="ae9ca-107">In BizTalk Editor, the **Any Element** node is represented with the string \<Any\> in the schema tree view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae9ca-108">你可以控制到未知消息部分进行验证格式正确的 XML 使用程度**过程内容**属性。</span><span class="sxs-lookup"><span data-stu-id="ae9ca-108">You can control the degree to which the unknown portion of the message is validated as well-formed XML by using the **Process Contents** property.</span></span> <span data-ttu-id="ae9ca-109">在许多情况下，你可能需要设置**过程内容**属性**跳过**实例消息的位置处的内容**Any 元素**要处理的节点。</span><span class="sxs-lookup"><span data-stu-id="ae9ca-109">In many cases you may need to set the **Process Contents** property to **Skip** for the contents of an instance message at the location of the **Any Element** node to be processed.</span></span> <span data-ttu-id="ae9ca-110">保留的默认值**Strict**为**过程内容**属性将阻止从传递的实例消息验证。</span><span class="sxs-lookup"><span data-stu-id="ae9ca-110">Retaining the default value of **Strict** for the **Process Contents** property will prevent instance message validation from passing.</span></span>  
> 
> <span data-ttu-id="ae9ca-111">此属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="ae9ca-111">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="xsd-representation"></a><span data-ttu-id="ae9ca-112">XSD 表示形式</span><span class="sxs-lookup"><span data-stu-id="ae9ca-112">XSD representation</span></span>  
 <span data-ttu-id="ae9ca-113">当**Any 元素**节点添加到**记录**节点，或到另一个节点，它可以添加到如**序列组**，**选项组**，或**所有组**节点，单个 XML 标记添加到相应的 XML 架构定义 (XSD) 语言架构表示形式。</span><span class="sxs-lookup"><span data-stu-id="ae9ca-113">When an **Any Element** node is added to a **Record** node, or to another node to which it can be added such as a **Sequence Group**, **Choice Group**, or **All Group** node, a single XML tag is added to the corresponding XML Schema definition (XSD) language representation of the schema.</span></span> <span data-ttu-id="ae9ca-114">在下面的示例中，新**Any 元素**节点，粗体类型中显示其 XSD 表示形式，但已添加到现有**记录**已包含的节点**Field 元素**节点。</span><span class="sxs-lookup"><span data-stu-id="ae9ca-114">In the following example, a new **Any Element** node, whose XSD representation is shown in bold type, has been added to an existing **Record** node that already contains a **Field Element** node.</span></span>  
  
```  
<xs:element name="ExistingRecord">  
    <xs:complexType>  
        <xs:sequence>  
             <xs:element name="ExistingFieldElement" type="xs:string" />  
            <xs:any />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="ae9ca-115">假设**过程内容**属性**Any 元素**节点设置为**跳过**中实例消息受此架构片段， **ExistingRecord**元素应包含**ExistingFieldElement**元素，其中包含字符串数据后, 跟任意复杂度的任何单个元素。</span><span class="sxs-lookup"><span data-stu-id="ae9ca-115">Assuming that the **Process Contents** property of the **Any Element** node is set to **Skip**, within an instance message governed by this schema fragment, an **ExistingRecord** element is expected to contain an **ExistingFieldElement** element containing string data, followed by any single element of arbitrary complexity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae9ca-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae9ca-116">See Also</span></span>  
 <span data-ttu-id="ae9ca-117">[BizTalk 表示形式架构](../core/biztalk-representation-of-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="ae9ca-117">[BizTalk Representation of Schemas](../core/biztalk-representation-of-schemas.md) </span></span>  
 <span data-ttu-id="ae9ca-118">[节点属性](../core/node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="ae9ca-118">[Node Properties](../core/node-properties.md) </span></span>  
 <span data-ttu-id="ae9ca-119">[如何设置节点属性](../core/how-to-set-node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="ae9ca-119">[How to Set Node Properties](../core/how-to-set-node-properties.md) </span></span>  
 [<span data-ttu-id="ae9ca-120">“任何属性”节点</span><span class="sxs-lookup"><span data-stu-id="ae9ca-120">Any Attribute Nodes</span></span>](../core/any-attribute-nodes.md)