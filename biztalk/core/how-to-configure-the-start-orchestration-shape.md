---
title: 如何配置启动业务流程形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f3e9524198b414fc43e5c4e957ba2f6b6f3f689
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386031"
---
# <a name="how-to-configure-the-start-orchestration-shape"></a><span data-ttu-id="2c635-102">如何配置启动业务流程形状</span><span class="sxs-lookup"><span data-stu-id="2c635-102">How to Configure the Start Orchestration Shape</span></span>
<span data-ttu-id="2c635-103">**启动业务流程**形状是类似于**调用业务流程**形状，但您调用以异步方式与其他业务流程**启动业务流程**形状-即，调用该业务流程中的控制流将继续调用，而无需等待调用的业务流程完成其工作。</span><span class="sxs-lookup"><span data-stu-id="2c635-103">The **Start Orchestration** shape is similar to the **Call Orchestration** shape, but you invoke another orchestration asynchronously with the **Start Orchestration** shape—that is, the flow of control in the invoking orchestration proceeds beyond the invocation, without waiting for the invoked orchestration to finish its work.</span></span>  
  
 <span data-ttu-id="2c635-104">您可以指定将传递给调用的业务流程的参数。</span><span class="sxs-lookup"><span data-stu-id="2c635-104">You can specify parameters that will be passed to the invoked orchestration.</span></span> <span data-ttu-id="2c635-105">参数可以是消息、 变量、 端口引用、 角色链接或相关集。</span><span class="sxs-lookup"><span data-stu-id="2c635-105">Parameters can be messages, variables, port references, role links, or correlation sets.</span></span> <span data-ttu-id="2c635-106">**启动业务流程**形状可能采用*中*参数; 它不能采用*out*或者*ref*参数。</span><span class="sxs-lookup"><span data-stu-id="2c635-106">The **Start Orchestration** shape can only take *in* parameters; it cannot take *out* or *ref* parameters.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="2c635-107">如果将 XmlDocument 或 XmlNode 之类的非可序列化对象作为参数传递给业务流程中，它将失败。</span><span class="sxs-lookup"><span data-stu-id="2c635-107">If you pass non-serializable objects such as XmlDocument or XmlNode as parameters to an orchestration, it will fail.</span></span>  
  
 <span data-ttu-id="2c635-108">**启动业务流程**形状是仅在其中可以在作为参数传递的端口反转极性的形状 — 例如*使用*端口 （发送端口） 可以传递给调用的业务流程，但调用的业务流程可以将它视为*实现*端口 （接收端口）。</span><span class="sxs-lookup"><span data-stu-id="2c635-108">The **Start Orchestration** shape is the only shape in which you can reverse the polarity on a port being passed as a parameter—for example a *uses* port (send port) can be passed in to an invoked orchestration, but the invoked orchestration can treat it as an *implements* port (receive port).</span></span> <span data-ttu-id="2c635-109">请注意这只完成与使用直接绑定端口。</span><span class="sxs-lookup"><span data-stu-id="2c635-109">Note that this can only be done with ports that use direct binding.</span></span>  
  
 <span data-ttu-id="2c635-110">**启动业务流程**形状还可用来调用另一个项目中引用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="2c635-110">The **Start Orchestration** shape can also be used to call an orchestration that is referenced in another project.</span></span> <span data-ttu-id="2c635-111">这允许重复使用常见的业务流程工作流模式的多个 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="2c635-111">This allows for reuse of common orchestration workflow patterns across BizTalk projects.</span></span> <span data-ttu-id="2c635-112">对于可调用的被引用业务流程，请确保**的类型修饰符**调用的业务流程的属性设置为**公共**。</span><span class="sxs-lookup"><span data-stu-id="2c635-112">For the referenced orchestration to be callable, ensure that the **Type Modifier** property for the called orchestration is set to **Public**.</span></span> <span data-ttu-id="2c635-113">若要设置**的类型修饰符**到业务流程的属性**公共**，在 Microsoft 中打开该业务流程[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，单击顶部的业务流程以显示绿色启动形状**业务流程属性**对话框并设置**的类型修饰符**属性设置为**公共**。</span><span class="sxs-lookup"><span data-stu-id="2c635-113">To set the **Type Modifier** property for an orchestration to **Public**, open the orchestration in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], click the green start shape at the top of the orchestration to display the **Orchestration Properties** dialog and set the **Type Modifier** property to **Public**.</span></span> <span data-ttu-id="2c635-114">默认值为**的类型修饰符**是**专用**。</span><span class="sxs-lookup"><span data-stu-id="2c635-114">The default value for **Type Modifier** is **Private**.</span></span>  
  
 <span data-ttu-id="2c635-115">有关如何使用的示例**启动业务流程**形状中，从下载 SDK 示例"实现分散和收集模式" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。</span><span class="sxs-lookup"><span data-stu-id="2c635-115">For an example of how to use **Start Orchestration** shape, download the SDK sample "Implementing Scatter and Gather Pattern" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
