---
title: 如何配置 Functoid 输入参数 |Microsoft Docs
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
ms.openlocfilehash: 75c2d7997f76df6e1b4983a896d409a93c628872
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341511"
---
# <a name="how-to-configure-functoid-input-parameters"></a><span data-ttu-id="28e04-102">如何配置 Functoid 输入参数</span><span class="sxs-lookup"><span data-stu-id="28e04-102">How to Configure Functoid Input Parameters</span></span>
<span data-ttu-id="28e04-103">正确配置映射中 functoid 的输入的参数是使用 functoid 的最重要的是，和潜在易出错的方面之一。</span><span class="sxs-lookup"><span data-stu-id="28e04-103">Properly configuring the input parameters to the functoids in your map is one of the most important, and potentially error-prone, aspects of using functoids.</span></span> <span data-ttu-id="28e04-104">可以按如下所示配置 functoid 输入的参数：</span><span class="sxs-lookup"><span data-stu-id="28e04-104">You can configure the functoid input parameters as follows:</span></span>  
  
- <span data-ttu-id="28e04-105">创建通过连接 schema 节点及各自的 functoid （拖放到 functoid 鼠标从 schema 节点） 的可见输入的链接。</span><span class="sxs-lookup"><span data-stu-id="28e04-105">Create visible input links by connecting schema nodes and respective functoids (drag-and-drop the mouse from schema node to the functoid).</span></span>  
  
