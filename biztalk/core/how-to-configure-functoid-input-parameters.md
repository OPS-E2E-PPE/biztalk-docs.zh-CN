---
title: 如何配置 Functoid 输入参数 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bts10.mapper.functoid.inputs
ms.assetid: 2c8f773a-932c-423d-b3fe-724265304b0a
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab04111835e7732aa8384e1d701a15ae8d268378
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-functoid-input-parameters"></a><span data-ttu-id="cc9a0-102">如何配置 Functoid 输入参数</span><span class="sxs-lookup"><span data-stu-id="cc9a0-102">How to Configure Functoid Input Parameters</span></span>
<span data-ttu-id="cc9a0-103">正确配置映射中 functoid 的输入参数是使用 functoid 最重要的一个方面，也是最可能出错的一个环节。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-103">Properly configuring the input parameters to the functoids in your map is one of the most important, and potentially error-prone, aspects of using functoids.</span></span> <span data-ttu-id="cc9a0-104">可以配置 functoid 输入的参数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc9a0-104">You can configure the functoid input parameters as follows:</span></span>  
  
-   <span data-ttu-id="cc9a0-105">创建可见的输入的链接，通过连接架构节点和相应 functoid （拖放到 functoid 从架构节点鼠标）。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-105">Create visible input links by connecting schema nodes and respective functoids (drag-and-drop the mouse from schema node to the functoid).</span></span>  
  
