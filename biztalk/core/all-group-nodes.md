---
title: "所有组节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e28d98c-746a-44d8-bed2-ba539b8432aa
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f51d6420b7d754ffb8706e2bc729a02df00b4338
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="all-group-nodes"></a><span data-ttu-id="035f2-102">“全部组”节点</span><span class="sxs-lookup"><span data-stu-id="035f2-102">All Group Nodes</span></span>
<span data-ttu-id="035f2-103">在 BizTalk 编辑器中，你可以插入**所有组**节点包含其他节点将出现零次或一次，按任何顺序。</span><span class="sxs-lookup"><span data-stu-id="035f2-103">In BizTalk Editor, you can insert an **All Group** node to contain other nodes that will appear zero or one time, in any order.</span></span> <span data-ttu-id="035f2-104">在 XML 架构定义 (XSD) 语言中，**所有组**具有比的详细使用情况限制**序列**和**选择**组，将转换为中的几种情况下其中你将能够创建 BizTalk 编辑器**所有组**节点。</span><span class="sxs-lookup"><span data-stu-id="035f2-104">In XML Schema definition (XSD) language, the **All group** has more usage limitations than **Sequence** and **Choice** groups, which translates to few situations within BizTalk Editor where you will be able to create an **All Group** node.</span></span>  
  
 <span data-ttu-id="035f2-105">若要使用**所有组**节点在 BizTalk 编辑器中，你需要执行一些额外步骤： 创建的最简单办法**所有组**节点是更改的值**组顺序类型**父属性**记录**节点**所有**。</span><span class="sxs-lookup"><span data-stu-id="035f2-105">To use an **All Group** node in BizTalk Editor, you need to follow some extra steps: The easiest way to create an **All Group** node is to change the value of the **Group Order Type** property of the parent **Record** node to **All**.</span></span> <span data-ttu-id="035f2-106">这样可确保所有的从属节点**记录**节点都包含在**所有组**节点。</span><span class="sxs-lookup"><span data-stu-id="035f2-106">This ensures that all of the subordinate nodes of the **Record** node are contained within the **All Group** node.</span></span>  <span data-ttu-id="035f2-107">请参阅**组顺序类型** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="035f2-107">See **Group Order Type** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="035f2-108">使用另一种**所有组**开头插入一个新节点在 BizTalk 编辑器**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="035f2-108">Another way to use an **All Group** node in BizTalk Editor begins with inserting a new **Record** node.</span></span> <span data-ttu-id="035f2-109">在插入新后**记录**节点，更改其**内容类型**属性**ComplexContent**。</span><span class="sxs-lookup"><span data-stu-id="035f2-109">After inserting the new **Record** node, change its **Content Type** property to **ComplexContent**.</span></span> <span data-ttu-id="035f2-110">然后你可以将插入**所有组**节点的子级作为**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="035f2-110">Then you can insert an **All Group** node as a child of the **Record** node.</span></span> <span data-ttu-id="035f2-111">这是必需的因为**所有组**只能当继承涉及到插入。</span><span class="sxs-lookup"><span data-stu-id="035f2-111">This is required because the **All Group** can only be inserted when inheritance is involved.</span></span> <span data-ttu-id="035f2-112">通过指定包含**记录**节点包含复杂内容，其数据类型将成为基于数据类型**xs: anytype**派生的扩展。</span><span class="sxs-lookup"><span data-stu-id="035f2-112">By specifying that the containing **Record** node contains complex content, its data type becomes based on the data type **xs:anyType**, derived by extension.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="035f2-113">在 BizTalk 编辑器中，**所有组**节点表示以字符串\<所有 > 架构树视图中。</span><span class="sxs-lookup"><span data-stu-id="035f2-113">In BizTalk Editor, the **All Group** node is represented with the string \<All> in the schema tree view.</span></span> <span data-ttu-id="035f2-114">如果引用设置为**所有组**节点，如到 x，它会表示为\<组： x > 架构树视图中。</span><span class="sxs-lookup"><span data-stu-id="035f2-114">If you set a reference to an **All Group** node, such as to x, it is represented as \<Group:x> in the schema tree view.</span></span>  
  
## <a name="xsd-representation"></a><span data-ttu-id="035f2-115">XSD 表示形式</span><span class="sxs-lookup"><span data-stu-id="035f2-115">XSD representation</span></span>  
 <span data-ttu-id="035f2-116">**所有组**节点可以插入到**记录**节点，但仅当它是唯一的非属性子节点的**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="035f2-116">An **All Group** node can be inserted into a **Record** node, but only if it is the only non-attribute child node of that **Record** node.</span></span> <span data-ttu-id="035f2-117">下面的示例显示，在步骤中，如何新**所有组**节点表示 XML 架构定义 (XSD) 语言**所有**元素作为 BizTalk 编辑器中的步骤执行 （具有名为的节点若要阐明其标识）。</span><span class="sxs-lookup"><span data-stu-id="035f2-117">The following example shows, in steps, how a new **All Group** node is represented in the XML Schema definition (XSD) language as an **all** element as the steps in BizTalk Editor are performed (with nodes named to clarify their identity).</span></span>  
  
```  
<xs:element name="NewRecord">  
    <xs:complexType />   
</xs:element>  
```  
  
 <span data-ttu-id="035f2-118">在前面的 XSD 片段中，所示添加一条新记录后其**内容类型**属性更改为**ComplexContent**，从而导致以下 XSD 修改。</span><span class="sxs-lookup"><span data-stu-id="035f2-118">After adding a new record as shown in the preceding XSD fragment, its **Content Type** property is changed to **ComplexContent**, resulting in the following XSD modifications.</span></span>  
  
```  
<xs:element name="NewRecord">  
    <xs:complexType>  
        <xs:complexContent mixed="false">  
             <xs:extension base="xs:anyType" />  
        </xs:complexContent>  
    </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="035f2-119">现在**所有组**可以作为新的记录的子级插入节点，如下面的 XSD 段中所示。</span><span class="sxs-lookup"><span data-stu-id="035f2-119">Now the **All Group** node can be inserted as a child of the new record, as shown in the following XSD fragment.</span></span>  
  
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
  
 <span data-ttu-id="035f2-120">最后，可以作为新的子级插入相应的节点**所有组**节点。</span><span class="sxs-lookup"><span data-stu-id="035f2-120">Finally, you can insert appropriate nodes as children of the new **All Group** node.</span></span> <span data-ttu-id="035f2-121">下面的示例演示**记录**节点和**Field 元素**节点作为新的子节点插入**所有组**节点。</span><span class="sxs-lookup"><span data-stu-id="035f2-121">The following example shows a **Record** node and a **Field Element** node inserted as child nodes of the new **All Group** node.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="035f2-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="035f2-122">See Also</span></span>  
-  [<span data-ttu-id="035f2-123">BizTalk 表示形式架构</span><span class="sxs-lookup"><span data-stu-id="035f2-123">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
-  [<span data-ttu-id="035f2-124">节点属性</span><span class="sxs-lookup"><span data-stu-id="035f2-124">Node Properties</span></span>](../core/node-properties.md)   
-  <span data-ttu-id="035f2-125">**序列组节点属性**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="035f2-125">**Sequence Group Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span> 
-  [<span data-ttu-id="035f2-126">如何设置节点属性</span><span class="sxs-lookup"><span data-stu-id="035f2-126">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)