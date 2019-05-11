---
title: Assert | Microsoft Docs
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
ms.openlocfilehash: ce3fcf26ae039999b4d4593f94ab4b8f375cd03a
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528623"
---
# <a name="assert"></a><span data-ttu-id="2d150-102">ActualRebinds</span><span class="sxs-lookup"><span data-stu-id="2d150-102">Assert</span></span>
<span data-ttu-id="2d150-103">*断言*是添加到业务规则引擎工作内存中的对象实例的过程。</span><span class="sxs-lookup"><span data-stu-id="2d150-103">*Assertion* is the process of adding object instances into the Business Rule engine's working memory.</span></span> <span data-ttu-id="2d150-104">引擎处理的情况和针对的实例，使用匹配-冲突解决-操作阶段类型编写的操作根据每个实例。</span><span class="sxs-lookup"><span data-stu-id="2d150-104">The engine processes each instance according to the conditions and actions that are written against the type of the instance, using the match-conflict resolution-action phases.</span></span>  
  
 <span data-ttu-id="2d150-105">下面的主题介绍使用而导致的行为**Assert**不同的事实类型的函数。</span><span class="sxs-lookup"><span data-stu-id="2d150-105">The following topics describe behaviors that result from using the **Assert** function for different fact types.</span></span>  
  
## <a name="net-objects"></a><span data-ttu-id="2d150-106">.NET 对象</span><span class="sxs-lookup"><span data-stu-id="2d150-106">.NET Objects</span></span>  
 <span data-ttu-id="2d150-107">每个对象作为单独的实例添加到工作内存中。</span><span class="sxs-lookup"><span data-stu-id="2d150-107">Each object is asserted into the working memory as a separate instance.</span></span> <span data-ttu-id="2d150-108">这意味着每个引用对象的类型的谓词分析的实例 (例如，IF Object.Property = 1)。</span><span class="sxs-lookup"><span data-stu-id="2d150-108">This means that the instance is analyzed by each predicate that references the object's type (for example, IF Object.Property = 1).</span></span> <span data-ttu-id="2d150-109">它还将提供到引用类型，依赖于规则条件的结果的规则操作。</span><span class="sxs-lookup"><span data-stu-id="2d150-109">It is also made available to rule actions that reference the type, dependent on the results of the rule conditions.</span></span>  
  
 <span data-ttu-id="2d150-110">请参考如下示例。</span><span class="sxs-lookup"><span data-stu-id="2d150-110">Consider the following example.</span></span>  
  
 <span data-ttu-id="2d150-111">**规则 1**</span><span class="sxs-lookup"><span data-stu-id="2d150-111">**Rule 1**</span></span>  
  
```  
IF A.Value = 1  
THEN A.Status = "good"  
```  
  
 <span data-ttu-id="2d150-112">**规则 2**</span><span class="sxs-lookup"><span data-stu-id="2d150-112">**Rule 2**</span></span>  
  
