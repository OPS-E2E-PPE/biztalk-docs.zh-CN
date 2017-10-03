---
title: "类型化事实 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RuleEngine library
- Business Rule Composer, typed facts
- ITypedFact interface
- DataConnection class
- facts, typed
- TypedDataTable class
- TypedDataRow class
- TypedXmlDocument class
ms.assetid: 8207bfd5-ebd2-45ac-8992-795acdf3ba4c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6041a64fcc4b3496c319a25a2ce758ed7f52a71
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="typed-facts"></a><span data-ttu-id="64b0d-102">类型化的事实</span><span class="sxs-lookup"><span data-stu-id="64b0d-102">Typed Facts</span></span>
<span data-ttu-id="64b0d-103">*类型化事实*是实现的类**ITypedFact**接口： **TypedXmlDocument**，**该组**， **TypedDataTable**，和**TypedDataRow**。</span><span class="sxs-lookup"><span data-stu-id="64b0d-103">*Typed facts* are classes that implement the **ITypedFact** interface: **TypedXmlDocument**, **DataConnection**, **TypedDataTable**, and **TypedDataRow**.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="64b0d-104">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="64b0d-104">TypedXmlDocument</span></span>  
 <span data-ttu-id="64b0d-105">**TypedXmlDocument**类表示业务规则框架中的 XML 文档类型。</span><span class="sxs-lookup"><span data-stu-id="64b0d-105">The **TypedXmlDocument** class represents the XML document type in the Business Rules Framework.</span></span> <span data-ttu-id="64b0d-106">在规则中使用 XML 文档的节点作为参数时，将创建两个 XPath 表达式：选择器绑定和字段绑定。</span><span class="sxs-lookup"><span data-stu-id="64b0d-106">When you use a node of an XML document as an argument in a rule, two XPath expressions are created: the Selector and Field bindings.</span></span>  
  
 <span data-ttu-id="64b0d-107">如果该节点不具有任何子节点，*选择器绑定*（也称为 XmlDocument 绑定） 创建到节点的父节点和*字段绑定*创建 （也称为 XmlDocumentMember 绑定）节点自身。</span><span class="sxs-lookup"><span data-stu-id="64b0d-107">If the node has no child nodes, a *Selector binding* (also known as an XmlDocument binding) is created to the node's parent node and a *Field binding* (also known as an XmlDocumentMember binding) is created to the node itself.</span></span> <span data-ttu-id="64b0d-108">此字段绑定是相对于选择器绑定的。</span><span class="sxs-lookup"><span data-stu-id="64b0d-108">This Field binding is relative to the Selector binding.</span></span> <span data-ttu-id="64b0d-109">如果该节点具有子节点，则将为该节点创建选择器绑定，而不创建任何字段绑定。</span><span class="sxs-lookup"><span data-stu-id="64b0d-109">If the node has child nodes, a Selector binding is created to the node and no Field binding is created.</span></span>  
  
 <span data-ttu-id="64b0d-110">假设您具有以下架构：</span><span class="sxs-lookup"><span data-stu-id="64b0d-110">Suppose that you have the following schema.</span></span>  
  
 <span data-ttu-id="64b0d-111">![事实数据资源管理器中显示的示例架构](../core/media/xmldocumentbrowser.gif "xmldocumentbrowser")</span><span class="sxs-lookup"><span data-stu-id="64b0d-111">![Sample schema displayed in Facts Explorer](../core/media/xmldocumentbrowser.gif "xmldocumentbrowser")</span></span>  
<span data-ttu-id="64b0d-112">Case.xsd</span><span class="sxs-lookup"><span data-stu-id="64b0d-112">Case.xsd</span></span>  
  
 <span data-ttu-id="64b0d-113">如果选择“Income”节点，则只创建选择器绑定，因为该节点具有子节点。</span><span class="sxs-lookup"><span data-stu-id="64b0d-113">If the Income node is selected, only a Selector binding is created, because the node has child nodes.</span></span> <span data-ttu-id="64b0d-114">中的默认 XPath 表达式**XPath 选择器**的属性窗格中的属性包含：</span><span class="sxs-lookup"><span data-stu-id="64b0d-114">The default XPath expression in the **XPath Selector** property of the Property pane contains:</span></span>  
  
```  
/*[local-name()='Root' and namespace-uri()='http://LoansProcessor.Case']/*[local-name()='Income' and namespace-uri()='']  
```  
  
 <span data-ttu-id="64b0d-115">但是，如果选择“Name”节点，则将创建选择器绑定和字段绑定。</span><span class="sxs-lookup"><span data-stu-id="64b0d-115">However, if the Name node is selected, both a Selector binding and a Field binding are created.</span></span> <span data-ttu-id="64b0d-116">绑定信息与下面所列相似：</span><span class="sxs-lookup"><span data-stu-id="64b0d-116">The binding information looks like.</span></span>  
  
