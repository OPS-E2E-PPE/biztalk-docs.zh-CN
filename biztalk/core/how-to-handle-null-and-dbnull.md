---
title: 如何处理 Null 和 DBNull |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, NULL
ms.assetid: d235c265-4947-470b-9f2d-9936ae1b88a1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea5635e289ce1d510e7e2701c79eeb3c9543b54e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385012"
---
# <a name="how-to-handle-null-and-dbnull"></a><span data-ttu-id="43159-102">如何处理 Null 和 DBNull</span><span class="sxs-lookup"><span data-stu-id="43159-102">How to Handle Null and DBNull</span></span>
<span data-ttu-id="43159-103">本主题介绍处理与不同类型的 null 值时的预期的行为，并讨论用于检查存在特定字段或成员的选项。</span><span class="sxs-lookup"><span data-stu-id="43159-103">This topic describes the expected behaviors when dealing with null values associated with different types, and discusses options for checking null or existence of a particular field or member.</span></span>  
  
## <a name="xml"></a><span data-ttu-id="43159-104">XML</span><span class="sxs-lookup"><span data-stu-id="43159-104">XML</span></span>  
 <span data-ttu-id="43159-105">以下情况适用于 XML:</span><span class="sxs-lookup"><span data-stu-id="43159-105">The following applies to XML:</span></span>  
  
-   <span data-ttu-id="43159-106">XML 值将永远不会返回从文档为 null。</span><span class="sxs-lookup"><span data-stu-id="43159-106">An XML value will never be returned from a document as null.</span></span> <span data-ttu-id="43159-107">它是空字符串或"不存在"错误。</span><span class="sxs-lookup"><span data-stu-id="43159-107">It is either an empty string or a "does not exist" error.</span></span> <span data-ttu-id="43159-108">空字符串时，错误可能会发生转换特定类型，例如，在生成规则时指定的整数类型的字段。</span><span class="sxs-lookup"><span data-stu-id="43159-108">When it is an empty string, an error may occur for conversion of certain types, for example, fields specified as an integer type when building rules.</span></span>  
  
-   <span data-ttu-id="43159-109">业务规则编辑器不允许您将字段设置为 null 或设置到字段的类型**对象**。</span><span class="sxs-lookup"><span data-stu-id="43159-109">The Business Rule Composer does not allow you to set a field to null or to set the type of a field to **object**.</span></span>  
  
-   <span data-ttu-id="43159-110">通过对象模型中，您可以设置类型为**对象**。</span><span class="sxs-lookup"><span data-stu-id="43159-110">Through the object model you can set the type to **Object**.</span></span> <span data-ttu-id="43159-111">在这种情况下，返回的值是 XPath 计算结果的类型 — **float**，**布尔**，或**字符串**，取决于 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="43159-111">In this case, the value returned is the type to which the XPath evaluates— **float**, **boolean**, or **string**, depending on the XPath expression.</span></span>  
  
## <a name="net-classes"></a><span data-ttu-id="43159-112">.NET 类</span><span class="sxs-lookup"><span data-stu-id="43159-112">.NET classes</span></span>  
 <span data-ttu-id="43159-113">以下内容适用于.NET 类：</span><span class="sxs-lookup"><span data-stu-id="43159-113">The following applies to .NET classes:</span></span>  
  
-   <span data-ttu-id="43159-114">您不能与 null 进行比较，如果返回类型不是**对象**类型。</span><span class="sxs-lookup"><span data-stu-id="43159-114">You are not allowed to compare to null if your return type is not an **object** type.</span></span>  
  
-   <span data-ttu-id="43159-115">您可以将 null 作为传递的参数的参数不是值类型，但可能会收到运行时错误，具体取决于成员的实现。</span><span class="sxs-lookup"><span data-stu-id="43159-115">You can pass null as a parameter for parameters that are not value types, but you may get a runtime error, depending on the implementation of the member.</span></span>  
  
-   <span data-ttu-id="43159-116">您可以设置字段的类型派生自**对象**为 null。</span><span class="sxs-lookup"><span data-stu-id="43159-116">You can set fields of types derived from **Object** to null.</span></span>  
  
## <a name="data-connection"></a><span data-ttu-id="43159-117">数据连接</span><span class="sxs-lookup"><span data-stu-id="43159-117">Data connection</span></span>  
 <span data-ttu-id="43159-118">以下内容适用于数据连接：</span><span class="sxs-lookup"><span data-stu-id="43159-118">The following applies to a data connection:</span></span>  
  
