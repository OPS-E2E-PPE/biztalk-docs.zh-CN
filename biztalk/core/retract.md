---
title: "收回 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Retract function [Business Rules Engine], TypedData table
- Retract function [Business Rules Engine], TypedXMLDocument
- Retract function [Business Rules Engine]
- Retract function [Business Rules Engine], DataConnection
- Retract function [Business Rules Engine], .NET objects
- .NET objects
ms.assetid: 24b6b894-6810-4497-a122-8c91f0b2e816
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17eb4739412d310d2a69b53c8470abc7461ce3ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="retract"></a><span data-ttu-id="ca4c2-102">收回</span><span class="sxs-lookup"><span data-stu-id="ca4c2-102">Retract</span></span>
<span data-ttu-id="ca4c2-103">你可以使用**收回**函数从业务规则引擎使用内存中移除对象。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-103">You can use the **Retract** function to remove objects from the Business Rule Engine's working memory.</span></span> <span data-ttu-id="ca4c2-104">以下各段落介绍了与从规则引擎的工作内存中取消不同类型的实体的操作相关联的行为。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-104">The following paragraphs describe the behavior associated with retracting entities of different types from the rule engine's working memory.</span></span>  
  
## <a name="net-objects"></a><span data-ttu-id="ca4c2-105">.NET 对象</span><span class="sxs-lookup"><span data-stu-id="ca4c2-105">.NET Objects</span></span>  
 <span data-ttu-id="ca4c2-106">.NET 对象是否被收回是在策略中使用**收回**函数。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-106">A .NET object is retracted in a policy by using the **Retract** function.</span></span> <span data-ttu-id="ca4c2-107">此函数可用于业务规则编辑器作为**函数**词汇项： 将类 （不的程序集或方法） 拖到**收回**参数。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-107">This function is available in the Business Rule Composer as a **Functions** vocabulary item: drag the class (not the assembly or method) into the **Retract** parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca4c2-108">如果拖动到方法**收回**函数，该引擎尝试收回由方法返回的对象。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-108">If you drag a method into the **Retract** function, the engine attempts to retract the object returned by the method.</span></span>  
  
 <span data-ttu-id="ca4c2-109">取消 .NET 对象将会从规则引擎的工作内存中删除该对象，并且此操作具有以下影响：</span><span class="sxs-lookup"><span data-stu-id="ca4c2-109">Retracting a .NET object removes it from the rule engine's working memory and has the following impact:</span></span>  
  
-   <span data-ttu-id="ca4c2-110">在谓词中使用该对象的规则将会从议程中删除其操作（如果在议程中存在任何操作）。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-110">Rules that use the object in a predicate have their actions removed from the agenda (if any exist on the agenda).</span></span>  
  
-   <span data-ttu-id="ca4c2-111">从议程中删除使用这些对象的操作。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-111">Actions on the agenda that use the objects are removed from the agenda.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca4c2-112">较高安排上其他操作可能已执行之前**收回**调用函数。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-112">Other actions higher up on the agenda may have already executed before the **Retract** function was called.</span></span>  
  
-   <span data-ttu-id="ca4c2-113">引擎不再评估该对象。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-113">The object is no longer evaluated by the engine.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="ca4c2-114">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="ca4c2-114">TypedXmlDocument</span></span>  
 <span data-ttu-id="ca4c2-115">您既可以收回原始**TypedXmlDocument** ，引擎所断言或收回一个子**TypedXmlDocument**从父节点创建的 s **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="ca4c2-115">You can either retract the original **TypedXmlDocument** that was asserted into the engine or retract one of the child **TypedXmlDocument**s created from a node of the parent **XmlDocument**.</span></span>  
  
 <span data-ttu-id="ca4c2-116">使用下面的 XML 作为示例，你可以既收回**TypedXmlDocument**与顺序或一个或两个关联**TypedXmlDocument**与 orderline 关联。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-116">Using the following XML as an example, you can either retract the **TypedXmlDocument** associated with order or one or both of the **TypedXmlDocument**s associated with orderline.</span></span>  
  
