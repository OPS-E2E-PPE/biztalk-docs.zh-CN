---
title: 序列组节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 139c3daa-a682-4bf7-bbb7-b5694ced0431
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c113d0cfd0f6055d55b0329bba3c1ec60bf835e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019739"
---
# <a name="sequence-group-nodes"></a><span data-ttu-id="e8d0a-102">“顺序组”节点</span><span class="sxs-lookup"><span data-stu-id="e8d0a-102">Sequence Group Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="e8d0a-103">概述</span><span class="sxs-lookup"><span data-stu-id="e8d0a-103">Overview</span></span>
<span data-ttu-id="e8d0a-104">在 BizTalk 编辑器中，可以插入**序列组**节点以包含其他节点必须出现在实例消息中出现的相同顺序**序列组**节点。</span><span class="sxs-lookup"><span data-stu-id="e8d0a-104">In BizTalk Editor, you can insert a **Sequence Group** node to contain other nodes that must appear in an instance message in the same order in which they appear within the **Sequence Group** node.</span></span> <span data-ttu-id="e8d0a-105">包含的节点必须是与 XML 元素对应的节点，但不能是与 XML 属性对应的节点。</span><span class="sxs-lookup"><span data-stu-id="e8d0a-105">The contained nodes must be nodes that correspond to XML elements, but cannot be nodes that correspond to XML attributes.</span></span>  

> [!NOTE]
>  <span data-ttu-id="e8d0a-106">在 BizTalk 编辑器中，**序列组**节点的表示方法的字符串的默认\<序列\>架构树视图中。</span><span class="sxs-lookup"><span data-stu-id="e8d0a-106">In BizTalk Editor, the **Sequence Group** node is represented by default with the string \<Sequence\> in the schema tree view.</span></span> <span data-ttu-id="e8d0a-107">如果引用设置为**序列组**节点，如 x，它将表示为\<Group: x\>架构树视图中。</span><span class="sxs-lookup"><span data-stu-id="e8d0a-107">If you set a reference to a **Sequence Group** node, such as x, it is represented as \<Group:x\> in the schema tree view.</span></span>  

 <span data-ttu-id="e8d0a-108">您可能想要添加**序列组**声明全局元素组。</span><span class="sxs-lookup"><span data-stu-id="e8d0a-108">You may want to add a **Sequence Group** to declare a global element group.</span></span>  

 <span data-ttu-id="e8d0a-109">可能需要为 XML 创建架构，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e8d0a-109">You may need to create a schema for XML as follows.</span></span>  

```  
<Root>  
    <Record1>  
        <GroupItem1/>  
        <GroupItem2/>  
        <NotAGroupItem>  
    </Record1>  
    <Record2>  
        <GroupItem1/>  
        <GroupItem2/>  
    </Record2>  
</Root>  

```  

 <span data-ttu-id="e8d0a-110">由于在两种情况下都存在 GroupItem1 和 GroupItem2，因此可以声明一个既是 Record1 的子项又是 Record2 的子项的全局顺序组。</span><span class="sxs-lookup"><span data-stu-id="e8d0a-110">Because GroupItem1 and GroupItem2 exist in both cases, you may declare a global sequence group that is a child of both Record1 and Record2.</span></span> <span data-ttu-id="e8d0a-111">有关如何声明全局顺序组的分步说明，请参阅[到另一个节点或类型创建引用](../core/how-to-create-references-to-another-node-or-type.md)。</span><span class="sxs-lookup"><span data-stu-id="e8d0a-111">For step-by-step instructions about how to declare a global sequence group, see [Creating References to Another Node or Type](../core/how-to-create-references-to-another-node-or-type.md).</span></span>  

 <span data-ttu-id="e8d0a-112">用户可以更改的隐藏的组要**选择组**节点或**全部组**节点 (因此它不一定是**序列组**节点) 通过更改**组顺序类型**属性。</span><span class="sxs-lookup"><span data-stu-id="e8d0a-112">A user can change the hidden group to be a **Choice Group** node or an **All Group** node (so it is not necessarily a **Sequence Group** node) by changing the **Group Order Type** property.</span></span> <span data-ttu-id="e8d0a-113">此属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="e8d0a-113">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="xsd-representation"></a><span data-ttu-id="e8d0a-114">XSD 表示形式</span><span class="sxs-lookup"><span data-stu-id="e8d0a-114">XSD representation</span></span>  
 <span data-ttu-id="e8d0a-115">当**序列组**节点插入到**记录**节点中的其他所有子节点结尾处插入该实体**序列**，**选择**，或**所有**中的元素**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="e8d0a-115">When a **Sequence Group** node is inserted into a **Record** node, it is inserted at the end of any other child nodes within the **sequence**, **choice**, or **all** element in the **Record** node.</span></span> <span data-ttu-id="e8d0a-116">下面的示例显示了一个新**序列组**节点，以粗体类型，在末尾处插入**序列**中的元素**记录**节点 (节点命名以说明其标识）。</span><span class="sxs-lookup"><span data-stu-id="e8d0a-116">The following example shows a new **Sequence Group** node, in bold type, inserted at the end of the **sequence** element in a **Record** node (with nodes named to clarify their identity).</span></span>  

```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  

```  

## <a name="see-also"></a><span data-ttu-id="e8d0a-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8d0a-117">See Also</span></span>  
- [<span data-ttu-id="e8d0a-118">架构的 BizTalk 表示形式</span><span class="sxs-lookup"><span data-stu-id="e8d0a-118">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
- [<span data-ttu-id="e8d0a-119">节点属性</span><span class="sxs-lookup"><span data-stu-id="e8d0a-119">Node Properties</span></span>](../core/node-properties.md)   
- <span data-ttu-id="e8d0a-120">**序列组节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="e8d0a-120">**Sequence Group Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
- [<span data-ttu-id="e8d0a-121">如何设置节点属性</span><span class="sxs-lookup"><span data-stu-id="e8d0a-121">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)