-   <span data-ttu-id="cc9a0-106">直接编辑的使用的输入参数的列表**配置\<Functoid\> Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-106">Directly edit the list of input parameters using the **Configure \<Functoid\> Functoid** dialog box.</span></span>  
  
 <span data-ttu-id="cc9a0-107">本主题提供了使用这些方法配置 functoid 的输入参数的分步说明。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-107">This topic provides step-by-step instructions for configuring the input parameters for a functoid using these methods.</span></span>  
  
 <span data-ttu-id="cc9a0-108">用拖放方法建立 functoid 输入参数可以很方便地指定在源架构中使用 XPath 规范所涉及的输入参数。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-108">The dragging method of establishing functoid input parameters provides a convenient way to specify input parameters that involve XPath specifications into the source schema.</span></span> <span data-ttu-id="cc9a0-109">有关创建节点和 functoid 的输入的参数的架构的信息，请参阅[如何向地图添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-109">For information on creating a schema node and functoid input parameters, see [How to Add Basic Functoids to a Map](../core/how-to-add-basic-functoids-to-a-map.md).</span></span> <span data-ttu-id="cc9a0-110">但是，**配置\<Functoid\> Functoid**对话框是用于查看所有 functoid 的输入的参数、 创建和修改任何常量参数，和的权威机制重新排列在必要时输入参数的顺序。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-110">However, the **Configure \<Functoid\> Functoid** dialog box is the definitive mechanism for viewing all the input parameters to a functoid, for creating and modifying any constant parameters, and for re-arranging the order of the input parameters when necessary.</span></span>  
  
 <span data-ttu-id="cc9a0-111">当您直接在网格页上为 functoid 配置输入参数时（通过使用鼠标从源 schema 节点执行拖放操作并将该节点链接到 functoid 来绘制线条），如果输入数量达到最大值，则光标将更改为 NO 状态。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-111">When you configure the input parameters for a functoid directly on the grid page (by drawing lines, using the mouse drag-and-drop, from the source schema node and linking it to the functoid), if the number of inputs reaches maximum, the cursor changes to a NO state.</span></span> <span data-ttu-id="cc9a0-112">此外，状态栏将显示原因。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-112">Also, the status bar displays the reason.</span></span> <span data-ttu-id="cc9a0-113">下图显示仅接受一个输入链接的 functoid。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-113">The figure below shows a functoid which accepts only one input link.</span></span>  
  
 <span data-ttu-id="cc9a0-114">![用于配置 functoid 输入的参数没有状态](../core/media/configure-input-parameters-no-state.gif "Configure_input_parameters_NO_state")</span><span class="sxs-lookup"><span data-stu-id="cc9a0-114">![NO state for configuring functoid input parameter](../core/media/configure-input-parameters-no-state.gif "Configure_input_parameters_NO_state")</span></span>  
  
 <span data-ttu-id="cc9a0-115">你可以配置使用的脚本和表循环 functoid**配置\<Functoid\> Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-115">You can configure the Scripting and Table Looping functoids using the **Configure \<Functoid\> Functoid** dialog box.</span></span> <span data-ttu-id="cc9a0-116">有关如何配置 functoid 的信息，请参阅[如何配置脚本 Functoid](../core/how-to-configure-the-scripting-functoid.md)和[如何配置表循环和表提取程序 Functoid](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-116">For information about how to configure the functoids, see [How to Configure the Scripting Functoid](../core/how-to-configure-the-scripting-functoid.md) and [How to Configure the Table Looping and Table Extractor Functoids](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cc9a0-117">先决条件</span><span class="sxs-lookup"><span data-stu-id="cc9a0-117">Prerequisites</span></span>  
 <span data-ttu-id="cc9a0-118">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-118">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="what-is-an-input-parameter"></a><span data-ttu-id="cc9a0-119">什么是输入参数？</span><span class="sxs-lookup"><span data-stu-id="cc9a0-119">What is an input parameter?</span></span>  
 <span data-ttu-id="cc9a0-120">输入参数可以是以下任何形式：</span><span class="sxs-lookup"><span data-stu-id="cc9a0-120">An input parameter can be any of the following:</span></span>  
  
-   <span data-ttu-id="cc9a0-121">从源 schema 节点到 functoid 的链接</span><span class="sxs-lookup"><span data-stu-id="cc9a0-121">A link from source schema node to a functoid</span></span>  
  
-   <span data-ttu-id="cc9a0-122">从 functoid 到另一个有效 functoid 的链接</span><span class="sxs-lookup"><span data-stu-id="cc9a0-122">A link from functoid to another valid functoid</span></span>  
  
-   <span data-ttu-id="cc9a0-123">常量值</span><span class="sxs-lookup"><span data-stu-id="cc9a0-123">A constant value</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc9a0-124">如有几个 functoid**日期**，**时间**，**日期和时间**，和**Nil**，哪些不需要任何输入的参数。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-124">There are a few functoids, such as **Date**, **Time**, **Date and Time**, and **Nil**, which do not need any input parameters.</span></span>  
  
 <span data-ttu-id="cc9a0-125">下图显示了具有两个输入参数（Input[0] 和 Input[1]）和一个常数参数 (Input[2]) 的 functoid（以红色突出显示）。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-125">The figure below displays a functoid (highlighted in red) with two input parameters (Input[0] and Input[1]) and a constant parameter (Input[2]).</span></span>  
  
 <span data-ttu-id="cc9a0-126">![向 functoid 显示输入的参数](../core/media/identifying-input-parameters.gif "Identifying_input_parameters")</span><span class="sxs-lookup"><span data-stu-id="cc9a0-126">![Displaying the input parameters to a functoid](../core/media/identifying-input-parameters.gif "Identifying_input_parameters")</span></span>  
  
## <a name="to-open-the-configure-functoid-functoid-dialog-box"></a><span data-ttu-id="cc9a0-127">若要打开配置\<Functoid\> Functoid 对话框</span><span class="sxs-lookup"><span data-stu-id="cc9a0-127">To open the Configure \<Functoid\> Functoid dialog box</span></span>  
 <span data-ttu-id="cc9a0-128">你可以打开**配置\<Functoid\> Functoid**对话框中，通过以下方式之一：</span><span class="sxs-lookup"><span data-stu-id="cc9a0-128">You can open the **Configure \<Functoid\> Functoid** dialog box in one of the following ways:</span></span>  
  
-   <span data-ttu-id="cc9a0-129">在相关的网格页中，右键单击提取 functoid，，然后单击**配置 Functoid 输入**。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-129">In the relevant grid page, right-click the functoid, and then click **Configure Functoid Inputs**.</span></span>  
  
-   <span data-ttu-id="cc9a0-130">双击要为其配置输入参数的 functoid。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-130">Double-click the functoid for which you want to configure the input parameters.</span></span>  
  
-   <span data-ttu-id="cc9a0-131">选择提取 functoid，然后单击省略号 (**...**) 在 Visual Studio 的**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-131">Select the functoid and then click the ellipses (**…**) in the Visual Studio’s **Properties** window.</span></span>  
  
-   <span data-ttu-id="cc9a0-132">选择 functoid，然后按键盘上的 Enter。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-132">Select the functoid and then press ENTER from the keyboard.</span></span>  
  
-   <span data-ttu-id="cc9a0-133">选择 functoid，然后按键盘上的 Ctrl+M、Ctrl+I。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-133">Select the functoid and then press CTRL+M, CTRL+I from the keyboard.</span></span> <span data-ttu-id="cc9a0-134">映射器键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-134">For a list of Mapper shortcut keys, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
### <a name="to-insert-constant-input-parameters"></a><span data-ttu-id="cc9a0-135">插入常数输入参数</span><span class="sxs-lookup"><span data-stu-id="cc9a0-135">To insert constant input parameters</span></span>  
  
1.  <span data-ttu-id="cc9a0-136">在**配置\<Functoid\> Functoid**对话框中，选择**Functoid 输入**选项卡。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-136">In the **Configure \<Functoid\> Functoid** dialog box, select the **Functoid Inputs** tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cc9a0-137">**Functoid 输入**选项卡在默认情况下处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-137">The **Functoid Inputs** tab is selected by default.</span></span>  
  
2.  <span data-ttu-id="cc9a0-138">单击![将常量的输入的参数添加到 functoid](../core/media/add-input-parameters.gif "Add_input_parameters")按钮。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-138">Click the ![Adding constant input parameters to a functoid](../core/media/add-input-parameters.gif "Add_input_parameters") button.</span></span> <span data-ttu-id="cc9a0-139">将添加一个新行。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-139">A new row is added.</span></span>  
  
3.  <span data-ttu-id="cc9a0-140">键入新的输入参数的值，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-140">Type the value for the new input parameter, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cc9a0-141">如果添加按钮未启用，则说明该 functoid 不接受或不需要输入参数，或者已经具有允许的最大输入数。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-141">If the add button is not enabled, the functoid does not accept or require input parameters, or may already have the maximum number of allowed inputs.</span></span>  
  
### <a name="to-edit-existing-constant-input-parameters"></a><span data-ttu-id="cc9a0-142">编辑现有常数输入参数</span><span class="sxs-lookup"><span data-stu-id="cc9a0-142">To edit existing constant input parameters</span></span>  
  
1.  <span data-ttu-id="cc9a0-143">在**配置\<Functoid\> Functoid**对话框中，单击现有常量输入你想要编辑的参数。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-143">In the **Configure \<Functoid\> Functoid** dialog box, click the existing constant input parameter that you want to edit.</span></span> <span data-ttu-id="cc9a0-144">当前值已被选中。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-144">The current value is selected.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="cc9a0-145">只能编辑常数输入的参数。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-145">You can edit the parameters of constant inputs only.</span></span> <span data-ttu-id="cc9a0-146">不能编辑所有其他类型的输入参数。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-146">Input parameters of all other types cannot be edited.</span></span> <span data-ttu-id="cc9a0-147">只能重新排列或删除这些参数。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-147">They can only be rearranged or deleted.</span></span>  
  
2.  <span data-ttu-id="cc9a0-148">单击![编辑常量的输入的参数](../core/media/edit-input-parameters.gif "Edit_input_parameters")按钮。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-148">Click the ![Editing constant input parameters](../core/media/edit-input-parameters.gif "Edit_input_parameters") button.</span></span> <span data-ttu-id="cc9a0-149">常量的值中，进行适当的更改，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-149">Make the appropriate changes to the constant value, and then click **OK**.</span></span>  
  
     <span data-ttu-id="cc9a0-150">此外，还可以双击常数输入参数来对其进行编辑，或按键盘上的 F2。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-150">Alternatively, you can double-click the constant input parameter to edit it, or press F2 from the keyboard.</span></span>  
  
## <a name="to-select-multiple-input-parameters"></a><span data-ttu-id="cc9a0-151">选择多个输入参数</span><span class="sxs-lookup"><span data-stu-id="cc9a0-151">To select multiple input parameters</span></span>  
 <span data-ttu-id="cc9a0-152">通过按住 Ctrl 键并单击所需的行，可以选择多个输入参数，然后执行以下任何操作。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-152">You can select multiple input parameters by holding down the CTRL key and clicking the desired rows, and then perform any of the following operations.</span></span> <span data-ttu-id="cc9a0-153">您可以按键盘上的 Ctrl+A 选择所有行。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-153">You can press CTRL+A from the keyboard to select all the rows.</span></span>  
  
-   <span data-ttu-id="cc9a0-154">上移/下移所选内容。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-154">Move the selection up/down.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cc9a0-155">如果大容量选择包括最顶层或其他行中的最底部的行，则无法移动所选内容上移/下移分别。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-155">If the bulk selection includes either the top-most or the bottom-most row among the other rows, you cannot move the selection up/down respectively.</span></span>  
  
-   <span data-ttu-id="cc9a0-156">重新排列所选内容。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-156">Rearrange the selection.</span></span>  
  
-   <span data-ttu-id="cc9a0-157">删除所选内容。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-157">Delete the selection.</span></span>  
  
### <a name="to-change-the-order-of-existing-input-parameters"></a><span data-ttu-id="cc9a0-158">更改现有输入参数的顺序</span><span class="sxs-lookup"><span data-stu-id="cc9a0-158">To change the order of existing input parameters</span></span>  
  
1.  <span data-ttu-id="cc9a0-159">在**配置\<Functoid\> Functoid**对话框中，单击现有输入你想要将移动到的有序列表中的输入参数的不同位置的参数。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-159">In the **Configure \<Functoid\> Functoid** dialog box, click the existing input parameter that you want to move to a different position in the ordered list of input parameters.</span></span>  
  
2.  <span data-ttu-id="cc9a0-160">单击![在列表中向上移动](../core/media/move-up-button.gif "Move_up_button")按钮在参数列表中向上移动参数。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-160">Click the ![Move up in the list](../core/media/move-up-button.gif "Move_up_button") button to move the parameter up in the parameter list.</span></span> <span data-ttu-id="cc9a0-161">根据需要重复此步骤，直到所选输入参数位于期望位置。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-161">Repeat as necessary until the selected input parameter is in the desired position.</span></span> <span data-ttu-id="cc9a0-162">或者，你可以按向上箭头键从键盘。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-162">Alternatively, you can press the UP ARROW key from the keyboard.</span></span> <span data-ttu-id="cc9a0-163">映射器键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-163">For a list of Mapper shortcut keys, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
     <span data-ttu-id="cc9a0-164">-或者-</span><span class="sxs-lookup"><span data-stu-id="cc9a0-164">-OR-</span></span>  
  
     <span data-ttu-id="cc9a0-165">单击![列表中向下移动](../core/media/move-down-button.gif "Move_down_button")按钮以在参数列表中向下移动参数。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-165">Click the ![Moving down in a list](../core/media/move-down-button.gif "Move_down_button") button to move the parameter down in the parameter list.</span></span> <span data-ttu-id="cc9a0-166">根据需要重复此步骤，直到所选输入参数位于期望位置。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-166">Repeat as necessary until the selected input parameter is in the desired position.</span></span> <span data-ttu-id="cc9a0-167">此外，还可以按键盘上的向下键。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-167">Alternatively, you can press the DOWN ARROW key from the keyboard.</span></span> <span data-ttu-id="cc9a0-168">映射器键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-168">For a list of Mapper shortcut keys, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="cc9a0-169">你可以重新排列的只能从输入序列**配置\<Functoid\> Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-169">You can rearrange the sequence of inputs only from the **Configure \<Functoid\> Functoid** dialog box.</span></span> <span data-ttu-id="cc9a0-170">如果你选择最顶层或最底部的行，![在列表中向上移动](../core/media/move-up-button.gif "Move_up_button")或![列表中向下移动](../core/media/move-down-button.gif "Move_down_button")按钮将处于禁用状态，分别。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-170">If you select the top-most or bottom-most row, the ![Move up in the list](../core/media/move-up-button.gif "Move_up_button") or ![Moving down in a list](../core/media/move-down-button.gif "Move_down_button") buttons would be disabled, respectively.</span></span>  
  
### <a name="to-delete-an-input-parameter-by-deleting-the-input-link"></a><span data-ttu-id="cc9a0-171">通过删除输入链接来删除输入参数</span><span class="sxs-lookup"><span data-stu-id="cc9a0-171">To delete an input parameter by deleting the input link</span></span>  
  
1.  <span data-ttu-id="cc9a0-172">在相关网格页中，单击与要删除的输入参数对应的输入链接。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-172">In the relevant grid page, click the input link corresponding to the input parameter you want to delete.</span></span>  
  
2.  <span data-ttu-id="cc9a0-173">上**编辑**菜单上，单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-173">On the **Edit** menu, click **Delete**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cc9a0-174">或者，可以按 DELETE 键，或右键单击相关的网格页中的链接，单击**删除**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-174">Alternatively, you can press the DELETE key, or right-click the link in the relevant grid page, and click **Delete** from the shortcut menu.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="cc9a0-175">将自行删除输入链接。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-175">The input link is deleted silently.</span></span> <span data-ttu-id="cc9a0-176">如果不确定，可以始终撤消删除。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-176">You can always undo delete if you are not sure about it.</span></span> <span data-ttu-id="cc9a0-177">有关撤消/重做操作的详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-177">For more information about undo/redo operations, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
### <a name="to-delete-existing-input-parameters-within-the-configure-functoid-functoid-dialog-box"></a><span data-ttu-id="cc9a0-178">若要删除现有输入的参数中配置\<Functoid\> Functoid 对话框</span><span class="sxs-lookup"><span data-stu-id="cc9a0-178">To delete existing input parameters within the Configure \<Functoid\> Functoid dialog box</span></span>  
  
1.  <span data-ttu-id="cc9a0-179">在**配置\<Functoid\> Functoid**对话框中，单击现有输入你想要删除的参数。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-179">In the **Configure \<Functoid\> Functoid** dialog box, click the existing input parameter that you want to delete.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cc9a0-180">您可以使用此方法删除任何输入参数，甚至是与输入链接相对应的输入参数。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-180">You can delete any input parameter using this technique, even those that correspond to an input link.</span></span>  
  
2.  <span data-ttu-id="cc9a0-181">单击![删除所选内容](../core/media/delete-button.gif "Delete_button")按钮。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-181">Click the ![Deleting the selection](../core/media/delete-button.gif "Delete_button") button.</span></span> <span data-ttu-id="cc9a0-182">将从参数列表中删除所选现有输入参数。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-182">The selected existing input parameter is deleted from the parameter list.</span></span> <span data-ttu-id="cc9a0-183">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-183">Click **OK**.</span></span>  
  
     <span data-ttu-id="cc9a0-184">或者，您可以选择要删除的行，然后按键盘上的 Delete 键。 </span><span class="sxs-lookup"><span data-stu-id="cc9a0-184">Alternatively, you can select the row you want to delete, and press the DELETE key from the keyboard.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="cc9a0-185">将自行删除输入参数。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-185">The input parameter is deleted silently.</span></span> <span data-ttu-id="cc9a0-186">如果不确定，可以始终撤消删除。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-186">You can always undo delete if you are not sure about it.</span></span> <span data-ttu-id="cc9a0-187">有关撤消/重做操作的详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-187">For more information about undo/redo operations, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cc9a0-188">如果参数列表中没有输入参数，则不启用删除按钮。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-188">The delete button is not enabled when there are no input parameters in the parameter list.</span></span>  
  
## <a name="to-set-labels-and-comments-for-functoids"></a><span data-ttu-id="cc9a0-189">为 functoid 设置标签和注释</span><span class="sxs-lookup"><span data-stu-id="cc9a0-189">To set labels and comments for functoids</span></span>  
 <span data-ttu-id="cc9a0-190">你可以设置标签和注释 functoid 使用**配置\<Functoid\> Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-190">You can set labels and comments for functoids using the **Configure \<Functoid\> Functoid** dialog box.</span></span>  
  
1.  <span data-ttu-id="cc9a0-191">在**配置\<Functoid\> Functoid**对话框中，单击**标签和注释**选项卡。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-191">In the **Configure \<Functoid\> Functoid** dialog box, click the **Label and Comments** tab.</span></span>  
  
2.  <span data-ttu-id="cc9a0-192">类型**标签**和**注释**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-192">Type the **Label** and **Comments**, and then click **OK**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="cc9a0-193">有关如何对标签和注释 functoid 和/或链接的详细信息，请参阅[如何标记链接](../core/how-to-label-a-link.md)和[如何标记和注释 Functoid](../core/how-to-label-and-comment-a-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="cc9a0-193">For more information about how to label and comment functoids and/or links, see [How to Label a Link](../core/how-to-label-a-link.md) and [How to Label and Comment a Functoid](../core/how-to-label-and-comment-a-functoid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc9a0-194">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc9a0-194">See Also</span></span>  
 [<span data-ttu-id="cc9a0-195">编辑 Functoid 属性和输入参数</span><span class="sxs-lookup"><span data-stu-id="cc9a0-195">Editing Functoid Properties and Input Parameters</span></span>](../core/editing-functoid-properties-and-input-parameters.md)