```  
<order>  
   <orderline customer="Joe" linenumber="001">  
      <product name="router" quantity="10" cost="550" />  
   </orderline>  
   <orderline customer="Jane" linenumber="002">  
      <product name="switch" quantity="1" cost="300" />  
   </orderline>  
</order>  
```  
  
 <span data-ttu-id="ca4c2-117">若要取消订单对象，应在 XML 架构事实窗格中拖动架构的顶部节点。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-117">To retract the order object, you would drag the top node for the schema in the XML Schemas fact pane.</span></span> <span data-ttu-id="ca4c2-118">此节点以".xsd"结尾，表示文档根节点 （不是文档元素节点）;它具有一个"/"的选择器，指的是初始**TypedXmlDocument**。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-118">This node ends in ".xsd" and represents the document root node (not the document element node); it has a "/" selector that refers to the initial **TypedXmlDocument**.</span></span> <span data-ttu-id="ca4c2-119">当父**TypedXmlDocument**是否被收回，所有**TypedXmlDocument**与关联的实例**TypedXmlDocument** (所有**TypedXmlDocument**通过调用创建的 s**断言**函数根据策略中使用的选择器) 从使用内存中删除。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-119">When the parent **TypedXmlDocument** is retracted, all **TypedXmlDocument** instances associated with the **TypedXmlDocument** (all **TypedXmlDocument**s created by calling the **Assert** function based on selectors used in the policy) are removed from working memory.</span></span>  
  
 <span data-ttu-id="ca4c2-120">收回仅各个子**TypedXmlDocument** (即 orderline)，可以将此节点拖到 XML 架构窗格中从**收回**函数。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-120">To retract only an individual child **TypedXmlDocument** (that is an orderline), you can drag this node from the XML Schemas pane into the **Retract** function.</span></span> <span data-ttu-id="ca4c2-121">务必请注意，所有**TypedXmlDocument**s 了与顶级**TypedXmlDocument**最初声明的而不是与**TypedXmlDocument**上面它出现在 XML 树层次结构。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-121">It is important to note that all **TypedXmlDocument**s are associated with the top-level **TypedXmlDocument** that was originally asserted, and not with the **TypedXmlDocument** that appears above it in the XML tree hierarchy.</span></span> <span data-ttu-id="ca4c2-122">例如，产品是**TypedXmlDocument**下面 orderline 对象中; 因此，它可能与订单关联**TypedXmlDocument**，而不是与 orderline **TypedXmlDocument**。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-122">For example, product is a **TypedXmlDocument** below the orderline object; therefore, it would be associated with the order **TypedXmlDocument**, and not with the orderline **TypedXmlDocument**.</span></span> <span data-ttu-id="ca4c2-123">在大多情况下，此差别并不重要。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-123">In most instances, this distinction is not important.</span></span> <span data-ttu-id="ca4c2-124">但是，如果取消订单对象，则也将取消订单行和产品对象。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-124">However, if you retract the order object, the orderline and product objects are also retracted.</span></span> <span data-ttu-id="ca4c2-125">如果取消订单行对象，则仅取消该对象，而不会取消产品对象。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-125">If you retract the orderline object, only that object is retracted, and not the product object.</span></span>  
  
 <span data-ttu-id="ca4c2-126">引擎仅适用于和跟踪对象实例 (**TypedXmlDocument**s) 它时创建**TypedXmlDocument**最初断言。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-126">The engine only works with and tracks object instances (**TypedXmlDocument**s) that it created when the **TypedXmlDocument** was initially asserted.</span></span> <span data-ttu-id="ca4c2-127">如果你创建的其他节点-例如，通过在策略中选择器选择的节点同级节点-除非这些节点不会评估规则中**TypedXmlDocument**进行创建，这些断言。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-127">If you create additional nodes—for example, sibling nodes to a node that was selected through a selector in the policy—these nodes are not evaluated in rules unless **TypedXmlDocument**s are created and asserted for them.</span></span> <span data-ttu-id="ca4c2-128">新的、 较低级别的这些断言**TypedXmlDocuments**使它们在规则，但顶级评估**TypedXmlDocument**没有了解它们。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-128">Asserting these new, lower-level **TypedXmlDocuments** causes them to be evaluated in rules, but the top-level **TypedXmlDocument** does not have knowledge of them.</span></span> <span data-ttu-id="ca4c2-129">当顶级**TypedXmlDocument**是否被收回，将新的、 独立断言**TypedXmlDocument**s 交换机间链路不自动收回。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-129">When the top-level **TypedXmlDocument** is retracted, the new, independently asserted **TypedXmlDocument**s isl not automatically retracted.</span></span> <span data-ttu-id="ca4c2-130">因此，如果创建新节点，它将通常最简单收回并重新声明完整**XmlDocument**。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-130">As a result, if new nodes are created, it is typically most straightforward to retract and reassert the full **XmlDocument**.</span></span>  
  
 <span data-ttu-id="ca4c2-131">**TypedXmlDocument**类支持大量的有用可作为操作的一部分中自定义.NET 成员调用的方法。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-131">The **TypedXmlDocument** class supports a number of useful methods that can be called within a custom .NET member as part of an action.</span></span> <span data-ttu-id="ca4c2-132">这些包括能够获取**XmlNode**与关联**TypedXmlDocument**或父**TypedXmlDocument**。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-132">These include the ability to get the **XmlNode** associated with the **TypedXmlDocument** or the parent **TypedXmlDocument**.</span></span>  
  