- <span data-ttu-id="28e04-106">直接编辑输入参数使用的列表**配置\<Functoid\> Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="28e04-106">Directly edit the list of input parameters using the **Configure \<Functoid\> Functoid** dialog box.</span></span>  
  
  <span data-ttu-id="28e04-107">本主题提供有关配置为使用这些方法的 functoid 的输入的参数的分步说明。</span><span class="sxs-lookup"><span data-stu-id="28e04-107">This topic provides step-by-step instructions for configuring the input parameters for a functoid using these methods.</span></span>  
  
  <span data-ttu-id="28e04-108">拖放方法建立 functoid 输入的参数提供了方便地指定在源架构中的 XPath 规范所涉及的输入的参数。</span><span class="sxs-lookup"><span data-stu-id="28e04-108">The dragging method of establishing functoid input parameters provides a convenient way to specify input parameters that involve XPath specifications into the source schema.</span></span> <span data-ttu-id="28e04-109">有关创建 schema 节点和 functoid 输入的参数的信息，请参阅[如何向映射添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)。</span><span class="sxs-lookup"><span data-stu-id="28e04-109">For information on creating a schema node and functoid input parameters, see [How to Add Basic Functoids to a Map](../core/how-to-add-basic-functoids-to-a-map.md).</span></span> <span data-ttu-id="28e04-110">但是，**配置\<Functoid\> Functoid**对话框是可靠的机制对于查看 functoid 的输入的参数，用于创建和修改任何常数参数，以及为重新排列输入参数在必要时的顺序。</span><span class="sxs-lookup"><span data-stu-id="28e04-110">However, the **Configure \<Functoid\> Functoid** dialog box is the definitive mechanism for viewing all the input parameters to a functoid, for creating and modifying any constant parameters, and for re-arranging the order of the input parameters when necessary.</span></span>  
  
  <span data-ttu-id="28e04-111">当你配置 functoid 的输入的参数直接在网格页上 （通过绘制线条、 使用鼠标拖放，来自源架构节点并将其链接到该 functoid），如果输入数量达到最大值，光标将更改为无状态。</span><span class="sxs-lookup"><span data-stu-id="28e04-111">When you configure the input parameters for a functoid directly on the grid page (by drawing lines, using the mouse drag-and-drop, from the source schema node and linking it to the functoid), if the number of inputs reaches maximum, the cursor changes to a NO state.</span></span> <span data-ttu-id="28e04-112">此外，状态栏显示的原因。</span><span class="sxs-lookup"><span data-stu-id="28e04-112">Also, the status bar displays the reason.</span></span> <span data-ttu-id="28e04-113">下图显示了 functoid 接受一个输入的链接。</span><span class="sxs-lookup"><span data-stu-id="28e04-113">The figure below shows a functoid which accepts only one input link.</span></span>  
  
  <span data-ttu-id="28e04-114">![用于配置 functoid 输入的参数没有状态](../core/media/configure-input-parameters-no-state.gif "Configure_input_parameters_NO_state")</span><span class="sxs-lookup"><span data-stu-id="28e04-114">![NO state for configuring functoid input parameter](../core/media/configure-input-parameters-no-state.gif "Configure_input_parameters_NO_state")</span></span>  
  
  <span data-ttu-id="28e04-115">你可以配置使用的脚本编写和表循环 functoid**配置\<Functoid\> Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="28e04-115">You can configure the Scripting and Table Looping functoids using the **Configure \<Functoid\> Functoid** dialog box.</span></span> <span data-ttu-id="28e04-116">有关如何配置 functoid 的信息，请参阅[如何配置脚本 Functoid](../core/how-to-configure-the-scripting-functoid.md)并[如何配置表循环和表提取程序 Functoid](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)。</span><span class="sxs-lookup"><span data-stu-id="28e04-116">For information about how to configure the functoids, see [How to Configure the Scripting Functoid](../core/how-to-configure-the-scripting-functoid.md) and [How to Configure the Table Looping and Table Extractor Functoids](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="28e04-117">先决条件</span><span class="sxs-lookup"><span data-stu-id="28e04-117">Prerequisites</span></span>  
 <span data-ttu-id="28e04-118">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="28e04-118">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="what-is-an-input-parameter"></a><span data-ttu-id="28e04-119">什么是输入的参数？</span><span class="sxs-lookup"><span data-stu-id="28e04-119">What is an input parameter?</span></span>  
 <span data-ttu-id="28e04-120">输入的参数可以是以下任一项：</span><span class="sxs-lookup"><span data-stu-id="28e04-120">An input parameter can be any of the following:</span></span>  
  
-   <span data-ttu-id="28e04-121">来自源架构节点到 functoid 的链接</span><span class="sxs-lookup"><span data-stu-id="28e04-121">A link from source schema node to a functoid</span></span>  
  
-   <span data-ttu-id="28e04-122">从 functoid 到另一个有效 functoid 的链接</span><span class="sxs-lookup"><span data-stu-id="28e04-122">A link from functoid to another valid functoid</span></span>  
  
-   <span data-ttu-id="28e04-123">常量值</span><span class="sxs-lookup"><span data-stu-id="28e04-123">A constant value</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28e04-124">有几个 functoid，如**日期**，**时间**，**日期和时间**，以及**Nil**，不需要任何输入的参数。</span><span class="sxs-lookup"><span data-stu-id="28e04-124">There are a few functoids, such as **Date**, **Time**, **Date and Time**, and **Nil**, which do not need any input parameters.</span></span>  
  
 <span data-ttu-id="28e04-125">下图显示了 functoid （以红色突出显示） 使用两个输入参数 （Input [0] 和 Input[1]) 和常数参数 （input[2]）。</span><span class="sxs-lookup"><span data-stu-id="28e04-125">The figure below displays a functoid (highlighted in red) with two input parameters (Input[0] and Input[1]) and a constant parameter (Input[2]).</span></span>  
  
 <span data-ttu-id="28e04-126">![显示 functoid 的输入的参数](../core/media/identifying-input-parameters.gif "Identifying_input_parameters")</span><span class="sxs-lookup"><span data-stu-id="28e04-126">![Displaying the input parameters to a functoid](../core/media/identifying-input-parameters.gif "Identifying_input_parameters")</span></span>  
  
## <a name="to-open-the-configure-functoid-functoid-dialog-box"></a><span data-ttu-id="28e04-127">若要打开配置\<Functoid\> Functoid 对话框</span><span class="sxs-lookup"><span data-stu-id="28e04-127">To open the Configure \<Functoid\> Functoid dialog box</span></span>  
 <span data-ttu-id="28e04-128">您可以打开**配置\<Functoid\> Functoid**对话框中的以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="28e04-128">You can open the **Configure \<Functoid\> Functoid** dialog box in one of the following ways:</span></span>  
  
