---
title: 如何创建词汇定义 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, vocabularies
- vocabularies, creating
- vocabularies, definitions
ms.assetid: 6f8fc4c2-2c46-4a7d-a02f-89de0396e3e2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff9fdfc7cd444a97d1a24353c13d93460c00d4ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250557"
---
# <a name="how-to-create-vocabulary-definitions"></a><span data-ttu-id="1b347-102">如何创建词汇定义</span><span class="sxs-lookup"><span data-stu-id="1b347-102">How to Create Vocabulary Definitions</span></span>
<span data-ttu-id="1b347-103">您可以使用词汇定义向导来创建词汇定义。</span><span class="sxs-lookup"><span data-stu-id="1b347-103">You can use the Vocabulary Definition Wizard to create vocabulary definitions.</span></span> <span data-ttu-id="1b347-104">词汇定义可以定义为常数值、值的范围或值的集合，或定义为 .NET 程序集、XML 文档或数据库表的元素。</span><span class="sxs-lookup"><span data-stu-id="1b347-104">You can define a vocabulary definition as a constant value, a range of values, a set of values, or elements of a .NET assembly, XML document, or database table.</span></span> <span data-ttu-id="1b347-105">如果你选择的公共变量，将有**获取**和**设置**选项就像在数据库和 XML 定义向导。</span><span class="sxs-lookup"><span data-stu-id="1b347-105">If you select a public variable, there will be **Get** and **Set** options just like in Database and XML definition wizard.</span></span>  
  
 <span data-ttu-id="1b347-106">或者，可以通过从三个选项卡之一选择事实创建新的词汇定义 — 例如，数据库列、 XML 节点或一个.NET 类的成员-事实拖动到**词汇**选项卡上，并将其放置到词汇未发布版本。</span><span class="sxs-lookup"><span data-stu-id="1b347-106">Alternatively, you can create a new vocabulary definition by selecting a fact from one of the three tabs—for example, a database column, an XML node, or a member of a .NET class—dragging the fact over to the **Vocabularies** tab, and dropping it to an unpublished version of a vocabulary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b347-107">您不能将词汇定义添加到已发布的词汇版本中。</span><span class="sxs-lookup"><span data-stu-id="1b347-107">You cannot add a vocabulary definition to a vocabulary version that has been published.</span></span>  
  
### <a name="to-define-a-vocabulary-definition-as-a-constant-value"></a><span data-ttu-id="1b347-108">将词汇定义定义为常数值</span><span class="sxs-lookup"><span data-stu-id="1b347-108">To define a vocabulary definition as a constant value</span></span>  
  
1.  <span data-ttu-id="1b347-109">右击词汇版本，然后单击**添加新定义**。</span><span class="sxs-lookup"><span data-stu-id="1b347-109">Right-click the vocabulary version, and then click **Add New Definition**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b347-110">您还可以从事实浏览器的其他选项卡（“XML 架构”、“数据库”和“.NET 类”）中拖放项</span><span class="sxs-lookup"><span data-stu-id="1b347-110">You can also drag and drop items from other tabs of Fact Explorer: XML Schemas, Databases and .NET Classes</span></span>  
  
2.  <span data-ttu-id="1b347-111">在词汇定义向导中，选择**常量值、 值的范围或设置的值**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1b347-111">In the Vocabulary Definition Wizard, select **Constant Value, Range of Values, or Set of Values**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="1b347-112">编辑定义名称和定义说明。</span><span class="sxs-lookup"><span data-stu-id="1b347-112">Edit the definition name and definition description.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b347-113">定义显示名称的最大长度为 512 个字符。</span><span class="sxs-lookup"><span data-stu-id="1b347-113">The maximum length for a definition display name is 512 characters.</span></span>  
  
4.  <span data-ttu-id="1b347-114">选择**常量值**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1b347-114">Select **Constant Value**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="1b347-115">从可用系统类型的下拉列表中选择一个定义类型。</span><span class="sxs-lookup"><span data-stu-id="1b347-115">Select a definition type from the drop-down list of available system types.</span></span>  
  
6.  <span data-ttu-id="1b347-116">编辑的显示名称和值，并依次**完成**。</span><span class="sxs-lookup"><span data-stu-id="1b347-116">Edit the display name and value, and then click **Finish**.</span></span>  
  