```  
IF B.Value = 1  
THEN A.Status = "good"  
```  
  
 <span data-ttu-id="2d150-113">在规则 1 中，只有这些实例的一个值为 1 会具有其**状态**更新的属性。</span><span class="sxs-lookup"><span data-stu-id="2d150-113">In Rule 1, only those instances of A that have a Value of 1 will have their **Status** property updated.</span></span> <span data-ttu-id="2d150-114">在规则 2，但是，如果条件计算结果为 **，则返回 true**，为将所有实例都具有其状态已更新。</span><span class="sxs-lookup"><span data-stu-id="2d150-114">In Rule 2, however, if the condition evaluates to **true**, all instances of A will have their status updated.</span></span> <span data-ttu-id="2d150-115">事实上，如果有多个 B 的实例，一个实例将更新条件计算结果为每次 **，则返回 true** B 实例。</span><span class="sxs-lookup"><span data-stu-id="2d150-115">In fact, if there are multiple instances of B, the A instances will be updated each time the condition evaluates to **true** for a B instance.</span></span>  
  
 <span data-ttu-id="2d150-116">若要添加.NET 对象从规则中的，可以添加内置**Assert**函数作为规则操作。</span><span class="sxs-lookup"><span data-stu-id="2d150-116">To assert a .NET object from within a rule, you can add the built-in **Assert** function as a rule action.</span></span> <span data-ttu-id="2d150-117">请注意，规则引擎的强大**CreateObject**函数，但它不会显示为单独的函数在业务规则编辑器。</span><span class="sxs-lookup"><span data-stu-id="2d150-117">Note that the rule engine has a **CreateObject** function, but it is not displayed as a separate function in the Business Rule Composer.</span></span> <span data-ttu-id="2d150-118">其调用旨在通过将你想要从事实浏览器的.NET 类视图创建到操作窗格中的对象的构造函数方法。</span><span class="sxs-lookup"><span data-stu-id="2d150-118">Its invocation is built by dragging the constructor method of the object you wish to create from the .NET Class view of the Facts Explorer to the action pane.</span></span> <span data-ttu-id="2d150-119">业务规则编辑器然后会将转换构造函数方法转换成**CreateObject**在规则定义中调用。</span><span class="sxs-lookup"><span data-stu-id="2d150-119">The Business Rule Composer then translates the constructor method into a **CreateObject** call in the rule definition.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="2d150-120">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="2d150-120">TypedXmlDocument</span></span>  
 <span data-ttu-id="2d150-121">当**TypedXmlDocument**被声明，业务规则引擎创建子**TypedXmlDocument**实例根据规则中定义的选择器。</span><span class="sxs-lookup"><span data-stu-id="2d150-121">When a **TypedXmlDocument** is asserted, the Business Rule Engine creates child **TypedXmlDocument** instances based on the selectors defined in the rule.</span></span>  
  
 <span data-ttu-id="2d150-122">这两个 XPath 表达式选择器和字段。</span><span class="sxs-lookup"><span data-stu-id="2d150-122">Selectors and fields are both XPath expressions.</span></span> <span data-ttu-id="2d150-123">可以选择器视为隔离 XML 文档时，将字段视为标识选择器中的特定项的节点的方法。</span><span class="sxs-lookup"><span data-stu-id="2d150-123">You can think of selectors as a way to isolate nodes of an XML document, and fields as identifying specific items within the selector.</span></span> <span data-ttu-id="2d150-124">一个选择器中的所有字段都组合在一起作为一个对象由引擎。</span><span class="sxs-lookup"><span data-stu-id="2d150-124">All the fields inside one selector are grouped together as an object by the engine.</span></span> <span data-ttu-id="2d150-125">当选择下的一个节点**XML 架构**在事实浏览器，业务规则编辑器的选项卡会自动填充**XPath 选择器**的所有节点的属性和**XPath 字段**不包含子节点的任何节点的属性。</span><span class="sxs-lookup"><span data-stu-id="2d150-125">When you select a node under the **XML Schemas** tab in the Facts Explorer, the Business Rule Composer automatically fills in the **XPath Selector** property for all nodes, and the **XPath Field** property for any node that does not contain child nodes.</span></span> <span data-ttu-id="2d150-126">或者，可以输入自己的 XPath 表达式**XPath 选择器**并**XPath 字段**如有必要。</span><span class="sxs-lookup"><span data-stu-id="2d150-126">Alternatively, you can enter your own XPath expressions for **XPath Selector** and **XPath Field** if necessary.</span></span>  
  
 <span data-ttu-id="2d150-127">如果选择器匹配的 XML 文档的多个部分，将其添加到或从规则引擎工作内存中取消此类型的多个对象。</span><span class="sxs-lookup"><span data-stu-id="2d150-127">If the selector matches multiple portions of the XML document, multiple objects of this type are asserted into or retracted from the rule engine working memory.</span></span> <span data-ttu-id="2d150-128">假设您有下面的 XML。</span><span class="sxs-lookup"><span data-stu-id="2d150-128">Assume you have the following XML.</span></span>  
  
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
  
 <span data-ttu-id="2d150-129">如果使用的选择器/顺序 (或 / / o)，两个对象添加到工作内存。</span><span class="sxs-lookup"><span data-stu-id="2d150-129">If you use the selector /root/order (or //order), two objects are added to the working memory.</span></span>  
  
 <span data-ttu-id="2d150-130">1\)</span><span class="sxs-lookup"><span data-stu-id="2d150-130">1\)</span></span>  
  
```  
<order customer="Joe">  
   <item name="router" quantity="10" cost="550" />  
   <item name="switch" quantity="3" cost="300" />  
</order>  
```  
  
 <span data-ttu-id="2d150-131">2\)</span><span class="sxs-lookup"><span data-stu-id="2d150-131">2\)</span></span>  
  
