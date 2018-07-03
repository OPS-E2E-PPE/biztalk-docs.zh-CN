---
title: 如何将数据复制到消息上下文为属性字段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fdfe475-d9b4-4cf9-898f-dbd7e719c27c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97c0440360a064eda7b6177967c2a48d992c1b9e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975878"
---
# <a name="how-to-copy-data-to-the-message-context-as-property-fields"></a><span data-ttu-id="9ed65-102">如何将数据复制到消息上下文为属性字段</span><span class="sxs-lookup"><span data-stu-id="9ed65-102">How to Copy Data to the Message Context as Property Fields</span></span>
<span data-ttu-id="9ed65-103">您可以将升级属性作为**属性字段**方法与将属性升级为大致相同**可分辨字段**，并且还可以使用**快速升级**功能设为简化过程。</span><span class="sxs-lookup"><span data-stu-id="9ed65-103">You can promote a property as a **Property Field** in much the same way as promoting a property as a **Distinguished Field**, and you can also use the **Quick Promotion** feature to streamline the process.</span></span>  
  
 <span data-ttu-id="9ed65-104">您可以选择**属性字段**通过升级**可分辨字段**出于以下原因升级：</span><span class="sxs-lookup"><span data-stu-id="9ed65-104">You might choose **Property Field** promotion over **Distinguished Field** promotion for the following reasons:</span></span>  
  
- <span data-ttu-id="9ed65-105">想要提升的值是小于 255 个字符限制，适用范围**属性字段**。</span><span class="sxs-lookup"><span data-stu-id="9ed65-105">The values you want to promote are shorter than the 255 character limitation that applies to **Property Fields**.</span></span>  
  
- <span data-ttu-id="9ed65-106">需要可以在业务流程之外访问升级的值，例如在管道或端口中。</span><span class="sxs-lookup"><span data-stu-id="9ed65-106">You need the values that you promote to be accessible outside of orchestrations, such as within pipelines or ports.</span></span>  
  
  <span data-ttu-id="9ed65-107">本主题提供有关将属性升级为的分步说明**属性字段**在这两种方式。</span><span class="sxs-lookup"><span data-stu-id="9ed65-107">This topic provides step-by-step instructions for promoting a property as a **Property Field** in both of these ways.</span></span>  
  
### <a name="to-promote-a-property-as-a-property-field-using-the-promote-properties-dialog-box"></a><span data-ttu-id="9ed65-108">使用“升级属性”对话框将属性升级为属性字段</span><span class="sxs-lookup"><span data-stu-id="9ed65-108">To promote a property as a Property Field using the Promote Properties dialog box</span></span>  
  