### <a name="to-configure-a-start-orchestration-shape"></a><span data-ttu-id="2c635-116">若要配置启动业务流程形状</span><span class="sxs-lookup"><span data-stu-id="2c635-116">To configure a Start Orchestration shape</span></span>  
  
1. <span data-ttu-id="2c635-117">使用**业务流程选择**下拉列表框中，选择某一业务流程从列表中。</span><span class="sxs-lookup"><span data-stu-id="2c635-117">Using the **Orchestration Selection** drop-down list box, select an orchestration from the list.</span></span>  
  
2. <span data-ttu-id="2c635-118">使用**业务流程参数**网格控件，指定要传递到业务流程参数-中指定的那样**业务流程选择**下拉列表框-，它开始。</span><span class="sxs-lookup"><span data-stu-id="2c635-118">Using the **Orchestration Parameters** grid control, specify arguments to pass to the orchestration—as specified in the **Orchestration Selection** drop-down list box—that is started.</span></span> <span data-ttu-id="2c635-119">通过键入变量名称或单击单元格中下拉列表中的某个变量的变量的列中，每个单元格，一个变量单元格中指定这些参数。</span><span class="sxs-lookup"><span data-stu-id="2c635-119">You specify these arguments in the cells of the Variable column, one variable per cell, by typing the name of a variable or clicking a variable from a drop-down list in a cell.</span></span>  
  
3. <span data-ttu-id="2c635-120">若要配置**启动业务流程**形状根据服务和对话框中指定的参数，请单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2c635-120">To configure the **Start Orchestration** shape according to the service and arguments that you specified in the dialog box, click **OK**.</span></span> <span data-ttu-id="2c635-121">若要关闭**启动业务流程配置**对话框，但不进行任何更改**启动业务流程**形状，请单击**取消**。</span><span class="sxs-lookup"><span data-stu-id="2c635-121">To close the **Start Orchestration Configuration** dialog box without making any changes to the **Start Orchestration** shape, click **Cancel**.</span></span>  
  
   > [!CAUTION]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="2c635-122">不支持递归业务流程。</span><span class="sxs-lookup"><span data-stu-id="2c635-122">does not support recursive orchestrations.</span></span> <span data-ttu-id="2c635-123">如果业务流程 A 调用或启动业务流程 B，然后业务流程 B 不能调用或启动业务流程 A 直接，也可以调用或启动任何直接或间接调用业务流程 A 的业务流程</span><span class="sxs-lookup"><span data-stu-id="2c635-123">If Orchestration A calls or starts Orchestration B, then Orchestration B cannot call or start Orchestration A directly, nor can it call or start any orchestration that directly or indirectly calls Orchestration A.</span></span>  
  
## <a name="orchestration-selection-drop-down-list-box"></a><span data-ttu-id="2c635-124">业务流程选择下拉列表框</span><span class="sxs-lookup"><span data-stu-id="2c635-124">Orchestration Selection drop-down list box</span></span>  
 <span data-ttu-id="2c635-125">单击以查看可用的业务流程并进行选择的下拉列表框中的下箭头。</span><span class="sxs-lookup"><span data-stu-id="2c635-125">Click the Down arrow in the drop-down list box to view available orchestrations and select one.</span></span> <span data-ttu-id="2c635-126">此列表包含可以从当前业务流程，其中包括被引用程序集启动所有业务流程。</span><span class="sxs-lookup"><span data-stu-id="2c635-126">This list contains all the orchestrations that can be started from the current orchestration, including referenced assemblies.</span></span>  
  