-   <span data-ttu-id="28e04-129">在相关网格页中，右键单击 functoid，然后依次**配置 Functoid 输入**。</span><span class="sxs-lookup"><span data-stu-id="28e04-129">In the relevant grid page, right-click the functoid, and then click **Configure Functoid Inputs**.</span></span>  
  
-   <span data-ttu-id="28e04-130">双击你想要配置的输入的参数的 functoid。</span><span class="sxs-lookup"><span data-stu-id="28e04-130">Double-click the functoid for which you want to configure the input parameters.</span></span>  
  
-   <span data-ttu-id="28e04-131">选择 functoid，然后单击省略号 (**...**) 在 Visual Studio**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="28e04-131">Select the functoid and then click the ellipses (**…**) in the Visual Studio’s **Properties** window.</span></span>  
  
-   <span data-ttu-id="28e04-132">选择 functoid，然后按 ENTER 键盘。</span><span class="sxs-lookup"><span data-stu-id="28e04-132">Select the functoid and then press ENTER from the keyboard.</span></span>  
  
-   <span data-ttu-id="28e04-133">选择 functoid，然后按 CTRL + M、 CTRL + I 键盘。</span><span class="sxs-lookup"><span data-stu-id="28e04-133">Select the functoid and then press CTRL+M, CTRL+I from the keyboard.</span></span> <span data-ttu-id="28e04-134">有关映射器键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="28e04-134">For a list of Mapper shortcut keys, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
### <a name="to-insert-constant-input-parameters"></a><span data-ttu-id="28e04-135">插入常数输入的参数</span><span class="sxs-lookup"><span data-stu-id="28e04-135">To insert constant input parameters</span></span>  
  
1.  <span data-ttu-id="28e04-136">在中**配置\<Functoid\> Functoid**对话框中，选择**Functoid 输入**选项卡。</span><span class="sxs-lookup"><span data-stu-id="28e04-136">In the **Configure \<Functoid\> Functoid** dialog box, select the **Functoid Inputs** tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="28e04-137">**Functoid 输入**默认情况下选择选项卡。</span><span class="sxs-lookup"><span data-stu-id="28e04-137">The **Functoid Inputs** tab is selected by default.</span></span>  
  
2.  <span data-ttu-id="28e04-138">单击![将常数输入的参数添加到 functoid](../core/media/add-input-parameters.gif "Add_input_parameters")按钮。</span><span class="sxs-lookup"><span data-stu-id="28e04-138">Click the ![Adding constant input parameters to a functoid](../core/media/add-input-parameters.gif "Add_input_parameters") button.</span></span> <span data-ttu-id="28e04-139">将添加一个新行。</span><span class="sxs-lookup"><span data-stu-id="28e04-139">A new row is added.</span></span>  
  
3.  <span data-ttu-id="28e04-140">键入新的输入参数的值，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="28e04-140">Type the value for the new input parameter, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="28e04-141">如果未启用添加按钮，该 functoid 不接受或不需要输入的参数，或者可能已具有的最大数目允许输入。</span><span class="sxs-lookup"><span data-stu-id="28e04-141">If the add button is not enabled, the functoid does not accept or require input parameters, or may already have the maximum number of allowed inputs.</span></span>  
  
### <a name="to-edit-existing-constant-input-parameters"></a><span data-ttu-id="28e04-142">若要编辑现有常数输入的参数</span><span class="sxs-lookup"><span data-stu-id="28e04-142">To edit existing constant input parameters</span></span>  
  
1.  <span data-ttu-id="28e04-143">在中**配置\<Functoid\> Functoid**对话框中，单击现有常数输入你想要编辑的参数。</span><span class="sxs-lookup"><span data-stu-id="28e04-143">In the **Configure \<Functoid\> Functoid** dialog box, click the existing constant input parameter that you want to edit.</span></span> <span data-ttu-id="28e04-144">选择的当前值。</span><span class="sxs-lookup"><span data-stu-id="28e04-144">The current value is selected.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="28e04-145">可以编辑常数输入参数。</span><span class="sxs-lookup"><span data-stu-id="28e04-145">You can edit the parameters of constant inputs only.</span></span> <span data-ttu-id="28e04-146">不能编辑所有其他类型的输入的参数。</span><span class="sxs-lookup"><span data-stu-id="28e04-146">Input parameters of all other types cannot be edited.</span></span> <span data-ttu-id="28e04-147">它们只能重新排列或删除。</span><span class="sxs-lookup"><span data-stu-id="28e04-147">They can only be rearranged or deleted.</span></span>  
  
