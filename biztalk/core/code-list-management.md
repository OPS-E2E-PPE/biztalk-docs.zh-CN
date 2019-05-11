---
title: 代码列表管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a924c814-d077-4aea-bacb-bf2e8a3dee01
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77af1ee5495ebf82fe0451e37bc5887c7bf1015f
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530383"
---
# <a name="code-list-management"></a><span data-ttu-id="5d9b0-102">代码列表管理</span><span class="sxs-lookup"><span data-stu-id="5d9b0-102">Code List Management</span></span>

## <a name="overview"></a><span data-ttu-id="5d9b0-103">概述</span><span class="sxs-lookup"><span data-stu-id="5d9b0-103">Overview</span></span>
<span data-ttu-id="5d9b0-104">XSD 用于指定一组特定的有效元素或属性的值。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-104">You use XSD to specify a specific set of values that are valid for an element or attribute.</span></span> <span data-ttu-id="5d9b0-105">此功能，则可使用**枚举**元素。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-105">This functionality is available using the **enumeration** element.</span></span> <span data-ttu-id="5d9b0-106">派生的数据类型时**Field 元素**或**Field 特性**通过限制，则可以在属性之一的节点**限制**类别是**枚举**属性。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-106">When you derive a data type for a **Field Element** or **Field Attribute** node by restriction, one of the properties that becomes available to you in the **Restriction** category is the **Enumeration** property.</span></span> <span data-ttu-id="5d9b0-107">使用此属性，可以打开**枚举编辑器**对话框可以在其中输入应被视为有效的相应元素或属性在实例消息中的值。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-107">Using this property, you can open the **Enumeration Editor** dialog box in which you can enter the values that should be considered valid for the corresponding element or attribute in instance messages.</span></span>  

 <span data-ttu-id="5d9b0-108">Microsoft BizTalk Server 提供了一种替代更丰富的方式来管理架构，即代码列表中的枚举。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-108">Microsoft BizTalk Server provides an alternative, richer way to manage enumerations in your schemas, known as code lists.</span></span> <span data-ttu-id="5d9b0-109">代码列表使用 Microsoft Access 数据库来存储各种枚举，以便您可以更加集中的方式来管理它们的选项。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-109">Code lists use a Microsoft Access database to store the choices for your various enumerations, which allows you to manage them in a more centralized way.</span></span> <span data-ttu-id="5d9b0-110">此外，如果您需要使用的枚举值包含的非直观的数字代码，将需要以该形式输入**枚举**属性中，Access 数据库用于代码列表中创建的表功能包括这些数值的文字说明。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-110">Further, if the enumeration values you need to use consist of non-intuitive numeric codes, which would need to be entered in that form using the **Enumeration** property, the tables you create in an Access database to use with the code list functionality include textual descriptions of these numeric values.</span></span> <span data-ttu-id="5d9b0-111">在中使用文字说明**CodeList**对话框而不是其更模糊的等效数值。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-111">The textual descriptions are used in the **CodeList** dialog box rather than their more obscure numeric equivalents.</span></span>  

## <a name="use-the-code-list"></a><span data-ttu-id="5d9b0-112">使用代码列表</span><span class="sxs-lookup"><span data-stu-id="5d9b0-112">Use the code list</span></span>  
 <span data-ttu-id="5d9b0-113">必须执行几个不同的步骤来使用代码列表功能，包括：</span><span class="sxs-lookup"><span data-stu-id="5d9b0-113">You must perform several different steps to use the code list feature, including:</span></span>  

