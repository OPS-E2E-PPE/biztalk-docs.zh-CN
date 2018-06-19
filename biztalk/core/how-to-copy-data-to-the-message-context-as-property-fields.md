---
title: 如何将数据复制到作为属性字段的消息上下文 |Microsoft 文档
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
ms.openlocfilehash: 18242f30f32974cc32ab5d39a4a9c63650f27ffa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249981"
---
# <a name="how-to-copy-data-to-the-message-context-as-property-fields"></a><span data-ttu-id="f0f09-102">如何将数据复制到作为属性字段的消息上下文</span><span class="sxs-lookup"><span data-stu-id="f0f09-102">How to Copy Data to the Message Context as Property Fields</span></span>
<span data-ttu-id="f0f09-103">你可以将提升属性作为**属性字段**方式与将提升属性作为得多相同**可分辨字段**，，也可以使用**快速升级**到功能优化过程。</span><span class="sxs-lookup"><span data-stu-id="f0f09-103">You can promote a property as a **Property Field** in much the same way as promoting a property as a **Distinguished Field**, and you can also use the **Quick Promotion** feature to streamline the process.</span></span>  
  
 <span data-ttu-id="f0f09-104">你可以选择**属性字段**通过升级**可分辨字段**出于以下原因升级：</span><span class="sxs-lookup"><span data-stu-id="f0f09-104">You might choose **Property Field** promotion over **Distinguished Field** promotion for the following reasons:</span></span>  
  
-   <span data-ttu-id="f0f09-105">想要提升的值是短于适用于的 255 个字符限制**属性字段**。</span><span class="sxs-lookup"><span data-stu-id="f0f09-105">The values you want to promote are shorter than the 255 character limitation that applies to **Property Fields**.</span></span>  
  
-   <span data-ttu-id="f0f09-106">需要可以在业务流程之外访问升级的值，例如在管道或端口中。</span><span class="sxs-lookup"><span data-stu-id="f0f09-106">You need the values that you promote to be accessible outside of orchestrations, such as within pipelines or ports.</span></span>  
  
 <span data-ttu-id="f0f09-107">本主题提供有关将提升为属性的分步说明**属性字段**在这两个通过以下方式。</span><span class="sxs-lookup"><span data-stu-id="f0f09-107">This topic provides step-by-step instructions for promoting a property as a **Property Field** in both of these ways.</span></span>  
  
### <a name="to-promote-a-property-as-a-property-field-using-the-promote-properties-dialog-box"></a><span data-ttu-id="f0f09-108">使用“升级属性”对话框将属性升级为属性字段</span><span class="sxs-lookup"><span data-stu-id="f0f09-108">To promote a property as a Property Field using the Promote Properties dialog box</span></span>  
  