2.  <span data-ttu-id="28e04-148">单击![编辑常数输入的参数](../core/media/edit-input-parameters.gif "Edit_input_parameters")按钮。</span><span class="sxs-lookup"><span data-stu-id="28e04-148">Click the ![Editing constant input parameters](../core/media/edit-input-parameters.gif "Edit_input_parameters") button.</span></span> <span data-ttu-id="28e04-149">对常数值进行适当的更改，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="28e04-149">Make the appropriate changes to the constant value, and then click **OK**.</span></span>  
  
     <span data-ttu-id="28e04-150">或者，可以双击常数输入的参数进行编辑，或按键盘上 F2。</span><span class="sxs-lookup"><span data-stu-id="28e04-150">Alternatively, you can double-click the constant input parameter to edit it, or press F2 from the keyboard.</span></span>  
  
## <a name="to-select-multiple-input-parameters"></a><span data-ttu-id="28e04-151">若要选择多个输入的参数</span><span class="sxs-lookup"><span data-stu-id="28e04-151">To select multiple input parameters</span></span>  
 <span data-ttu-id="28e04-152">您可以通过按住 CTRL 键并单击所需的行，选择多个输入的参数，然后执行任何以下操作。</span><span class="sxs-lookup"><span data-stu-id="28e04-152">You can select multiple input parameters by holding down the CTRL key and clicking the desired rows, and then perform any of the following operations.</span></span> <span data-ttu-id="28e04-153">您可以从键盘来选择所有的行按 CTRL + A。</span><span class="sxs-lookup"><span data-stu-id="28e04-153">You can press CTRL+A from the keyboard to select all the rows.</span></span>  
  
-   <span data-ttu-id="28e04-154">将选择向上/向下的移动。</span><span class="sxs-lookup"><span data-stu-id="28e04-154">Move the selection up/down.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="28e04-155">如果批量选择包含最顶层或其他行中的最底层的行，则不能移动所选内容向上/向下分别。</span><span class="sxs-lookup"><span data-stu-id="28e04-155">If the bulk selection includes either the top-most or the bottom-most row among the other rows, you cannot move the selection up/down respectively.</span></span>  
  
-   <span data-ttu-id="28e04-156">重新排列所选内容。</span><span class="sxs-lookup"><span data-stu-id="28e04-156">Rearrange the selection.</span></span>  
  
-   <span data-ttu-id="28e04-157">删除所选内容。</span><span class="sxs-lookup"><span data-stu-id="28e04-157">Delete the selection.</span></span>  
  
### <a name="to-change-the-order-of-existing-input-parameters"></a><span data-ttu-id="28e04-158">若要更改现有输入参数的顺序</span><span class="sxs-lookup"><span data-stu-id="28e04-158">To change the order of existing input parameters</span></span>  
  
1.  <span data-ttu-id="28e04-159">在中**配置\<Functoid\> Functoid**对话框中，单击现有输入你想要移动到其他位置有序列表中的输入参数的参数。</span><span class="sxs-lookup"><span data-stu-id="28e04-159">In the **Configure \<Functoid\> Functoid** dialog box, click the existing input parameter that you want to move to a different position in the ordered list of input parameters.</span></span>  
  
