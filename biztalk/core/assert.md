---
title: 断言 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Assert function [Business Rules Engine], .NET objects
- Assert function [Business Rules Engine], TypedXMLDocument
- Assert function [Business Rules Engine]
- Assert function [Business Rules Engine], examples
- Assert function [Business Rules Engine], TypedData table
- Assert function [Business Rules Engine], DataConnection
- .NET objects
ms.assetid: e9989214-3c10-4691-9c38-f6fe64e511ed
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2de66aab5cde0a9515f41713d3390632180fbff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234045"
---
# <a name="assert"></a><span data-ttu-id="c2fd9-102">ActualRebinds</span><span class="sxs-lookup"><span data-stu-id="c2fd9-102">Assert</span></span>
<span data-ttu-id="c2fd9-103">*断言*是添加到业务规则引擎的工作内存的对象实例的过程。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-103">*Assertion* is the process of adding object instances into the Business Rule engine's working memory.</span></span> <span data-ttu-id="c2fd9-104">引擎根据针对实例类型编写的条件和操作，使用匹配-冲突解决-操作阶段来处理每个实例。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-104">The engine processes each instance according to the conditions and actions that are written against the type of the instance, using the match-conflict resolution-action phases.</span></span>  
  
 <span data-ttu-id="c2fd9-105">以下主题介绍使用而导致的行为**断言**不同的事实类型的函数。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-105">The following topics describe behaviors that result from using the **Assert** function for different fact types.</span></span>  
  
## <a name="net-objects"></a><span data-ttu-id="c2fd9-106">.NET 对象</span><span class="sxs-lookup"><span data-stu-id="c2fd9-106">.NET Objects</span></span>  
 <span data-ttu-id="c2fd9-107">每个对象作为单独的实例添加到工作内存中。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-107">Each object is asserted into the working memory as a separate instance.</span></span> <span data-ttu-id="c2fd9-108">这意味着实例由每个引用对象类型的谓词进行分析（例如，IF Object.Property = 1）。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-108">This means that the instance is analyzed by each predicate that references the object's type (for example, IF Object.Property = 1).</span></span> <span data-ttu-id="c2fd9-109">它还可用于引用类型的规则操作（取决于规则条件的结果）。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-109">It is also made available to rule actions that reference the type, dependent on the results of the rule conditions.</span></span>  
  
 <span data-ttu-id="c2fd9-110">请参考如下示例。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-110">Consider the following example.</span></span>  
  
 <span data-ttu-id="c2fd9-111">**规则 1**</span><span class="sxs-lookup"><span data-stu-id="c2fd9-111">**Rule 1**</span></span>  
  
```  
IF A.Value = 1  
THEN A.Status = "good"  
```  
  
 <span data-ttu-id="c2fd9-112">**规则 2**</span><span class="sxs-lookup"><span data-stu-id="c2fd9-112">**Rule 2**</span></span>  
  