### <a name="to-define-a-vocabulary-definition-as-a-range-of-values"></a><span data-ttu-id="1b347-117">将词汇定义定义为值的范围</span><span class="sxs-lookup"><span data-stu-id="1b347-117">To define a vocabulary definition as a range of values</span></span>  
  
1.  <span data-ttu-id="1b347-118">右击词汇版本，然后单击**添加新定义**。</span><span class="sxs-lookup"><span data-stu-id="1b347-118">Right-click the vocabulary version, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="1b347-119">在词汇定义向导中，选择**常量值、 值的范围或设置的值**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1b347-119">In the Vocabulary Definition Wizard, select **Constant Value, Range of Values, or Set of Values**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="1b347-120">编辑定义名称和定义说明。</span><span class="sxs-lookup"><span data-stu-id="1b347-120">Edit the definition name and definition description.</span></span>  
  
4.  <span data-ttu-id="1b347-121">选择**值的范围**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1b347-121">Select **Range of Values**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="1b347-122">从下拉列表中选择一个定义类型。</span><span class="sxs-lookup"><span data-stu-id="1b347-122">Select a definition type from the drop-down list.</span></span>  
  
6.  <span data-ttu-id="1b347-123">单击**范围低**，然后单击**编辑**指定较低范围的值。</span><span class="sxs-lookup"><span data-stu-id="1b347-123">Click **Range Low**, and then click **Edit** to specify the values for the lower range.</span></span> <span data-ttu-id="1b347-124">此时，将打开“参数定义”对话框。</span><span class="sxs-lookup"><span data-stu-id="1b347-124">The parameter definition dialog will be opened.</span></span>  
  
7.  <span data-ttu-id="1b347-125">选择**使用常量值**并输入一个常量值，或选择**发布的词汇中使用定义**并浏览到词汇定义，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1b347-125">Select **Use Constant Value** and enter a constant value, or select **Use Definition from a Published Vocabulary** and browse to a vocabulary definition, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="1b347-126">重复步骤 6 和 7 适用于**范围上限**。</span><span class="sxs-lookup"><span data-stu-id="1b347-126">Repeat steps 6 and 7 for **Range High**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b347-127">**范围上限**值必须超过**范围低**值。</span><span class="sxs-lookup"><span data-stu-id="1b347-127">The **Range High** value must exceed the **Range Low** value.</span></span>  
  
9. <span data-ttu-id="1b347-128">键入的显示格式字符串或单击**默认**以还原到默认的显示格式字符串，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="1b347-128">Type the display format string or click **Default** to revert to the default display format string, and then click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b347-129">格式字符串应包括在大括号中的参数索引 — 例如，"{0}"和"{1}"—to 充当高和低范围参数的占位符的不同而不同。</span><span class="sxs-lookup"><span data-stu-id="1b347-129">Your format string should include parameter indexes in curly braces—for example, "{0}" and "{1}"—to serve as placeholders for the high and low range parameters.</span></span>  
  
     <span data-ttu-id="1b347-130">![词汇定义](../core/media/3db84492-d6b8-4059-9d2c-a720ccc207b6.gif "3db84492-d6b8-4059-9d2c-a720ccc207b6")</span><span class="sxs-lookup"><span data-stu-id="1b347-130">![Vocabulary Definitions](../core/media/3db84492-d6b8-4059-9d2c-a720ccc207b6.gif "3db84492-d6b8-4059-9d2c-a720ccc207b6")</span></span>  
<span data-ttu-id="1b347-131">带有格式字符串的值的范围</span><span class="sxs-lookup"><span data-stu-id="1b347-131">Range of values with formatted string</span></span>  
  
### <a name="to-define-a-vocabulary-definition-as-a-set-of-values"></a><span data-ttu-id="1b347-132">将词汇定义定义为值的集合</span><span class="sxs-lookup"><span data-stu-id="1b347-132">To define a vocabulary definition as a set of values</span></span>  
  