2.  <span data-ttu-id="28e04-160">单击![在列表中上移](../core/media/move-up-button.gif "Move_up_button")按钮在参数列表中向上移动参数。</span><span class="sxs-lookup"><span data-stu-id="28e04-160">Click the ![Move up in the list](../core/media/move-up-button.gif "Move_up_button") button to move the parameter up in the parameter list.</span></span> <span data-ttu-id="28e04-161">根据需要重复执行，直到所选的输入的参数为所需的位置。</span><span class="sxs-lookup"><span data-stu-id="28e04-161">Repeat as necessary until the selected input parameter is in the desired position.</span></span> <span data-ttu-id="28e04-162">此外，您可以按键盘向上键。</span><span class="sxs-lookup"><span data-stu-id="28e04-162">Alternatively, you can press the UP ARROW key from the keyboard.</span></span> <span data-ttu-id="28e04-163">有关映射器键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="28e04-163">For a list of Mapper shortcut keys, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
     <span data-ttu-id="28e04-164">-或-</span><span class="sxs-lookup"><span data-stu-id="28e04-164">-OR-</span></span>  
  
     <span data-ttu-id="28e04-165">单击![列表中向下移动](../core/media/move-down-button.gif "Move_down_button")按钮在参数列表中向下移动参数。</span><span class="sxs-lookup"><span data-stu-id="28e04-165">Click the ![Moving down in a list](../core/media/move-down-button.gif "Move_down_button") button to move the parameter down in the parameter list.</span></span> <span data-ttu-id="28e04-166">根据需要重复执行，直到所选的输入的参数为所需的位置。</span><span class="sxs-lookup"><span data-stu-id="28e04-166">Repeat as necessary until the selected input parameter is in the desired position.</span></span> <span data-ttu-id="28e04-167">此外，您可以按键盘向下箭头键。</span><span class="sxs-lookup"><span data-stu-id="28e04-167">Alternatively, you can press the DOWN ARROW key from the keyboard.</span></span> <span data-ttu-id="28e04-168">有关映射器键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="28e04-168">For a list of Mapper shortcut keys, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="28e04-169">您可以重新排列输入只能从顺序**配置\<Functoid\> Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="28e04-169">You can rearrange the sequence of inputs only from the **Configure \<Functoid\> Functoid** dialog box.</span></span> <span data-ttu-id="28e04-170">如果你选择最顶层或最底层的行![在列表中上移](../core/media/move-up-button.gif "Move_up_button")或![列表中向下移动](../core/media/move-down-button.gif "Move_down_button")按钮，将禁用，分别。</span><span class="sxs-lookup"><span data-stu-id="28e04-170">If you select the top-most or bottom-most row, the ![Move up in the list](../core/media/move-up-button.gif "Move_up_button") or ![Moving down in a list](../core/media/move-down-button.gif "Move_down_button") buttons would be disabled, respectively.</span></span>  
  
### <a name="to-delete-an-input-parameter-by-deleting-the-input-link"></a><span data-ttu-id="28e04-171">若要通过删除输入的链接来删除输入的参数</span><span class="sxs-lookup"><span data-stu-id="28e04-171">To delete an input parameter by deleting the input link</span></span>  
  
1.  <span data-ttu-id="28e04-172">在相关网格页中，单击与你想要删除的输入参数对应的输入的链接。</span><span class="sxs-lookup"><span data-stu-id="28e04-172">In the relevant grid page, click the input link corresponding to the input parameter you want to delete.</span></span>  
  
2.  <span data-ttu-id="28e04-173">上**编辑**菜单上，单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="28e04-173">On the **Edit** menu, click **Delete**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="28e04-174">或者，可以按 DELETE 键，或右键单击该链接在相关网格页中，并单击**删除**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="28e04-174">Alternatively, you can press the DELETE key, or right-click the link in the relevant grid page, and click **Delete** from the shortcut menu.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="28e04-175">将自行删除输入的链接。</span><span class="sxs-lookup"><span data-stu-id="28e04-175">The input link is deleted silently.</span></span> <span data-ttu-id="28e04-176">如果您不能确定有关它，可以始终撤消删除。</span><span class="sxs-lookup"><span data-stu-id="28e04-176">You can always undo delete if you are not sure about it.</span></span> <span data-ttu-id="28e04-177">有关撤消/重做操作的详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="28e04-177">For more information about undo/redo operations, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
### <a name="to-delete-existing-input-parameters-within-the-configure-functoid-functoid-dialog-box"></a><span data-ttu-id="28e04-178">若要删除现有输入的参数中配置\<Functoid\> Functoid 对话框</span><span class="sxs-lookup"><span data-stu-id="28e04-178">To delete existing input parameters within the Configure \<Functoid\> Functoid dialog box</span></span>  
  
