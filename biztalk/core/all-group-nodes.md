---
title: 所有节点进行分组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e28d98c-746a-44d8-bed2-ba539b8432aa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29b189311ebf6aa61a762cc31f09239cb69387b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360414"
---
# <a name="all-group-nodes"></a><span data-ttu-id="aff73-102">所有组节点</span><span class="sxs-lookup"><span data-stu-id="aff73-102">All Group Nodes</span></span>
<span data-ttu-id="aff73-103">在 BizTalk 编辑器中，可以插入**全部组**节点可包含零个或一个时，按任意顺序将出现其他节点。</span><span class="sxs-lookup"><span data-stu-id="aff73-103">In BizTalk Editor, you can insert an **All Group** node to contain other nodes that will appear zero or one time, in any order.</span></span> <span data-ttu-id="aff73-104">在 XML 架构定义 (XSD) 语言中，**所有组**具有更多的使用情况限制比**序列**并**选择**组，这会转换为内，这样的情况BizTalk 编辑器中，你将能够创建**全部组**节点。</span><span class="sxs-lookup"><span data-stu-id="aff73-104">In XML Schema definition (XSD) language, the **All group** has more usage limitations than **Sequence** and **Choice** groups, which translates to few situations within BizTalk Editor where you will be able to create an **All Group** node.</span></span>  

 <span data-ttu-id="aff73-105">若要使用**全部组**节点在 BizTalk 编辑器中，你需要遵循一些额外的步骤：创建的最简单办法**全部组**节点是若要更改的值**Group Order Type**的父对象**记录**节点到**所有**.</span><span class="sxs-lookup"><span data-stu-id="aff73-105">To use an **All Group** node in BizTalk Editor, you need to follow some extra steps: The easiest way to create an **All Group** node is to change the value of the **Group Order Type** property of the parent **Record** node to **All**.</span></span> <span data-ttu-id="aff73-106">这可确保所有的从属节点**记录**节点中包含**全部组**节点。</span><span class="sxs-lookup"><span data-stu-id="aff73-106">This ensures that all of the subordinate nodes of the **Record** node are contained within the **All Group** node.</span></span>  <span data-ttu-id="aff73-107">请参阅**组顺序类型** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="aff73-107">See **Group Order Type** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

 <span data-ttu-id="aff73-108">另一种方法使用**全部组**节点在 BizTalk 编辑器中首先插入一个新**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="aff73-108">Another way to use an **All Group** node in BizTalk Editor begins with inserting a new **Record** node.</span></span> <span data-ttu-id="aff73-109">插入新后**记录**节点，更改其**内容类型**属性设置为**ComplexContent**。</span><span class="sxs-lookup"><span data-stu-id="aff73-109">After inserting the new **Record** node, change its **Content Type** property to **ComplexContent**.</span></span> <span data-ttu-id="aff73-110">然后可以插入**全部组**节点的子级作为节点**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="aff73-110">Then you can insert an **All Group** node as a child of the **Record** node.</span></span> <span data-ttu-id="aff73-111">这是必需的因为**全部组**仅涉及继承时，要插入。</span><span class="sxs-lookup"><span data-stu-id="aff73-111">This is required because the **All Group** can only be inserted when inheritance is involved.</span></span> <span data-ttu-id="aff73-112">通过指定包含**记录**节点包含复杂内容，其数据类型将变为基于的数据类型**xs: anytype**、 通过扩展派生。</span><span class="sxs-lookup"><span data-stu-id="aff73-112">By specifying that the containing **Record** node contains complex content, its data type becomes based on the data type **xs:anyType**, derived by extension.</span></span>  

> [!NOTE]
>  <span data-ttu-id="aff73-113">在 BizTalk 编辑器中，**全部组**节点表示的字符串\<所有 > 架构树视图中。</span><span class="sxs-lookup"><span data-stu-id="aff73-113">In BizTalk Editor, the **All Group** node is represented with the string \<All> in the schema tree view.</span></span> <span data-ttu-id="aff73-114">如果引用设置为**全部组**节点，例如为 x，它表示为\<Group: x > 架构树视图中。</span><span class="sxs-lookup"><span data-stu-id="aff73-114">If you set a reference to an **All Group** node, such as to x, it is represented as \<Group:x> in the schema tree view.</span></span>  