1.  <span data-ttu-id="1b347-133">右击词汇版本，然后单击**添加新定义**。</span><span class="sxs-lookup"><span data-stu-id="1b347-133">Right-click the vocabulary version, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="1b347-134">在词汇定义向导中，选择**常量值、 值的范围或设置的值**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1b347-134">In the Vocabulary Definition Wizard, select **Constant Value, Range of Values, or Set of Values**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="1b347-135">编辑定义名称和定义说明。</span><span class="sxs-lookup"><span data-stu-id="1b347-135">Edit the definition name and definition description.</span></span>  
  
4.  <span data-ttu-id="1b347-136">选择**设置的值**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1b347-136">Select **Set of Values**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="1b347-137">输入定义类型和显示名称。</span><span class="sxs-lookup"><span data-stu-id="1b347-137">Enter the definition type and display name.</span></span>  
  
6.  <span data-ttu-id="1b347-138">若要将成员添加到组中，选择**使用常量值**并输入一个常量值，或选择**发布的词汇中使用定义**并浏览到词汇定义，，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="1b347-138">To add a member to the set, select **Use Constant Value** and enter a constant value, or select **Use Definition from a Published Vocabulary** and browse to a vocabulary definition, and then click **Add**.</span></span>  
  
7.  <span data-ttu-id="1b347-139">重复步骤 6，以便使用常数或词汇定义的任意组合，向集合添加所需数目的项。</span><span class="sxs-lookup"><span data-stu-id="1b347-139">Repeat step 6, with any combination of constants or vocabulary definitions, for as many items as you want to include in your set.</span></span>  
  
8.  <span data-ttu-id="1b347-140">若要移动的相对顺序的集内的成员，请选择它，然后单击**向上**或**下**。</span><span class="sxs-lookup"><span data-stu-id="1b347-140">To move a member within the relative order of the set, select it and then click **Up** or **Down**.</span></span>  
  
9. <span data-ttu-id="1b347-141">若要从集中删除成员，请选择它，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="1b347-141">To remove a member from the set, select it and then click **Remove**.</span></span>  
  
10. <span data-ttu-id="1b347-142">完成你的集后，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="1b347-142">When you have completed your set, click **Finish**.</span></span>  
  
     <span data-ttu-id="1b347-143">![词汇定义](../core/media/461d0d70-52ed-4f43-927d-3efb1fbfb934.gif "461d0d70-52ed-4f43-927d-3efb1fbfb934")</span><span class="sxs-lookup"><span data-stu-id="1b347-143">![Vocabulary Definitions](../core/media/461d0d70-52ed-4f43-927d-3efb1fbfb934.gif "461d0d70-52ed-4f43-927d-3efb1fbfb934")</span></span>  
<span data-ttu-id="1b347-144">值的集合</span><span class="sxs-lookup"><span data-stu-id="1b347-144">Set of values</span></span>  
  
### <a name="to-define-a-vocabulary-definition-as-a-net-class-or-class-member"></a><span data-ttu-id="1b347-145">将词汇定义定义为 .NET 类或类成员</span><span class="sxs-lookup"><span data-stu-id="1b347-145">To define a vocabulary definition as a .NET class or class member</span></span>  
  
1.  <span data-ttu-id="1b347-146">右击词汇版本，然后单击**添加新定义**。</span><span class="sxs-lookup"><span data-stu-id="1b347-146">Right-click the vocabulary version, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="1b347-147">在词汇定义向导中，选择 **.NET 类或类成员**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1b347-147">In the Vocabulary Definition Wizard, select **.NET Class or Class Member**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="1b347-148">编辑**定义名称**和**说明**字段。</span><span class="sxs-lookup"><span data-stu-id="1b347-148">Edit the **Definition Name** and **Description** fields.</span></span>  
  
4.  <span data-ttu-id="1b347-149">单击 **“浏览”**。</span><span class="sxs-lookup"><span data-stu-id="1b347-149">Click **Browse**.</span></span>  
  