```  
IF B.Value = 1  
THEN A.Status = "good"  
```  
  
 <span data-ttu-id="c2fd9-113">仅这些具有的实例的值为 1 将具有在规则 1 中，其**状态**更新的属性。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-113">In Rule 1, only those instances of A that have a Value of 1 will have their **Status** property updated.</span></span> <span data-ttu-id="c2fd9-114">在规则 2，但是，如果条件计算结果为**true**，将的所有实例都具有更新其状态。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-114">In Rule 2, however, if the condition evaluates to **true**, all instances of A will have their status updated.</span></span> <span data-ttu-id="c2fd9-115">事实上，如果有 B 的多个实例，一个实例将更新条件计算结果为每次**true** B 实例。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-115">In fact, if there are multiple instances of B, the A instances will be updated each time the condition evaluates to **true** for a B instance.</span></span>  
  
 <span data-ttu-id="c2fd9-116">若要断言中规则中的.NET 对象，你可以添加内置**断言**充当规则操作。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-116">To assert a .NET object from within a rule, you can add the built-in **Assert** function as a rule action.</span></span> <span data-ttu-id="c2fd9-117">请注意，为规则引擎**CreateObject**函数，但它不会显示为单独的函数中业务规则编辑器。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-117">Note that the rule engine has a **CreateObject** function, but it is not displayed as a separate function in the Business Rule Composer.</span></span> <span data-ttu-id="c2fd9-118">通过将要创建的对象的构造函数方法从事实浏览器的 .NET 类视图拖动到操作窗格，可以生成对该函数的调用。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-118">Its invocation is built by dragging the constructor method of the object you wish to create from the .NET Class view of the Facts Explorer to the action pane.</span></span> <span data-ttu-id="c2fd9-119">业务规则编辑器会将转换到的构造函数方法**CreateObject**调用中的规则定义的。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-119">The Business Rule Composer then translates the constructor method into a **CreateObject** call in the rule definition.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="c2fd9-120">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="c2fd9-120">TypedXmlDocument</span></span>  
 <span data-ttu-id="c2fd9-121">当**TypedXmlDocument**被声明，业务规则引擎创建子**TypedXmlDocument**实例基于规则中定义的选择器。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-121">When a **TypedXmlDocument** is asserted, the Business Rule Engine creates child **TypedXmlDocument** instances based on the selectors defined in the rule.</span></span>  
  
 <span data-ttu-id="c2fd9-122">选择器和字段都是 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-122">Selectors and fields are both XPath expressions.</span></span> <span data-ttu-id="c2fd9-123">您可以将选择器视为隔离 XML 文档的节点的方法，将字段视为标识选择器中的特定项的方法。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-123">You can think of selectors as a way to isolate nodes of an XML document, and fields as identifying specific items within the selector.</span></span> <span data-ttu-id="c2fd9-124">一个选择器中的所有字段按引擎分组为一个对象。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-124">All the fields inside one selector are grouped together as an object by the engine.</span></span> <span data-ttu-id="c2fd9-125">当选择一个节点下的**XML 架构**选项卡上的事实数据资源管理器，业务规则编辑器自动填写**XPath 选择器**属性的所有节点，和**XPath 字段**的任何不包含子节点的节点的属性。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-125">When you select a node under the **XML Schemas** tab in the Facts Explorer, the Business Rule Composer automatically fills in the **XPath Selector** property for all nodes, and the **XPath Field** property for any node that does not contain child nodes.</span></span> <span data-ttu-id="c2fd9-126">或者，也可以输入自己的 XPath 表达式**XPath 选择器**和**XPath 字段**如有必要。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-126">Alternatively, you can enter your own XPath expressions for **XPath Selector** and **XPath Field** if necessary.</span></span>  
  
 <span data-ttu-id="c2fd9-127">如果选择器与 XML 文档的多个部分相匹配，则将向规则引擎工作内存中添加或从中取消多个此类型的对象。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-127">If the selector matches multiple portions of the XML document, multiple objects of this type are asserted into or retracted from the rule engine working memory.</span></span> <span data-ttu-id="c2fd9-128">假定存在以下 XML：</span><span class="sxs-lookup"><span data-stu-id="c2fd9-128">Assume you have the following XML.</span></span>  
  
```  
<root>  
   <order customer="Joe">  
      <item name="router" quantity="10" cost="550" />  
      <item name="switch" quantity="3" cost="300" />  
   </order>  
   <order customer="Jane">  
      <item name="switch" quantity="1" cost="300" />  
      <item name="cable" quantity="23" cost="9.99" />  
   </order>  
</root>  
```  
  
 <span data-ttu-id="c2fd9-129">如果使用选择器 /root/order（或 //order），则将向工作内存添加两个对象。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-129">If you use the selector /root/order (or //order), two objects are added to the working memory.</span></span>  
  
 <span data-ttu-id="c2fd9-130">1\)</span><span class="sxs-lookup"><span data-stu-id="c2fd9-130">1\)</span></span>  
  
```  
<order customer="Joe">  
   <item name="router" quantity="10" cost="550" />  
   <item name="switch" quantity="3" cost="300" />  
</order>  
```  
  
 <span data-ttu-id="c2fd9-131">2\)</span><span class="sxs-lookup"><span data-stu-id="c2fd9-131">2\)</span></span>  
  
