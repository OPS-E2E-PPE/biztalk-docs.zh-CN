---
title: "如何处理 Null 和 DBNull |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: business rules, NULL
ms.assetid: d235c265-4947-470b-9f2d-9936ae1b88a1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b07ac74828a858b368cac5d401081a58b8602323
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-handle-null-and-dbnull"></a><span data-ttu-id="a2cae-102">如何处理 Null 和 DBNull</span><span class="sxs-lookup"><span data-stu-id="a2cae-102">How to Handle Null and DBNull</span></span>
<span data-ttu-id="a2cae-103">本主题介绍处理与不同类型相关的 null 值时的预期行为，并讨论用于检查特定字段或成员是否为 null（即是否存在）的选项。</span><span class="sxs-lookup"><span data-stu-id="a2cae-103">This topic describes the expected behaviors when dealing with null values associated with different types, and discusses options for checking null or existence of a particular field or member.</span></span>  
  
## <a name="xml"></a><span data-ttu-id="a2cae-104">XML</span><span class="sxs-lookup"><span data-stu-id="a2cae-104">XML</span></span>  
 <span data-ttu-id="a2cae-105">以下准则适用于 XML：</span><span class="sxs-lookup"><span data-stu-id="a2cae-105">The following applies to XML:</span></span>  
  
-   <span data-ttu-id="a2cae-106">XML 值将永远不会作为 null 值从文档返回。</span><span class="sxs-lookup"><span data-stu-id="a2cae-106">An XML value will never be returned from a document as null.</span></span> <span data-ttu-id="a2cae-107">它返回空字符串或“不存在”错误。</span><span class="sxs-lookup"><span data-stu-id="a2cae-107">It is either an empty string or a "does not exist" error.</span></span> <span data-ttu-id="a2cae-108">如果是空字符串，则转换特定类型（例如，生成规则时将字段指定为整数类型）时可能会发生错误。</span><span class="sxs-lookup"><span data-stu-id="a2cae-108">When it is an empty string, an error may occur for conversion of certain types, for example, fields specified as an integer type when building rules.</span></span>  
  
-   <span data-ttu-id="a2cae-109">业务规则编辑器不允许你将字段设置为 null 或设置字段的类型**对象**。</span><span class="sxs-lookup"><span data-stu-id="a2cae-109">The Business Rule Composer does not allow you to set a field to null or to set the type of a field to **object**.</span></span>  
  
-   <span data-ttu-id="a2cae-110">通过对象模型中，你可以将类型为**对象**。</span><span class="sxs-lookup"><span data-stu-id="a2cae-110">Through the object model you can set the type to **Object**.</span></span> <span data-ttu-id="a2cae-111">在这种情况下，返回的值是 XPath 计算结果的类型- **float**，**布尔**，或**字符串**，取决于 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="a2cae-111">In this case, the value returned is the type to which the XPath evaluates— **float**, **boolean**, or **string**, depending on the XPath expression.</span></span>  
  
## <a name="net-classes"></a><span data-ttu-id="a2cae-112">.NET 类</span><span class="sxs-lookup"><span data-stu-id="a2cae-112">.NET classes</span></span>  
 <span data-ttu-id="a2cae-113">以下情况适用于 .NET 类：</span><span class="sxs-lookup"><span data-stu-id="a2cae-113">The following applies to .NET classes:</span></span>  
  
-   <span data-ttu-id="a2cae-114">不允许为 null 比较，如果返回类型不是**对象**类型。</span><span class="sxs-lookup"><span data-stu-id="a2cae-114">You are not allowed to compare to null if your return type is not an **object** type.</span></span>  
  
-   <span data-ttu-id="a2cae-115">您可以将 null 作为非值类型的参数的参数传递，但是可能会产生运行时错误，这取决于成员的实现情况。</span><span class="sxs-lookup"><span data-stu-id="a2cae-115">You can pass null as a parameter for parameters that are not value types, but you may get a runtime error, depending on the implementation of the member.</span></span>  
  
-   <span data-ttu-id="a2cae-116">你可以设置字段的类型派生自**对象**为 null。</span><span class="sxs-lookup"><span data-stu-id="a2cae-116">You can set fields of types derived from **Object** to null.</span></span>  
  
## <a name="data-connection"></a><span data-ttu-id="a2cae-117">数据连接</span><span class="sxs-lookup"><span data-stu-id="a2cae-117">Data connection</span></span>  
 <span data-ttu-id="a2cae-118">以下情况适用于数据连接：</span><span class="sxs-lookup"><span data-stu-id="a2cae-118">The following applies to a data connection:</span></span>  
  