5.  <span data-ttu-id="1b347-150">在 **.NET 程序集**对话框中，选择一个程序集，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1b347-150">In the **.NET Assemblies** dialog box, select an assembly, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b347-151">可用程序集必须位于全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="1b347-151">The assemblies have to be in the global assembly cache (GAC).</span></span> <span data-ttu-id="1b347-152">业务规则编辑器加载.NET 程序集的.NET 程序集在浏览时**事实数据资源管理器**窗口中或在 **.NET 类或类成员定义**页**词汇定义**窗口。</span><span class="sxs-lookup"><span data-stu-id="1b347-152">The business rule composer loads a .NET assembly when you browse for the .NET assembly in the **Facts Explorer** window or in the **.NET Class or Class Member Definition** page of the **Vocabulary Definition** window.</span></span>  <span data-ttu-id="1b347-153">如果您在 GAC 中更新该程序集，则关闭业务规则编辑器然后重新启动它，以便加载已更新的 .NET 程序集。</span><span class="sxs-lookup"><span data-stu-id="1b347-153">If you update the assembly in the GAC, close the business rule composer and restart it to load the updated .NET assembly.</span></span> <span data-ttu-id="1b347-154">业务规则编辑器并不自动刷新该程序集。</span><span class="sxs-lookup"><span data-stu-id="1b347-154">The business rule composer does not refresh the assembly automatically.</span></span>  
  
6.  <span data-ttu-id="1b347-155">展开该程序集节点。</span><span class="sxs-lookup"><span data-stu-id="1b347-155">Expand the assembly node.</span></span>  
  
7.  <span data-ttu-id="1b347-156">选择类，或展开某个类，并选择一个类成员，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1b347-156">Select a class, or expand a class and select a class member, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="1b347-157">单击**下一步**，并指定显示名称。</span><span class="sxs-lookup"><span data-stu-id="1b347-157">Click **Next**, and specify the display name.</span></span>  
  
     <span data-ttu-id="1b347-158">有关详细信息，请参阅本主题中后面部分的“使用参数指定词汇定义的显示格式”。</span><span class="sxs-lookup"><span data-stu-id="1b347-158">For more information, see "To specify the display format of a vocabulary definition by using parameters" later in this topic.</span></span>  
  
9. <span data-ttu-id="1b347-159">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="1b347-159">Click **Finish**.</span></span>  
  
     <span data-ttu-id="1b347-160">![词汇定义](../core/media/4259101f-26dd-488f-81c0-f8d225e4016e.gif "4259101f-26dd-488f-81c0-f8d225e4016e")</span><span class="sxs-lookup"><span data-stu-id="1b347-160">![Vocabulary Definitions](../core/media/4259101f-26dd-488f-81c0-f8d225e4016e.gif "4259101f-26dd-488f-81c0-f8d225e4016e")</span></span>  
<span data-ttu-id="1b347-161">Net 对象词汇定义</span><span class="sxs-lookup"><span data-stu-id="1b347-161">Net object vocabulary definition</span></span>  
  
### <a name="to-define-a-vocabulary-definition-as-an-xml-document-element-or-attribute"></a><span data-ttu-id="1b347-162">将词汇定义定义为 XML 文档元素或属性</span><span class="sxs-lookup"><span data-stu-id="1b347-162">To define a vocabulary definition as an XML document element or attribute</span></span>  
  
1.  <span data-ttu-id="1b347-163">右击词汇版本，然后单击**添加新定义**。</span><span class="sxs-lookup"><span data-stu-id="1b347-163">Right-click the vocabulary version, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="1b347-164">在词汇定义向导中，选择**XML 文档元素或属性**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1b347-164">In the Vocabulary Definition Wizard, select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="1b347-165">键入定义名称和定义说明。</span><span class="sxs-lookup"><span data-stu-id="1b347-165">Type a definition name and a definition description.</span></span>  
  
4.  <span data-ttu-id="1b347-166">单击**浏览**以查找架构文件并指定文档元素或属性。</span><span class="sxs-lookup"><span data-stu-id="1b347-166">Click **Browse** to locate a schema file and specify a document element or attribute.</span></span>  
  
5.  <span data-ttu-id="1b347-167">从下拉列表中，选择一个与架构中元素或属性的类型相兼容的类型。</span><span class="sxs-lookup"><span data-stu-id="1b347-167">From the drop-down list, select a type that is compatible with the type of the element or attribute in the schema.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b347-168">如果在指定的类型和文档元素或属性的类型之间无法实现有效的转换，则会在运行时出现错误。</span><span class="sxs-lookup"><span data-stu-id="1b347-168">If a valid cast cannot be done to or from the specified type to the type of the document element or attribute, you will get an error at run time.</span></span>  
  
