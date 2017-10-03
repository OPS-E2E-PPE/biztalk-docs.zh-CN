---
title: "扩展枚举 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- enumeration values
- 2.X schemas, enumeration values
ms.assetid: 043def35-b644-4502-a2e2-cc1a5fc0328a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 527894b27c5720a1b006387f861922eb978069b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="extending-enumerations"></a><span data-ttu-id="51a05-102">扩展枚举</span><span class="sxs-lookup"><span data-stu-id="51a05-102">Extending Enumerations</span></span>
<span data-ttu-id="51a05-103">可以将值添加到 HL7 消息正文、 确认和消息正文架构中建立的许多字段、 线段和数据类型可接受的值的枚举。</span><span class="sxs-lookup"><span data-stu-id="51a05-103">You can add values to the enumerations that establish accepted values for many fields, segments, and data types in HL7 message body, acknowledgment, and message body schemas.</span></span> <span data-ttu-id="51a05-104">这涉及到的更改的值中的特定表中您正在工作的 HL7 版本的通用表值架构文件集 ( **Tablevalues_\<***版本***>.xsd**架构文件)。</span><span class="sxs-lookup"><span data-stu-id="51a05-104">This involves changing the set of values in a specific table in the common table values schema file for the HL7 version in which you are working (the **Tablevalues_\<***version***>.xsd** schema file).</span></span>  
  
 <span data-ttu-id="51a05-105">你将添加到枚举为消息标头架构不同的方式比你在其他架构中，如消息正文架构。</span><span class="sxs-lookup"><span data-stu-id="51a05-105">You add to the enumeration in a different way for the message header schema than you do in other schemas, such as the message body schema.</span></span> <span data-ttu-id="51a05-106">对于消息标头架构，则必须更改 MSH_25_GLO_DEF.xsd 文件中的表。</span><span class="sxs-lookup"><span data-stu-id="51a05-106">For the message header schema, you must change the table within the MSH_25_GLO_DEF.xsd file.</span></span> <span data-ttu-id="51a05-107">对于其他架构中，更改表值架构文件中的表 (tablevalues_\<版本 >.xsd)。</span><span class="sxs-lookup"><span data-stu-id="51a05-107">For other schemas, you change the table in the table values schema file (tablevalues_\<version>.xsd).</span></span>  
  
### <a name="to-add-an-enumeration-value-to-the-table-values-common-schema-file"></a><span data-ttu-id="51a05-108">若要将一个枚举值添加到表值常见架构文件</span><span class="sxs-lookup"><span data-stu-id="51a05-108">To add an enumeration value to the table values common schema file</span></span>  
  
1.  <span data-ttu-id="51a05-109">你首先需要确定包含你想要添加到枚举的表。</span><span class="sxs-lookup"><span data-stu-id="51a05-109">You first need to determine the table that contains the enumeration that you want to add to.</span></span> <span data-ttu-id="51a05-110">在解决方案资源管理器的[!INCLUDE[vs2012](../../includes/vs2012-md.md)]，打开包含你想要更改的元素的架构文件。</span><span class="sxs-lookup"><span data-stu-id="51a05-110">In Solution Explorer of [!INCLUDE[vs2012](../../includes/vs2012-md.md)], open the schema file that contains the element that you want to change.</span></span> <span data-ttu-id="51a05-111">在 BizTalk 资源管理器，单击你想要添加的值的字段元素。</span><span class="sxs-lookup"><span data-stu-id="51a05-111">In BizTalk Explorer, click the field element that you want to add a value for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51a05-112">当您更改表值常见架构文件中的一个枚举时，引用该枚举的所有对象会受到都影响。</span><span class="sxs-lookup"><span data-stu-id="51a05-112">When you change an enumeration in the table values common schema file, all objects that reference that enumeration are affected.</span></span>  
  
2.  <span data-ttu-id="51a05-113">在**属性**窗格中，记下的表中的名称**基数据类型**字段。</span><span class="sxs-lookup"><span data-stu-id="51a05-113">In the **Properties** pane, note the name of the table in the **Base Data Type** field.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51a05-114">如果没有任何表中列出**基数据类型**字段中，和**派生源**属性未设置为**Restricted**，则该字段不具有与之关联的枚举.</span><span class="sxs-lookup"><span data-stu-id="51a05-114">If there is no table listed in **Base Data Type** field, and the **Derived By** property is not set to **Restricted**, then the field does not have an enumeration associated with it.</span></span>  
  
3.  <span data-ttu-id="51a05-115">在解决方案资源管理器，打开**Tablevalues_\<***版本***>.xsd**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="51a05-115">In Solution Explorer, open the **Tablevalues_\<***version***>.xsd**, and then click **Open**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51a05-116">你必须为你想要更改的 HL7 架构的每个版本单独执行此过程。</span><span class="sxs-lookup"><span data-stu-id="51a05-116">You must perform this procedure separately for each version of the HL7 schema that you want to change.</span></span>  
  
4.  <span data-ttu-id="51a05-117">在 BizTalk 编辑器中，浏览到你想要更改，然后单击该节点将表的表。</span><span class="sxs-lookup"><span data-stu-id="51a05-117">In BizTalk Editor, browse to the table you want to change, and then click that table node.</span></span>  
  