-   <span data-ttu-id="a2cae-119">如果表允许空值的列和列类型不是，你可以比较为 null，任何数据库表列**文本**， **ntext**，和**映像**。</span><span class="sxs-lookup"><span data-stu-id="a2cae-119">You can compare any database table column to null, if the table allows nulls for the column and the column type is not **text**, **ntext**, and **image**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a2cae-120">业务规则编辑器，可使用的类型，列**文本**和**ntext**，在条件中。</span><span class="sxs-lookup"><span data-stu-id="a2cae-120">The Business Rule Composer allows you to use columns of type, **text** and **ntext**, in conditions.</span></span> <span data-ttu-id="a2cae-121">但是，您执行该策略时将会收到错误消息，指出：“text、ntext、和 image 数据类型不能比较或排序，除非使用 IS NULL 或 LIKE 运算符”。</span><span class="sxs-lookup"><span data-stu-id="a2cae-121">However, when you execute the policy, you will receive an error message, which says, "The text, ntext, and image data types cannot be compared or sorted, except when using IS NULL or LIKE operator".</span></span>  
  
-   <span data-ttu-id="a2cae-122">如果数据库表允许列具有 null 值，则可以将该表的任何列设置为 null。</span><span class="sxs-lookup"><span data-stu-id="a2cae-122">You can set any database table column to null, if the table allows nulls for the column.</span></span>  
  
-   <span data-ttu-id="a2cae-123">业务规则编辑器会自动设置到绑定中的成员类型**对象**，如果比较或将设置为 null 的值类型; 它可以将其更改回原始类型如果重置或替换自变量。</span><span class="sxs-lookup"><span data-stu-id="a2cae-123">The Business Rule Composer automatically sets the member type in the binding to **object**, if you compare or set to null for a value type; it changes back to the original type if you reset or replace the argument.</span></span>  
  
-   <span data-ttu-id="a2cae-124">对于字符串类型，它更改为的类型**对象**如果将其设置为 null，但将其保留为一个字符串，如果比较结果为 null。</span><span class="sxs-lookup"><span data-stu-id="a2cae-124">For a string type, it changes the type to **object** if you set it to null, but leaves it as a string if you compare against null.</span></span>  
  
-   <span data-ttu-id="a2cae-125">不能比较或将设置为**DBNull.Value**从业务规则编辑器，因为它不会更改的列类型**对象**。</span><span class="sxs-lookup"><span data-stu-id="a2cae-125">You cannot compare or set to **DBNull.Value** from the Business Rule Composer, because it will not change the column type to **object**.</span></span>  
  
-   <span data-ttu-id="a2cae-126">该引擎会将 DBNull 值转换为 null 以便进行比较，并将 null 值转换为 DBNull 值以便插入到数据库中。</span><span class="sxs-lookup"><span data-stu-id="a2cae-126">The engine will convert a DBNull value to null for comparison and will convert null to a DBNull value for insertion into the database.</span></span>  
  
-   <span data-ttu-id="a2cae-127">测试将忽略 null 值（这是 SQL Server 的工作方式）。</span><span class="sxs-lookup"><span data-stu-id="a2cae-127">Tests will ignore null values (this is the way SQL Server works).</span></span> <span data-ttu-id="a2cae-128">例如，如果您有规则“IF db.column > 5 THEN”，则只测试 db.column 中具有值的行，跳过含 null 值的行。</span><span class="sxs-lookup"><span data-stu-id="a2cae-128">For example, if you have the rule "IF db.column > 5 THEN .", only the rows that have a value in db.column are tested—rows with null are skipped.</span></span>  
  
## <a name="typeddatatable-and-typeddatarow"></a><span data-ttu-id="a2cae-129">TypedDataTable 和 TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="a2cae-129">TypedDataTable and TypedDataRow</span></span>  
 <span data-ttu-id="a2cae-130">以下情况适用于 TypedDataTable 和 TypedDataRow：</span><span class="sxs-lookup"><span data-stu-id="a2cae-130">The following applies to TypedDataTable and TypedDataRow:</span></span>  
  
-   <span data-ttu-id="a2cae-131">业务规则编辑器更改的字段类型**对象**中与使用相同的方式**该组**s。</span><span class="sxs-lookup"><span data-stu-id="a2cae-131">The Business Rule Composer changes the field type to **object** in the same manner as with **DataConnection**s.</span></span>  
  