6.  <span data-ttu-id="1b347-169">选择一种操作类型，以指示是要获取该元素或属性的值，还是要设置它的值。</span><span class="sxs-lookup"><span data-stu-id="1b347-169">Select an operation type to indicate whether you plan to get the value of the element or attribute, or to set its value.</span></span>  
  
7.  <span data-ttu-id="1b347-170">如果你选择的值设置，请单击**下一步**，然后指定的显示格式。</span><span class="sxs-lookup"><span data-stu-id="1b347-170">If you chose to set the value, click **Next**, and then specify the display format.</span></span>  
  
8.  <span data-ttu-id="1b347-171">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="1b347-171">Click **Finish**.</span></span>  
  
     <span data-ttu-id="1b347-172">![词汇定义](../core/media/fd81b534-ec41-4147-b716-1e10ffc01d6f.gif "fd81b534-ec41-4147-b716-1e10ffc01d6f")</span><span class="sxs-lookup"><span data-stu-id="1b347-172">![Vocabulary Definitions](../core/media/fd81b534-ec41-4147-b716-1e10ffc01d6f.gif "fd81b534-ec41-4147-b716-1e10ffc01d6f")</span></span>  
<span data-ttu-id="1b347-173">XML 词汇定义</span><span class="sxs-lookup"><span data-stu-id="1b347-173">XML vocabulary definition</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b347-174">系统从不验证所定义元素和文档类型是否存在。</span><span class="sxs-lookup"><span data-stu-id="1b347-174">The existence of the defined element and the document type is never validated.</span></span> <span data-ttu-id="1b347-175">如果所添加的文档中不存在该元素，则会出现运行时错误。</span><span class="sxs-lookup"><span data-stu-id="1b347-175">If the asserted document does not have the element, you will get a runtime error.</span></span> <span data-ttu-id="1b347-176">如果添加未知类型的文档，则只会将其忽略。</span><span class="sxs-lookup"><span data-stu-id="1b347-176">If you assert a document with unknown document type, it will simply be ignored.</span></span>  
  
#### <a name="to-define-a-vocabulary-definition-as-a-database-table-or-database-table-column"></a><span data-ttu-id="1b347-177">将词汇定义定义为数据库表或数据库表列</span><span class="sxs-lookup"><span data-stu-id="1b347-177">To define a vocabulary definition as a database table or database table column</span></span>  
  
1.  <span data-ttu-id="1b347-178">右击词汇版本，然后单击**添加新定义**。</span><span class="sxs-lookup"><span data-stu-id="1b347-178">Right-click the vocabulary version and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="1b347-179">在词汇定义向导中，选择**数据库表或数据库表列定义**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1b347-179">In the Vocabulary Definition Wizard, select **Database Table or Database Table Column Definition**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="1b347-180">键入定义名称和定义说明。</span><span class="sxs-lookup"><span data-stu-id="1b347-180">Type a definition name and definition description.</span></span>  
  
4.  <span data-ttu-id="1b347-181">单击 **“浏览”**。</span><span class="sxs-lookup"><span data-stu-id="1b347-181">Click **Browse**.</span></span>  
  
5.  <span data-ttu-id="1b347-182">选择要连接的 SQL Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="1b347-182">Select a SQL Server computer to connect with.</span></span> <span data-ttu-id="1b347-183">如果当前未启动 SQL Server 计算机，选择**启动 SQL Server 如果已停止**复选框。</span><span class="sxs-lookup"><span data-stu-id="1b347-183">If the SQL Server computer is not currently started, select the **Start SQL Server if it is stopped** check box.</span></span>  
  
