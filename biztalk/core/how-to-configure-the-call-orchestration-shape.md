---
title: 如何配置调用业务流程形状 |Microsoft 文档
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
ms.openlocfilehash: dabb73b3bed616f17c69923799169a7c6ca2b6d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249701"
---
# <a name="how-to-configure-the-call-orchestration-shape"></a><span data-ttu-id="148cb-102">如何配置调用业务流程形状</span><span class="sxs-lookup"><span data-stu-id="148cb-102">How to Configure the Call Orchestration Shape</span></span>
<span data-ttu-id="148cb-103">**调用 Orchestration**形状可以用于以同步方式调用另一个项目中引用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="148cb-103">The **Call Orchestration** shape can be used to synchronously call an orchestration that is referenced in another project.</span></span> <span data-ttu-id="148cb-104">这允许在多个 BizTalk 项目中重复使用公用的业务流程工作流模式。</span><span class="sxs-lookup"><span data-stu-id="148cb-104">This allows for reuse of common orchestration workflow patterns across BizTalk projects.</span></span> <span data-ttu-id="148cb-105">当调用另一个嵌套的业务流程的情况下同步**调用 Orchestration**封闭业务流程等待嵌套的业务流程，在继续之前完成的形状。</span><span class="sxs-lookup"><span data-stu-id="148cb-105">When you invoke another nested orchestration synchronously with the **Call Orchestration** shape the enclosing orchestration waits for the nested orchestration to finish before continuing.</span></span>  
  
 <span data-ttu-id="148cb-106">您可以指定将传递到嵌套的业务流程的参数。</span><span class="sxs-lookup"><span data-stu-id="148cb-106">You can specify parameters that will be passed to the nested orchestration.</span></span> <span data-ttu-id="148cb-107">参数可以是消息、变量、端口引用、角色链接或相关集。</span><span class="sxs-lookup"><span data-stu-id="148cb-107">Parameters can be messages, variables, port references, role links, or correlation sets.</span></span> <span data-ttu-id="148cb-108">传入的端口引用、 角色链接和关联集所有执行操作时像自寻址包络线： 提供可用于将信息发送回封闭业务流程的嵌套的业务流程信息。</span><span class="sxs-lookup"><span data-stu-id="148cb-108">Passed-in port references, role links, and correlation sets all perform like self-addressed envelopes: they supply the nested orchestration information it can use to send information back to the enclosing orchestration.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="148cb-109">如果您将不可序列化的对象（例如 XmlDocument 或 XmlNode）作为参数传递到某一业务流程，它将失败。</span><span class="sxs-lookup"><span data-stu-id="148cb-109">If you pass nonserializable objects such as XmlDocument or XmlNode as parameters to an orchestration, it will fail.</span></span>  
  
 <span data-ttu-id="148cb-110">有关如何使用的示例**调用 Orchestration**形状，请参阅[CallOrchestration （BizTalk Server 示例）](../core/callorchestration-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="148cb-110">For an example of how to use **Call Orchestration** shape, see [CallOrchestration (BizTalk Server Sample)](../core/callorchestration-biztalk-server-sample.md).</span></span>  
  
### <a name="to-configure-a-call-orchestration-shape"></a><span data-ttu-id="148cb-111">配置调用业务流程形状</span><span class="sxs-lookup"><span data-stu-id="148cb-111">To configure a Call Orchestration shape</span></span>  
  
1.  <span data-ttu-id="148cb-112">使用**Orchestration 选择**下拉列表框中，选择一个从列表中的业务流程。</span><span class="sxs-lookup"><span data-stu-id="148cb-112">Using the **Orchestration Selection** drop-down list box, select an orchestration from the list.</span></span>  
  
2.  <span data-ttu-id="148cb-113">使用**业务流程参数**网格控件中，指定要传递给业务流程自变量-中指定**Orchestration 选择**下拉列表框-调用的。</span><span class="sxs-lookup"><span data-stu-id="148cb-113">Using the **Orchestration Parameters** grid control, specify arguments to pass to the orchestration—as specified in the **Orchestration Selection** drop-down list box—that is called.</span></span> <span data-ttu-id="148cb-114">您通过键入变量的名称或从单元格的下拉列表中单击某一变量，在“变量”列的单元格中指定这些参数，每个单元格一个变量。</span><span class="sxs-lookup"><span data-stu-id="148cb-114">You specify these arguments in the cells of the Variable column, one variable per cell, by typing the name of a variable or clicking a variable from a drop-down list in a cell.</span></span>  
  
3.  <span data-ttu-id="148cb-115">若要配置**调用 Orchestration**调整根据服务和在对话框中指定的自变量，请单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="148cb-115">To configure the **Call Orchestration** shape according to the service and arguments that you specified in the dialog box, click **OK**.</span></span> <span data-ttu-id="148cb-116">若要关闭**调用业务流程配置**对话框，而不进行任何更改到**调用 Orchestration**形状，请单击**取消**。</span><span class="sxs-lookup"><span data-stu-id="148cb-116">To close the **Call Orchestration Configuration** dialog box without making any changes to the **Call Orchestration** shape, click **Cancel**.</span></span>  
  
    > [!CAUTION]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="148cb-117">不支持递归业务流程。</span><span class="sxs-lookup"><span data-stu-id="148cb-117"> does not support recursive orchestrations.</span></span> <span data-ttu-id="148cb-118">如果业务流程 A 调用或启动业务流程 B，则业务流程 B 既无法直接调用或启动业务流程 A，也无法调用或启动直接或间接调用业务流程 A 的任何业务流程。</span><span class="sxs-lookup"><span data-stu-id="148cb-118">If Orchestration A calls or starts Orchestration B, then Orchestration B cannot call or start Orchestration A directly, nor can it call or start any orchestration that directly or indirectly calls Orchestration A.</span></span>  
  
## <a name="referenced-orchestrations"></a><span data-ttu-id="148cb-119">引用的业务流程</span><span class="sxs-lookup"><span data-stu-id="148cb-119">Referenced Orchestrations</span></span>  
 <span data-ttu-id="148cb-120">为使引用的业务流程可调用，请确保为调用的业务流程配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="148cb-120">For the referenced orchestration to be callable, ensure that the following properties have been configured for the called orchestration:</span></span>  
  
-   <span data-ttu-id="148cb-121">设置**类型修饰符**属性**公共**调用业务流程。</span><span class="sxs-lookup"><span data-stu-id="148cb-121">Set the **Type Modifier** property to **Public** for the called orchestration.</span></span> <span data-ttu-id="148cb-122">若要设置**类型修饰符**属性的业务流程**公共**，在 Microsoft 中打开业务流程[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，单击顶部的业务流程，以显示绿色启动形状**业务流程属性**对话框并设置**类型修饰符**属性**公共**。</span><span class="sxs-lookup"><span data-stu-id="148cb-122">To set the **Type Modifier** property for an orchestration to **Public**, open the orchestration in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], click the green start shape at the top of the orchestration to display the **Orchestration Properties** dialog and set the **Type Modifier** property to **Public**.</span></span>  
  
-   <span data-ttu-id="148cb-123">设置**激活**属性中的业务流程的初始接收形状**False**。</span><span class="sxs-lookup"><span data-stu-id="148cb-123">Set the **Activate** property of the initial receive shape in the orchestration to **False**.</span></span>  
  
## <a name="orchestration-selection-drop-down-list-box"></a><span data-ttu-id="148cb-124">“业务流程选择”下拉列表框</span><span class="sxs-lookup"><span data-stu-id="148cb-124">Orchestration Selection drop-down list box</span></span>  
 <span data-ttu-id="148cb-125">单击该下拉列表框中的下箭头可以查看可用服务并进行选择。</span><span class="sxs-lookup"><span data-stu-id="148cb-125">Click the Down arrow in the drop-down list box to view available services and select one.</span></span> <span data-ttu-id="148cb-126">下表包含可从当前业务流程中调用的所有服务，包括引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="148cb-126">This list contains all the services that can be called from the current orchestration, including referenced assemblies.</span></span>  
  
## <a name="orchestration-parameters-grid-control"></a><span data-ttu-id="148cb-127">“业务流程参数”网格控件</span><span class="sxs-lookup"><span data-stu-id="148cb-127">Orchestration Parameters grid control</span></span>  
 <span data-ttu-id="148cb-128">指定要传递到参数化的业务流程，通过使用参数**业务流程参数**网格控件。</span><span class="sxs-lookup"><span data-stu-id="148cb-128">You specify the arguments to pass to a parameterized orchestration by using the **Orchestration Parameters** grid control.</span></span> <span data-ttu-id="148cb-129">网格包含四列： 作用域、 参数名称、 参数类型和参数方向中的变量。</span><span class="sxs-lookup"><span data-stu-id="148cb-129">The grid has four columns: Variables in Scope, Parameter Name, Parameter Type, and Parameter Direction.</span></span> <span data-ttu-id="148cb-130">您只能对第一列进行更改；其他列是只读的。</span><span class="sxs-lookup"><span data-stu-id="148cb-130">You can make changes only in the first column; the other columns are read-only.</span></span>  
  
 <span data-ttu-id="148cb-131">当你选择有效的业务流程时，其参数填充参数名称、 类型和方向列的网格控件。</span><span class="sxs-lookup"><span data-stu-id="148cb-131">When you select a valid orchestration, its parameters populate the parameter name, type and direction columns of the grid control.</span></span> <span data-ttu-id="148cb-132">然后，您可以选择每一行中要作为参数传递的变量。</span><span class="sxs-lookup"><span data-stu-id="148cb-132">You then select the variables in each row to pass as arguments.</span></span> <span data-ttu-id="148cb-133">您从“作用域中的变量”列的各单元格上的下拉列表中选择这些变量。</span><span class="sxs-lookup"><span data-stu-id="148cb-133">You select these variables from a drop-down list present in each cell in the Variables in Scope column.</span></span> <span data-ttu-id="148cb-134">此列表显示在相邻的“参数类型”单元格中指定的类型的所有可用变量。</span><span class="sxs-lookup"><span data-stu-id="148cb-134">This list displays all the available variables of the type specified in the adjacent Parameter Type cell.</span></span> <span data-ttu-id="148cb-135">如果该类型只有一个对象可用，将自动用该对象填充“作用域中的变量”单元格。</span><span class="sxs-lookup"><span data-stu-id="148cb-135">If only one object of that type is available, the Variables in Scope cell is automatically populated with that object.</span></span> <span data-ttu-id="148cb-136">您还可以在“作用域中的变量”单元格中键入，以便选择在该下拉列表中提供的变量。</span><span class="sxs-lookup"><span data-stu-id="148cb-136">You can also type in a Variables in Scope cell to select a variable that is available in the drop-down list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="148cb-137">因为**调用 Orchestration**形状调用业务流程，在此对话框中选择"Orchestration Parameters"实际上指业务流程变量。</span><span class="sxs-lookup"><span data-stu-id="148cb-137">Because a **Call Orchestration** shape calls an orchestration, the "Orchestration Parameters" you select in this dialog box actually refer to orchestration variables.</span></span>  
  
 <span data-ttu-id="148cb-138">如果您在调用的业务流程没有定义的参数，则该对话框中的网格控件将不可用。</span><span class="sxs-lookup"><span data-stu-id="148cb-138">If an orchestration you are calling has no defined parameters, the grid control in this dialog box is unavailable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="148cb-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="148cb-139">See Also</span></span>  
 [<span data-ttu-id="148cb-140">如何配置开始业务流程形状</span><span class="sxs-lookup"><span data-stu-id="148cb-140">How to Configure the Start Orchestration Shape</span></span>](../core/how-to-configure-the-start-orchestration-shape.md)