## <a name="typeddatatable"></a><span data-ttu-id="ca4c2-133">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="ca4c2-133">TypedDataTable</span></span>  
 <span data-ttu-id="ca4c2-134">您可以收回任一单个**TypedDataRow**s 或整个**TypedDataTable**。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-134">You can retract either individual **TypedDataRow**s or the entire **TypedDataTable**.</span></span> <span data-ttu-id="ca4c2-135">如果取消表，则将从工作内存中取消所包含的所有行。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-135">If you retract a table, all the containing rows are retracted from working memory.</span></span>  
  
 <span data-ttu-id="ca4c2-136">收回整个**TypedDataTable**你需要使用 helper 函数访问**父**属性**TypedDataRow**，例如：</span><span class="sxs-lookup"><span data-stu-id="ca4c2-136">To retract the entire **TypedDataTable** you need to use a helper function to access the **Parent** property on **TypedDataRow**, for example:</span></span>  
  
```  
Retract(MyHelper.GetTypedDataTable(TypedDataRow))  
```  
  
 <span data-ttu-id="ca4c2-137">在前面的操作，将拖动到表**TypedDataRow**。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-137">In the preceding action, you would drag the table into **TypedDataRow**.</span></span> <span data-ttu-id="ca4c2-138">在**GetTypedDataTable**将返回的值**TypedDataRow.Parent**。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-138">In **GetTypedDataTable** you would return the value of **TypedDataRow.Parent**.</span></span>  
  
 <span data-ttu-id="ca4c2-139">与**TypedXmlDocument**s，如果你断言附加的新**TypedDataRow**s 针对相同**DataTable**后断言**TypedDataTable**，它们被视为单个实体和收回**TypedDataTable**不会导致这些收回额外**TypedDataRow**s。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-139">As with **TypedXmlDocument**s, if you assert additional, new **TypedDataRow**s for the same **DataTable** after asserting the **TypedDataTable**, they are treated as individual entities and retracting the **TypedDataTable** does not result in the retraction of these extra **TypedDataRow**s.</span></span> <span data-ttu-id="ca4c2-140">仅**TypedDataRow**s 中包含**TypedDataTable**时它所断言收回。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-140">Only the **TypedDataRow**s contained in the **TypedDataTable** when it was asserted are retracted.</span></span>  
  
## <a name="dataconnection"></a><span data-ttu-id="ca4c2-141">DataConnection</span><span class="sxs-lookup"><span data-stu-id="ca4c2-141">DataConnection</span></span>  
 <span data-ttu-id="ca4c2-142">当**该组**是否被收回，所有**TypedDataRow**s 从通过由构造的查询数据库中检索**该组**从收回工作内存。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-142">When a **DataConnection** is retracted, all **TypedDataRow**s retrieved from the database through the query constructed by the **DataConnection** are retracted from working memory.</span></span> <span data-ttu-id="ca4c2-143">**该组**本身是否也被收回，也就是说，没有更**TypedDataRow**将通过检索 s**该组**（即，通过使用**数据连接**其他谓词或操作中)。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-143">The **DataConnection** itself is also retracted, meaning that no more **TypedDataRow**s will be retrieved through the **DataConnection** (that is, through use of the **DataConnection** in other predicates or actions).</span></span>  
  
 <span data-ttu-id="ca4c2-144">使用时**该组**，任何收回操作对单个**TypedDataRow**引擎将置于不一致状态。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-144">When using a **DataConnection**, any retract operation on an individual **TypedDataRow** puts the engine into an inconsistent state.</span></span> <span data-ttu-id="ca4c2-145">因此，操作不允许对各个**TypedDataRow**与关联**该组**。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-145">Therefore, operations are not allowed on individual **TypedDataRow**s associated with a **DataConnection**.</span></span> <span data-ttu-id="ca4c2-146">如果拖动表 (使用**该组**参数) 到**收回**函数，你将会收回**该组**。</span><span class="sxs-lookup"><span data-stu-id="ca4c2-146">If you drag the table (using the **DataConnection** parameter) into the **Retract** function, you will be retracting the **DataConnection**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca4c2-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca4c2-147">See Also</span></span>  
 [<span data-ttu-id="ca4c2-148">引擎控制功能</span><span class="sxs-lookup"><span data-stu-id="ca4c2-148">Engine Control Functions</span></span>](../core/engine-control-functions.md)