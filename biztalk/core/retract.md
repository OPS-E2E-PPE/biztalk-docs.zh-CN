---
title: 收回 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Retract function [Business Rules Engine], TypedData table
- Retract function [Business Rules Engine], TypedXMLDocument
- Retract function [Business Rules Engine]
- Retract function [Business Rules Engine], DataConnection
- Retract function [Business Rules Engine], .NET objects
- .NET objects
ms.assetid: 24b6b894-6810-4497-a122-8c91f0b2e816
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94967d573bf4293c0a2dcf6bf6c718f79d19736f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399086"
---
# <a name="retract"></a><span data-ttu-id="bfc02-102">收回</span><span class="sxs-lookup"><span data-stu-id="bfc02-102">Retract</span></span>
<span data-ttu-id="bfc02-103">可以使用**Retract**函数以从业务规则引擎工作内存中删除对象。</span><span class="sxs-lookup"><span data-stu-id="bfc02-103">You can use the **Retract** function to remove objects from the Business Rule Engine's working memory.</span></span> <span data-ttu-id="bfc02-104">以下各段介绍了与收回从规则引擎工作内存的不同类型的实体相关联的行为。</span><span class="sxs-lookup"><span data-stu-id="bfc02-104">The following paragraphs describe the behavior associated with retracting entities of different types from the rule engine's working memory.</span></span>  
  
## <a name="net-objects"></a><span data-ttu-id="bfc02-105">.NET 对象</span><span class="sxs-lookup"><span data-stu-id="bfc02-105">.NET Objects</span></span>  
 <span data-ttu-id="bfc02-106">.NET 对象在策略中可以使用收回**Retract**函数。</span><span class="sxs-lookup"><span data-stu-id="bfc02-106">A .NET object is retracted in a policy by using the **Retract** function.</span></span> <span data-ttu-id="bfc02-107">此函数是可在业务规则编辑器中作为**函数**词汇项： 将类 （不程序集或方法） 拖至**Retract**参数。</span><span class="sxs-lookup"><span data-stu-id="bfc02-107">This function is available in the Business Rule Composer as a **Functions** vocabulary item: drag the class (not the assembly or method) into the **Retract** parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bfc02-108">如果将方法转换成**Retract**函数，引擎将尝试取消由方法返回的对象。</span><span class="sxs-lookup"><span data-stu-id="bfc02-108">If you drag a method into the **Retract** function, the engine attempts to retract the object returned by the method.</span></span>  
  
 <span data-ttu-id="bfc02-109">取消.NET 对象从规则引擎工作内存中删除它，并会产生以下影响：</span><span class="sxs-lookup"><span data-stu-id="bfc02-109">Retracting a .NET object removes it from the rule engine's working memory and has the following impact:</span></span>  
  
-   <span data-ttu-id="bfc02-110">在谓词中使用的对象的规则将其从议程中删除 （如果存在在议程上） 的操作。</span><span class="sxs-lookup"><span data-stu-id="bfc02-110">Rules that use the object in a predicate have their actions removed from the agenda (if any exist on the agenda).</span></span>  
  
-   <span data-ttu-id="bfc02-111">使用对象在议程的操作是从议程中删除。</span><span class="sxs-lookup"><span data-stu-id="bfc02-111">Actions on the agenda that use the objects are removed from the agenda.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bfc02-112">议程别的其他操作可能之前已执行**Retract**调用函数。</span><span class="sxs-lookup"><span data-stu-id="bfc02-112">Other actions higher up on the agenda may have already executed before the **Retract** function was called.</span></span>  
  