1.  <span data-ttu-id="28e04-179">在中**配置\<Functoid\> Functoid**对话框中，单击现有输入你想要删除的参数。</span><span class="sxs-lookup"><span data-stu-id="28e04-179">In the **Configure \<Functoid\> Functoid** dialog box, click the existing input parameter that you want to delete.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="28e04-180">您可以删除使用此技术，甚至与输入链接相对应的任何输入的参数。</span><span class="sxs-lookup"><span data-stu-id="28e04-180">You can delete any input parameter using this technique, even those that correspond to an input link.</span></span>  
  
2.  <span data-ttu-id="28e04-181">单击![删除所选内容](../core/media/delete-button.gif "Delete_button")按钮。</span><span class="sxs-lookup"><span data-stu-id="28e04-181">Click the ![Deleting the selection](../core/media/delete-button.gif "Delete_button") button.</span></span> <span data-ttu-id="28e04-182">从参数列表中删除所选现有输入的参数。</span><span class="sxs-lookup"><span data-stu-id="28e04-182">The selected existing input parameter is deleted from the parameter list.</span></span> <span data-ttu-id="28e04-183">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="28e04-183">Click **OK**.</span></span>  
  
     <span data-ttu-id="28e04-184">或者，可以选择你想要删除的行并按 DELETE 键键盘。</span><span class="sxs-lookup"><span data-stu-id="28e04-184">Alternatively, you can select the row you want to delete, and press the DELETE key from the keyboard.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="28e04-185">将自行删除输入的参数。</span><span class="sxs-lookup"><span data-stu-id="28e04-185">The input parameter is deleted silently.</span></span> <span data-ttu-id="28e04-186">如果您不能确定有关它，可以始终撤消删除。</span><span class="sxs-lookup"><span data-stu-id="28e04-186">You can always undo delete if you are not sure about it.</span></span> <span data-ttu-id="28e04-187">有关撤消/重做操作的详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="28e04-187">For more information about undo/redo operations, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="28e04-188">在参数列表中没有任何输入的参数时，不启用删除按钮。</span><span class="sxs-lookup"><span data-stu-id="28e04-188">The delete button is not enabled when there are no input parameters in the parameter list.</span></span>  
  
## <a name="to-set-labels-and-comments-for-functoids"></a><span data-ttu-id="28e04-189">若要为 functoid 设置标签和注释</span><span class="sxs-lookup"><span data-stu-id="28e04-189">To set labels and comments for functoids</span></span>  
 <span data-ttu-id="28e04-190">您可以设置标签和注释 functoid 使用的**配置\<Functoid\> Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="28e04-190">You can set labels and comments for functoids using the **Configure \<Functoid\> Functoid** dialog box.</span></span>  
  
1.  <span data-ttu-id="28e04-191">在中**配置\<Functoid\> Functoid**对话框中，单击**标签和注释**选项卡。</span><span class="sxs-lookup"><span data-stu-id="28e04-191">In the **Configure \<Functoid\> Functoid** dialog box, click the **Label and Comments** tab.</span></span>  
  
2.  <span data-ttu-id="28e04-192">类型**标签**并**注释**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="28e04-192">Type the **Label** and **Comments**, and then click **OK**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="28e04-193">有关如何对标签和注释 functoid 和/或链接的详细信息，请参阅[如何标记链接](../core/how-to-label-a-link.md)并[如何标签和注释 Functoid](../core/how-to-label-and-comment-a-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="28e04-193">For more information about how to label and comment functoids and/or links, see [How to Label a Link](../core/how-to-label-a-link.md) and [How to Label and Comment a Functoid](../core/how-to-label-and-comment-a-functoid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28e04-194">请参阅</span><span class="sxs-lookup"><span data-stu-id="28e04-194">See Also</span></span>  
 [<span data-ttu-id="28e04-195">编辑 Functoid 属性和输入参数</span><span class="sxs-lookup"><span data-stu-id="28e04-195">Editing Functoid Properties and Input Parameters</span></span>](../core/editing-functoid-properties-and-input-parameters.md)