6.  <span data-ttu-id="1b347-184">选择身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="1b347-184">Select an authentication type.</span></span> <span data-ttu-id="1b347-185">如果选择 SQL Server 身份验证，键入你的登录名和密码，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1b347-185">If you select SQL Server authentication, type your logon name and password, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="1b347-186">选择的表或你想要将绑定到，然后单击的表列**确定**。</span><span class="sxs-lookup"><span data-stu-id="1b347-186">Select the table or table column that you want to bind to, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="1b347-187">如果选择了表列，请选择是要获取它的值还是设置它的值。</span><span class="sxs-lookup"><span data-stu-id="1b347-187">If you selected a table column, select whether you want to get its value or set its value.</span></span> <span data-ttu-id="1b347-188">如果选择获取它的值，请键入显示名称。</span><span class="sxs-lookup"><span data-stu-id="1b347-188">If you choose to get its value, type the display name.</span></span> <span data-ttu-id="1b347-189">如果你选择将其值设置，请单击**下一步**若要指定显示格式。</span><span class="sxs-lookup"><span data-stu-id="1b347-189">If you choose to set its value, click **Next** to specify the display format.</span></span>  
  
     <span data-ttu-id="1b347-190">有关详细信息，请参阅本主题中后面部分的“使用参数指定词汇定义的显示格式”。</span><span class="sxs-lookup"><span data-stu-id="1b347-190">For more information, see "To specify the display format of a vocabulary definition by using parameters" later in this topic.</span></span>  
  
9. <span data-ttu-id="1b347-191">如果选择了表，请键入显示名称。</span><span class="sxs-lookup"><span data-stu-id="1b347-191">If you selected a table, type a display name.</span></span>  
  
10. <span data-ttu-id="1b347-192">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="1b347-192">Click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b347-193">默认情况下，**该组**使用绑定</span><span class="sxs-lookup"><span data-stu-id="1b347-193">By default, **DataConnection** binding is used</span></span>  
  
     <span data-ttu-id="1b347-194">![词汇定义](../core/media/f8121306-cd73-4997-adc4-71a055dfd824.gif "f8121306-cd73-4997-adc4-71a055dfd824")</span><span class="sxs-lookup"><span data-stu-id="1b347-194">![Vocabulary Definitions](../core/media/f8121306-cd73-4997-adc4-71a055dfd824.gif "f8121306-cd73-4997-adc4-71a055dfd824")</span></span>  
<span data-ttu-id="1b347-195">数据库词汇定义</span><span class="sxs-lookup"><span data-stu-id="1b347-195">Database vocabulary definition</span></span>  
  
#### <a name="to-specify-the-display-format-of-a-vocabulary-definition-by-using-parameters"></a><span data-ttu-id="1b347-196">使用参数指定词汇定义的显示格式</span><span class="sxs-lookup"><span data-stu-id="1b347-196">To specify the display format of a vocabulary definition by using parameters</span></span>  
  
1.  <span data-ttu-id="1b347-197">从列表中选择一个参数**参数**在词汇定义向导，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="1b347-197">Select a parameter from the list of **Parameters** in Vocabulary Definition Wizard, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="1b347-198">选择**使用常量值**并输入一个常量值，或选择**发布的词汇中使用定义**并浏览到词汇定义，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1b347-198">Select **Use Constant Value** and enter a constant value, or select **Use Definition from a Published Vocabulary** and browse to a vocabulary definition, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="1b347-199">键入的显示格式字符串或单击**默认**以还原到默认的显示格式字符串，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="1b347-199">Type the display format string or click **Default** to revert to the default display format string, and then click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b347-200">格式字符串应包括在大括号中的参数索引 — 例如，"{0}"和"{1}"—to 用作占位符的参数的不同而不同。</span><span class="sxs-lookup"><span data-stu-id="1b347-200">Your format string should include parameter indexes in curly braces—for example, "{0}" and "{1}"—to serve as placeholders for the parameters.</span></span>  
  
     <span data-ttu-id="1b347-201">![词汇定义](../core/media/822f78f4-278a-4211-83ad-44032fa81f13.gif "822f78f4-278a-4211-83ad-44032fa81f13")</span><span class="sxs-lookup"><span data-stu-id="1b347-201">![Vocabulary Definitions](../core/media/822f78f4-278a-4211-83ad-44032fa81f13.gif "822f78f4-278a-4211-83ad-44032fa81f13")</span></span>  
<span data-ttu-id="1b347-202">带有参数的词汇定义</span><span class="sxs-lookup"><span data-stu-id="1b347-202">Vocabulary definition with parameters</span></span>