- <span data-ttu-id="5d9b0-114">必须使用适当命名的表中，使用所需的列，创建 Access 数据库和值填充该表。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-114">You must create an Access database with an appropriately named table, with the expected columns, and populate it with values.</span></span>  

  - <span data-ttu-id="5d9b0-115">表的名称是的组合**标准**并**标准版本**的属性**架构**节点，以下划线 (_) 字符分隔。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-115">The name of the table is a combination of the **Standard** and **Standard Version** properties of the **Schema** node, separated by an underscore (_) character.</span></span> <span data-ttu-id="5d9b0-116">例如，如果设置了**标准**的属性**架构**到 XML 节点和**标准版本**MyVersion1，通过指定的 Access 数据库的属性**代码列表数据库**属性必须具有名为 XML_MyVersion1 的表。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-116">For example, if you have set the **Standard** property of the **Schema** node to XML and the **Standard Version** property to MyVersion1, the Access database specified by the **CodeList Database** property must have a table named XML_MyVersion1.</span></span>  

    <span data-ttu-id="5d9b0-117">这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-117">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

  - <span data-ttu-id="5d9b0-118">此表必须具有三列，通常命名为代码、 值和 Desc。第一列标识与，其中每个此类行提供了一种可能对应于所选的数据允许在枚举选项相关的行**Field 元素**或**字段属性**节点。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-118">This table must have three columns, typically named Code, Value, and Desc. The first column identifies rows that are related to one another, where each such row provides one of the enumeration choices that may potentially be allowed for the data that corresponds to the selected **Field Element** or **Field Attribute** node.</span></span> <span data-ttu-id="5d9b0-119">第一列中的相同值的所有行都组成一个组。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-119">All rows with the same value in the first column form a group.</span></span> <span data-ttu-id="5d9b0-120">这些值通常是整数，但可以是任何不能包含空格的字符串。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-120">These values are typically integers, but can be any string that does not contain spaces.</span></span>  

     <span data-ttu-id="5d9b0-121">在表中的每一行的第二个和第三个列必须配置为分别包含相应的值和每个可能的枚举值的文本表示形式。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-121">The second and third columns of each row in the table must be configured to contain the corresponding value and textual representation of each possible enumeration value, respectively.</span></span>  

     <span data-ttu-id="5d9b0-122">例如，Access 数据库表以用于代码列表功能的以下表示形式包含两个集的三个相关的枚举值。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-122">For example, the following representation of an Access database table for use with the Code List feature contains two sets of three related enumeration values.</span></span> <span data-ttu-id="5d9b0-123">第一列中的特定值是任意的用于将相关的行相关联。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-123">The specific values in the first column are arbitrary and are used to associate related rows.</span></span>  


    | <span data-ttu-id="5d9b0-124">代码</span><span class="sxs-lookup"><span data-stu-id="5d9b0-124">Code</span></span> | <span data-ttu-id="5d9b0-125">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="5d9b0-125">Value</span></span> |  <span data-ttu-id="5d9b0-126">Desc</span><span class="sxs-lookup"><span data-stu-id="5d9b0-126">Desc</span></span>  |
    |------|-------|--------|
    |  <span data-ttu-id="5d9b0-127">1</span><span class="sxs-lookup"><span data-stu-id="5d9b0-127">1</span></span>   |  <span data-ttu-id="5d9b0-128">13</span><span class="sxs-lookup"><span data-stu-id="5d9b0-128">13</span></span>   |  <span data-ttu-id="5d9b0-129">Red</span><span class="sxs-lookup"><span data-stu-id="5d9b0-129">Red</span></span>   |
    |  <span data-ttu-id="5d9b0-130">1</span><span class="sxs-lookup"><span data-stu-id="5d9b0-130">1</span></span>   |  <span data-ttu-id="5d9b0-131">16</span><span class="sxs-lookup"><span data-stu-id="5d9b0-131">16</span></span>   | <span data-ttu-id="5d9b0-132">绿色</span><span class="sxs-lookup"><span data-stu-id="5d9b0-132">Green</span></span>  |
    |  <span data-ttu-id="5d9b0-133">1</span><span class="sxs-lookup"><span data-stu-id="5d9b0-133">1</span></span>   |  <span data-ttu-id="5d9b0-134">19</span><span class="sxs-lookup"><span data-stu-id="5d9b0-134">19</span></span>   |  <span data-ttu-id="5d9b0-135">蓝色</span><span class="sxs-lookup"><span data-stu-id="5d9b0-135">Blue</span></span>  |
    |  <span data-ttu-id="5d9b0-136">2</span><span class="sxs-lookup"><span data-stu-id="5d9b0-136">2</span></span>   |   <span data-ttu-id="5d9b0-137">1</span><span class="sxs-lookup"><span data-stu-id="5d9b0-137">1</span></span>   | <span data-ttu-id="5d9b0-138">小</span><span class="sxs-lookup"><span data-stu-id="5d9b0-138">Small</span></span>  |
    |  <span data-ttu-id="5d9b0-139">2</span><span class="sxs-lookup"><span data-stu-id="5d9b0-139">2</span></span>   |   <span data-ttu-id="5d9b0-140">2</span><span class="sxs-lookup"><span data-stu-id="5d9b0-140">2</span></span>   | <span data-ttu-id="5d9b0-141">Medium</span><span class="sxs-lookup"><span data-stu-id="5d9b0-141">Medium</span></span> |
    |  <span data-ttu-id="5d9b0-142">2</span><span class="sxs-lookup"><span data-stu-id="5d9b0-142">2</span></span>   |   <span data-ttu-id="5d9b0-143">3</span><span class="sxs-lookup"><span data-stu-id="5d9b0-143">3</span></span>   | <span data-ttu-id="5d9b0-144">大型</span><span class="sxs-lookup"><span data-stu-id="5d9b0-144">Large</span></span>  |


