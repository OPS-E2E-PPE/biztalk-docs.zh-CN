---
title: "如何配置接收形状 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- filter expressions, Receive shape [Orchestration Designer]
- Receive shape [Orchestration Designer], about Receive shape
- configuring [Orchestration Designer], Receive shapes
- Receive shape [Orchestration Designer]
- Receive shape [Orchestration Designer], filter expressions
ms.assetid: 15aadee4-fa05-4edd-a191-e4d191c1ea22
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e74220ab71c0efcc09e1736511e8388de71f387
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-the-receive-shape"></a><span data-ttu-id="0b4db-102">如何配置接收形状</span><span class="sxs-lookup"><span data-stu-id="0b4db-102">How to Configure the Receive Shape</span></span>
<span data-ttu-id="0b4db-103">![](../core/media/ebiz-orch-receive.gif "ebiz_orch_receive")</span><span class="sxs-lookup"><span data-stu-id="0b4db-103">![](../core/media/ebiz-orch-receive.gif "ebiz_orch_receive")</span></span>  
<span data-ttu-id="0b4db-104">接收形状</span><span class="sxs-lookup"><span data-stu-id="0b4db-104">Receive shape</span></span>  
  
 <span data-ttu-id="0b4db-105">A**接收**形状可以用于启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="0b4db-105">A **Receive** shape can be used to start an orchestration.</span></span> <span data-ttu-id="0b4db-106">如果你设置**激活**属性**True**，运行时引擎将测试传入消息以查看是否它是正确的类型，如果已应用筛选器，筛选器表达式是满足的条件。</span><span class="sxs-lookup"><span data-stu-id="0b4db-106">If you set the **Activate** property to **True**, the runtime engine will test an incoming message to see whether it is of the right type and, if a filter has been applied, whether the filter expression is satisfied.</span></span> <span data-ttu-id="0b4db-107">如果满足收到消息的条件，则运行时引擎创建并运行新的业务流程实例，与**接收**形状接收消息。</span><span class="sxs-lookup"><span data-stu-id="0b4db-107">If the criteria for receipt of the message are met, the runtime engine creates and runs a new orchestration instance, and the **Receive** shape receives the message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b4db-108">如果**激活**接收形状的属性设置为 True，**接收**必须是业务流程中的第一个操作。</span><span class="sxs-lookup"><span data-stu-id="0b4db-108">If the **Activate** property of a Receive shape is set to True, the **Receive** must be the first action in the orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b4db-109">如果**激活**属性设置为 False 上所有**接收**形状，您的业务流程必须由调用另一个业务流程才能运行。</span><span class="sxs-lookup"><span data-stu-id="0b4db-109">If the **Activate** property is set to False on all **Receive** shapes, your orchestration must be called by another orchestration in order to run.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b4db-110">如果将放**接收**具有的作用域内的形状**激活**属性设置为**True**，然后将.NET 类变量而无需更改添加到您的业务流程变量的**使用默认构造函数**属性**False**、 激活接收语句将外部的作用域内生成的 XLANG/S 代码，但是，设计图面将继续到为该范围中显示它。</span><span class="sxs-lookup"><span data-stu-id="0b4db-110">If you put a **Receive** shape inside a scope with the **Activate** property set to **True**, and then add a .NET Class variable to your orchestration without changing the variable's **Use Default Constructor** property to **False**, the activate receive statement will be outside of the scope in the generated XLANG/S code, but the design surface will continue to show it as being inside the scope.</span></span>  
  
 <span data-ttu-id="0b4db-111">每个业务流程必须至少一个**接收**调整与**激活**属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="0b4db-111">Each orchestration must have at least one **Receive** shape with the **Activate** property set to **True**.</span></span>  
  
 <span data-ttu-id="0b4db-112">对于以前已发送的消息，如果希望接收到间接或异步响应（不在请求-响应端口上），则需要将该消息与当前正在运行的业务流程实例相关联，以便响应者可以获得对正确实例的响应。</span><span class="sxs-lookup"><span data-stu-id="0b4db-112">If you expect to receive an indirect or asynchronous response (not on a request-response port) to a message that you have previously sent, you need to correlate the message with the currently running instance of the orchestration, so that the respondent can get the response to the correct instance.</span></span> <span data-ttu-id="0b4db-113">如果您计划继续对传入消息中的值进行关联，则可以对接收形状应用初始化相关集，或者您也可以应用沿用相关集，以便使用以前初始化的相关集进行关联。</span><span class="sxs-lookup"><span data-stu-id="0b4db-113">You can apply an initializing correlation set to the Receive shape if you plan to do subsequent correlation on values in the incoming message, or a following correlation set for correlating using a previously initialized correlation set.</span></span> <span data-ttu-id="0b4db-114">有关详细信息，请参阅[在业务流程中使用相关性](../core/using-correlations-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="0b4db-114">For more information, see [Using Correlations in Orchestrations](../core/using-correlations-in-orchestrations.md).</span></span>  
  
### <a name="to-configure-a-receive-shape"></a><span data-ttu-id="0b4db-115">配置接收形状</span><span class="sxs-lookup"><span data-stu-id="0b4db-115">To configure a Receive shape</span></span>  
  
1.  <span data-ttu-id="0b4db-116">设置消息和端口操作。</span><span class="sxs-lookup"><span data-stu-id="0b4db-116">Set a message and a port operation.</span></span>  
  
    1.  <span data-ttu-id="0b4db-117">在“业务流程视图”窗口中，确认您的业务流程具有消息以及为要接收的消息类型定义的端口操作。</span><span class="sxs-lookup"><span data-stu-id="0b4db-117">In the Orchestration View window, verify that your orchestration has both a message and a port operation defined for the message type being received.</span></span>  
  
         <span data-ttu-id="0b4db-118">在属性窗口中，选择要从接收的消息**消息**属性下拉列表。</span><span class="sxs-lookup"><span data-stu-id="0b4db-118">In the Properties window, select the message to receive from the **Message** property drop-down list.</span></span>  
  
    2.  <span data-ttu-id="0b4db-119">在属性窗口中，选择要接收来自的消息的端口操作**操作**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="0b4db-119">In the Properties window, select the port operation to receive the message from the **Operation** drop-down list.</span></span>  
  
         <span data-ttu-id="0b4db-120">-或者-</span><span class="sxs-lookup"><span data-stu-id="0b4db-120">—Or—</span></span>  
  
         <span data-ttu-id="0b4db-121">将从接收连接线**接收**对端口套接字将接收消息的形状。</span><span class="sxs-lookup"><span data-stu-id="0b4db-121">Drag the receive connector from the **Receive** shape to the port socket that will receive the message.</span></span>  
  
2.  <span data-ttu-id="0b4db-122">指定**接收**形状将激活业务流程。</span><span class="sxs-lookup"><span data-stu-id="0b4db-122">Specify that the **Receive** shape will activate the orchestration.</span></span>  
  
3.  <span data-ttu-id="0b4db-123">在“属性”窗口中，将“激活”属性设置为 True。</span><span class="sxs-lookup"><span data-stu-id="0b4db-123">In the Properties window, set the Activate property to True.</span></span>  
  
    1.  <span data-ttu-id="0b4db-124">在属性窗口中，单击**省略号**(**...**) 要创建筛选器来限制的消息的筛选器表达式属性的按钮此**接收**形状接受。</span><span class="sxs-lookup"><span data-stu-id="0b4db-124">In the Properties window, click the **Ellipsis** (**...**) button for the Filter Expression property to create a filter to restrict the messages that this **Receive** shape accepts.</span></span>  
  
         <span data-ttu-id="0b4db-125">-或者-</span><span class="sxs-lookup"><span data-stu-id="0b4db-125">—Or—</span></span>  
  
         <span data-ttu-id="0b4db-126">右键单击**接收**形状，然后单击**编辑筛选器表达式**。</span><span class="sxs-lookup"><span data-stu-id="0b4db-126">Right-click the **Receive** shape and then click **Edit Filter Expression**.</span></span>  
  
    2.  <span data-ttu-id="0b4db-127">**筛选器表达式**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="0b4db-127">The **Filter Expression** dialog box appears.</span></span> <span data-ttu-id="0b4db-128">使用该对话框可以创建一个或多个筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="0b4db-128">Use this dialog box to create one or more filter expressions.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0b4db-129">必须定义消息类型，并将其分配给**接收**调整之前可以将筛选器应用于它。</span><span class="sxs-lookup"><span data-stu-id="0b4db-129">A message type must be defined and assigned to the **Receive** shape before you can apply a filter to it.</span></span>  
  
4.  <span data-ttu-id="0b4db-130">指定相关设置来限制的消息**接收**形状接受。</span><span class="sxs-lookup"><span data-stu-id="0b4db-130">Specify correlation sets to restrict the messages the **Receive** shape accepts.</span></span>  
  
    -   <span data-ttu-id="0b4db-131">你想要遵照每个关联集，请检查关联集从下拉列表上**以下相关集**属性。</span><span class="sxs-lookup"><span data-stu-id="0b4db-131">For each correlation set you want to follow, check a correlation set from the drop-down on the **Following Correlation Sets** property.</span></span>  
  
    -   <span data-ttu-id="0b4db-132">每个相关设置你想要初始化，请从下拉列表设置上一个相关性**初始化关联集**属性。</span><span class="sxs-lookup"><span data-stu-id="0b4db-132">For each correlation set that you want to initialize, check a correlation set from the drop-down on the **Initializing Correlation Sets** property.</span></span>  
  
## <a name="filter-expression-grid-control"></a><span data-ttu-id="0b4db-133">筛选器表达式网格控件</span><span class="sxs-lookup"><span data-stu-id="0b4db-133">Filter Expression grid control</span></span>  
 <span data-ttu-id="0b4db-134">您可以通过使用此网格控件来定义构成表达式的谓词，生成筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="0b4db-134">You build a filter expression by using this grid control to define the predicates that make up the expression.</span></span> <span data-ttu-id="0b4db-135">您还可以从网格的单元格中添加、编辑和删除谓词。</span><span class="sxs-lookup"><span data-stu-id="0b4db-135">You can add, edit, and delete predicates from the cells of the grid.</span></span> <span data-ttu-id="0b4db-136">此网格控件有四列： 属性、 运算符、 值和分组。</span><span class="sxs-lookup"><span data-stu-id="0b4db-136">This grid control has four columns: Property, Operator, Value, and Grouping.</span></span>  
  
-   <span data-ttu-id="0b4db-137">**属性。**</span><span class="sxs-lookup"><span data-stu-id="0b4db-137">**Property.**</span></span> <span data-ttu-id="0b4db-138">您可以键入某一属性引用，或者从单元格的下拉列表中选择一个属性。</span><span class="sxs-lookup"><span data-stu-id="0b4db-138">You can type a property reference, or select one from the cell's drop-down list.</span></span> <span data-ttu-id="0b4db-139">该列表包含传入消息的属性。</span><span class="sxs-lookup"><span data-stu-id="0b4db-139">The list contains properties on the incoming message.</span></span>  
  
-   <span data-ttu-id="0b4db-140">**运算符。**</span><span class="sxs-lookup"><span data-stu-id="0b4db-140">**Operator.**</span></span> <span data-ttu-id="0b4db-141">您可以在此单元格中键入某一运算符，或者从下拉列表中选择一个运算符。</span><span class="sxs-lookup"><span data-stu-id="0b4db-141">You can type in this cell, or select an operator from the drop-down list.</span></span> <span data-ttu-id="0b4db-142">可能的选项包括：</span><span class="sxs-lookup"><span data-stu-id="0b4db-142">Possible selections are:</span></span>  
  
    |<span data-ttu-id="0b4db-143">操作数</span><span class="sxs-lookup"><span data-stu-id="0b4db-143">Operand</span></span>|<span data-ttu-id="0b4db-144">含义</span><span class="sxs-lookup"><span data-stu-id="0b4db-144">Meaning</span></span>|  
    |-------------|-------------|  
    |==|<span data-ttu-id="0b4db-145">等于</span><span class="sxs-lookup"><span data-stu-id="0b4db-145">Is equal to</span></span>|  
    |<span data-ttu-id="0b4db-146">!=</span><span class="sxs-lookup"><span data-stu-id="0b4db-146">!=</span></span>|<span data-ttu-id="0b4db-147">不等于</span><span class="sxs-lookup"><span data-stu-id="0b4db-147">Is not equal to</span></span>|  
    |<|<span data-ttu-id="0b4db-148">小于</span><span class="sxs-lookup"><span data-stu-id="0b4db-148">Is less than</span></span>|  
    |\<=|<span data-ttu-id="0b4db-149">小于或等于</span><span class="sxs-lookup"><span data-stu-id="0b4db-149">Is less than or equal to</span></span>|  
    |>|<span data-ttu-id="0b4db-150">大于</span><span class="sxs-lookup"><span data-stu-id="0b4db-150">Is greater than</span></span>|  
    |\>=|<span data-ttu-id="0b4db-151">大于或等于</span><span class="sxs-lookup"><span data-stu-id="0b4db-151">Is greater than or equal to</span></span>|  
    |<span data-ttu-id="0b4db-152">Exists</span><span class="sxs-lookup"><span data-stu-id="0b4db-152">Exists</span></span>|<span data-ttu-id="0b4db-153">Exists</span><span class="sxs-lookup"><span data-stu-id="0b4db-153">Exists</span></span>|  
  
-   <span data-ttu-id="0b4db-154">**值。**</span><span class="sxs-lookup"><span data-stu-id="0b4db-154">**Value.**</span></span> <span data-ttu-id="0b4db-155">中的单元格**值**列所能容纳中键入任何常量： 字符串文本、 整数文字，则为 null。</span><span class="sxs-lookup"><span data-stu-id="0b4db-155">Cells in the **Value** column can hold any constant that you type in: a string-literal, an integer-literal, or null.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0b4db-156">如果选择的属性为字符串类型，则需要用引号将该值括起来。</span><span class="sxs-lookup"><span data-stu-id="0b4db-156">If the property selected is of type string, the value needs to be in quotes.</span></span> <span data-ttu-id="0b4db-157">例如 SMTP.From = "MyServer"。</span><span class="sxs-lookup"><span data-stu-id="0b4db-157">For example, SMTP.From = "MyServer".</span></span>  
  
-   <span data-ttu-id="0b4db-158">**分组。**</span><span class="sxs-lookup"><span data-stu-id="0b4db-158">**Grouping.**</span></span> <span data-ttu-id="0b4db-159">使用此列可控制谓词分组。</span><span class="sxs-lookup"><span data-stu-id="0b4db-159">Use this column to control predicate grouping.</span></span> <span data-ttu-id="0b4db-160">筛选器表达式始终用析取范式 (DNF) 形式表示，因此可以自动确定分组。</span><span class="sxs-lookup"><span data-stu-id="0b4db-160">Filter expressions are always expressed in Disjunctive Normal Form (DNF) so grouping can be determined automatically.</span></span> <span data-ttu-id="0b4db-161">AND 表示谓词要与其后的谓词分在一组，而 OR 表示该谓词与下一行中的谓词相互独立。</span><span class="sxs-lookup"><span data-stu-id="0b4db-161">AND means the predicate is to be grouped with the predicate following it, while OR means the predicate is separate from the predicate in the next row.</span></span> <span data-ttu-id="0b4db-162">将谓词组合在一起后，网格控件的左侧将显示灰色括号。</span><span class="sxs-lookup"><span data-stu-id="0b4db-162">Gray brackets to the left of the grid control appear when predicates are grouped together.</span></span> <span data-ttu-id="0b4db-163">谓词组不能嵌套。</span><span class="sxs-lookup"><span data-stu-id="0b4db-163">Predicate groups cannot be nested.</span></span> <span data-ttu-id="0b4db-164">如果您不在此单元格中指定值，则该单元格默认的值为 AND。</span><span class="sxs-lookup"><span data-stu-id="0b4db-164">If you do not specify a value in this cell, the value of the cell defaults to AND.</span></span>  
  
 <span data-ttu-id="0b4db-165">例如，您可以创建如下所示的表达式：</span><span class="sxs-lookup"><span data-stu-id="0b4db-165">For example, you might create an expression like the following:</span></span>  
  
 `MSMQ.MsgID = 1`  
  
 <span data-ttu-id="0b4db-166">使用此筛选器，发送端口组将只订阅 MSMQ 消息 ID 为 1 的消息。</span><span class="sxs-lookup"><span data-stu-id="0b4db-166">With this filter, the send port group would only subscribe to messages having an MSMQ message ID of 1.</span></span>  
  
 <span data-ttu-id="0b4db-167">您可以创建其他表达式，并指定该表达式与其他表达式有 AND 或 OR 关系，例如：</span><span class="sxs-lookup"><span data-stu-id="0b4db-167">You can create additional expressions and specify that they have an AND or OR relationship with other expressions, for example:</span></span>  
  
 `MSMQ.MsgID = 1 OR`  
  
 `SMTP.From = "MyServer"`  
  
 <span data-ttu-id="0b4db-168">在这种情况下，发送端口组将订阅 MSMQ 消息 ID 为 1 或发自名为 MyServer 的 SMTP 服务器的所有消息。</span><span class="sxs-lookup"><span data-stu-id="0b4db-168">In this case, the send port group would subscribe to all messages that have either an MSMQ message ID of 1 or that have been sent from the SMTP server named MyServer.</span></span>  
  
## <a name="hint-label"></a><span data-ttu-id="0b4db-169">提示标签</span><span class="sxs-lookup"><span data-stu-id="0b4db-169">Hint label</span></span>  
 <span data-ttu-id="0b4db-170">该字段提供用户指导。</span><span class="sxs-lookup"><span data-stu-id="0b4db-170">This field provides user guidance.</span></span> <span data-ttu-id="0b4db-171">标签文本将根据包含活动单元格的列而变化。</span><span class="sxs-lookup"><span data-stu-id="0b4db-171">The label text changes depending on which column contains the active cell.</span></span> <span data-ttu-id="0b4db-172">标签文本将显示列名称，后随如下指导文本：</span><span class="sxs-lookup"><span data-stu-id="0b4db-172">The text displays the column name followed by guidance text as follows:</span></span>  
  
-   <span data-ttu-id="0b4db-173">**属性。**</span><span class="sxs-lookup"><span data-stu-id="0b4db-173">**Property.**</span></span> <span data-ttu-id="0b4db-174">请从列表中选择传入消息的属性。</span><span class="sxs-lookup"><span data-stu-id="0b4db-174">Please select a property on the incoming message from the list.</span></span>  
  
-   <span data-ttu-id="0b4db-175">**运算符。**</span><span class="sxs-lookup"><span data-stu-id="0b4db-175">**Operator.**</span></span> <span data-ttu-id="0b4db-176">选择用于将属性与值进行比较的运算符。</span><span class="sxs-lookup"><span data-stu-id="0b4db-176">Select an operator to compare the Property with the Value.</span></span>  
  
-   <span data-ttu-id="0b4db-177">**值。**</span><span class="sxs-lookup"><span data-stu-id="0b4db-177">**Value.**</span></span> <span data-ttu-id="0b4db-178">从列表中选择某一消息属性，或者键入文本值。</span><span class="sxs-lookup"><span data-stu-id="0b4db-178">Select a message property from the list, or type in a literal value.</span></span>  
  
-   <span data-ttu-id="0b4db-179">**分组。**</span><span class="sxs-lookup"><span data-stu-id="0b4db-179">**Grouping.**</span></span> <span data-ttu-id="0b4db-180">指定此行要如何与下一行组合在一起。</span><span class="sxs-lookup"><span data-stu-id="0b4db-180">Specify how this row is to be grouped with the next row.</span></span> <span data-ttu-id="0b4db-181">“AND”将连接行，而“OR”将分隔行。</span><span class="sxs-lookup"><span data-stu-id="0b4db-181">'AND' will join the rows, and 'OR' will separate them.</span></span>  
  
## <a name="move-up-button"></a><span data-ttu-id="0b4db-182">“上移”按钮</span><span class="sxs-lookup"><span data-stu-id="0b4db-182">Move Up button</span></span>  
 <span data-ttu-id="0b4db-183">单击此按钮可以将所选行上移。</span><span class="sxs-lookup"><span data-stu-id="0b4db-183">Click this to move a selected row up.</span></span> <span data-ttu-id="0b4db-184">(第一次通过单击选择一行*右箭头*(**>)**网格控件的左侧的按钮。)</span><span class="sxs-lookup"><span data-stu-id="0b4db-184">(First select a row by clicking the *right arrow* (**>)** button at the left side of the grid control.)</span></span>  
  
## <a name="move-down-button"></a><span data-ttu-id="0b4db-185">“下移”按钮</span><span class="sxs-lookup"><span data-stu-id="0b4db-185">Move Down button</span></span>  
 <span data-ttu-id="0b4db-186">单击此按钮可以将所选行下移。</span><span class="sxs-lookup"><span data-stu-id="0b4db-186">Click this to move a selected row down.</span></span> <span data-ttu-id="0b4db-187">(第一次通过单击选择一行*右箭头*(**>)**网格控件的左侧的按钮。)</span><span class="sxs-lookup"><span data-stu-id="0b4db-187">(First select a row by clicking the *right arrow* (**>)** button at the left side of the grid control.)</span></span>  
  
## <a name="filter-expression-created-field"></a><span data-ttu-id="0b4db-188">“创建的筛选器表达式”字段</span><span class="sxs-lookup"><span data-stu-id="0b4db-188">Filter Expression Created field</span></span>  
 <span data-ttu-id="0b4db-189">此只读文本框将随着您生成表达式而显示该表达式。</span><span class="sxs-lookup"><span data-stu-id="0b4db-189">This read-only text box shows the expression as you are building it.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0b4db-190">本节内容</span><span class="sxs-lookup"><span data-stu-id="0b4db-190">In This Section</span></span>  
 [<span data-ttu-id="0b4db-191">使用带接收消息形状的筛选器</span><span class="sxs-lookup"><span data-stu-id="0b4db-191">Using Filters With the Receive Message Shape</span></span>](../core/using-filters-with-the-receive-message-shape.md)