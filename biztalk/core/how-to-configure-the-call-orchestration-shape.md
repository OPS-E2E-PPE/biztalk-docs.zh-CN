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
ms.openlocfilehash: f20025f771f28f91e1fe40b10bfc0e999685eb68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386118"
---
# <a name="how-to-configure-the-call-orchestration-shape"></a><span data-ttu-id="466c0-102">如何配置调用业务流程形状</span><span class="sxs-lookup"><span data-stu-id="466c0-102">How to Configure the Call Orchestration Shape</span></span>
<span data-ttu-id="466c0-103">**调用业务流程**形状可用于同步调用另一个项目中引用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="466c0-103">The **Call Orchestration** shape can be used to synchronously call an orchestration that is referenced in another project.</span></span> <span data-ttu-id="466c0-104">这允许重复使用常见的业务流程工作流模式的多个 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="466c0-104">This allows for reuse of common orchestration workflow patterns across BizTalk projects.</span></span> <span data-ttu-id="466c0-105">调用以同步方式与另一个嵌套的业务流程时**调用业务流程**等到嵌套的业务流程完成后才能继续的封闭的业务流程的形状。</span><span class="sxs-lookup"><span data-stu-id="466c0-105">When you invoke another nested orchestration synchronously with the **Call Orchestration** shape the enclosing orchestration waits for the nested orchestration to finish before continuing.</span></span>  
  
 <span data-ttu-id="466c0-106">您可以指定将传递给嵌套的业务流程的参数。</span><span class="sxs-lookup"><span data-stu-id="466c0-106">You can specify parameters that will be passed to the nested orchestration.</span></span> <span data-ttu-id="466c0-107">参数可以是消息、 变量、 端口引用、 角色链接或相关集。</span><span class="sxs-lookup"><span data-stu-id="466c0-107">Parameters can be messages, variables, port references, role links, or correlation sets.</span></span> <span data-ttu-id="466c0-108">传入的端口引用、 角色链接和相关集所有像自寻址的信封一样执行： 它们提供可用于将信息发送回封闭业务流程的嵌套的业务流程信息。</span><span class="sxs-lookup"><span data-stu-id="466c0-108">Passed-in port references, role links, and correlation sets all perform like self-addressed envelopes: they supply the nested orchestration information it can use to send information back to the enclosing orchestration.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="466c0-109">如果将不可序列化对象，例如 XmlDocument 或 XmlNode 作为参数传递给业务流程中，它将失败。</span><span class="sxs-lookup"><span data-stu-id="466c0-109">If you pass nonserializable objects such as XmlDocument or XmlNode as parameters to an orchestration, it will fail.</span></span>  
  
 <span data-ttu-id="466c0-110">有关如何使用的示例**调用业务流程**形状中，请参阅[CallOrchestration （BizTalk Server 示例）](../core/callorchestration-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="466c0-110">For an example of how to use **Call Orchestration** shape, see [CallOrchestration (BizTalk Server Sample)](../core/callorchestration-biztalk-server-sample.md).</span></span>  
  
### <a name="to-configure-a-call-orchestration-shape"></a><span data-ttu-id="466c0-111">若要配置调用业务流程形状</span><span class="sxs-lookup"><span data-stu-id="466c0-111">To configure a Call Orchestration shape</span></span>  
  
1. <span data-ttu-id="466c0-112">使用**业务流程选择**下拉列表框中，选择某一业务流程从列表中。</span><span class="sxs-lookup"><span data-stu-id="466c0-112">Using the **Orchestration Selection** drop-down list box, select an orchestration from the list.</span></span>  
  
2. <span data-ttu-id="466c0-113">使用**业务流程参数**网格控件，指定要传递到业务流程参数 — 中指定的那样**业务流程选择**下拉列表框中，可调用。</span><span class="sxs-lookup"><span data-stu-id="466c0-113">Using the **Orchestration Parameters** grid control, specify arguments to pass to the orchestration—as specified in the **Orchestration Selection** drop-down list box—that is called.</span></span> <span data-ttu-id="466c0-114">通过键入变量名称或单击单元格中下拉列表中的某个变量的变量的列中，每个单元格，一个变量单元格中指定这些参数。</span><span class="sxs-lookup"><span data-stu-id="466c0-114">You specify these arguments in the cells of the Variable column, one variable per cell, by typing the name of a variable or clicking a variable from a drop-down list in a cell.</span></span>  
  
3. <span data-ttu-id="466c0-115">若要配置**调用业务流程**形状根据服务和对话框中指定的参数，请单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="466c0-115">To configure the **Call Orchestration** shape according to the service and arguments that you specified in the dialog box, click **OK**.</span></span> <span data-ttu-id="466c0-116">若要关闭**调用业务流程配置**对话框，但不进行任何更改**调用业务流程**形状，请单击**取消**。</span><span class="sxs-lookup"><span data-stu-id="466c0-116">To close the **Call Orchestration Configuration** dialog box without making any changes to the **Call Orchestration** shape, click **Cancel**.</span></span>  
  
   > [!CAUTION]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="466c0-117">不支持递归业务流程。</span><span class="sxs-lookup"><span data-stu-id="466c0-117">does not support recursive orchestrations.</span></span> <span data-ttu-id="466c0-118">如果业务流程 A 调用或启动业务流程 B，然后业务流程 B 不能调用或启动业务流程 A 直接，也可以调用或启动任何直接或间接调用业务流程 A 的业务流程</span><span class="sxs-lookup"><span data-stu-id="466c0-118">If Orchestration A calls or starts Orchestration B, then Orchestration B cannot call or start Orchestration A directly, nor can it call or start any orchestration that directly or indirectly calls Orchestration A.</span></span>  
  
## <a name="referenced-orchestrations"></a><span data-ttu-id="466c0-119">引用的业务流程</span><span class="sxs-lookup"><span data-stu-id="466c0-119">Referenced Orchestrations</span></span>  
 <span data-ttu-id="466c0-120">可调用的被引用业务流程，请确保已为调用的业务流程配置了以下属性：</span><span class="sxs-lookup"><span data-stu-id="466c0-120">For the referenced orchestration to be callable, ensure that the following properties have been configured for the called orchestration:</span></span>  
  
- <span data-ttu-id="466c0-121">设置**的类型修饰符**属性设置为**公共**的调用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="466c0-121">Set the **Type Modifier** property to **Public** for the called orchestration.</span></span> <span data-ttu-id="466c0-122">若要设置**的类型修饰符**到业务流程的属性**公共**，在 Microsoft 中打开该业务流程[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，单击顶部的业务流程以显示绿色启动形状**业务流程属性**对话框并设置**的类型修饰符**属性设置为**公共**。</span><span class="sxs-lookup"><span data-stu-id="466c0-122">To set the **Type Modifier** property for an orchestration to **Public**, open the orchestration in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], click the green start shape at the top of the orchestration to display the **Orchestration Properties** dialog and set the **Type Modifier** property to **Public**.</span></span>  
  
- <span data-ttu-id="466c0-123">设置**激活**属性中的业务流程的初始接收形状**False**。</span><span class="sxs-lookup"><span data-stu-id="466c0-123">Set the **Activate** property of the initial receive shape in the orchestration to **False**.</span></span>  
  
## <a name="orchestration-selection-drop-down-list-box"></a><span data-ttu-id="466c0-124">业务流程选择下拉列表框</span><span class="sxs-lookup"><span data-stu-id="466c0-124">Orchestration Selection drop-down list box</span></span>  
 <span data-ttu-id="466c0-125">单击以查看可用的服务并进行选择的下拉列表框中的下箭头。</span><span class="sxs-lookup"><span data-stu-id="466c0-125">Click the Down arrow in the drop-down list box to view available services and select one.</span></span> <span data-ttu-id="466c0-126">此列表包含可以从当前业务流程，其中包括被引用程序集调用的所有服务。</span><span class="sxs-lookup"><span data-stu-id="466c0-126">This list contains all the services that can be called from the current orchestration, including referenced assemblies.</span></span>  
  
## <a name="orchestration-parameters-grid-control"></a><span data-ttu-id="466c0-127">业务流程参数网格控件</span><span class="sxs-lookup"><span data-stu-id="466c0-127">Orchestration Parameters grid control</span></span>  
 <span data-ttu-id="466c0-128">指定要传递到通过参数化的业务流程使用的参数**业务流程参数**网格控件。</span><span class="sxs-lookup"><span data-stu-id="466c0-128">You specify the arguments to pass to a parameterized orchestration by using the **Orchestration Parameters** grid control.</span></span> <span data-ttu-id="466c0-129">网格具有四列：作用域、 参数名称、 参数类型和参数方向中的变量。</span><span class="sxs-lookup"><span data-stu-id="466c0-129">The grid has four columns: Variables in Scope, Parameter Name, Parameter Type, and Parameter Direction.</span></span> <span data-ttu-id="466c0-130">您可以更改仅在第一列;其他列是只读的。</span><span class="sxs-lookup"><span data-stu-id="466c0-130">You can make changes only in the first column; the other columns are read-only.</span></span>  
  
 <span data-ttu-id="466c0-131">当选择一个有效的业务流程时，其参数将自动填充网格控件的参数名称、 类型和方向列。</span><span class="sxs-lookup"><span data-stu-id="466c0-131">When you select a valid orchestration, its parameters populate the parameter name, type and direction columns of the grid control.</span></span> <span data-ttu-id="466c0-132">然后，作为参数传递每个行中选择变量。</span><span class="sxs-lookup"><span data-stu-id="466c0-132">You then select the variables in each row to pass as arguments.</span></span> <span data-ttu-id="466c0-133">从范围列中的变量中的每个单元中存在的下拉列表中选择这些变量。</span><span class="sxs-lookup"><span data-stu-id="466c0-133">You select these variables from a drop-down list present in each cell in the Variables in Scope column.</span></span> <span data-ttu-id="466c0-134">此列表显示在相邻的参数类型单元格中指定的类型的所有可用的变量。</span><span class="sxs-lookup"><span data-stu-id="466c0-134">This list displays all the available variables of the type specified in the adjacent Parameter Type cell.</span></span> <span data-ttu-id="466c0-135">如果只有一个该类型的对象不可用，该对象自动填充范围单元格中的变量。</span><span class="sxs-lookup"><span data-stu-id="466c0-135">If only one object of that type is available, the Variables in Scope cell is automatically populated with that object.</span></span> <span data-ttu-id="466c0-136">此外可以键入单元格中作用域变量，以选择下拉列表中的变量中。</span><span class="sxs-lookup"><span data-stu-id="466c0-136">You can also type in a Variables in Scope cell to select a variable that is available in the drop-down list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="466c0-137">因为**调用业务流程**形状调用业务流程，在此对话框中选择"业务流程参数"实际上表示业务流程变量。</span><span class="sxs-lookup"><span data-stu-id="466c0-137">Because a **Call Orchestration** shape calls an orchestration, the "Orchestration Parameters" you select in this dialog box actually refer to orchestration variables.</span></span>  
  
 <span data-ttu-id="466c0-138">如果正在调用业务流程具有未定义的参数，此对话框中的网格控件将不可用。</span><span class="sxs-lookup"><span data-stu-id="466c0-138">If an orchestration you are calling has no defined parameters, the grid control in this dialog box is unavailable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="466c0-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="466c0-139">See Also</span></span>  
 [<span data-ttu-id="466c0-140">如何配置启动业务流程形状</span><span class="sxs-lookup"><span data-stu-id="466c0-140">How to Configure the Start Orchestration Shape</span></span>](../core/how-to-configure-the-start-orchestration-shape.md)