-   <span data-ttu-id="43159-119">如果允许空值的列和列类型不是，您可以比较为 null，任何数据库表列**文本**， **ntext**，并**图像**。</span><span class="sxs-lookup"><span data-stu-id="43159-119">You can compare any database table column to null, if the table allows nulls for the column and the column type is not **text**, **ntext**, and **image**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="43159-120">业务规则编辑器，可使用的类型，列**文本**并**ntext**，在条件中。</span><span class="sxs-lookup"><span data-stu-id="43159-120">The Business Rule Composer allows you to use columns of type, **text** and **ntext**, in conditions.</span></span> <span data-ttu-id="43159-121">但是，在执行策略时，你将收到错误消息，指出:"text、 ntext 和 image 数据类型不能比较或排序，除非使用 IS NULL 或 LIKE 运算符"。</span><span class="sxs-lookup"><span data-stu-id="43159-121">However, when you execute the policy, you will receive an error message, which says, "The text, ntext, and image data types cannot be compared or sorted, except when using IS NULL or LIKE operator".</span></span>  
  
-   <span data-ttu-id="43159-122">如果允许空值的列，可以为 null，设置任何数据库表的列。</span><span class="sxs-lookup"><span data-stu-id="43159-122">You can set any database table column to null, if the table allows nulls for the column.</span></span>  
  
-   <span data-ttu-id="43159-123">业务规则编辑器会自动将绑定中设置的成员类型**对象**，如果比较或将设置为值类型，则为 null; 如果重置或替换该参数，它更改回原始类型。</span><span class="sxs-lookup"><span data-stu-id="43159-123">The Business Rule Composer automatically sets the member type in the binding to **object**, if you compare or set to null for a value type; it changes back to the original type if you reset or replace the argument.</span></span>  
  
-   <span data-ttu-id="43159-124">对于字符串类型，它更改为的类型**对象**如果将其设置为 null，但将其保留为一个字符串，如果与 null 进行比较。</span><span class="sxs-lookup"><span data-stu-id="43159-124">For a string type, it changes the type to **object** if you set it to null, but leaves it as a string if you compare against null.</span></span>  
  
-   <span data-ttu-id="43159-125">不能比较或将设置为**DBNull.Value**从业务规则编辑器中，因为它不会更改为的列类型**对象**。</span><span class="sxs-lookup"><span data-stu-id="43159-125">You cannot compare or set to **DBNull.Value** from the Business Rule Composer, because it will not change the column type to **object**.</span></span>  
  
-   <span data-ttu-id="43159-126">引擎会将 DBNull 值转换为 null 以便进行比较，并会将 null 转换为 DBNull 值以便插入到数据库。</span><span class="sxs-lookup"><span data-stu-id="43159-126">The engine will convert a DBNull value to null for comparison and will convert null to a DBNull value for insertion into the database.</span></span>  
  
-   <span data-ttu-id="43159-127">测试将忽略 null 值 （这是 SQL Server 的工作的方式）。</span><span class="sxs-lookup"><span data-stu-id="43159-127">Tests will ignore null values (this is the way SQL Server works).</span></span> <span data-ttu-id="43159-128">例如，如果您有规则"IF db.column > 5 THEN。"，测试 db.column 中具有值的行，为 null 的行被跳过。</span><span class="sxs-lookup"><span data-stu-id="43159-128">For example, if you have the rule "IF db.column > 5 THEN .", only the rows that have a value in db.column are tested—rows with null are skipped.</span></span>  
  
## <a name="typeddatatable-and-typeddatarow"></a><span data-ttu-id="43159-129">TypedDataTable 和 TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="43159-129">TypedDataTable and TypedDataRow</span></span>  
 <span data-ttu-id="43159-130">以下内容适用于 TypedDataTable 和 TypedDataRow:</span><span class="sxs-lookup"><span data-stu-id="43159-130">The following applies to TypedDataTable and TypedDataRow:</span></span>  
  
-   <span data-ttu-id="43159-131">业务规则编辑器更改字段类型为**对象**中与使用相同的方式**DataConnection**s。</span><span class="sxs-lookup"><span data-stu-id="43159-131">The Business Rule Composer changes the field type to **object** in the same manner as with **DataConnection**s.</span></span>  
  