```  
<order customer="Jane">  
   <item name="switch" quantity="1" cost="300" />  
   <item name="cable" quantity="23" cost="9.99" />  
</order>  
```  
  
 <span data-ttu-id="c2fd9-132">在每个选择器中，各个字段通过 XPaths 进行引用。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-132">Within each selector, the individual fields are referred to by XPaths.</span></span>  
  
 <span data-ttu-id="c2fd9-133">如果您使用选择器 /root/order/item（或 //order/item 或 //item），则将向规则引擎工作内存添加四个对象，Joe 两个项目，Jane 两个项目。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-133">If you use the selector /root/order/item (or (//order/item or //item), four objects  are added to the rule engine working memory, the two items for Joe and the two items for Jane.</span></span>  
  
```  
<root>  
   <order customer="Joe">  
  
   </order>  
   <order customer="Jane">  
  
   </order>  
</root>  
```  
  
 <span data-ttu-id="c2fd9-134">每个对象有权访问三个字段 —@name， @quantity，和@cost。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-134">Each object has access to three fields—@name, @quantity, and @cost.</span></span> <span data-ttu-id="c2fd9-135">因为对象是为原始文档的引用，你可以引用的父字段 (例如，"../@customer")。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-135">Because the object is a reference into the original document, you can refer to parent fields (for example, "../@customer").</span></span>  
  
 <span data-ttu-id="c2fd9-136">您可以在同一文档中使用多个选择器。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-136">You can use multiple selectors within the same document.</span></span> <span data-ttu-id="c2fd9-137">这样您就可以查看文档的不同部分（例如，如果一个部分为订单，而另一个部分包含发货地址）。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-137">This enables you to view different parts of the document (for example, if one section is the order and another section contains the shipping address).</span></span> <span data-ttu-id="c2fd9-138">但请记住，所创建的对象是由创建它们的 XPath 字符串定义的。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-138">However, keep in mind that the objects that are created are defined by the XPath string that created them.</span></span> <span data-ttu-id="c2fd9-139">使用不同的 XPath 表达式中，即使它解析为同一节点，导致唯一**TypedXmlDocument**。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-139">Using a different XPath expression, even if it resolves to the same node, results in a unique **TypedXmlDocument**.</span></span>  
  
 <span data-ttu-id="c2fd9-140">规则引擎本身支持基本 .NET 标量类型以及引用类型的对象。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-140">The rule engine supports basic .NET scalar types natively, as well as objects for reference types.</span></span> <span data-ttu-id="c2fd9-141">XML 文档基本上都是文本，但根据在构造规则时指定的类型，字段值可以是任何类型。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-141">XML documents are basically text, but based on the type that was specified when the rule was built, the field value may be of any type.</span></span> <span data-ttu-id="c2fd9-142">同时，由于字段是 XPath 表达式，因此它们可能会返回节点集。在这种情况下，将使用集合中的第一项作为值。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-142">Also, because fields are XPath expressions, they may return a nodeset, in which case the first item in the set is used as the value.</span></span>  
  
 <span data-ttu-id="c2fd9-143">在后台，规则引擎可以将文本字段值转换为任何一种通过受支持的类型**XmlConvert**函数。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-143">Behind the scenes, the rule engine can convert a text field value to any one of the supported types through the **XmlConvert** function.</span></span> <span data-ttu-id="c2fd9-144">可以通过在业务规则编辑器中设置类型来指定该功能。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-144">You can specify this by setting the type in the Business Rule Composer.</span></span> <span data-ttu-id="c2fd9-145">如果无法进行转换，则将会引发异常。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-145">An exception is thrown if a conversion is not possible.</span></span> <span data-ttu-id="c2fd9-146">类型**bool**和**double**可以检索仅作为其各自的类型、 字符串或对象。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-146">The types **bool** and **double** can be retrieved only as their respective type, strings, or objects.</span></span>  
  