1.  <span data-ttu-id="9ed65-109">如果需要，创建相应的属性架构，以便将属性升级到该架构中。</span><span class="sxs-lookup"><span data-stu-id="9ed65-109">If necessary, create an appropriate property schema into which you will promote a property.</span></span> <span data-ttu-id="9ed65-110">创建属性架构的分步说明，请参阅[创建属性架构](../core/how-to-create-property-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="9ed65-110">For step-by-step instructions for creating property schemas, see [Creating Property Schemas](../core/how-to-create-property-schemas.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9ed65-111">此步骤可能不需要如果您已经创建属性架构并插入适当**Field 元素**为的子节点的节点**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="9ed65-111">This step might not be necessary if you have already created a property schema and inserted the appropriate **Field Element** nodes as child nodes of the **Schema** node.</span></span>  
  
2.  <span data-ttu-id="9ed65-112">在 BizTalk 编辑器中，打开你想要升级一个或多个属性的架构，然后选择 （第一个） **Field 元素**， **Field 特性**，或**记录**节点你想要将提升为**属性字段**。</span><span class="sxs-lookup"><span data-stu-id="9ed65-112">In BizTalk Editor, open the schema for which you want to promote one or more properties, and then select the (first) **Field Element**, **Field Attribute**, or **Record** node that you want to promote as a **Property Field**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9ed65-113">仅可以升级**记录**节点，如果它们已配置为仅包含简单内容通过让其**内容类型**属性设置为**SimpleContent**。</span><span class="sxs-lookup"><span data-stu-id="9ed65-113">You can only promote **Record** nodes if they are configured to contain only simple content by having its **Content Type** property set to **SimpleContent**.</span></span>  
  
3.  <span data-ttu-id="9ed65-114">右键单击所选的节点，单击**Promote**，然后单击**显示升级**。</span><span class="sxs-lookup"><span data-stu-id="9ed65-114">Right-click the selected node, click **Promote**, and then click **Show Promotions**.</span></span>  
  
     <span data-ttu-id="9ed65-115">**升级属性**对话框将打开与所选的节点显示为对话框的左侧的架构树中已选中。</span><span class="sxs-lookup"><span data-stu-id="9ed65-115">The **Promote Properties** dialog box opens with the selected node showing as selected in the schema tree on the left side of the dialog box.</span></span>  
  
4.  <span data-ttu-id="9ed65-116">在中**升级属性**对话框中，选择**属性字段**选项卡。</span><span class="sxs-lookup"><span data-stu-id="9ed65-116">In the **Promote Properties** dialog box, select the **Property Fields** tab.</span></span>  
  
5.  <span data-ttu-id="9ed65-117">确认你想要将属性升级到其中的属性架构中存在**属性架构列表**属性字段选项卡中。如果存在，请跳到步骤 8。</span><span class="sxs-lookup"><span data-stu-id="9ed65-117">Confirm that the property schema into which you want to promote a property is present in the **Property Schemas List** in the Property Fields tab. If it is present, skip to step 8.</span></span>  
  
6.  <span data-ttu-id="9ed65-118">在中**属性架构列表**部分中，单击**文件夹**图标。</span><span class="sxs-lookup"><span data-stu-id="9ed65-118">In the **Property Schemas List** section, click the **Folder** icon.</span></span> <span data-ttu-id="9ed65-119">**BizTalk 类型选取器**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="9ed65-119">The **BizTalk Type Picker** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="9ed65-120">在中**BizTalk 类型选取器**对话框框中，导航到相应的属性架构 （即您可能已在步骤 1 中创建的），选择该架构，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9ed65-120">In the **BizTalk Type Picker** dialog box, navigate to the appropriate property schema (that you may have created in step 1), select that schema, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9ed65-121">（可选） 你可以通过更改在相应的字符串与属性架构关联的命名空间前缀**前缀**列字段。</span><span class="sxs-lookup"><span data-stu-id="9ed65-121">Optionally, you can change the namespace prefix associated with the property schema by changing the string in the appropriate **Prefix** column field.</span></span>  
  
8.  <span data-ttu-id="9ed65-122">与要升级在左侧和右侧的架构树中仍然处于选中状态的节点**升级属性**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="9ed65-122">With the node to be promoted still selected in the schema tree on the left side of the **Promote Properties** dialog box, click **Add**.</span></span>  
  
     <span data-ttu-id="9ed65-123">如果允许，选定的节点添加到末尾**属性字段列表**上**属性字段**选项卡。如果不允许，消息框将提供说明。</span><span class="sxs-lookup"><span data-stu-id="9ed65-123">If allowed, the selected node is added to the end of the **Property Fields List** on the **Property Fields** tab. If not allowed, a message box provides an explanation.</span></span> <span data-ttu-id="9ed65-124">如果不允许，**添加**按钮未启用。</span><span class="sxs-lookup"><span data-stu-id="9ed65-124">If not allowed, the **Add** button is not enabled.</span></span>  
  
9. <span data-ttu-id="9ed65-125">双击**属性**刚添加到行的列单元格**属性字段列表**，然后在下拉列表中，选择**属性架构**和对应**Field 元素**要在其中升级所选的节点的节点。</span><span class="sxs-lookup"><span data-stu-id="9ed65-125">Double-click **Property** column cell for the row you just added to the **Property Fields List**, and then in the drop-down list, select the **Property Schema** and corresponding **Field Element** node into which you want to promote the selected node.</span></span> <span data-ttu-id="9ed65-126">下拉列表值具有窗体 X:Y，其中 X 是属性架构中的命名空间前缀**属性架构列表**，，Y 是节点名称**Field 元素**该属性架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="9ed65-126">Drop-down list values have the form X:Y, where X is the namespace prefix of a property schema in the **Property Schemas List**, and Y is the node name of a **Field Element** node in that property schema.</span></span>  
  
     <span data-ttu-id="9ed65-127">下拉列表中的默认值是第一个属性架构 **（Field 元素）** 节点尚未升级，按字母顺序排列所有相关属性架构。</span><span class="sxs-lookup"><span data-stu-id="9ed65-127">The default value in the drop-down list is the first property schema **(Field Element)** node that has not yet been promoted, sorted alphabetically across all relevant property schemas.</span></span> <span data-ttu-id="9ed65-128">此节点一般不会是要将给定架构节点升级到的属性架构节点。</span><span class="sxs-lookup"><span data-stu-id="9ed65-128">This will rarely be the property schema node into which you intend to promote a given schema node.</span></span>  
  
10. <span data-ttu-id="9ed65-129">您可以选择升级的其他节点在架构树中的对话框中，单击左侧**添加**，然后执行每次选择后步骤 9。</span><span class="sxs-lookup"><span data-stu-id="9ed65-129">You can select additional nodes for promotion in the schema tree on the left side of the dialog box, clicking **Add** and then performing step 9 after each selection.</span></span>  
  
11. <span data-ttu-id="9ed65-130">完成后，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9ed65-130">When complete, click **OK**.</span></span>  
  
     <span data-ttu-id="9ed65-131">现已选定要升级的节点**属性字段**并关联与特定**Field 元素**属性架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="9ed65-131">The nodes that you selected to promote are now **Property Fields** and are associated with a particular **Field Element** node in a property schema.</span></span>  
  
### <a name="to-promote-a-property-as-a-property-field-using-the-quick-promotion-command"></a><span data-ttu-id="9ed65-132">使用“快速升级”命令将属性升级为属性字段</span><span class="sxs-lookup"><span data-stu-id="9ed65-132">To promote a property as a Property Field using the Quick Promotion command</span></span>  
  
1.  <span data-ttu-id="9ed65-133">在 BizTalk 编辑器中，打开你想要升级一个或多个属性的架构，然后选择 （第一个） **Field 元素**， **Field 特性**，或**记录**节点你想要将提升为**属性字段**。</span><span class="sxs-lookup"><span data-stu-id="9ed65-133">In BizTalk Editor, open the schema for which you want to promote one or more properties, and then select the (first) **Field Element**, **Field Attribute**, or **Record** node that you want to promote as a **Property Field**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9ed65-134">仅可以升级**记录**节点，如果它们已配置为仅包含简单内容通过让其**内容类型**属性设置为**SimpleContent**。</span><span class="sxs-lookup"><span data-stu-id="9ed65-134">You can only promote **Record** nodes if they are configured to contain only simple content by having its **Content Type** property set to **SimpleContent**.</span></span>  
  
2.  <span data-ttu-id="9ed65-135">右键单击所选的节点，单击**Promote**，然后单击**快速升级**。</span><span class="sxs-lookup"><span data-stu-id="9ed65-135">Right-click the selected node, click **Promote**, and then click **Quick Promotion**.</span></span>  
  
     <span data-ttu-id="9ed65-136">如果默认属性定义的架构，通过**默认属性架构名**上的属性**属性页**相关架构不存在，则必须单击**确定**在确认对话框中创建的默认属性架构并将其配置相应**字段元素**节点以允许属性升级。</span><span class="sxs-lookup"><span data-stu-id="9ed65-136">If the default property schema, as defined by the **Default Property Schema Name** property on the **Property Pages** for the relevant schema, does not exist, you must click **OK** in the confirmation dialog to create the default property schema and configure it with an appropriate **Field Element** node to accommodate your property promotion.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ed65-137">可以查看和管理使用升级的属性**快速升级**通过打开功能**升级属性**对话框中，然后单击**属性字段**选项卡。有关分步说明，用于打开**升级属性**对话框中，请参阅[打开升级属性对话框](../core/how-to-open-the-promote-properties-dialog-box.md)。</span><span class="sxs-lookup"><span data-stu-id="9ed65-137">You can view and manage properties promoted using the **Quick Promotions** feature by opening the **Promote Properties** dialog box and then clicking the **Property Fields** tab. For step-by-step instructions for opening the **Promote Properties** dialog box, see [Opening the Promote Properties Dialog Box](../core/how-to-open-the-promote-properties-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ed65-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ed65-138">See Also</span></span>  
 <span data-ttu-id="9ed65-139">[升级属性](../core/promoting-properties.md) </span><span class="sxs-lookup"><span data-stu-id="9ed65-139">[Promoting Properties](../core/promoting-properties.md) </span></span>  
 <span data-ttu-id="9ed65-140">[如何创建属性架构](../core/how-to-create-property-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="9ed65-140">[How to Create Property Schemas](../core/how-to-create-property-schemas.md) </span></span>  
 [<span data-ttu-id="9ed65-141">使用消息内容控制消息处理的方法</span><span class="sxs-lookup"><span data-stu-id="9ed65-141">Ways to Use Message Content to Control Message Processing</span></span>](../core/ways-to-use-message-content-to-control-message-processing.md)