-   <span data-ttu-id="bfc02-113">引擎不再评估该对象。</span><span class="sxs-lookup"><span data-stu-id="bfc02-113">The object is no longer evaluated by the engine.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="bfc02-114">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="bfc02-114">TypedXmlDocument</span></span>  
 <span data-ttu-id="bfc02-115">也可以取消原始**TypedXmlDocument** ，添加到引擎或收回的一个子**TypedXmlDocument**从父节点的**XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="bfc02-115">You can either retract the original **TypedXmlDocument** that was asserted into the engine or retract one of the child **TypedXmlDocument**s created from a node of the parent **XmlDocument**.</span></span>  
  
 <span data-ttu-id="bfc02-116">使用以下 XML 作为一个示例，您可以或者收回**TypedXmlDocument**与顺序或一个或两个关联**TypedXmlDocument**与订单行关联。</span><span class="sxs-lookup"><span data-stu-id="bfc02-116">Using the following XML as an example, you can either retract the **TypedXmlDocument** associated with order or one or both of the **TypedXmlDocument**s associated with orderline.</span></span>  
  
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
  
 <span data-ttu-id="bfc02-117">若要取消订单对象，将 XML 架构事实窗格中拖动架构的顶级节点。</span><span class="sxs-lookup"><span data-stu-id="bfc02-117">To retract the order object, you would drag the top node for the schema in the XML Schemas fact pane.</span></span> <span data-ttu-id="bfc02-118">此节点以".xsd"结尾，表示文档根节点 （不是文档元素节点）;它具有一个"/"的选择器，引用初始**TypedXmlDocument**。</span><span class="sxs-lookup"><span data-stu-id="bfc02-118">This node ends in ".xsd" and represents the document root node (not the document element node); it has a "/" selector that refers to the initial **TypedXmlDocument**.</span></span> <span data-ttu-id="bfc02-119">当父**TypedXmlDocument**将被取消，所有**TypedXmlDocument**与关联的实例**TypedXmlDocument** (所有**TypedXmlDocument**通过调用创建的 s **Assert**函数根据策略中使用的选择器) 从工作内存中删除。</span><span class="sxs-lookup"><span data-stu-id="bfc02-119">When the parent **TypedXmlDocument** is retracted, all **TypedXmlDocument** instances associated with the **TypedXmlDocument** (all **TypedXmlDocument**s created by calling the **Assert** function based on selectors used in the policy) are removed from working memory.</span></span>  
  
 <span data-ttu-id="bfc02-120">若要取消只有单个子**TypedXmlDocument** （即订单行），可以拖动到 XML 架构窗格上的此节点**Retract**函数。</span><span class="sxs-lookup"><span data-stu-id="bfc02-120">To retract only an individual child **TypedXmlDocument** (that is an orderline), you can drag this node from the XML Schemas pane into the **Retract** function.</span></span> <span data-ttu-id="bfc02-121">务必要注意的所有**TypedXmlDocument**s 都与顶级**TypedXmlDocument**原始添加的而不是与**TypedXmlDocument**，其上方会出现在 XML 树层次结构中。</span><span class="sxs-lookup"><span data-stu-id="bfc02-121">It is important to note that all **TypedXmlDocument**s are associated with the top-level **TypedXmlDocument** that was originally asserted, and not with the **TypedXmlDocument** that appears above it in the XML tree hierarchy.</span></span> <span data-ttu-id="bfc02-122">例如，产品是**TypedXmlDocument**如下订单行对象; 因此，它会与订单关联**TypedXmlDocument**，而不是与订单行**TypedXmlDocument**。</span><span class="sxs-lookup"><span data-stu-id="bfc02-122">For example, product is a **TypedXmlDocument** below the orderline object; therefore, it would be associated with the order **TypedXmlDocument**, and not with the orderline **TypedXmlDocument**.</span></span> <span data-ttu-id="bfc02-123">在大多数情况下，这一区别并不重要。</span><span class="sxs-lookup"><span data-stu-id="bfc02-123">In most instances, this distinction is not important.</span></span> <span data-ttu-id="bfc02-124">但是，如果取消订单对象，订单行和产品对象也将取消。</span><span class="sxs-lookup"><span data-stu-id="bfc02-124">However, if you retract the order object, the orderline and product objects are also retracted.</span></span> <span data-ttu-id="bfc02-125">如果取消订单行对象，该对象只将被取消，而不是产品对象。</span><span class="sxs-lookup"><span data-stu-id="bfc02-125">If you retract the orderline object, only that object is retracted, and not the product object.</span></span>  
  
 <span data-ttu-id="bfc02-126">引擎仅处理和跟踪对象实例 (**TypedXmlDocument**s) 它时创建**TypedXmlDocument**最初添加。</span><span class="sxs-lookup"><span data-stu-id="bfc02-126">The engine only works with and tracks object instances (**TypedXmlDocument**s) that it created when the **TypedXmlDocument** was initially asserted.</span></span> <span data-ttu-id="bfc02-127">如果创建其他节点 — 例如，通过在策略中的选择器选择的节点同级节点，这些节点不计算在规则中，除非**TypedXmlDocument**进行创建，这些断言。</span><span class="sxs-lookup"><span data-stu-id="bfc02-127">If you create additional nodes—for example, sibling nodes to a node that was selected through a selector in the policy—these nodes are not evaluated in rules unless **TypedXmlDocument**s are created and asserted for them.</span></span> <span data-ttu-id="bfc02-128">添加这些新的、 较低级别**TypedXmlDocuments**会导致其进行评估规则，但顶级**TypedXmlDocument**不具备这些知识。</span><span class="sxs-lookup"><span data-stu-id="bfc02-128">Asserting these new, lower-level **TypedXmlDocuments** causes them to be evaluated in rules, but the top-level **TypedXmlDocument** does not have knowledge of them.</span></span> <span data-ttu-id="bfc02-129">当顶级**TypedXmlDocument**将被取消，将新的、 独立断言**TypedXmlDocument**不会自动取消单独。</span><span class="sxs-lookup"><span data-stu-id="bfc02-129">When the top-level **TypedXmlDocument** is retracted, the new, independently asserted **TypedXmlDocument**s isl not automatically retracted.</span></span> <span data-ttu-id="bfc02-130">因此，如果创建新节点，则通常取消并重新添加完整的最简单**XmlDocument**。</span><span class="sxs-lookup"><span data-stu-id="bfc02-130">As a result, if new nodes are created, it is typically most straightforward to retract and reassert the full **XmlDocument**.</span></span>  
  
 <span data-ttu-id="bfc02-131">**TypedXmlDocument**类支持多种可作为操作的一部分中的自定义.NET 成员调用的有效方法。</span><span class="sxs-lookup"><span data-stu-id="bfc02-131">The **TypedXmlDocument** class supports a number of useful methods that can be called within a custom .NET member as part of an action.</span></span> <span data-ttu-id="bfc02-132">其中包括能够获取**XmlNode**与关联**TypedXmlDocument**或父**TypedXmlDocument**。</span><span class="sxs-lookup"><span data-stu-id="bfc02-132">These include the ability to get the **XmlNode** associated with the **TypedXmlDocument** or the parent **TypedXmlDocument**.</span></span>  
  