## <a name="typeddatatable"></a><span data-ttu-id="c2fd9-147">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="c2fd9-147">TypedDataTable</span></span>  
 <span data-ttu-id="c2fd9-148">当**TypedDataTable**被声明，所有**Datarow**中包含**DataTable**自动断言作为引擎**TypedDataRows**.</span><span class="sxs-lookup"><span data-stu-id="c2fd9-148">When a **TypedDataTable** is asserted, all **DataRows** contained in the **DataTable** are automatically asserted into the engine as **TypedDataRows**.</span></span> <span data-ttu-id="c2fd9-149">任何时候，只要一个表或表的列用作规则参数，针对单个计算该表达式**TypedDataRows**，而不是针对**TypedDataTable**。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-149">Any time a table or table column is used as a rule argument, the expression is evaluated against the individual **TypedDataRows**, and not against the **TypedDataTable**.</span></span>  
  
 <span data-ttu-id="c2fd9-150">例如，假设您针对“Customers”表构建了以下规则：</span><span class="sxs-lookup"><span data-stu-id="c2fd9-150">For example, suppose that you have the following rule built against a "Customers" table:</span></span>  
  
```  
IF Northwind.Customers.CustomerID = 001  
THEN Northwind.Customers.ContactTitle = "Purchasing Manager"  
```  
  
> [!NOTE]
>  <span data-ttu-id="c2fd9-151">若要生成针对数据库表的规则，你必须使用**数据表 / 行**作为数据库绑定类型。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-151">To build a rule against a database table, you must use **Data table / row** as the database binding type.</span></span>  
  
 <span data-ttu-id="c2fd9-152">假设你断言以下**DataTable**有三个**Datarow**引擎 (作为**TypedDataTable**)。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-152">Suppose that you assert the following **DataTable** with three **DataRows** into the engine (as a **TypedDataTable**).</span></span>  
  
|<span data-ttu-id="c2fd9-153">CustomerID</span><span class="sxs-lookup"><span data-stu-id="c2fd9-153">CustomerID</span></span>|<span data-ttu-id="c2fd9-154">ContactTitle</span><span class="sxs-lookup"><span data-stu-id="c2fd9-154">ContactTitle</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="c2fd9-155">001</span><span class="sxs-lookup"><span data-stu-id="c2fd9-155">001</span></span>|<span data-ttu-id="c2fd9-156">Supply Clerk</span><span class="sxs-lookup"><span data-stu-id="c2fd9-156">Supply Clerk</span></span>|  
|<span data-ttu-id="c2fd9-157">002</span><span class="sxs-lookup"><span data-stu-id="c2fd9-157">002</span></span>|<span data-ttu-id="c2fd9-158">Supply Clerk</span><span class="sxs-lookup"><span data-stu-id="c2fd9-158">Supply Clerk</span></span>|  
|<span data-ttu-id="c2fd9-159">003</span><span class="sxs-lookup"><span data-stu-id="c2fd9-159">003</span></span>|<span data-ttu-id="c2fd9-160">Supply Clerk</span><span class="sxs-lookup"><span data-stu-id="c2fd9-160">Supply Clerk</span></span>|  
  
 <span data-ttu-id="c2fd9-161">引擎插入三个**TypedDataRows**: 001、 002 以及 003。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-161">The engine inserts three **TypedDataRows**: 001, 002, and 003.</span></span>  
  
 <span data-ttu-id="c2fd9-162">每个**TypedDataRow**根据规则单独计算。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-162">Each **TypedDataRow** is evaluated independently against the rule.</span></span> <span data-ttu-id="c2fd9-163">第一个**TypedDataRow**满足规则条件和两个失败。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-163">The first **TypedDataRow** meets the rule condition and the second two fail.</span></span> <span data-ttu-id="c2fd9-164">结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="c2fd9-164">The results appear as follows.</span></span>  
  