- <span data-ttu-id="5d9b0-145">必须正确配置的三个属性**架构**节点：</span><span class="sxs-lookup"><span data-stu-id="5d9b0-145">You must properly configure three properties of the **Schema** node:</span></span>  

  -   <span data-ttu-id="5d9b0-146">**代码列表数据库**属性必须设置为已创建的 Access 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-146">The **CodeList Database** property must be set to the name of the Access database you have created.</span></span>  

  -   <span data-ttu-id="5d9b0-147">**标准**并**标准版本**必须设置属性，以便当它们组合在一起的分隔开来将下划线 (_) 字符，它们构成中指定的相应表的名称访问数据库。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-147">The **Standard** and **Standard Version** properties must be set such that when they are combined with a separating underscore (_) character, they form the name of the appropriate table within the specified Access database.</span></span>  

- <span data-ttu-id="5d9b0-148">要实际做出选择特定的 Access 数据库中的值使用**字段元素**或**字段属性**节点，必须配置其两个属性：</span><span class="sxs-lookup"><span data-stu-id="5d9b0-148">To actually make use of the values in the Access database for a particular selected **Field Element** or **Field Attribute** node, you must configure two of its properties:</span></span>  

  -   <span data-ttu-id="5d9b0-149">必须设置其**Derived By**属性设置为**限制**。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-149">You must set its **Derived By** property to **Restriction**.</span></span> <span data-ttu-id="5d9b0-150">若要配置，您需要的其他属性**CodeList**，只有在执行此步骤后将不会启用。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-150">The other property you need to configure, **CodeList**, will not be enabled until you perform this step.</span></span>  

  -   <span data-ttu-id="5d9b0-151">必须键入值**CodeList**对应于第一列中值的属性 (**代码**列) 的一个或多个行中指定的 Access 数据库。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-151">You must type a value into the **CodeList** property that corresponds to the value in the first column (the **Code** column) of one or more rows in the specified Access database.</span></span> <span data-ttu-id="5d9b0-152">此操作将标识你想要具有对应于所选的枚举值的一套**Field 元素**或**字段属性**节点。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-152">This action identifies the set of enumeration values that you intend to have correspond to the selected **Field Element** or **Field Attribute** node.</span></span>  

       <span data-ttu-id="5d9b0-153">然后，您必须单击省略号 (**...**) 按钮位于右侧的**CodeList**属性值字段中，打开**代码列表**对话框。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-153">Then you must click the ellipsis (**...**) button located to the right of the **CodeList** property value field to open the **CodeList** dialog box.</span></span> <span data-ttu-id="5d9b0-154">在此对话框中，使用对应的复选框选择想要允许作为合法值对应于所选的实例消息数据的值**Field 元素**或**字段属性**节点。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-154">Using the check boxes in this dialog box, select the values that you want to allow as legal values for the instance message data that corresponds to the selected **Field Element** or **Field Attribute** node.</span></span> <span data-ttu-id="5d9b0-155">允许您选择的可用值的一个子集。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-155">You are allowed to select only a subset of the available values.</span></span> <span data-ttu-id="5d9b0-156">如果键入值 1，例如，就使用前面的表的示例中， **CodeList**属性，**代码列表**对话框将包含红色、 绿色和蓝色的选择。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-156">For example, using the preceding table example, if you type the value 1 into the **CodeList** property, the **CodeList** dialog box will contain the choices Red, Green, and Blue.</span></span> <span data-ttu-id="5d9b0-157">如果您选中红色和绿色的复选框，并没有为蓝色选中此复选框，只有前两种颜色将显示在 XSD 中为有效的值为所选**Field 元素**或**字段属性**节点。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-157">If you select the check boxes for Red and Green, and do not select the check box for Blue, only the former colors will appear in the XSD as valid values for the selected **Field Element** or **Field Attribute** node.</span></span>  

> [!NOTE]
>  <span data-ttu-id="5d9b0-158">**CodeList**并**代码列表数据库**属性只能在设计时使用和保存到 XSD 中的相应设置为**枚举**属性。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-158">The **CodeList** and **CodeList Database** properties are used at design time only and are persisted in the XSD as corresponding settings for the **Enumeration** property.</span></span> <span data-ttu-id="5d9b0-159">在运行时，所有值来都验证对**枚举**只属性。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-159">At run time, all values are verified against the **Enumeration** property only.</span></span>  

> [!CAUTION]
>  <span data-ttu-id="5d9b0-160">为给定**Field 元素**或**Field 特性**节点，不要同时使用**枚举**属性和**代码列表**属性。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-160">For a given **Field Element** or **Field Attribute** node, do not use both the **Enumeration** property and the **CodeList** property.</span></span> <span data-ttu-id="5d9b0-161">使用后一种属性可能会导致使用前一属性覆盖输入的值。</span><span class="sxs-lookup"><span data-stu-id="5d9b0-161">Using the latter property can result in values entered using the former property to be overwritten.</span></span>  

## <a name="see-also"></a><span data-ttu-id="5d9b0-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d9b0-162">See Also</span></span>  
 [<span data-ttu-id="5d9b0-163">创建架构时的注意事项</span><span class="sxs-lookup"><span data-stu-id="5d9b0-163">Considerations When Creating Schemas</span></span>](../core/considerations-when-creating-schemas.md)