5.  <span data-ttu-id="51a05-118">在属性窗口中，在**限制**部分中，单击**枚举**，然后单击省略号 （…） 按钮以打开枚举编辑器。</span><span class="sxs-lookup"><span data-stu-id="51a05-118">In the Properties window, in the **Restriction** section, click **Enumeration**, and then click the ellipsis (…) button to open the Enumeration Editor.</span></span>  
  
6.  <span data-ttu-id="51a05-119">在枚举编辑器中，添加到现有值列表的新值，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="51a05-119">In the Enumeration Editor, add the new value to the list of existing values, and then click **OK**.</span></span>  
  
### <a name="to-add-an-enumeration-value-to-a-message-header-schema"></a><span data-ttu-id="51a05-120">若要将一个枚举值添加到消息标头架构</span><span class="sxs-lookup"><span data-stu-id="51a05-120">To add an enumeration value to a message header schema</span></span>  
  
1.  <span data-ttu-id="51a05-121">在解决方案资源管理器，打开 MSH_25_GLO_DEF 架构，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="51a05-121">In Solution Explorer, open the MSH_25_GLO_DEF schema, and then click **Open**.</span></span>  
  
2.  <span data-ttu-id="51a05-122">右键单击**MSH**节点，指向**插入架构节点**，然后单击**子字段元素**。</span><span class="sxs-lookup"><span data-stu-id="51a05-122">Right-click the **MSH** node, point to **Insert Schema Node**, and then click **Child Field Element**.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="51a05-123">将某一字段节点添加到 MSH，调用**字段**。</span><span class="sxs-lookup"><span data-stu-id="51a05-123"> adds a field node to MSH, called **Field**.</span></span> <span data-ttu-id="51a05-124">单击**ENTER**。</span><span class="sxs-lookup"><span data-stu-id="51a05-124">Click **ENTER**.</span></span>  
  
3.  <span data-ttu-id="51a05-125">在**属性**窗口中，单击**数据类型**节点，然后从下拉列表中，选择你想要添加的枚举值的表。</span><span class="sxs-lookup"><span data-stu-id="51a05-125">In the **Properties** window, click the **Data Type** node, then from the drop-down list, select the table to which you want to add the enumeration value.</span></span>  
  
4.  <span data-ttu-id="51a05-126">在**属性**窗口，请在**限制**部分中，单击**枚举**，然后单击省略号 （…） 按钮以打开枚举编辑器。</span><span class="sxs-lookup"><span data-stu-id="51a05-126">In the **Properties** window, in the **Restriction** section, click **Enumeration**, and then click the ellipsis (…) button to open the Enumeration Editor.</span></span>  
  
5.  <span data-ttu-id="51a05-127">在枚举编辑器中，添加到现有值列表的新值，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="51a05-127">In the Enumeration Editor, add the new value to the list of existing values, and then click **OK**.</span></span>  
  
     <span data-ttu-id="51a05-128">当你将添加一个值到枚举为任何节点，比如**字段**节点，你将添加全局使用该表的所有对象的值。</span><span class="sxs-lookup"><span data-stu-id="51a05-128">When you add a value to the enumeration for any node, such as the **Field** node, you add that value globally for all objects that use that table.</span></span> <span data-ttu-id="51a05-129">因此，您现在可以删除**字段**节点和的值仍将存在的表。</span><span class="sxs-lookup"><span data-stu-id="51a05-129">As a result, you can now delete the **Field** node, and the value will still be present for the table.</span></span> <span data-ttu-id="51a05-130">可以通过在右窗格中的 BizTalk 编辑器，到表中，滚动，并验证你添加的值存在对此进行验证。</span><span class="sxs-lookup"><span data-stu-id="51a05-130">You can verify this by scrolling in the right pane of BizTalk Editor to the table, and verifying that the value that you added is present.</span></span>  
  
6.  <span data-ttu-id="51a05-131">右键单击**字段**节点在 BizTalk 编辑器中，单击**删除**，然后单击**是**。</span><span class="sxs-lookup"><span data-stu-id="51a05-131">Right-click the **Field** node in BizTalk Editor, click **Delete**, and then click **Yes**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51a05-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51a05-132">See Also</span></span>  
 <span data-ttu-id="51a05-133">[表值通用架构](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="51a05-133">[Table Values Common Schemas](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md) </span></span>  
 <span data-ttu-id="51a05-134">[扩展 HL7 2.X 架构具有 Z 对象](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="51a05-134">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="51a05-135">[创建声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span><span class="sxs-lookup"><span data-stu-id="51a05-135">[Creating Declared Z Segments](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span></span>  
 <span data-ttu-id="51a05-136">[在架构中创建自定义数据类型](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="51a05-136">[Creating Custom Data Types in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span></span>  
 <span data-ttu-id="51a05-137">[在架构中创建自定义的表](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="51a05-137">[Creating Custom Tables in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span></span>  
 [<span data-ttu-id="51a05-138">处理未声明的 Z 段</span><span class="sxs-lookup"><span data-stu-id="51a05-138">Handling Undeclared Z Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)