## <a name="xsd-representation"></a><span data-ttu-id="aff73-115">XSD 表示形式</span><span class="sxs-lookup"><span data-stu-id="aff73-115">XSD representation</span></span>  
 <span data-ttu-id="aff73-116">**全部组**节点可以插入到**记录**节点，但只有它的唯一非属性子节点**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="aff73-116">An **All Group** node can be inserted into a **Record** node, but only if it is the only non-attribute child node of that **Record** node.</span></span> <span data-ttu-id="aff73-117">下面的示例所示，在步骤中，一个新的方式**全部组**节点以 XML 架构定义 (XSD) 语言表示**所有**元素与在 BizTalk 编辑器中的步骤执行 （具有节点名分别为以说明其标识）。</span><span class="sxs-lookup"><span data-stu-id="aff73-117">The following example shows, in steps, how a new **All Group** node is represented in the XML Schema definition (XSD) language as an **all** element as the steps in BizTalk Editor are performed (with nodes named to clarify their identity).</span></span>  

```  
<xs:element name="NewRecord">  
    <xs:complexType />   
</xs:element>  
```  

 <span data-ttu-id="aff73-118">按照以上 XSD 片断中, 所示添加新记录后其**内容类型**属性更改为**ComplexContent**，从而导致以下 XSD 修改。</span><span class="sxs-lookup"><span data-stu-id="aff73-118">After adding a new record as shown in the preceding XSD fragment, its **Content Type** property is changed to **ComplexContent**, resulting in the following XSD modifications.</span></span>  

```  
<xs:element name="NewRecord">  
    <xs:complexType>  
        <xs:complexContent mixed="false">  
             <xs:extension base="xs:anyType" />  
        </xs:complexContent>  
    </xs:complexType>  
</xs:element>  
```  

 <span data-ttu-id="aff73-119">现在**全部组**中以下 XSD 片断所示，可以为新记录的子级插入节点。</span><span class="sxs-lookup"><span data-stu-id="aff73-119">Now the **All Group** node can be inserted as a child of the new record, as shown in the following XSD fragment.</span></span>  

```  
<xs:element name="NewRecord">  
    <xs:complexType>  
        <xs:complexContent mixed="false">  
            <xs:extension base="xs:anyType">  
                <xs:all />   
             </xs:extension>  
          </xs:complexContent>  
     </xs:complexType>  
</xs:element>  
```  

 <span data-ttu-id="aff73-120">最后，可以插入相应的节点作为新的子级**全部组**节点。</span><span class="sxs-lookup"><span data-stu-id="aff73-120">Finally, you can insert appropriate nodes as children of the new **All Group** node.</span></span> <span data-ttu-id="aff73-121">下面的示例演示**记录**节点和一个**Field 元素**节点作为新的子节点插入**全部组**节点。</span><span class="sxs-lookup"><span data-stu-id="aff73-121">The following example shows a **Record** node and a **Field Element** node inserted as child nodes of the new **All Group** node.</span></span>  

```  
<xs:element name="NewRecord">  
    <xs:complexType>  
        <xs:complexContent mixed="false">  
            <xs:extension base="xs:anyType">  
                <xs:all>  
                    <xs:element name="RecordChildOfAllGroup">  
                        <xs:complexType />  
                    </xs:element>  
                    <xs:element name="FieldElementChildOfAllGroup" type="xs:string" />  
                </xs:all>  
            </xs:extension>  
        </xs:complexContent>  
    </xs:complexType>  
</xs:element>  
```  

## <a name="see-also"></a><span data-ttu-id="aff73-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="aff73-122">See Also</span></span>  
- [<span data-ttu-id="aff73-123">架构的 BizTalk 表示形式</span><span class="sxs-lookup"><span data-stu-id="aff73-123">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
- [<span data-ttu-id="aff73-124">节点属性</span><span class="sxs-lookup"><span data-stu-id="aff73-124">Node Properties</span></span>](../core/node-properties.md)   
- <span data-ttu-id="aff73-125">**序列组节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="aff73-125">**Sequence Group Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span> 
- [<span data-ttu-id="aff73-126">如何设置节点属性</span><span class="sxs-lookup"><span data-stu-id="aff73-126">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)
