---
title: 如何配置调用业务流程形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Call Orchestration shape [Orchestration Designer], parameters
- Call Orchestration shape [Orchestration Designer], configuring
- Call Orchestration shape [Orchestration Designer], about Call Orchestration shapes
- configuring [Orchestration Designer], Call Orchestration shapes
- Call Orchestration shape [Orchestration Designer]
- nonserializable objects
- orchestrations, nonserializable objects
- Call Orchestration shape [Orchestration Designer], referencing orchestrations
- orchestrations, parameters
ms.assetid: 718ce2a0-ac08-4662-8b4e-1be279dbc749
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aab9f1ab84836d436ea1570b7d63f8a3cc0c0064
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981030"
---
# <a name="how-to-configure-the-call-orchestration-shape"></a><span data-ttu-id="a3580-102">如何配置调用业务流程形状</span><span class="sxs-lookup"><span data-stu-id="a3580-102">How to Configure the Call Orchestration Shape</span></span>
<span data-ttu-id="a3580-103">**调用业务流程**形状可用于同步调用另一个项目中引用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="a3580-103">The **Call Orchestration** shape can be used to synchronously call an orchestration that is referenced in another project.</span></span> <span data-ttu-id="a3580-104">这允许在多个 BizTalk 项目中重复使用公用的业务流程工作流模式。</span><span class="sxs-lookup"><span data-stu-id="a3580-104">This allows for reuse of common orchestration workflow patterns across BizTalk projects.</span></span> <span data-ttu-id="a3580-105">调用以同步方式与另一个嵌套的业务流程时**调用业务流程**等到嵌套的业务流程完成后才能继续的封闭的业务流程的形状。</span><span class="sxs-lookup"><span data-stu-id="a3580-105">When you invoke another nested orchestration synchronously with the **Call Orchestration** shape the enclosing orchestration waits for the nested orchestration to finish before continuing.</span></span>  
  
 <span data-ttu-id="a3580-106">您可以指定将传递到嵌套的业务流程的参数。</span><span class="sxs-lookup"><span data-stu-id="a3580-106">You can specify parameters that will be passed to the nested orchestration.</span></span> <span data-ttu-id="a3580-107">参数可以是消息、变量、端口引用、角色链接或相关集。</span><span class="sxs-lookup"><span data-stu-id="a3580-107">Parameters can be messages, variables, port references, role links, or correlation sets.</span></span> <span data-ttu-id="a3580-108">传入的端口引用、 角色链接和相关集所有像自寻址的信封一样执行： 它们提供可用于将信息发送回封闭业务流程的嵌套的业务流程信息。</span><span class="sxs-lookup"><span data-stu-id="a3580-108">Passed-in port references, role links, and correlation sets all perform like self-addressed envelopes: they supply the nested orchestration information it can use to send information back to the enclosing orchestration.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="a3580-109">如果您将不可序列化的对象（例如 XmlDocument 或 XmlNode）作为参数传递到某一业务流程，它将失败。</span><span class="sxs-lookup"><span data-stu-id="a3580-109">If you pass nonserializable objects such as XmlDocument or XmlNode as parameters to an orchestration, it will fail.</span></span>  
  
 <span data-ttu-id="a3580-110">有关如何使用的示例**调用业务流程**形状中，请参阅[CallOrchestration （BizTalk Server 示例）](../core/callorchestration-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="a3580-110">For an example of how to use **Call Orchestration** shape, see [CallOrchestration (BizTalk Server Sample)](../core/callorchestration-biztalk-server-sample.md).</span></span>  
  
### <a name="to-configure-a-call-orchestration-shape"></a><span data-ttu-id="a3580-111">配置调用业务流程形状</span><span class="sxs-lookup"><span data-stu-id="a3580-111">To configure a Call Orchestration shape</span></span>  
  
1. <span data-ttu-id="a3580-112">使用**业务流程选择**下拉列表框中，选择某一业务流程从列表中。</span><span class="sxs-lookup"><span data-stu-id="a3580-112">Using the **Orchestration Selection** drop-down list box, select an orchestration from the list.</span></span>  
  
2. <span data-ttu-id="a3580-113">使用**业务流程参数**网格控件，指定要传递到业务流程参数 — 中指定的那样**业务流程选择**下拉列表框中，可调用。</span><span class="sxs-lookup"><span data-stu-id="a3580-113">Using the **Orchestration Parameters** grid control, specify arguments to pass to the orchestration—as specified in the **Orchestration Selection** drop-down list box—that is called.</span></span> <span data-ttu-id="a3580-114">您通过键入变量的名称或从单元格的下拉列表中单击某一变量，在“变量”列的单元格中指定这些参数，每个单元格一个变量。</span><span class="sxs-lookup"><span data-stu-id="a3580-114">You specify these arguments in the cells of the Variable column, one variable per cell, by typing the name of a variable or clicking a variable from a drop-down list in a cell.</span></span>  
  
3. <span data-ttu-id="a3580-115">若要配置**调用业务流程**形状根据服务和对话框中指定的参数，请单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a3580-115">To configure the **Call Orchestration** shape according to the service and arguments that you specified in the dialog box, click **OK**.</span></span> <span data-ttu-id="a3580-116">若要关闭**调用业务流程配置**对话框，但不进行任何更改**调用业务流程**形状，请单击**取消**。</span><span class="sxs-lookup"><span data-stu-id="a3580-116">To close the **Call Orchestration Configuration** dialog box without making any changes to the **Call Orchestration** shape, click **Cancel**.</span></span>  
  
   > [!CAUTION]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a3580-117"> 不支持递归业务流程。</span><span class="sxs-lookup"><span data-stu-id="a3580-117"> does not support recursive orchestrations.</span></span> <span data-ttu-id="a3580-118">如果业务流程 A 调用或启动业务流程 B，则业务流程 B 既无法直接调用或启动业务流程 A，也无法调用或启动直接或间接调用业务流程 A 的任何业务流程。</span><span class="sxs-lookup"><span data-stu-id="a3580-118">If Orchestration A calls or starts Orchestration B, then Orchestration B cannot call or start Orchestration A directly, nor can it call or start any orchestration that directly or indirectly calls Orchestration A.</span></span>  
  
## <a name="referenced-orchestrations"></a><span data-ttu-id="a3580-119">引用的业务流程</span><span class="sxs-lookup"><span data-stu-id="a3580-119">Referenced Orchestrations</span></span>  
 <span data-ttu-id="a3580-120">为使引用的业务流程可调用，请确保为调用的业务流程配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="a3580-120">For the referenced orchestration to be callable, ensure that the following properties have been configured for the called orchestration:</span></span>  
  
- <span data-ttu-id="a3580-121">设置**的类型修饰符**属性设置为**公共**的调用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="a3580-121">Set the **Type Modifier** property to **Public** for the called orchestration.</span></span> <span data-ttu-id="a3580-122">若要设置**的类型修饰符**到业务流程的属性**公共**，在 Microsoft 中打开该业务流程[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，单击顶部的业务流程以显示绿色启动形状**业务流程属性**对话框并设置**的类型修饰符**属性设置为**公共**。</span><span class="sxs-lookup"><span data-stu-id="a3580-122">To set the **Type Modifier** property for an orchestration to **Public**, open the orchestration in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], click the green start shape at the top of the orchestration to display the **Orchestration Properties** dialog and set the **Type Modifier** property to **Public**.</span></span>  
  
- <span data-ttu-id="a3580-123">设置**激活**属性中的业务流程的初始接收形状**False**。</span><span class="sxs-lookup"><span data-stu-id="a3580-123">Set the **Activate** property of the initial receive shape in the orchestration to **False**.</span></span>  
  
## <a name="orchestration-selection-drop-down-list-box"></a><span data-ttu-id="a3580-124">“业务流程选择”下拉列表框</span><span class="sxs-lookup"><span data-stu-id="a3580-124">Orchestration Selection drop-down list box</span></span>  
 <span data-ttu-id="a3580-125">单击该下拉列表框中的下箭头可以查看可用服务并进行选择。</span><span class="sxs-lookup"><span data-stu-id="a3580-125">Click the Down arrow in the drop-down list box to view available services and select one.</span></span> <span data-ttu-id="a3580-126">下表包含可从当前业务流程中调用的所有服务，包括引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="a3580-126">This list contains all the services that can be called from the current orchestration, including referenced assemblies.</span></span>  
  
## <a name="orchestration-parameters-grid-control"></a><span data-ttu-id="a3580-127">“业务流程参数”网格控件</span><span class="sxs-lookup"><span data-stu-id="a3580-127">Orchestration Parameters grid control</span></span>  
 <span data-ttu-id="a3580-128">指定要传递到通过参数化的业务流程使用的参数**业务流程参数**网格控件。</span><span class="sxs-lookup"><span data-stu-id="a3580-128">You specify the arguments to pass to a parameterized orchestration by using the **Orchestration Parameters** grid control.</span></span> <span data-ttu-id="a3580-129">网格具有四列： 作用域、 参数名称、 参数类型和参数方向中的变量。</span><span class="sxs-lookup"><span data-stu-id="a3580-129">The grid has four columns: Variables in Scope, Parameter Name, Parameter Type, and Parameter Direction.</span></span> <span data-ttu-id="a3580-130">您只能对第一列进行更改；其他列是只读的。</span><span class="sxs-lookup"><span data-stu-id="a3580-130">You can make changes only in the first column; the other columns are read-only.</span></span>  
  
 <span data-ttu-id="a3580-131">当选择一个有效的业务流程时，其参数将自动填充网格控件的参数名称、 类型和方向列。</span><span class="sxs-lookup"><span data-stu-id="a3580-131">When you select a valid orchestration, its parameters populate the parameter name, type and direction columns of the grid control.</span></span> <span data-ttu-id="a3580-132">然后，您可以选择每一行中要作为参数传递的变量。</span><span class="sxs-lookup"><span data-stu-id="a3580-132">You then select the variables in each row to pass as arguments.</span></span> <span data-ttu-id="a3580-133">您从“作用域中的变量”列的各单元格上的下拉列表中选择这些变量。</span><span class="sxs-lookup"><span data-stu-id="a3580-133">You select these variables from a drop-down list present in each cell in the Variables in Scope column.</span></span> <span data-ttu-id="a3580-134">此列表显示在相邻的“参数类型”单元格中指定的类型的所有可用变量。</span><span class="sxs-lookup"><span data-stu-id="a3580-134">This list displays all the available variables of the type specified in the adjacent Parameter Type cell.</span></span> <span data-ttu-id="a3580-135">如果该类型只有一个对象可用，将自动用该对象填充“作用域中的变量”单元格。</span><span class="sxs-lookup"><span data-stu-id="a3580-135">If only one object of that type is available, the Variables in Scope cell is automatically populated with that object.</span></span> <span data-ttu-id="a3580-136">您还可以在“作用域中的变量”单元格中键入，以便选择在该下拉列表中提供的变量。</span><span class="sxs-lookup"><span data-stu-id="a3580-136">You can also type in a Variables in Scope cell to select a variable that is available in the drop-down list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3580-137">因为**调用业务流程**形状调用业务流程，在此对话框中选择"业务流程参数"实际上表示业务流程变量。</span><span class="sxs-lookup"><span data-stu-id="a3580-137">Because a **Call Orchestration** shape calls an orchestration, the "Orchestration Parameters" you select in this dialog box actually refer to orchestration variables.</span></span>  
  
 <span data-ttu-id="a3580-138">如果您在调用的业务流程没有定义的参数，则该对话框中的网格控件将不可用。</span><span class="sxs-lookup"><span data-stu-id="a3580-138">If an orchestration you are calling has no defined parameters, the grid control in this dialog box is unavailable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3580-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3580-139">See Also</span></span>  
 [<span data-ttu-id="a3580-140">如何配置启动业务流程形状</span><span class="sxs-lookup"><span data-stu-id="a3580-140">How to Configure the Start Orchestration Shape</span></span>](../core/how-to-configure-the-start-orchestration-shape.md)