## <a name="typeddatatable"></a><span data-ttu-id="bfc02-133">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="bfc02-133">TypedDataTable</span></span>  
 <span data-ttu-id="bfc02-134">可以取消两个**TypedDataRow**s 或整个**TypedDataTable**。</span><span class="sxs-lookup"><span data-stu-id="bfc02-134">You can retract either individual **TypedDataRow**s or the entire **TypedDataTable**.</span></span> <span data-ttu-id="bfc02-135">如果取消表，从工作内存中取消包含的所有行。</span><span class="sxs-lookup"><span data-stu-id="bfc02-135">If you retract a table, all the containing rows are retracted from working memory.</span></span>  
  
 <span data-ttu-id="bfc02-136">若要取消整个**TypedDataTable**需要使用一个帮助程序函数来访问**父**属性上的**TypedDataRow**，例如：</span><span class="sxs-lookup"><span data-stu-id="bfc02-136">To retract the entire **TypedDataTable** you need to use a helper function to access the **Parent** property on **TypedDataRow**, for example:</span></span>  
  
```  
Retract(MyHelper.GetTypedDataTable(TypedDataRow))  
```  
  
 <span data-ttu-id="bfc02-137">在前面的操作中，将拖动到表**TypedDataRow**。</span><span class="sxs-lookup"><span data-stu-id="bfc02-137">In the preceding action, you would drag the table into **TypedDataRow**.</span></span> <span data-ttu-id="bfc02-138">在中**GetTypedDataTable**将返回的值**TypedDataRow.Parent**。</span><span class="sxs-lookup"><span data-stu-id="bfc02-138">In **GetTypedDataTable** you would return the value of **TypedDataRow.Parent**.</span></span>  
  
 <span data-ttu-id="bfc02-139">如同**TypedXmlDocument**s，如果你断言附加的新**TypedDataRow**的相同**DataTable**后断言**TypedDataTable**，它们被视为单个实体和收回**TypedDataTable**不会导致这些收回额外**TypedDataRow**s。</span><span class="sxs-lookup"><span data-stu-id="bfc02-139">As with **TypedXmlDocument**s, if you assert additional, new **TypedDataRow**s for the same **DataTable** after asserting the **TypedDataTable**, they are treated as individual entities and retracting the **TypedDataTable** does not result in the retraction of these extra **TypedDataRow**s.</span></span> <span data-ttu-id="bfc02-140">仅**TypedDataRow**中包含**TypedDataTable**添加时取消。</span><span class="sxs-lookup"><span data-stu-id="bfc02-140">Only the **TypedDataRow**s contained in the **TypedDataTable** when it was asserted are retracted.</span></span>  
  
