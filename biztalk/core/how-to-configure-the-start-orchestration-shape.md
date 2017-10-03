---
title: "如何配置开始业务流程形状 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [Orchestration Designer], Start Orchestration shapes
- Start Orchestration shape [Orchestration Designer], parameters
- Start Orchestration shape [Orchestration Designer], configuring
- orchestrations, starting
- Start Orchestration shape [Orchestration Designer]
- Start Orchestration shape [Orchestration Designer], starting orchestrations
- Start Orchestration shape [Orchestration Designer], about Star Orchestration shape
ms.assetid: 9d01c41e-9bc5-4c1c-a869-b2f0df13036a
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f8181849b700939ba86f55cd372b80ed2ebf70e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-start-orchestration-shape"></a><span data-ttu-id="eaff5-102">如何配置开始业务流程形状</span><span class="sxs-lookup"><span data-stu-id="eaff5-102">How to Configure the Start Orchestration Shape</span></span>
<span data-ttu-id="eaff5-103">**启动 Orchestration**形状是类似于**调用 Orchestration**形状，但你调用以异步方式与其他业务流程**启动 Orchestration**形状 — 也就是说，调用该业务流程的控制流继续执行后续调用，而无需等待调用的业务流程，以完成其工作。</span><span class="sxs-lookup"><span data-stu-id="eaff5-103">The **Start Orchestration** shape is similar to the **Call Orchestration** shape, but you invoke another orchestration asynchronously with the **Start Orchestration** shape—that is, the flow of control in the invoking orchestration proceeds beyond the invocation, without waiting for the invoked orchestration to finish its work.</span></span>  
  
 <span data-ttu-id="eaff5-104">您可以指定将传递到被调用的业务流程的参数。</span><span class="sxs-lookup"><span data-stu-id="eaff5-104">You can specify parameters that will be passed to the invoked orchestration.</span></span> <span data-ttu-id="eaff5-105">参数可以是消息、变量、端口引用、角色链接或相关集。</span><span class="sxs-lookup"><span data-stu-id="eaff5-105">Parameters can be messages, variables, port references, role links, or correlation sets.</span></span> <span data-ttu-id="eaff5-106">**启动 Orchestration**只能采用形状*中*参数; 它无法接受*出*或*ref*参数。</span><span class="sxs-lookup"><span data-stu-id="eaff5-106">The **Start Orchestration** shape can only take *in* parameters; it cannot take *out* or *ref* parameters.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="eaff5-107">如果将非可序列化的对象，如 XmlDocument 或 XmlNode 作为参数传递给业务流程中，文件将失败。</span><span class="sxs-lookup"><span data-stu-id="eaff5-107">If you pass non-serializable objects such as XmlDocument or XmlNode as parameters to an orchestration, it will fail.</span></span>  
  
 <span data-ttu-id="eaff5-108">**启动 Orchestration**形状是在其中你可以在作为参数传递的端口调转极性的唯一形状 — 例如*使用*端口 （发送端口） 可以在传递给调用的业务流程，但调用的业务流程可以将其视为*实现*端口 （接收端口）。</span><span class="sxs-lookup"><span data-stu-id="eaff5-108">The **Start Orchestration** shape is the only shape in which you can reverse the polarity on a port being passed as a parameter—for example a *uses* port (send port) can be passed in to an invoked orchestration, but the invoked orchestration can treat it as an *implements* port (receive port).</span></span> <span data-ttu-id="eaff5-109">请注意，只能通过使用直接绑定的端口实现这一点。</span><span class="sxs-lookup"><span data-stu-id="eaff5-109">Note that this can only be done with ports that use direct binding.</span></span>  
  
 <span data-ttu-id="eaff5-110">**启动 Orchestration**形状还可以用于调用另一个项目中引用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="eaff5-110">The **Start Orchestration** shape can also be used to call an orchestration that is referenced in another project.</span></span> <span data-ttu-id="eaff5-111">这允许在多个 BizTalk 项目中重复使用公用的业务流程工作流模式。</span><span class="sxs-lookup"><span data-stu-id="eaff5-111">This allows for reuse of common orchestration workflow patterns across BizTalk projects.</span></span> <span data-ttu-id="eaff5-112">对于引用业务流程可以被调用，请确保**类型修饰符**调用的业务流程的属性设置为**公共**。</span><span class="sxs-lookup"><span data-stu-id="eaff5-112">For the referenced orchestration to be callable, ensure that the **Type Modifier** property for the called orchestration is set to **Public**.</span></span> <span data-ttu-id="eaff5-113">若要设置**类型修饰符**属性的业务流程**公共**，在 Microsoft 中打开业务流程[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，单击顶部的业务流程，以显示绿色启动形状**业务流程属性**对话框并设置**类型修饰符**属性**公共**。</span><span class="sxs-lookup"><span data-stu-id="eaff5-113">To set the **Type Modifier** property for an orchestration to **Public**, open the orchestration in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], click the green start shape at the top of the orchestration to display the **Orchestration Properties** dialog and set the **Type Modifier** property to **Public**.</span></span> <span data-ttu-id="eaff5-114">默认值为**类型修饰符**是**私有**。</span><span class="sxs-lookup"><span data-stu-id="eaff5-114">The default value for **Type Modifier** is **Private**.</span></span>  
  
 <span data-ttu-id="eaff5-115">有关如何使用的示例**启动 Orchestration**形状，请从下载 SDK 示例"实现的散点图和收集模式" [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="eaff5-115">For an example of how to use **Start Orchestration** shape, download the SDK sample "Implementing Scatter and Gather Pattern" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
### <a name="to-configure-a-start-orchestration-shape"></a><span data-ttu-id="eaff5-116">若要配置启动 Orchestration 形状</span><span class="sxs-lookup"><span data-stu-id="eaff5-116">To configure a Start Orchestration shape</span></span>  
  
1.  <span data-ttu-id="eaff5-117">使用**Orchestration 选择**下拉列表框中，选择一个从列表中的业务流程。</span><span class="sxs-lookup"><span data-stu-id="eaff5-117">Using the **Orchestration Selection** drop-down list box, select an orchestration from the list.</span></span>  
  
2.  <span data-ttu-id="eaff5-118">使用**业务流程参数**网格控件中，指定要传递给业务流程自变量-中指定**Orchestration 选择**下拉列表框-，它开始。</span><span class="sxs-lookup"><span data-stu-id="eaff5-118">Using the **Orchestration Parameters** grid control, specify arguments to pass to the orchestration—as specified in the **Orchestration Selection** drop-down list box—that is started.</span></span> <span data-ttu-id="eaff5-119">您通过键入变量的名称或从单元格的下拉列表中单击某一变量，在“变量”列的单元格中指定这些参数，每个单元格一个变量。</span><span class="sxs-lookup"><span data-stu-id="eaff5-119">You specify these arguments in the cells of the Variable column, one variable per cell, by typing the name of a variable or clicking a variable from a drop-down list in a cell.</span></span>  
  
3.  <span data-ttu-id="eaff5-120">若要配置**启动 Orchestration**调整根据服务和在对话框中指定的自变量，请单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="eaff5-120">To configure the **Start Orchestration** shape according to the service and arguments that you specified in the dialog box, click **OK**.</span></span> <span data-ttu-id="eaff5-121">若要关闭**启动业务流程配置**对话框，而不进行任何更改到**启动 Orchestration**形状，请单击**取消**。</span><span class="sxs-lookup"><span data-stu-id="eaff5-121">To close the **Start Orchestration Configuration** dialog box without making any changes to the **Start Orchestration** shape, click **Cancel**.</span></span>  
  
    > [!CAUTION]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="eaff5-122">不支持递归业务流程。</span><span class="sxs-lookup"><span data-stu-id="eaff5-122"> does not support recursive orchestrations.</span></span> <span data-ttu-id="eaff5-123">如果业务流程 A 调用或启动业务流程 B，则业务流程 B 既无法直接调用或启动业务流程 A，也无法调用或启动直接或间接调用业务流程 A 的任何业务流程。</span><span class="sxs-lookup"><span data-stu-id="eaff5-123">If Orchestration A calls or starts Orchestration B, then Orchestration B cannot call or start Orchestration A directly, nor can it call or start any orchestration that directly or indirectly calls Orchestration A.</span></span>  
  
## <a name="orchestration-selection-drop-down-list-box"></a><span data-ttu-id="eaff5-124">“业务流程选择”下拉列表框</span><span class="sxs-lookup"><span data-stu-id="eaff5-124">Orchestration Selection drop-down list box</span></span>  
 <span data-ttu-id="eaff5-125">单击该下拉列表框中的下箭头可以查看可用的业务流程并进行选择。</span><span class="sxs-lookup"><span data-stu-id="eaff5-125">Click the Down arrow in the drop-down list box to view available orchestrations and select one.</span></span> <span data-ttu-id="eaff5-126">此列表包含可从当前业务流程中启动的所有业务流程，包括引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="eaff5-126">This list contains all the orchestrations that can be started from the current orchestration, including referenced assemblies.</span></span>  
  
## <a name="orchestration-parameters-grid-control"></a><span data-ttu-id="eaff5-127">“业务流程参数”网格控件</span><span class="sxs-lookup"><span data-stu-id="eaff5-127">Orchestration Parameters grid control</span></span>  
 <span data-ttu-id="eaff5-128">指定要传递到参数化的业务流程，通过使用参数**业务流程参数**网格控件。</span><span class="sxs-lookup"><span data-stu-id="eaff5-128">You specify the arguments to pass to a parameterized orchestration by using the **Orchestration Parameters** grid control.</span></span> <span data-ttu-id="eaff5-129">网格包含四列： 作用域、 参数名称、 参数类型和参数方向中的变量。</span><span class="sxs-lookup"><span data-stu-id="eaff5-129">The grid has four columns: Variables in Scope, Parameter Name, Parameter Type, and Parameter Direction.</span></span> <span data-ttu-id="eaff5-130">您只能对第一列进行更改；其他列是只读的。</span><span class="sxs-lookup"><span data-stu-id="eaff5-130">You can make changes only in the first column; the other columns are read-only.</span></span>  
  
 <span data-ttu-id="eaff5-131">在您选择某一有效业务流程后，其参数将自动填充该网格控件的参数名称、类型和方向列。</span><span class="sxs-lookup"><span data-stu-id="eaff5-131">When you select a valid orchestration, its parameters populate the parameter name, type, and direction columns of the grid control.</span></span> <span data-ttu-id="eaff5-132">然后，您可以选择每一行中要作为参数传递的变量。</span><span class="sxs-lookup"><span data-stu-id="eaff5-132">You then select the variables in each row to pass as arguments.</span></span> <span data-ttu-id="eaff5-133">您从“作用域中的变量”列的各单元格上的下拉列表中选择这些变量。</span><span class="sxs-lookup"><span data-stu-id="eaff5-133">You select these variables from a drop-down list present in each cell in the Variables in Scope column.</span></span> <span data-ttu-id="eaff5-134">此列表显示在相邻的“参数类型”单元格中指定的类型的所有可用变量。</span><span class="sxs-lookup"><span data-stu-id="eaff5-134">This list displays all the available variables of the type specified in the adjacent Parameter Type cell.</span></span> <span data-ttu-id="eaff5-135">如果该类型只有一个对象可用，将自动用该对象填充“作用域中的变量”单元格。</span><span class="sxs-lookup"><span data-stu-id="eaff5-135">If only one object of that type is available, the Variables in Scope cell is automatically populated with that object.</span></span> <span data-ttu-id="eaff5-136">您还可以在“作用域中的变量”单元格中键入，以便选择在该下拉列表中提供的变量。</span><span class="sxs-lookup"><span data-stu-id="eaff5-136">You can also type in a Variables in Scope cell to select a variable that is available in the drop-down list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eaff5-137">因为**启动 Orchestration**形状启动业务流程，在此对话框中选择"Orchestration Parameters"实际上指业务流程变量。</span><span class="sxs-lookup"><span data-stu-id="eaff5-137">Because a **Start Orchestration** shape starts an orchestration, the "Orchestration Parameters" you select in this dialog box actually refer to orchestration variables.</span></span>  
  
 <span data-ttu-id="eaff5-138">如果您正在执行的业务流程没有已定义的参数，则该对话框中的网格控件将不可用。</span><span class="sxs-lookup"><span data-stu-id="eaff5-138">If an orchestration you are executing has no defined parameters, the grid control in this dialog box is unavailable.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eaff5-139">本节内容</span><span class="sxs-lookup"><span data-stu-id="eaff5-139">In This Section</span></span>  
 [<span data-ttu-id="eaff5-140">如何创建接收上调用的业务流程的订阅</span><span class="sxs-lookup"><span data-stu-id="eaff5-140">How to Create Receive Subscriptions at Invoked Orchestrations</span></span>](../core/how-to-create-receive-subscriptions-at-invoked-orchestrations.md) 
  
## <a name="see-also"></a><span data-ttu-id="eaff5-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eaff5-141">See Also</span></span>  
 [<span data-ttu-id="eaff5-142">如何配置调用业务流程形状</span><span class="sxs-lookup"><span data-stu-id="eaff5-142">How to Configure the Call Orchestration Shape</span></span>](../core/how-to-configure-the-call-orchestration-shape.md)