## <a name="orchestration-parameters-grid-control"></a><span data-ttu-id="2c635-127">业务流程参数网格控件</span><span class="sxs-lookup"><span data-stu-id="2c635-127">Orchestration Parameters grid control</span></span>  
 <span data-ttu-id="2c635-128">指定要传递到通过参数化的业务流程使用的参数**业务流程参数**网格控件。</span><span class="sxs-lookup"><span data-stu-id="2c635-128">You specify the arguments to pass to a parameterized orchestration by using the **Orchestration Parameters** grid control.</span></span> <span data-ttu-id="2c635-129">网格具有四列：作用域、 参数名称、 参数类型和参数方向中的变量。</span><span class="sxs-lookup"><span data-stu-id="2c635-129">The grid has four columns: Variables in Scope, Parameter Name, Parameter Type, and Parameter Direction.</span></span> <span data-ttu-id="2c635-130">您可以更改仅在第一列;其他列是只读的。</span><span class="sxs-lookup"><span data-stu-id="2c635-130">You can make changes only in the first column; the other columns are read-only.</span></span>  
  
 <span data-ttu-id="2c635-131">当选择一个有效的业务流程时，其参数将自动填充参数名称、 类型和方向列的网格控件。</span><span class="sxs-lookup"><span data-stu-id="2c635-131">When you select a valid orchestration, its parameters populate the parameter name, type, and direction columns of the grid control.</span></span> <span data-ttu-id="2c635-132">然后，作为参数传递每个行中选择变量。</span><span class="sxs-lookup"><span data-stu-id="2c635-132">You then select the variables in each row to pass as arguments.</span></span> <span data-ttu-id="2c635-133">从范围列中的变量中的每个单元中存在的下拉列表中选择这些变量。</span><span class="sxs-lookup"><span data-stu-id="2c635-133">You select these variables from a drop-down list present in each cell in the Variables in Scope column.</span></span> <span data-ttu-id="2c635-134">此列表显示在相邻的参数类型单元格中指定的类型的所有可用的变量。</span><span class="sxs-lookup"><span data-stu-id="2c635-134">This list displays all the available variables of the type specified in the adjacent Parameter Type cell.</span></span> <span data-ttu-id="2c635-135">如果只有一个该类型的对象不可用，该对象自动填充范围单元格中的变量。</span><span class="sxs-lookup"><span data-stu-id="2c635-135">If only one object of that type is available, the Variables in Scope cell is automatically populated with that object.</span></span> <span data-ttu-id="2c635-136">此外可以键入单元格中作用域变量，以选择下拉列表中的变量中。</span><span class="sxs-lookup"><span data-stu-id="2c635-136">You can also type in a Variables in Scope cell to select a variable that is available in the drop-down list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c635-137">因为**启动业务流程**形状将启动业务流程，在此对话框中选择"业务流程参数"实际上表示业务流程变量。</span><span class="sxs-lookup"><span data-stu-id="2c635-137">Because a **Start Orchestration** shape starts an orchestration, the "Orchestration Parameters" you select in this dialog box actually refer to orchestration variables.</span></span>  
  
 <span data-ttu-id="2c635-138">如果正在执行业务流程具有未定义的参数，此对话框中的网格控件将不可用。</span><span class="sxs-lookup"><span data-stu-id="2c635-138">If an orchestration you are executing has no defined parameters, the grid control in this dialog box is unavailable.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2c635-139">本节内容</span><span class="sxs-lookup"><span data-stu-id="2c635-139">In This Section</span></span>  
 [<span data-ttu-id="2c635-140">如何创建接收调用的业务流程上的订阅</span><span class="sxs-lookup"><span data-stu-id="2c635-140">How to Create Receive Subscriptions at Invoked Orchestrations</span></span>](../core/how-to-create-receive-subscriptions-at-invoked-orchestrations.md) 
  
## <a name="see-also"></a><span data-ttu-id="2c635-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c635-141">See Also</span></span>  
 [<span data-ttu-id="2c635-142">如何配置调用业务流程形状</span><span class="sxs-lookup"><span data-stu-id="2c635-142">How to Configure the Call Orchestration Shape</span></span>](../core/how-to-configure-the-call-orchestration-shape.md)