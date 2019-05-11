---
title: 如何配置接收形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- filter expressions, Receive shape [Orchestration Designer]
- Receive shape [Orchestration Designer], about Receive shape
- configuring [Orchestration Designer], Receive shapes
- Receive shape [Orchestration Designer]
- Receive shape [Orchestration Designer], filter expressions
ms.assetid: 15aadee4-fa05-4edd-a191-e4d191c1ea22
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5169234fd253eaa4819db5edf29f018bae09bb90
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386001"
---
# <a name="how-to-configure-the-receive-shape"></a><span data-ttu-id="dc681-102">如何配置接收形状</span><span class="sxs-lookup"><span data-stu-id="dc681-102">How to Configure the Receive Shape</span></span>
<span data-ttu-id="dc681-103">![](../core/media/ebiz-orch-receive.gif "ebiz_orch_receive")</span><span class="sxs-lookup"><span data-stu-id="dc681-103">![](../core/media/ebiz-orch-receive.gif "ebiz_orch_receive")</span></span>  
<span data-ttu-id="dc681-104">接收形状</span><span class="sxs-lookup"><span data-stu-id="dc681-104">Receive shape</span></span>  

 <span data-ttu-id="dc681-105">一个**接收**形状可用于启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="dc681-105">A **Receive** shape can be used to start an orchestration.</span></span> <span data-ttu-id="dc681-106">如果您设置**激活**属性设置为**True**，运行时引擎将测试传入消息以查看是否属于正确的类型，如果应用了筛选器，筛选器表达式是满足的条件。</span><span class="sxs-lookup"><span data-stu-id="dc681-106">If you set the **Activate** property to **True**, the runtime engine will test an incoming message to see whether it is of the right type and, if a filter has been applied, whether the filter expression is satisfied.</span></span> <span data-ttu-id="dc681-107">如果满足消息接收条件，运行时引擎创建并运行新的业务流程实例，并**接收**形状将接收该消息。</span><span class="sxs-lookup"><span data-stu-id="dc681-107">If the criteria for receipt of the message are met, the runtime engine creates and runs a new orchestration instance, and the **Receive** shape receives the message.</span></span>  

> [!NOTE]
>  <span data-ttu-id="dc681-108">如果**激活**接收形状的属性设置为 True，**接收**必须在业务流程中的第一个操作。</span><span class="sxs-lookup"><span data-stu-id="dc681-108">If the **Activate** property of a Receive shape is set to True, the **Receive** must be the first action in the orchestration.</span></span>  

> [!NOTE]
>  <span data-ttu-id="dc681-109">如果**激活**属性设置为 False 上所有**接收**形状，您的业务流程必须调用由另一个业务流程才能运行。</span><span class="sxs-lookup"><span data-stu-id="dc681-109">If the **Activate** property is set to False on all **Receive** shapes, your orchestration must be called by another orchestration in order to run.</span></span>  