-   <span data-ttu-id="a2cae-132">如果是 null 值，则测试将失败；除非与 null 进行比较。</span><span class="sxs-lookup"><span data-stu-id="a2cae-132">Tests will fail for null values, unless you are comparing to null.</span></span> <span data-ttu-id="a2cae-133">例如，如果添加的任何行具有 null 值，则规则“IF db.column > 5 THEN”中将会生成错误。</span><span class="sxs-lookup"><span data-stu-id="a2cae-133">For example, there will be an error in the rule "IF db.column > 5 THEN ", if any row asserted has a null value.</span></span>  
  
     <span data-ttu-id="a2cae-134">请注意，由于条件是并行计算的，像“IF db.column != NULL AND db.column > 5 THEN”这样的测试仍会失败，这是因为两个测试在每行中可能都会进行评估。</span><span class="sxs-lookup"><span data-stu-id="a2cae-134">Note that because conditions are evaluated in parallel, tests like "IF db.column != NULL AND db.column > 5 THEN  " will still fail, because both tests are potentially evaluated on every row.</span></span>  
  
## <a name="checking-for-null-or-existence"></a><span data-ttu-id="a2cae-135">检查是否存在</span><span class="sxs-lookup"><span data-stu-id="a2cae-135">Checking for null or existence</span></span>  
 <span data-ttu-id="a2cae-136">编写业务规则时，在比较字段的值之前检查该字段是否存在是很正常的。</span><span class="sxs-lookup"><span data-stu-id="a2cae-136">When writing business rules, it is natural to check for the existence of a field before comparing its value.</span></span> <span data-ttu-id="a2cae-137">但是，如果该字段为 null（即不存在），则比较该值将引起错误。</span><span class="sxs-lookup"><span data-stu-id="a2cae-137">However, if the field is null or does not exist, comparing the value will cause an error.</span></span> <span data-ttu-id="a2cae-138">假定存在以下规则：</span><span class="sxs-lookup"><span data-stu-id="a2cae-138">Assume you have the following rule:</span></span>  
  
 <span data-ttu-id="a2cae-139">如果产品/数量存在 AND 产品/数量 > 1</span><span class="sxs-lookup"><span data-stu-id="a2cae-139">IF Product/Quantity Exists AND Product/Quantity > 1</span></span>  
  
 <span data-ttu-id="a2cae-140">如果 Product/Quantity 不存在，规则中将引发错误。</span><span class="sxs-lookup"><span data-stu-id="a2cae-140">An error will be thrown in the rule if Product/Quantity does not exist.</span></span> <span data-ttu-id="a2cae-141">规避此问题的方法之一是将父节点传递到 helper 方法，如果元素值存在，helper 方法将返回元素值；如果元素值不存在，则返回其他内容。</span><span class="sxs-lookup"><span data-stu-id="a2cae-141">One of the ways to circumvent this problem is to pass a parent node to a helper method that returns the element value if it exists or something else if it does not.</span></span> <span data-ttu-id="a2cae-142">请参阅以下规则。</span><span class="sxs-lookup"><span data-stu-id="a2cae-142">See the following rules.</span></span>  
  
 <span data-ttu-id="a2cae-143">**规则 1**</span><span class="sxs-lookup"><span data-stu-id="a2cae-143">**Rule 1**</span></span>  
  
 <span data-ttu-id="a2cae-144">IF EXISTS(Product/Quantity) THEN ASSERT(CREATEOBJECT(typeof(Helper), Product/Quantity)</span><span class="sxs-lookup"><span data-stu-id="a2cae-144">IF EXISTS(Product/Quantity) THEN ASSERT(CREATEOBJECT(typeof(Helper), Product/Quantity)</span></span>  
  
 <span data-ttu-id="a2cae-145">**规则 2**</span><span class="sxs-lookup"><span data-stu-id="a2cae-145">**Rule 2**</span></span>  
  
 <span data-ttu-id="a2cae-146">IF Helper.Value == X THEN...</span><span class="sxs-lookup"><span data-stu-id="a2cae-146">IF Helper.Value == X THEN...</span></span>  
  
 <span data-ttu-id="a2cae-147">另一个可能的解决方案是创建以下规则：</span><span class="sxs-lookup"><span data-stu-id="a2cae-147">Another possible solution is to create a rule like the following:</span></span>  
  
 <span data-ttu-id="a2cae-148">IF Product/Quantity Exist Then CheckQuantityAndDoSomething(Product/Quantity)</span><span class="sxs-lookup"><span data-stu-id="a2cae-148">IF Product/Quantity Exist Then CheckQuantityAndDoSomething(Product/Quantity)</span></span>  
  
 <span data-ttu-id="a2cae-149">在上例中，CheckQuantityAndDoSomething 函数将会检查参数值，如果条件满足则执行该函数。</span><span class="sxs-lookup"><span data-stu-id="a2cae-149">In the preceding example, the CheckQuantityAndDoSomething function will check the parameter value and execute if the condition is met.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2cae-150">或者，你可以修改 XPath**字段**XML 事实来捕获任何错误，但它的属性不是建议的方法。</span><span class="sxs-lookup"><span data-stu-id="a2cae-150">Alternatively, you can modify the XPath **Field** property for the XML fact to catch any errors, but it is not the recommended approach.</span></span>