1.  <span data-ttu-id="f0f09-109">如果需要，创建相应的属性架构，以便将属性升级到该架构中。</span><span class="sxs-lookup"><span data-stu-id="f0f09-109">If necessary, create an appropriate property schema into which you will promote a property.</span></span> <span data-ttu-id="f0f09-110">用于创建属性架构的分步说明，请参阅[创建属性架构](../core/how-to-create-property-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="f0f09-110">For step-by-step instructions for creating property schemas, see [Creating Property Schemas](../core/how-to-create-property-schemas.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f0f09-111">此步骤可能不是必要如果你已经创建属性架构并插入相应**Field 元素**作为的子节点的节点**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="f0f09-111">This step might not be necessary if you have already created a property schema and inserted the appropriate **Field Element** nodes as child nodes of the **Schema** node.</span></span>  
  
2.  <span data-ttu-id="f0f09-112">在 BizTalk 编辑器中，打开你想要升级一个或多个属性的架构，然后选择 （第一个） **Field 元素**，**字段特性**，或**记录**节点你想要将提升为**属性字段**。</span><span class="sxs-lookup"><span data-stu-id="f0f09-112">In BizTalk Editor, open the schema for which you want to promote one or more properties, and then select the (first) **Field Element**, **Field Attribute**, or **Record** node that you want to promote as a **Property Field**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f0f09-113">你可以仅将提升**记录**节点如果它们配置为简单内容仅包含通过让其**内容类型**属性设置为**SimpleContent**。</span><span class="sxs-lookup"><span data-stu-id="f0f09-113">You can only promote **Record** nodes if they are configured to contain only simple content by having its **Content Type** property set to **SimpleContent**.</span></span>  
  
3.  <span data-ttu-id="f0f09-114">右键单击所选的节点，单击**Promote**，然后单击**显示提升**。</span><span class="sxs-lookup"><span data-stu-id="f0f09-114">Right-click the selected node, click **Promote**, and then click **Show Promotions**.</span></span>  
  
     <span data-ttu-id="f0f09-115">**升级属性**对话框随即打开与所选的节点显示的所选对话框左侧的架构树中。</span><span class="sxs-lookup"><span data-stu-id="f0f09-115">The **Promote Properties** dialog box opens with the selected node showing as selected in the schema tree on the left side of the dialog box.</span></span>  
  
4.  <span data-ttu-id="f0f09-116">在**升级属性**对话框中，选择**属性字段**选项卡。</span><span class="sxs-lookup"><span data-stu-id="f0f09-116">In the **Promote Properties** dialog box, select the **Property Fields** tab.</span></span>  
  
5.  <span data-ttu-id="f0f09-117">确认要以升级属性的属性架构中存在**属性架构列表**属性字段选项卡中。如果存在，请跳到步骤 8。</span><span class="sxs-lookup"><span data-stu-id="f0f09-117">Confirm that the property schema into which you want to promote a property is present in the **Property Schemas List** in the Property Fields tab. If it is present, skip to step 8.</span></span>  
  
6.  <span data-ttu-id="f0f09-118">在**属性架构列表**部分中，单击**文件夹**图标。</span><span class="sxs-lookup"><span data-stu-id="f0f09-118">In the **Property Schemas List** section, click the **Folder** icon.</span></span> <span data-ttu-id="f0f09-119">**BizTalk 类型选取器**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="f0f09-119">The **BizTalk Type Picker** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="f0f09-120">在**BizTalk 类型选取器**对话框框中，导航到相应的属性架构 （即你可能已在步骤 1 中创建的），选择该架构，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f0f09-120">In the **BizTalk Type Picker** dialog box, navigate to the appropriate property schema (that you may have created in step 1), select that schema, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f0f09-121">（可选） 可以更改通过更改在相应的字符串属性架构与关联的命名空间前缀**前缀**列字段。</span><span class="sxs-lookup"><span data-stu-id="f0f09-121">Optionally, you can change the namespace prefix associated with the property schema by changing the string in the appropriate **Prefix** column field.</span></span>  
  
8.  <span data-ttu-id="f0f09-122">与节点可升级的左侧的架构树中仍选定**升级属性**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="f0f09-122">With the node to be promoted still selected in the schema tree on the left side of the **Promote Properties** dialog box, click **Add**.</span></span>  
  
     <span data-ttu-id="f0f09-123">如果允许，所选的节点添加到末尾**属性字段列表**上**属性字段**选项卡。如果不允许，消息框将提供说明。</span><span class="sxs-lookup"><span data-stu-id="f0f09-123">If allowed, the selected node is added to the end of the **Property Fields List** on the **Property Fields** tab. If not allowed, a message box provides an explanation.</span></span> <span data-ttu-id="f0f09-124">如果不允许，**添加**按钮未启用。</span><span class="sxs-lookup"><span data-stu-id="f0f09-124">If not allowed, the **Add** button is not enabled.</span></span>  
  
9. <span data-ttu-id="f0f09-125">双击**属性**刚刚添加到的行的列单元格**属性字段列表**，然后在下拉列表中，选择**属性架构**和对应**Field 元素**到想要提升所选的节点的节点。</span><span class="sxs-lookup"><span data-stu-id="f0f09-125">Double-click **Property** column cell for the row you just added to the **Property Fields List**, and then in the drop-down list, select the **Property Schema** and corresponding **Field Element** node into which you want to promote the selected node.</span></span> <span data-ttu-id="f0f09-126">下拉列表值具有窗体 X:Y，其中 X 是中的属性架构的命名空间前缀**属性架构列表**，Y 是节点名称和**Field 元素**该属性架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="f0f09-126">Drop-down list values have the form X:Y, where X is the namespace prefix of a property schema in the **Property Schemas List**, and Y is the node name of a **Field Element** node in that property schema.</span></span>  
  
     <span data-ttu-id="f0f09-127">下拉列表中的默认值是第一个属性架构 **（Field 元素）** 尚未升级，节点按字母顺序在所有相关属性架构。</span><span class="sxs-lookup"><span data-stu-id="f0f09-127">The default value in the drop-down list is the first property schema **(Field Element)** node that has not yet been promoted, sorted alphabetically across all relevant property schemas.</span></span> <span data-ttu-id="f0f09-128">此节点一般不会是要将给定架构节点升级到的属性架构节点。</span><span class="sxs-lookup"><span data-stu-id="f0f09-128">This will rarely be the property schema node into which you intend to promote a given schema node.</span></span>  
  
10. <span data-ttu-id="f0f09-129">你可以在对话框中，单击左侧架构树中选择更多节点升级**添加**和每个所选内容后再执行步骤 9。</span><span class="sxs-lookup"><span data-stu-id="f0f09-129">You can select additional nodes for promotion in the schema tree on the left side of the dialog box, clicking **Add** and then performing step 9 after each selection.</span></span>  
  
11. <span data-ttu-id="f0f09-130">完成后，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f0f09-130">When complete, click **OK**.</span></span>  
  
     <span data-ttu-id="f0f09-131">选择进行升级的节点现**属性字段**并关联与特定**Field 元素**属性架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="f0f09-131">The nodes that you selected to promote are now **Property Fields** and are associated with a particular **Field Element** node in a property schema.</span></span>  
  
### <a name="to-promote-a-property-as-a-property-field-using-the-quick-promotion-command"></a><span data-ttu-id="f0f09-132">使用“快速升级”命令将属性升级为属性字段</span><span class="sxs-lookup"><span data-stu-id="f0f09-132">To promote a property as a Property Field using the Quick Promotion command</span></span>  
  
1.  <span data-ttu-id="f0f09-133">在 BizTalk 编辑器中，打开你想要升级一个或多个属性的架构，然后选择 （第一个） **Field 元素**，**字段特性**，或**记录**节点你想要将提升为**属性字段**。</span><span class="sxs-lookup"><span data-stu-id="f0f09-133">In BizTalk Editor, open the schema for which you want to promote one or more properties, and then select the (first) **Field Element**, **Field Attribute**, or **Record** node that you want to promote as a **Property Field**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f0f09-134">你可以仅将提升**记录**节点如果它们配置为简单内容仅包含通过让其**内容类型**属性设置为**SimpleContent**。</span><span class="sxs-lookup"><span data-stu-id="f0f09-134">You can only promote **Record** nodes if they are configured to contain only simple content by having its **Content Type** property set to **SimpleContent**.</span></span>  
  
2.  <span data-ttu-id="f0f09-135">右键单击所选的节点，单击**Promote**，然后单击**快速升级**。</span><span class="sxs-lookup"><span data-stu-id="f0f09-135">Right-click the selected node, click **Promote**, and then click **Quick Promotion**.</span></span>  
  
     <span data-ttu-id="f0f09-136">如果默认属性定义的架构，通过**默认属性架构名称**属性**属性页**对于相关的架构，不存在，必须单击**确定**在确认对话框中创建的默认属性架构并将其配置与相应**Field 元素**节点以适应属性提升。</span><span class="sxs-lookup"><span data-stu-id="f0f09-136">If the default property schema, as defined by the **Default Property Schema Name** property on the **Property Pages** for the relevant schema, does not exist, you must click **OK** in the confirmation dialog to create the default property schema and configure it with an appropriate **Field Element** node to accommodate your property promotion.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0f09-137">你可以查看和管理使用升级属性**快速提升**功能通过打开**升级属性**对话框中，然后单击**属性字段**选项卡。有关分步说明打开**升级属性**对话框中，请参阅[打开提升的属性对话框中](../core/how-to-open-the-promote-properties-dialog-box.md)。</span><span class="sxs-lookup"><span data-stu-id="f0f09-137">You can view and manage properties promoted using the **Quick Promotions** feature by opening the **Promote Properties** dialog box and then clicking the **Property Fields** tab. For step-by-step instructions for opening the **Promote Properties** dialog box, see [Opening the Promote Properties Dialog Box](../core/how-to-open-the-promote-properties-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0f09-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0f09-138">See Also</span></span>  
 <span data-ttu-id="f0f09-139">[提升属性](../core/promoting-properties.md) </span><span class="sxs-lookup"><span data-stu-id="f0f09-139">[Promoting Properties](../core/promoting-properties.md) </span></span>  
 <span data-ttu-id="f0f09-140">[如何创建属性架构](../core/how-to-create-property-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="f0f09-140">[How to Create Property Schemas](../core/how-to-create-property-schemas.md) </span></span>  
 [<span data-ttu-id="f0f09-141">使用与控件消息处理的消息内容的方法</span><span class="sxs-lookup"><span data-stu-id="f0f09-141">Ways to Use Message Content to Control Message Processing</span></span>](../core/ways-to-use-message-content-to-control-message-processing.md)