|<span data-ttu-id="c2fd9-165">CustomerID</span><span class="sxs-lookup"><span data-stu-id="c2fd9-165">CustomerID</span></span>|<span data-ttu-id="c2fd9-166">ContactTitle</span><span class="sxs-lookup"><span data-stu-id="c2fd9-166">ContactTitle</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="c2fd9-167">001</span><span class="sxs-lookup"><span data-stu-id="c2fd9-167">001</span></span>|<span data-ttu-id="c2fd9-168">采购经理</span><span class="sxs-lookup"><span data-stu-id="c2fd9-168">Purchasing Manager</span></span>|  
|<span data-ttu-id="c2fd9-169">002</span><span class="sxs-lookup"><span data-stu-id="c2fd9-169">002</span></span>|<span data-ttu-id="c2fd9-170">Supply Clerk</span><span class="sxs-lookup"><span data-stu-id="c2fd9-170">Supply Clerk</span></span>|  
|<span data-ttu-id="c2fd9-171">003</span><span class="sxs-lookup"><span data-stu-id="c2fd9-171">003</span></span>|<span data-ttu-id="c2fd9-172">Supply Clerk</span><span class="sxs-lookup"><span data-stu-id="c2fd9-172">Supply Clerk</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="c2fd9-173">TypedDataRow 也可以直接添加引擎中。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-173">TypedDataRows can also be directly asserted into the engine.</span></span> <span data-ttu-id="c2fd9-174">其处理方式与前面所述的方式相同。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-174">These are processed in the same way as described earlier.</span></span>  
  
 <span data-ttu-id="c2fd9-175">**DataSetName.DataTableName**被视为唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-175">The **DataSetName.DataTableName** is considered to be a unique identifier.</span></span> <span data-ttu-id="c2fd9-176">因此，如果第二个**TypedDataTable**声明具有相同**数据集**名称和**DataTable**名称，第一个与它所取代**TypedDataTable**.</span><span class="sxs-lookup"><span data-stu-id="c2fd9-176">Therefore, if a second **TypedDataTable** is asserted with the same **DataSet** name and **DataTable** name, it supersedes the first **TypedDataTable**.</span></span> <span data-ttu-id="c2fd9-177">所有**TypedDataRow**与第一个关联**TypedDataTable**收回，第二个**TypedDataTable**断言。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-177">All **TypedDataRow**s associated with the first **TypedDataTable** are retracted, and the second **TypedDataTable** is asserted.</span></span>  
  
## <a name="dataconnection"></a><span data-ttu-id="c2fd9-178">DataConnection</span><span class="sxs-lookup"><span data-stu-id="c2fd9-178">DataConnection</span></span>  
 <span data-ttu-id="c2fd9-179">与**TypedDataTable**，拖动表或列作为业务规则编辑器中规则参数会导致规则生成针对返回**TypedDataRow**相对于 s **数据连接**本身。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-179">As with a **TypedDataTable**, dragging a table or column as a rule argument in the Business Rule Composer results in rules built against the returned **TypedDataRow**s as opposed to the **DataConnection** itself.</span></span>  
  
 <span data-ttu-id="c2fd9-180">假设创建以下规则和**该组**断言，该字符串包含**SqlConnection** Northwind.Customers 到：</span><span class="sxs-lookup"><span data-stu-id="c2fd9-180">Suppose that the following rule is created and a **DataConnection** is asserted that contains a **SqlConnection** to Northwind.Customers:</span></span>  
  
```  
IF Northwind.Customers.CustomerID = 001  
THEN Northwind.Customers.ContactTitle = "Purchasing Manager"  
```  
  
 <span data-ttu-id="c2fd9-181">当引擎的计算结果中使用规则**TypedDataTable**部分中，它动态生成如下所示的查询：</span><span class="sxs-lookup"><span data-stu-id="c2fd9-181">When the engine evaluates the rule used in the **TypedDataTable** section, it dynamically builds a query that looks like:</span></span>  
  
```  
SELECT *  
FROM Northwind.Customers  
WHERE CustomerID = 1  
```  
  
 <span data-ttu-id="c2fd9-182">因为数据库中的只有一个行满足此条件，只有一个**TypedDataRow**被创建并进行进一步处理引擎断言。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-182">Because only one row in the database meets this criterion, only one **TypedDataRow** is created and asserted into the engine for further processing.</span></span>  
  
## <a name="summary-of-asserted-entities-and-instance-types"></a><span data-ttu-id="c2fd9-183">添加的实体和实例类型摘要</span><span class="sxs-lookup"><span data-stu-id="c2fd9-183">Summary of Asserted Entities and Instance Types</span></span>  
 <span data-ttu-id="c2fd9-184">下表概括列出了各种类型的添加行为，显示了在引擎中为添加的每个实体创建的结果实例数，以及应用于这些实例以便对其进行标识的类型。</span><span class="sxs-lookup"><span data-stu-id="c2fd9-184">The following table summarizes the assert behavior for the various types, showing the number of resulting instances created in the engine for each asserted entity, as well as the type that is applied to each of those instances to identify them.</span></span>  
  