-   <span data-ttu-id="43159-132">除非与 null 进行比较，测试将失败的 null 值。</span><span class="sxs-lookup"><span data-stu-id="43159-132">Tests will fail for null values, unless you are comparing to null.</span></span> <span data-ttu-id="43159-133">例如，将有一个错误在规则中"IF db.column > 5 THEN"，如果添加的任何行具有 null 值。</span><span class="sxs-lookup"><span data-stu-id="43159-133">For example, there will be an error in the rule "IF db.column > 5 THEN ", if any row asserted has a null value.</span></span>  
  
     <span data-ttu-id="43159-134">请注意，条件并行计算的因为测试类似于"IF db.column ！ = NULL AND db.column > 5 THEN"仍会失败，因为这两个测试的每一行上可能都会进行评估。</span><span class="sxs-lookup"><span data-stu-id="43159-134">Note that because conditions are evaluated in parallel, tests like "IF db.column != NULL AND db.column > 5 THEN  " will still fail, because both tests are potentially evaluated on every row.</span></span>  
  
## <a name="checking-for-null-or-existence"></a><span data-ttu-id="43159-135">检查存在</span><span class="sxs-lookup"><span data-stu-id="43159-135">Checking for null or existence</span></span>  
 <span data-ttu-id="43159-136">在编写业务规则时，是自然会检查存在的字段之前，请将其值进行比较。</span><span class="sxs-lookup"><span data-stu-id="43159-136">When writing business rules, it is natural to check for the existence of a field before comparing its value.</span></span> <span data-ttu-id="43159-137">但是，如果该字段为 null 或不存在，则将值进行比较将导致错误。</span><span class="sxs-lookup"><span data-stu-id="43159-137">However, if the field is null or does not exist, comparing the value will cause an error.</span></span> <span data-ttu-id="43159-138">假设具有以下规则：</span><span class="sxs-lookup"><span data-stu-id="43159-138">Assume you have the following rule:</span></span>  
  
 <span data-ttu-id="43159-139">如果 Product/Quantity 存在 AND Product/Quantity > 1</span><span class="sxs-lookup"><span data-stu-id="43159-139">IF Product/Quantity Exists AND Product/Quantity > 1</span></span>  
  
 <span data-ttu-id="43159-140">如果 Product/Quantity 不存在，将在规则中引发错误。</span><span class="sxs-lookup"><span data-stu-id="43159-140">An error will be thrown in the rule if Product/Quantity does not exist.</span></span> <span data-ttu-id="43159-141">要解决此问题的方法之一是将父节点传递到返回元素值，如果存在，或如果不是其他内容的帮助器方法。</span><span class="sxs-lookup"><span data-stu-id="43159-141">One of the ways to circumvent this problem is to pass a parent node to a helper method that returns the element value if it exists or something else if it does not.</span></span> <span data-ttu-id="43159-142">请参阅下面的规则。</span><span class="sxs-lookup"><span data-stu-id="43159-142">See the following rules.</span></span>  
  
 <span data-ttu-id="43159-143">**规则 1**</span><span class="sxs-lookup"><span data-stu-id="43159-143">**Rule 1**</span></span>  
  
 <span data-ttu-id="43159-144">如果 EXISTS(Product/Quantity) 然后 ASSERT(CREATEOBJECT(typeof(Helper)，产品/数量)</span><span class="sxs-lookup"><span data-stu-id="43159-144">IF EXISTS(Product/Quantity) THEN ASSERT(CREATEOBJECT(typeof(Helper), Product/Quantity)</span></span>  
  
 <span data-ttu-id="43159-145">**规则 2**</span><span class="sxs-lookup"><span data-stu-id="43159-145">**Rule 2**</span></span>  
  
 <span data-ttu-id="43159-146">IF Helper.Value == X THEN...</span><span class="sxs-lookup"><span data-stu-id="43159-146">IF Helper.Value == X THEN...</span></span>  
  
 <span data-ttu-id="43159-147">另一个可能的解决方案是创建的规则如下所示：</span><span class="sxs-lookup"><span data-stu-id="43159-147">Another possible solution is to create a rule like the following:</span></span>  
  
 <span data-ttu-id="43159-148">如果 Product/Quantity 存在然后 CheckQuantityAndDoSomething(Product/Quantity)</span><span class="sxs-lookup"><span data-stu-id="43159-148">IF Product/Quantity Exist Then CheckQuantityAndDoSomething(Product/Quantity)</span></span>  
  
 <span data-ttu-id="43159-149">在前面的示例中，CheckQuantityAndDoSomething 函数将检查参数值并执行如果满足该条件。</span><span class="sxs-lookup"><span data-stu-id="43159-149">In the preceding example, the CheckQuantityAndDoSomething function will check the parameter value and execute if the condition is met.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43159-150">或者，可以修改 XPath**字段**属性 XML 事实来捕获任何错误，但它不是建议的方法。</span><span class="sxs-lookup"><span data-stu-id="43159-150">Alternatively, you can modify the XPath **Field** property for the XML fact to catch any errors, but it is not the recommended approach.</span></span>