```  
<order customer="Jane">  
   <item name="switch" quantity="1" cost="300" />  
   <item name="cable" quantity="23" cost="9.99" />  
</order>  
```  
  
 <span data-ttu-id="2d150-132">中每个选择器中，单个字段是通过 Xpath 引用的。</span><span class="sxs-lookup"><span data-stu-id="2d150-132">Within each selector, the individual fields are referred to by XPaths.</span></span>  
  
 <span data-ttu-id="2d150-133">如果使用选择器 /root/order/item (或 (//order/item 或 //item)，四个对象添加到规则引擎工作内存中，Joe 的两个项目和 Jane 的两个项。</span><span class="sxs-lookup"><span data-stu-id="2d150-133">If you use the selector /root/order/item (or (//order/item or //item), four objects  are added to the rule engine working memory, the two items for Joe and the two items for Jane.</span></span>  
  
```  
<root>  
   <order customer="Joe">  
  
   </order>  
   <order customer="Jane">  
  
   </order>  
</root>  
```  
  
 <span data-ttu-id="2d150-134">每个对象有权访问三个字段 —@name， @quantity，和@cost。</span><span class="sxs-lookup"><span data-stu-id="2d150-134">Each object has access to three fields—@name, @quantity, and @cost.</span></span> <span data-ttu-id="2d150-135">因为该对象是对原始文档的引用，您可以引用父字段 (例如，"../@customer")。</span><span class="sxs-lookup"><span data-stu-id="2d150-135">Because the object is a reference into the original document, you can refer to parent fields (for example, "../@customer").</span></span>  
  
 <span data-ttu-id="2d150-136">可以使用同一文档中的多个选择器。</span><span class="sxs-lookup"><span data-stu-id="2d150-136">You can use multiple selectors within the same document.</span></span> <span data-ttu-id="2d150-137">这使您可以查看该文档的不同部分 （例如，如果一个部分为订单，另一个部分包含发货地址）。</span><span class="sxs-lookup"><span data-stu-id="2d150-137">This enables you to view different parts of the document (for example, if one section is the order and another section contains the shipping address).</span></span> <span data-ttu-id="2d150-138">但是，请注意，创建的对象由创建它们的 XPath 字符串定义。</span><span class="sxs-lookup"><span data-stu-id="2d150-138">However, keep in mind that the objects that are created are defined by the XPath string that created them.</span></span> <span data-ttu-id="2d150-139">使用不同的 XPath 表达式，即使它解析为同一节点中，会导致唯一**TypedXmlDocument**。</span><span class="sxs-lookup"><span data-stu-id="2d150-139">Using a different XPath expression, even if it resolves to the same node, results in a unique **TypedXmlDocument**.</span></span>  
  
 <span data-ttu-id="2d150-140">规则引擎支持基本.NET 标量类型本身，以及引用类型的对象。</span><span class="sxs-lookup"><span data-stu-id="2d150-140">The rule engine supports basic .NET scalar types natively, as well as objects for reference types.</span></span> <span data-ttu-id="2d150-141">XML 文档基本上是文本，但根据规则生成时指定的类型，字段值可以是任何类型。</span><span class="sxs-lookup"><span data-stu-id="2d150-141">XML documents are basically text, but based on the type that was specified when the rule was built, the field value may be of any type.</span></span> <span data-ttu-id="2d150-142">此外，由于字段是 XPath 表达式，它们可能会返回节点集，此情况下在集中的第一项都使用作为值。</span><span class="sxs-lookup"><span data-stu-id="2d150-142">Also, because fields are XPath expressions, they may return a nodeset, in which case the first item in the set is used as the value.</span></span>  
  
 <span data-ttu-id="2d150-143">在后台，规则引擎可以将文本字段值转换为任何一种通过受支持的类型**XmlConvert**函数。</span><span class="sxs-lookup"><span data-stu-id="2d150-143">Behind the scenes, the rule engine can convert a text field value to any one of the supported types through the **XmlConvert** function.</span></span> <span data-ttu-id="2d150-144">您可以将类型设置业务规则编辑器中进行指定。</span><span class="sxs-lookup"><span data-stu-id="2d150-144">You can specify this by setting the type in the Business Rule Composer.</span></span> <span data-ttu-id="2d150-145">如果转换不可能，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="2d150-145">An exception is thrown if a conversion is not possible.</span></span> <span data-ttu-id="2d150-146">类型**bool**并**double**可以仅作为其各自的类型、 字符串或对象进行检索。</span><span class="sxs-lookup"><span data-stu-id="2d150-146">The types **bool** and **double** can be retrieved only as their respective type, strings, or objects.</span></span>  
  
## <a name="typeddatatable"></a><span data-ttu-id="2d150-147">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="2d150-147">TypedDataTable</span></span>  
 <span data-ttu-id="2d150-148">当**TypedDataTable**被声明，所有**Datarow**中包含**DataTable**自动将其添加到引擎作为**TypedDataRows**.</span><span class="sxs-lookup"><span data-stu-id="2d150-148">When a **TypedDataTable** is asserted, all **DataRows** contained in the **DataTable** are automatically asserted into the engine as **TypedDataRows**.</span></span> <span data-ttu-id="2d150-149">任何时候，只要一个表或表列用作规则参数，针对单个计算表达式**TypedDataRows**，而不是根据**TypedDataTable**。</span><span class="sxs-lookup"><span data-stu-id="2d150-149">Any time a table or table column is used as a rule argument, the expression is evaluated against the individual **TypedDataRows**, and not against the **TypedDataTable**.</span></span>  
  
 <span data-ttu-id="2d150-150">例如，假设您有针对"客户"表构建了以下规则：</span><span class="sxs-lookup"><span data-stu-id="2d150-150">For example, suppose that you have the following rule built against a "Customers" table:</span></span>  
  
```  
IF Northwind.Customers.CustomerID = 001  
THEN Northwind.Customers.ContactTitle = "Purchasing Manager"  
```  
  
> [!NOTE]
>  <span data-ttu-id="2d150-151">若要生成一条规则针对数据库表，必须使用**数据表 / 行**作为数据库绑定类型。</span><span class="sxs-lookup"><span data-stu-id="2d150-151">To build a rule against a database table, you must use **Data table / row** as the database binding type.</span></span>  
  
 <span data-ttu-id="2d150-152">假设您添加以下**DataTable**具有三个**Datarow**到引擎中 (作为**TypedDataTable**)。</span><span class="sxs-lookup"><span data-stu-id="2d150-152">Suppose that you assert the following **DataTable** with three **DataRows** into the engine (as a **TypedDataTable**).</span></span>  
  
|<span data-ttu-id="2d150-153">CustomerID</span><span class="sxs-lookup"><span data-stu-id="2d150-153">CustomerID</span></span>|<span data-ttu-id="2d150-154">ContactTitle</span><span class="sxs-lookup"><span data-stu-id="2d150-154">ContactTitle</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="2d150-155">001</span><span class="sxs-lookup"><span data-stu-id="2d150-155">001</span></span>|<span data-ttu-id="2d150-156">提供分配器</span><span class="sxs-lookup"><span data-stu-id="2d150-156">Supply Clerk</span></span>|  
|<span data-ttu-id="2d150-157">002</span><span class="sxs-lookup"><span data-stu-id="2d150-157">002</span></span>|<span data-ttu-id="2d150-158">提供分配器</span><span class="sxs-lookup"><span data-stu-id="2d150-158">Supply Clerk</span></span>|  
|<span data-ttu-id="2d150-159">003</span><span class="sxs-lookup"><span data-stu-id="2d150-159">003</span></span>|<span data-ttu-id="2d150-160">提供分配器</span><span class="sxs-lookup"><span data-stu-id="2d150-160">Supply Clerk</span></span>|  
  
 <span data-ttu-id="2d150-161">该引擎将插入三个**TypedDataRows**:001、 002 和 003。</span><span class="sxs-lookup"><span data-stu-id="2d150-161">The engine inserts three **TypedDataRows**: 001, 002, and 003.</span></span>  
  
 <span data-ttu-id="2d150-162">每个**TypedDataRow**针对规则独立计算。</span><span class="sxs-lookup"><span data-stu-id="2d150-162">Each **TypedDataRow** is evaluated independently against the rule.</span></span> <span data-ttu-id="2d150-163">第一个**TypedDataRow**是否满足规则条件和两个故障。</span><span class="sxs-lookup"><span data-stu-id="2d150-163">The first **TypedDataRow** meets the rule condition and the second two fail.</span></span> <span data-ttu-id="2d150-164">结果将显示，如下所示。</span><span class="sxs-lookup"><span data-stu-id="2d150-164">The results appear as follows.</span></span>  
  
|<span data-ttu-id="2d150-165">CustomerID</span><span class="sxs-lookup"><span data-stu-id="2d150-165">CustomerID</span></span>|<span data-ttu-id="2d150-166">ContactTitle</span><span class="sxs-lookup"><span data-stu-id="2d150-166">ContactTitle</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="2d150-167">001</span><span class="sxs-lookup"><span data-stu-id="2d150-167">001</span></span>|<span data-ttu-id="2d150-168">采购经理</span><span class="sxs-lookup"><span data-stu-id="2d150-168">Purchasing Manager</span></span>|  
|<span data-ttu-id="2d150-169">002</span><span class="sxs-lookup"><span data-stu-id="2d150-169">002</span></span>|<span data-ttu-id="2d150-170">提供分配器</span><span class="sxs-lookup"><span data-stu-id="2d150-170">Supply Clerk</span></span>|  
|<span data-ttu-id="2d150-171">003</span><span class="sxs-lookup"><span data-stu-id="2d150-171">003</span></span>|<span data-ttu-id="2d150-172">提供分配器</span><span class="sxs-lookup"><span data-stu-id="2d150-172">Supply Clerk</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="2d150-173">Typeddatarow 也可以直接添加到引擎中。</span><span class="sxs-lookup"><span data-stu-id="2d150-173">TypedDataRows can also be directly asserted into the engine.</span></span> <span data-ttu-id="2d150-174">如前面所述相同的方式处理。</span><span class="sxs-lookup"><span data-stu-id="2d150-174">These are processed in the same way as described earlier.</span></span>  
  
 <span data-ttu-id="2d150-175">**DataSetName.DataTableName**被视为是唯一的标识符。</span><span class="sxs-lookup"><span data-stu-id="2d150-175">The **DataSetName.DataTableName** is considered to be a unique identifier.</span></span> <span data-ttu-id="2d150-176">因此，如果第二个**TypedDataTable**具有相同断言**数据集**名称并**DataTable**名称，它将取代第一个**TypedDataTable**.</span><span class="sxs-lookup"><span data-stu-id="2d150-176">Therefore, if a second **TypedDataTable** is asserted with the same **DataSet** name and **DataTable** name, it supersedes the first **TypedDataTable**.</span></span> <span data-ttu-id="2d150-177">所有**TypedDataRow**与第一个关联**TypedDataTable**将被取消，第二个**TypedDataTable**进行断言。</span><span class="sxs-lookup"><span data-stu-id="2d150-177">All **TypedDataRow**s associated with the first **TypedDataTable** are retracted, and the second **TypedDataTable** is asserted.</span></span>  
  
## <a name="dataconnection"></a><span data-ttu-id="2d150-178">DataConnection</span><span class="sxs-lookup"><span data-stu-id="2d150-178">DataConnection</span></span>  
 <span data-ttu-id="2d150-179">如同**TypedDataTable**，将表或列拖动作为规则参数在业务规则编辑器会导致针对返回生成的规则**TypedDataRow**而不是 s **DataConnection**本身。</span><span class="sxs-lookup"><span data-stu-id="2d150-179">As with a **TypedDataTable**, dragging a table or column as a rule argument in the Business Rule Composer results in rules built against the returned **TypedDataRow**s as opposed to the **DataConnection** itself.</span></span>  
  
 <span data-ttu-id="2d150-180">假设创建以下规则和一个**DataConnection** ，其中包含断言**SqlConnection**到 Northwind.Customers:</span><span class="sxs-lookup"><span data-stu-id="2d150-180">Suppose that the following rule is created and a **DataConnection** is asserted that contains a **SqlConnection** to Northwind.Customers:</span></span>  
  
```  
IF Northwind.Customers.CustomerID = 001  
THEN Northwind.Customers.ContactTitle = "Purchasing Manager"  
```  
  
 <span data-ttu-id="2d150-181">当引擎的计算结果中使用的规则**TypedDataTable**部分中，会动态生成一个查询如下所示：</span><span class="sxs-lookup"><span data-stu-id="2d150-181">When the engine evaluates the rule used in the **TypedDataTable** section, it dynamically builds a query that looks like:</span></span>  
  
```  
SELECT *  
FROM Northwind.Customers  
WHERE CustomerID = 1  
```  
  
 <span data-ttu-id="2d150-182">因为只有一个数据库中的行满足此条件，只有一个**TypedDataRow**创建并将其添加到引擎中以便进一步处理。</span><span class="sxs-lookup"><span data-stu-id="2d150-182">Because only one row in the database meets this criterion, only one **TypedDataRow** is created and asserted into the engine for further processing.</span></span>  
  
## <a name="summary-of-asserted-entities-and-instance-types"></a><span data-ttu-id="2d150-183">断言的实体和实例类型的摘要</span><span class="sxs-lookup"><span data-stu-id="2d150-183">Summary of Asserted Entities and Instance Types</span></span>  
 <span data-ttu-id="2d150-184">下表汇总了各种类型，显示的结果中的每个断言的实体，引擎创建的实例数，以及应用于每个这些实例，以便于识别这些类型的添加行为。</span><span class="sxs-lookup"><span data-stu-id="2d150-184">The following table summarizes the assert behavior for the various types, showing the number of resulting instances created in the engine for each asserted entity, as well as the type that is applied to each of those instances to identify them.</span></span>  
  
|<span data-ttu-id="2d150-185">实体</span><span class="sxs-lookup"><span data-stu-id="2d150-185">Entity</span></span>|<span data-ttu-id="2d150-186">添加的实例数</span><span class="sxs-lookup"><span data-stu-id="2d150-186">Number of instances asserted</span></span>|<span data-ttu-id="2d150-187">实例类型</span><span class="sxs-lookup"><span data-stu-id="2d150-187">Instance type</span></span>|  
|------------|----------------------------------|-------------------|  
|<span data-ttu-id="2d150-188">.NET 对象</span><span class="sxs-lookup"><span data-stu-id="2d150-188">.NET object</span></span>|<span data-ttu-id="2d150-189">1 （对象本身）</span><span class="sxs-lookup"><span data-stu-id="2d150-189">1 (the object itself)</span></span>|<span data-ttu-id="2d150-190">完全限定的.NET 类</span><span class="sxs-lookup"><span data-stu-id="2d150-190">Fully Qualified .NET Class</span></span>|  
|<span data-ttu-id="2d150-191">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="2d150-191">TypedXmlDocument</span></span>|<span data-ttu-id="2d150-192">1-N TypedXmlDocument(s):基于创建的选择器绑定和文档内容</span><span class="sxs-lookup"><span data-stu-id="2d150-192">1-N TypedXmlDocument(s): Based on Selector bindings created and document content</span></span>|<span data-ttu-id="2d150-193">DocumentType.Selector</span><span class="sxs-lookup"><span data-stu-id="2d150-193">DocumentType.Selector</span></span>|  
|<span data-ttu-id="2d150-194">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="2d150-194">TypedDataTable</span></span>|<span data-ttu-id="2d150-195">1-N TypedDataRow(s):</span><span class="sxs-lookup"><span data-stu-id="2d150-195">1-N TypedDataRow(s):</span></span><br /><br /> <span data-ttu-id="2d150-196">一个用于每个 DataRow 的 DataTable 中</span><span class="sxs-lookup"><span data-stu-id="2d150-196">One for each DataRow in the DataTable</span></span>|<span data-ttu-id="2d150-197">DataSetName.DataTableName</span><span class="sxs-lookup"><span data-stu-id="2d150-197">DataSetName.DataTableName</span></span>|  
|<span data-ttu-id="2d150-198">TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="2d150-198">TypedDataRow</span></span>|<span data-ttu-id="2d150-199">1 (添加的 TypedDataRow)</span><span class="sxs-lookup"><span data-stu-id="2d150-199">1 (the TypedDataRow asserted)</span></span>|<span data-ttu-id="2d150-200">DataSetName.DataTableName</span><span class="sxs-lookup"><span data-stu-id="2d150-200">DataSetName.DataTableName</span></span>|  
|<span data-ttu-id="2d150-201">DataConnection</span><span class="sxs-lookup"><span data-stu-id="2d150-201">DataConnection</span></span>|<span data-ttu-id="2d150-202">1-N （一个用于通过查询 DataConnection 返回每个 TypedDataRow）</span><span class="sxs-lookup"><span data-stu-id="2d150-202">1-N (one for each TypedDataRow returned by querying the DataConnection)</span></span>|<span data-ttu-id="2d150-203">DataSetName.DataTableName</span><span class="sxs-lookup"><span data-stu-id="2d150-203">DataSetName.DataTableName</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2d150-204">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d150-204">See Also</span></span>  
 [<span data-ttu-id="2d150-205">引擎控制函数</span><span class="sxs-lookup"><span data-stu-id="2d150-205">Engine Control Functions</span></span>](../core/engine-control-functions.md)