|<span data-ttu-id="c2fd9-185">实体</span><span class="sxs-lookup"><span data-stu-id="c2fd9-185">Entity</span></span>|<span data-ttu-id="c2fd9-186">添加的实例数</span><span class="sxs-lookup"><span data-stu-id="c2fd9-186">Number of instances asserted</span></span>|<span data-ttu-id="c2fd9-187">实例类型</span><span class="sxs-lookup"><span data-stu-id="c2fd9-187">Instance type</span></span>|  
|------------|----------------------------------|-------------------|  
|<span data-ttu-id="c2fd9-188">.NET 对象</span><span class="sxs-lookup"><span data-stu-id="c2fd9-188">.NET object</span></span>|<span data-ttu-id="c2fd9-189">1 个（对象本身）</span><span class="sxs-lookup"><span data-stu-id="c2fd9-189">1 (the object itself)</span></span>|<span data-ttu-id="c2fd9-190">完全限定的 .NET 类</span><span class="sxs-lookup"><span data-stu-id="c2fd9-190">Fully Qualified .NET Class</span></span>|  
|<span data-ttu-id="c2fd9-191">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="c2fd9-191">TypedXmlDocument</span></span>|<span data-ttu-id="c2fd9-192">1-N 个 TypedXmlDocument：基于所创建的选择器绑定和文档内容</span><span class="sxs-lookup"><span data-stu-id="c2fd9-192">1-N TypedXmlDocument(s): Based on Selector bindings created and document content</span></span>|<span data-ttu-id="c2fd9-193">DocumentType.Selector</span><span class="sxs-lookup"><span data-stu-id="c2fd9-193">DocumentType.Selector</span></span>|  
|<span data-ttu-id="c2fd9-194">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="c2fd9-194">TypedDataTable</span></span>|<span data-ttu-id="c2fd9-195">1-N 个 TypedDataRow：</span><span class="sxs-lookup"><span data-stu-id="c2fd9-195">1-N TypedDataRow(s):</span></span><br /><br /> <span data-ttu-id="c2fd9-196">DataTable 中的每个 DataRow 各一个</span><span class="sxs-lookup"><span data-stu-id="c2fd9-196">One for each DataRow in the DataTable</span></span>|<span data-ttu-id="c2fd9-197">DataSetName.DataTableName</span><span class="sxs-lookup"><span data-stu-id="c2fd9-197">DataSetName.DataTableName</span></span>|  
|<span data-ttu-id="c2fd9-198">TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="c2fd9-198">TypedDataRow</span></span>|<span data-ttu-id="c2fd9-199">1 个（添加的 TypedDataRow）</span><span class="sxs-lookup"><span data-stu-id="c2fd9-199">1 (the TypedDataRow asserted)</span></span>|<span data-ttu-id="c2fd9-200">DataSetName.DataTableName</span><span class="sxs-lookup"><span data-stu-id="c2fd9-200">DataSetName.DataTableName</span></span>|  
|<span data-ttu-id="c2fd9-201">DataConnection</span><span class="sxs-lookup"><span data-stu-id="c2fd9-201">DataConnection</span></span>|<span data-ttu-id="c2fd9-202">1-N 个（通过查询 DataConnection 返回的每个 TypedDataRow 各一个）</span><span class="sxs-lookup"><span data-stu-id="c2fd9-202">1-N (one for each TypedDataRow returned by querying the DataConnection)</span></span>|<span data-ttu-id="c2fd9-203">DataSetName.DataTableName</span><span class="sxs-lookup"><span data-stu-id="c2fd9-203">DataSetName.DataTableName</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c2fd9-204">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2fd9-204">See Also</span></span>  
 [<span data-ttu-id="c2fd9-205">引擎控制功能</span><span class="sxs-lookup"><span data-stu-id="c2fd9-205">Engine Control Functions</span></span>](../core/engine-control-functions.md)