## <a name="dataconnection"></a><span data-ttu-id="bfc02-141">DataConnection</span><span class="sxs-lookup"><span data-stu-id="bfc02-141">DataConnection</span></span>  
 <span data-ttu-id="bfc02-142">当**DataConnection**将被取消，所有**TypedDataRow**s 从通过构造的查询数据库中检索**DataConnection**从取消工作内存中。</span><span class="sxs-lookup"><span data-stu-id="bfc02-142">When a **DataConnection** is retracted, all **TypedDataRow**s retrieved from the database through the query constructed by the **DataConnection** are retracted from working memory.</span></span> <span data-ttu-id="bfc02-143">**DataConnection**本身也将被取消，也就是说，没有更多**TypedDataRow**s 将通过检索**DataConnection** （即，通过使用**DataConnection**中其他谓词或操作)。</span><span class="sxs-lookup"><span data-stu-id="bfc02-143">The **DataConnection** itself is also retracted, meaning that no more **TypedDataRow**s will be retrieved through the **DataConnection** (that is, through use of the **DataConnection** in other predicates or actions).</span></span>  
  
 <span data-ttu-id="bfc02-144">使用时**DataConnection**，对单个操作的任何取消**TypedDataRow**将引擎放入不一致的状态。</span><span class="sxs-lookup"><span data-stu-id="bfc02-144">When using a **DataConnection**, any retract operation on an individual **TypedDataRow** puts the engine into an inconsistent state.</span></span> <span data-ttu-id="bfc02-145">因此，操作不允许对个人**TypedDataRow**与关联**DataConnection**。</span><span class="sxs-lookup"><span data-stu-id="bfc02-145">Therefore, operations are not allowed on individual **TypedDataRow**s associated with a **DataConnection**.</span></span> <span data-ttu-id="bfc02-146">如果将表 (使用**DataConnection**参数) 到**Retract**函数，则将会取消**DataConnection**。</span><span class="sxs-lookup"><span data-stu-id="bfc02-146">If you drag the table (using the **DataConnection** parameter) into the **Retract** function, you will be retracting the **DataConnection**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfc02-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="bfc02-147">See Also</span></span>  
 [<span data-ttu-id="bfc02-148">引擎控制函数</span><span class="sxs-lookup"><span data-stu-id="bfc02-148">Engine Control Functions</span></span>](../core/engine-control-functions.md)