|<span data-ttu-id="64b0d-117">属性</span><span class="sxs-lookup"><span data-stu-id="64b0d-117">Property</span></span>|<span data-ttu-id="64b0d-118">值</span><span class="sxs-lookup"><span data-stu-id="64b0d-118">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="64b0d-119">**XPath 的字段**</span><span class="sxs-lookup"><span data-stu-id="64b0d-119">**XPath Field**</span></span>|<span data-ttu-id="64b0d-120">*[local-name()='Name' and namespace-uri()='']</span><span class="sxs-lookup"><span data-stu-id="64b0d-120">*[local-name()='Name' and namespace-uri()='']</span></span>|  
|<span data-ttu-id="64b0d-121">**XPath 选择器**</span><span class="sxs-lookup"><span data-stu-id="64b0d-121">**XPath Selector**</span></span>|<span data-ttu-id="64b0d-122">/*[local-name()='Root' and namespace-uri()='http://LoansProcessor.Case']</span><span class="sxs-lookup"><span data-stu-id="64b0d-122">/*[local-name()='Root' and namespace-uri()='http://LoansProcessor.Case']</span></span>|  
  
 <span data-ttu-id="64b0d-123">在将节点拖动到规则参数中，将新的绑定信息放入策略之前，您可以更改 XML 节点的默认 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="64b0d-123">You can change the default XPath expressions for the XML nodes before you drag the node into a rule argument, and the new binding information is placed in the policy.</span></span> <span data-ttu-id="64b0d-124">但是请注意，对 XPath 表达式所做的任何编辑内容都必须在重新加载架构时重新输入到业务规则编辑器中。</span><span class="sxs-lookup"><span data-stu-id="64b0d-124">Note, however, that any edits that are made to the XPath expressions must be re-entered in the Business Rule Composer when the schema is reloaded.</span></span>  
  
 <span data-ttu-id="64b0d-125">如果为 XML 节点创建了词汇定义，则根据之前描述的规则，这些绑定的 XPath 表达式具有相似的默认值，但可在词汇定义向导中进行编辑。</span><span class="sxs-lookup"><span data-stu-id="64b0d-125">When vocabulary definitions are created for XML nodes, the XPath expressions for the bindings have similar defaults based on the rules described earlier, but can be edited in the Vocabulary Definition Wizard.</span></span> <span data-ttu-id="64b0d-126">对表达式所做的更改放在词汇定义中，并反映在使用这些定义生成的所有规则参数中。</span><span class="sxs-lookup"><span data-stu-id="64b0d-126">Changes to the expressions are placed in the vocabulary definition and are reflected in any rule arguments built from the definitions.</span></span>  
  
## <a name="dataconnection"></a><span data-ttu-id="64b0d-127">DataConnection</span><span class="sxs-lookup"><span data-stu-id="64b0d-127">DataConnection</span></span>  
 <span data-ttu-id="64b0d-128">**数据连接**中提供一个.NET 类**RuleEngine**库。</span><span class="sxs-lookup"><span data-stu-id="64b0d-128">**DataConnection** is a .NET class provided in the **RuleEngine** library.</span></span> <span data-ttu-id="64b0d-129">它包含一种.NET **SqlConnection**实例和一个**数据集**名称。</span><span class="sxs-lookup"><span data-stu-id="64b0d-129">It contains a .NET **SqlConnection** instance and a **DataSet** name.</span></span> <span data-ttu-id="64b0d-130">**数据集**名称可用于创建的唯一标识符**SqlConnection**并可用于定义生成的类型。</span><span class="sxs-lookup"><span data-stu-id="64b0d-130">The **DataSet** name enables you to create a unique identifier for the **SqlConnection** and is used in defining the resulting type.</span></span>  
  
 <span data-ttu-id="64b0d-131">**该组**类提供了一种性能优化到业务规则引擎。</span><span class="sxs-lookup"><span data-stu-id="64b0d-131">The **DataConnection** class provides a performance optimization to the Business Rule engine.</span></span> <span data-ttu-id="64b0d-132">而不是断言到引擎非常大的数据库表 (**TypedDataTable**类) 可以包含许多数据库行 (**TypedDataRow**类) 不相关的策略，你可以断言轻量**该组**。</span><span class="sxs-lookup"><span data-stu-id="64b0d-132">Rather than asserting into the engine very large database tables (**TypedDataTable** class) that may contain many database rows (**TypedDataRow** class) that are not relevant to the policy, you can assert a lightweight **DataConnection**.</span></span> <span data-ttu-id="64b0d-133">当引擎评估策略时，它动态生成基于规则谓词/操作和查询的 SELECT 查询**该组**在执行。</span><span class="sxs-lookup"><span data-stu-id="64b0d-133">When the engine evaluates a policy, it dynamically builds a SELECT query based on the rule predicates/actions and queries the **DataConnection** at execution.</span></span> <span data-ttu-id="64b0d-134">例如，假设您具有以下规则：</span><span class="sxs-lookup"><span data-stu-id="64b0d-134">For example, suppose you have the following rule:</span></span>  
  
```  
IF NorthWind.Products.UnitPrice >= 0   
THEN <do something>  
```  
  
 <span data-ttu-id="64b0d-135">以下 SQL 查询生成于该规则：</span><span class="sxs-lookup"><span data-stu-id="64b0d-135">The following SQL query is generated by from the rule:</span></span>  
  
```  
Select * From [Product] Where [UnitPrice] >= 0  
```  
  
 <span data-ttu-id="64b0d-136">查询的结果被作为数据行添加回引擎中。</span><span class="sxs-lookup"><span data-stu-id="64b0d-136">The results of the query are asserted back into the engine as data rows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64b0d-137">使用**OleDbConnection**中**该组**当前不支持。</span><span class="sxs-lookup"><span data-stu-id="64b0d-137">The use of an **OleDbConnection** in a **DataConnection** is not currently supported.</span></span>  
  
 <span data-ttu-id="64b0d-138">当你选择要在规则条件或操作中使用的数据库表/列时，你可以选择将绑定到使用对象**该组**或**TypedDataTable**通过选择"数据连接"或"数据库表/行"从**数据库绑定类型**性的属性窗口中的下拉列表框**数据库**事实浏览器选项卡。</span><span class="sxs-lookup"><span data-stu-id="64b0d-138">When you select a database table/column to use in a rule condition or action, you can choose to bind to the object using either **DataConnection** or **TypedDataTable** by selecting "Data connection" or "Database table/row" from the **Database binding type**drop-down box in the Property Window for the **Databases** tab of Fact Explorer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64b0d-139">默认情况下，将使用 DataConnection 绑定。</span><span class="sxs-lookup"><span data-stu-id="64b0d-139">The DataConnection binding is used by default.</span></span>  
  
## <a name="typeddatatable"></a><span data-ttu-id="64b0d-140">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="64b0d-140">TypedDataTable</span></span>  
 <span data-ttu-id="64b0d-141">你可以断言 ADO.NET **DataTable**对象插入引擎，但它将被视为任何其他.NET 对象。</span><span class="sxs-lookup"><span data-stu-id="64b0d-141">You can assert an ADO.NET **DataTable** object into the engine, but it will be treated like any other .NET object.</span></span> <span data-ttu-id="64b0d-142">在大多数情况下你将改为想要断言的规则引擎类**TypedDataTable**。</span><span class="sxs-lookup"><span data-stu-id="64b0d-142">In most cases you will instead want to assert the rule engine class **TypedDataTable**.</span></span>  
  
 <span data-ttu-id="64b0d-143">**TypedDataTable**是一个包装类，包含 ADO.NET **DataTable**。</span><span class="sxs-lookup"><span data-stu-id="64b0d-143">**TypedDataTable** is a wrapper class that contains an ADO.NET **DataTable**.</span></span> <span data-ttu-id="64b0d-144">该构造函数只需使用**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="64b0d-144">The constructor simply takes a **DataTable**.</span></span> <span data-ttu-id="64b0d-145">任何时候，只要一个表或表的列用作规则参数，针对单个计算该表达式**TypedDataRow**包装器，而不是针对**TypedDataTable**。</span><span class="sxs-lookup"><span data-stu-id="64b0d-145">Any time a table or table column is used as a rule argument, the expression is evaluated against the individual **TypedDataRow** wrappers, and not against the **TypedDataTable**.</span></span>  
  
## <a name="typeddatarow"></a><span data-ttu-id="64b0d-146">TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="64b0d-146">TypedDataRow</span></span>  
 <span data-ttu-id="64b0d-147">这是 ADO 的类型化的事实包装**DataRow**对象。</span><span class="sxs-lookup"><span data-stu-id="64b0d-147">This is a typed fact wrapper for an ADO **DataRow** object.</span></span> <span data-ttu-id="64b0d-148">将表或列拖动到业务规则编辑器中的规则参数会导致规则生成针对返回**TypedDataRow**包装器。</span><span class="sxs-lookup"><span data-stu-id="64b0d-148">Dragging a table or column to a rule argument in the Business Rule Composer results in rules built against the returned **TypedDataRow** wrappers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64b0d-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64b0d-149">See Also</span></span>  
 [<span data-ttu-id="64b0d-150">事实</span><span class="sxs-lookup"><span data-stu-id="64b0d-150">Facts</span></span>](../core/facts.md)