> [!NOTE]
>  <span data-ttu-id="dc681-110">如果将放**接收**内具有的作用域形状**激活**属性设置为**True**，然后将.NET 类变量而无需更改添加到您的业务流程变量的**使用默认构造函数**属性设置为**False**，则激活接收语句将在生成的 XLANG/S 代码中，范围之外但设计图面上也会继续对将其显示为正在该范围中。</span><span class="sxs-lookup"><span data-stu-id="dc681-110">If you put a **Receive** shape inside a scope with the **Activate** property set to **True**, and then add a .NET Class variable to your orchestration without changing the variable's **Use Default Constructor** property to **False**, the activate receive statement will be outside of the scope in the generated XLANG/S code, but the design surface will continue to show it as being inside the scope.</span></span>  

 <span data-ttu-id="dc681-111">每个业务流程必须至少一个**接收**形状和**激活**属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="dc681-111">Each orchestration must have at least one **Receive** shape with the **Activate** property set to **True**.</span></span>  

 <span data-ttu-id="dc681-112">如果想要接收您先前发送的消息 （不在请求-响应端口） 到间接或异步响应，则需要将消息与当前正在运行的业务流程实例相关联，以便响应者可以获得对正确实例的响应。</span><span class="sxs-lookup"><span data-stu-id="dc681-112">If you expect to receive an indirect or asynchronous response (not on a request-response port) to a message that you have previously sent, you need to correlate the message with the currently running instance of the orchestration, so that the respondent can get the response to the correct instance.</span></span> <span data-ttu-id="dc681-113">您可以应用初始化相关集对接收形状，如果你打算对传入消息中的值相关或沿用相关集进行关联使用以前初始化的相关集。</span><span class="sxs-lookup"><span data-stu-id="dc681-113">You can apply an initializing correlation set to the Receive shape if you plan to do subsequent correlation on values in the incoming message, or a following correlation set for correlating using a previously initialized correlation set.</span></span> <span data-ttu-id="dc681-114">有关详细信息，请参阅[业务流程中使用相关性](../core/using-correlations-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="dc681-114">For more information, see [Using Correlations in Orchestrations](../core/using-correlations-in-orchestrations.md).</span></span>  

### <a name="to-configure-a-receive-shape"></a><span data-ttu-id="dc681-115">若要配置接收形状</span><span class="sxs-lookup"><span data-stu-id="dc681-115">To configure a Receive shape</span></span>  

1.  <span data-ttu-id="dc681-116">设置一条消息和端口操作。</span><span class="sxs-lookup"><span data-stu-id="dc681-116">Set a message and a port operation.</span></span>  

    1.  <span data-ttu-id="dc681-117">在业务流程视图窗口中，验证您的业务流程具有一条消息并键入要接收的消息定义的端口操作。</span><span class="sxs-lookup"><span data-stu-id="dc681-117">In the Orchestration View window, verify that your orchestration has both a message and a port operation defined for the message type being received.</span></span>  

         <span data-ttu-id="dc681-118">在属性窗口中，选择要从接收的消息**消息**属性下拉列表。</span><span class="sxs-lookup"><span data-stu-id="dc681-118">In the Properties window, select the message to receive from the **Message** property drop-down list.</span></span>  

    2.  <span data-ttu-id="dc681-119">在属性窗口中，选择要接收的消息的端口操作**操作**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="dc681-119">In the Properties window, select the port operation to receive the message from the **Operation** drop-down list.</span></span>  

         <span data-ttu-id="dc681-120">-或-</span><span class="sxs-lookup"><span data-stu-id="dc681-120">—Or—</span></span>  

         <span data-ttu-id="dc681-121">将从接收连接器拖**接收**形状将接收该消息的端口套接字。</span><span class="sxs-lookup"><span data-stu-id="dc681-121">Drag the receive connector from the **Receive** shape to the port socket that will receive the message.</span></span>  

2.  <span data-ttu-id="dc681-122">指定的**接收**接收形状将激活业务流程。</span><span class="sxs-lookup"><span data-stu-id="dc681-122">Specify that the **Receive** shape will activate the orchestration.</span></span>  

3.  <span data-ttu-id="dc681-123">在属性窗口中，将激活属性设置为 True。</span><span class="sxs-lookup"><span data-stu-id="dc681-123">In the Properties window, set the Activate property to True.</span></span>  

    1.  <span data-ttu-id="dc681-124">在属性窗口中，单击**省略号**(**...**) 按钮以创建一个筛选器以限制的消息的筛选器表达式属性，此**接收**接收形状接受。</span><span class="sxs-lookup"><span data-stu-id="dc681-124">In the Properties window, click the **Ellipsis** (**...**) button for the Filter Expression property to create a filter to restrict the messages that this **Receive** shape accepts.</span></span>  

         <span data-ttu-id="dc681-125">-或-</span><span class="sxs-lookup"><span data-stu-id="dc681-125">—Or—</span></span>  

         <span data-ttu-id="dc681-126">右键单击**接收**形状，然后单击**编辑筛选器表达式**。</span><span class="sxs-lookup"><span data-stu-id="dc681-126">Right-click the **Receive** shape and then click **Edit Filter Expression**.</span></span>  

    2.  <span data-ttu-id="dc681-127">**筛选器表达式**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="dc681-127">The **Filter Expression** dialog box appears.</span></span> <span data-ttu-id="dc681-128">使用此对话框可以创建一个或多个筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="dc681-128">Use this dialog box to create one or more filter expressions.</span></span>  

        > [!NOTE]
        >  <span data-ttu-id="dc681-129">必须定义消息类型，并将其分配给**接收**形状之前可以向其应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="dc681-129">A message type must be defined and assigned to the **Receive** shape before you can apply a filter to it.</span></span>  

4.  <span data-ttu-id="dc681-130">指定相关集来限制的消息**接收**接收形状接受。</span><span class="sxs-lookup"><span data-stu-id="dc681-130">Specify correlation sets to restrict the messages the **Receive** shape accepts.</span></span>  

    -   <span data-ttu-id="dc681-131">你想要按照每个相关集，请检查该相关集从下拉列表**沿用相关集**属性。</span><span class="sxs-lookup"><span data-stu-id="dc681-131">For each correlation set you want to follow, check a correlation set from the drop-down on the **Following Correlation Sets** property.</span></span>  

    -   <span data-ttu-id="dc681-132">有关每个相关集要用于初始化，检查该相关集从下拉列表**初始化相关集**属性。</span><span class="sxs-lookup"><span data-stu-id="dc681-132">For each correlation set that you want to initialize, check a correlation set from the drop-down on the **Initializing Correlation Sets** property.</span></span>  

## <a name="filter-expression-grid-control"></a><span data-ttu-id="dc681-133">筛选器表达式网格控件</span><span class="sxs-lookup"><span data-stu-id="dc681-133">Filter Expression grid control</span></span>  
 <span data-ttu-id="dc681-134">通过使用此网格控件来定义构成表达式的谓词生成筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="dc681-134">You build a filter expression by using this grid control to define the predicates that make up the expression.</span></span> <span data-ttu-id="dc681-135">您可以添加、 编辑和删除谓词中的网格单元格。</span><span class="sxs-lookup"><span data-stu-id="dc681-135">You can add, edit, and delete predicates from the cells of the grid.</span></span> <span data-ttu-id="dc681-136">此网格控件具有四列：属性、 运算符、 值和分组。</span><span class="sxs-lookup"><span data-stu-id="dc681-136">This grid control has four columns: Property, Operator, Value, and Grouping.</span></span>  

- <span data-ttu-id="dc681-137">**属性。**</span><span class="sxs-lookup"><span data-stu-id="dc681-137">**Property.**</span></span> <span data-ttu-id="dc681-138">您可以键入属性的参考信息，或从单元格的下拉列表中选择一个。</span><span class="sxs-lookup"><span data-stu-id="dc681-138">You can type a property reference, or select one from the cell's drop-down list.</span></span> <span data-ttu-id="dc681-139">该列表包含传入消息的属性。</span><span class="sxs-lookup"><span data-stu-id="dc681-139">The list contains properties on the incoming message.</span></span>  

- <span data-ttu-id="dc681-140">**运算符。**</span><span class="sxs-lookup"><span data-stu-id="dc681-140">**Operator.**</span></span> <span data-ttu-id="dc681-141">可以在此单元格中，键入或从下拉列表选择一个运算符。</span><span class="sxs-lookup"><span data-stu-id="dc681-141">You can type in this cell, or select an operator from the drop-down list.</span></span> <span data-ttu-id="dc681-142">可能的选项包括：</span><span class="sxs-lookup"><span data-stu-id="dc681-142">Possible selections are:</span></span>  


  | <span data-ttu-id="dc681-143">操作数</span><span class="sxs-lookup"><span data-stu-id="dc681-143">Operand</span></span> |           <span data-ttu-id="dc681-144">含义</span><span class="sxs-lookup"><span data-stu-id="dc681-144">Meaning</span></span>           |
  |---------|-----------------------------|
  |   ==    |         <span data-ttu-id="dc681-145">等于</span><span class="sxs-lookup"><span data-stu-id="dc681-145">Is equal to</span></span>         |
  |   <span data-ttu-id="dc681-146">!=</span><span class="sxs-lookup"><span data-stu-id="dc681-146">!=</span></span>    |       <span data-ttu-id="dc681-147">不等于</span><span class="sxs-lookup"><span data-stu-id="dc681-147">Is not equal to</span></span>       |
  |    <    |        <span data-ttu-id="dc681-148">小于</span><span class="sxs-lookup"><span data-stu-id="dc681-148">Is less than</span></span>         |
  |   \<=   |  <span data-ttu-id="dc681-149">小于或等于</span><span class="sxs-lookup"><span data-stu-id="dc681-149">Is less than or equal to</span></span>   |
  |    >    |       <span data-ttu-id="dc681-150">大于</span><span class="sxs-lookup"><span data-stu-id="dc681-150">Is greater than</span></span>       |
  |   \>=   | <span data-ttu-id="dc681-151">大于或等于</span><span class="sxs-lookup"><span data-stu-id="dc681-151">Is greater than or equal to</span></span> |
  | <span data-ttu-id="dc681-152">Exists</span><span class="sxs-lookup"><span data-stu-id="dc681-152">Exists</span></span>  |           <span data-ttu-id="dc681-153">Exists</span><span class="sxs-lookup"><span data-stu-id="dc681-153">Exists</span></span>            |


- <span data-ttu-id="dc681-154">**值。**</span><span class="sxs-lookup"><span data-stu-id="dc681-154">**Value.**</span></span> <span data-ttu-id="dc681-155">中的单元格**值**列所能容纳您键入的任何常量： 字符串文本、 整数文字，则为 null。</span><span class="sxs-lookup"><span data-stu-id="dc681-155">Cells in the **Value** column can hold any constant that you type in: a string-literal, an integer-literal, or null.</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="dc681-156">如果所选属性的类型是字符串，值必须是用引号引起来。</span><span class="sxs-lookup"><span data-stu-id="dc681-156">If the property selected is of type string, the value needs to be in quotes.</span></span> <span data-ttu-id="dc681-157">例如，SMTP。From ="MyServer"。</span><span class="sxs-lookup"><span data-stu-id="dc681-157">For example, SMTP.From = "MyServer".</span></span>  

- <span data-ttu-id="dc681-158">**分组。**</span><span class="sxs-lookup"><span data-stu-id="dc681-158">**Grouping.**</span></span> <span data-ttu-id="dc681-159">使用此列可控制谓词分组。</span><span class="sxs-lookup"><span data-stu-id="dc681-159">Use this column to control predicate grouping.</span></span> <span data-ttu-id="dc681-160">筛选器表达式始终表示中析取范式 (DNF)，因此可以自动确定分组。</span><span class="sxs-lookup"><span data-stu-id="dc681-160">Filter expressions are always expressed in Disjunctive Normal Form (DNF) so grouping can be determined automatically.</span></span> <span data-ttu-id="dc681-161">表示谓词是要与其后的谓词进行分组，而 OR 表示该谓词是独立于下一行中的谓词。</span><span class="sxs-lookup"><span data-stu-id="dc681-161">AND means the predicate is to be grouped with the predicate following it, while OR means the predicate is separate from the predicate in the next row.</span></span> <span data-ttu-id="dc681-162">当谓词组合在一起时显示的网格控件左侧的灰色括号。</span><span class="sxs-lookup"><span data-stu-id="dc681-162">Gray brackets to the left of the grid control appear when predicates are grouped together.</span></span> <span data-ttu-id="dc681-163">不能嵌套谓词组。</span><span class="sxs-lookup"><span data-stu-id="dc681-163">Predicate groups cannot be nested.</span></span> <span data-ttu-id="dc681-164">如果不在此单元格中指定一个值，单元格的值默认为 and。</span><span class="sxs-lookup"><span data-stu-id="dc681-164">If you do not specify a value in this cell, the value of the cell defaults to AND.</span></span>  

  <span data-ttu-id="dc681-165">例如，可以创建如下所示的表达式：</span><span class="sxs-lookup"><span data-stu-id="dc681-165">For example, you might create an expression like the following:</span></span>  

  `MSMQ.MsgID = 1`  

  <span data-ttu-id="dc681-166">使用此筛选器，发送端口组将只订阅 MSMQ 消息 ID 为 1 的消息。</span><span class="sxs-lookup"><span data-stu-id="dc681-166">With this filter, the send port group would only subscribe to messages having an MSMQ message ID of 1.</span></span>  

  <span data-ttu-id="dc681-167">可以创建其他表达式并指定它们具有一个 AND 或 OR 关系与其他表达式，例如：</span><span class="sxs-lookup"><span data-stu-id="dc681-167">You can create additional expressions and specify that they have an AND or OR relationship with other expressions, for example:</span></span>  

  `MSMQ.MsgID = 1 OR`  

  `SMTP.From = "MyServer"`  

  <span data-ttu-id="dc681-168">在这种情况下，发送端口组将订阅拥有的所有消息到 MSMQ 消息 ID 为 1 或已从名为 MyServer 的 SMTP 服务器发送的。</span><span class="sxs-lookup"><span data-stu-id="dc681-168">In this case, the send port group would subscribe to all messages that have either an MSMQ message ID of 1 or that have been sent from the SMTP server named MyServer.</span></span>  

## <a name="hint-label"></a><span data-ttu-id="dc681-169">提示标签</span><span class="sxs-lookup"><span data-stu-id="dc681-169">Hint label</span></span>  
 <span data-ttu-id="dc681-170">此字段提供用户指导。</span><span class="sxs-lookup"><span data-stu-id="dc681-170">This field provides user guidance.</span></span> <span data-ttu-id="dc681-171">根据包含活动单元格的列标签的文本更改。</span><span class="sxs-lookup"><span data-stu-id="dc681-171">The label text changes depending on which column contains the active cell.</span></span> <span data-ttu-id="dc681-172">文本显示列名称后跟指导文本，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dc681-172">The text displays the column name followed by guidance text as follows:</span></span>  

-   <span data-ttu-id="dc681-173">**属性。**</span><span class="sxs-lookup"><span data-stu-id="dc681-173">**Property.**</span></span> <span data-ttu-id="dc681-174">请从列表中选择传入消息的属性。</span><span class="sxs-lookup"><span data-stu-id="dc681-174">Please select a property on the incoming message from the list.</span></span>  

-   <span data-ttu-id="dc681-175">**运算符。**</span><span class="sxs-lookup"><span data-stu-id="dc681-175">**Operator.**</span></span> <span data-ttu-id="dc681-176">选择用于属性与值进行比较的运算符。</span><span class="sxs-lookup"><span data-stu-id="dc681-176">Select an operator to compare the Property with the Value.</span></span>  

-   <span data-ttu-id="dc681-177">**值。**</span><span class="sxs-lookup"><span data-stu-id="dc681-177">**Value.**</span></span> <span data-ttu-id="dc681-178">从列表中，选择消息属性或键入的文本值。</span><span class="sxs-lookup"><span data-stu-id="dc681-178">Select a message property from the list, or type in a literal value.</span></span>  

-   <span data-ttu-id="dc681-179">**分组。**</span><span class="sxs-lookup"><span data-stu-id="dc681-179">**Grouping.**</span></span> <span data-ttu-id="dc681-180">指定此行的方式与下一步的行进行分组。</span><span class="sxs-lookup"><span data-stu-id="dc681-180">Specify how this row is to be grouped with the next row.</span></span> <span data-ttu-id="dc681-181">AND 将连接行、 和 OR 将分隔。</span><span class="sxs-lookup"><span data-stu-id="dc681-181">'AND' will join the rows, and 'OR' will separate them.</span></span>  

## <a name="move-up-button"></a><span data-ttu-id="dc681-182">上移按钮</span><span class="sxs-lookup"><span data-stu-id="dc681-182">Move Up button</span></span>  
 <span data-ttu-id="dc681-183">单击此按钮可以将所选的行上移。</span><span class="sxs-lookup"><span data-stu-id="dc681-183">Click this to move a selected row up.</span></span> <span data-ttu-id="dc681-184">(首次通过单击选择行*向右箭头*(**>)** 按钮位于左侧和右侧的网格控件。)</span><span class="sxs-lookup"><span data-stu-id="dc681-184">(First select a row by clicking the *right arrow* (**>)** button at the left side of the grid control.)</span></span>  

## <a name="move-down-button"></a><span data-ttu-id="dc681-185">下移按钮</span><span class="sxs-lookup"><span data-stu-id="dc681-185">Move Down button</span></span>  
 <span data-ttu-id="dc681-186">单击此按钮可以向下移动所选的行。</span><span class="sxs-lookup"><span data-stu-id="dc681-186">Click this to move a selected row down.</span></span> <span data-ttu-id="dc681-187">(首次通过单击选择行*向右箭头*(**>)** 按钮位于左侧和右侧的网格控件。)</span><span class="sxs-lookup"><span data-stu-id="dc681-187">(First select a row by clicking the *right arrow* (**>)** button at the left side of the grid control.)</span></span>  

## <a name="filter-expression-created-field"></a><span data-ttu-id="dc681-188">筛选器表达式创建的字段</span><span class="sxs-lookup"><span data-stu-id="dc681-188">Filter Expression Created field</span></span>  
 <span data-ttu-id="dc681-189">随着您生成，此只读文本框中显示的表达式。</span><span class="sxs-lookup"><span data-stu-id="dc681-189">This read-only text box shows the expression as you are building it.</span></span>  

## <a name="in-this-section"></a><span data-ttu-id="dc681-190">本节内容</span><span class="sxs-lookup"><span data-stu-id="dc681-190">In This Section</span></span>  
 [<span data-ttu-id="dc681-191">使用带接收消息形状的筛选器</span><span class="sxs-lookup"><span data-stu-id="dc681-191">Using Filters With the Receive Message Shape</span></span>](../core/using-filters-with-the-receive-message-shape.md)