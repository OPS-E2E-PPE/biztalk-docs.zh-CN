---
title: 如何配置转换形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Orchestration Designer], Transform shape
- Transform shape [Orchestration Designer]
ms.assetid: ca81d153-77a6-4bcc-b14f-8f48469fffe0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c813505481fd0331a5e5f229b6007a0a773a1f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340302"
---
# <a name="how-to-configure-the-transform-shape"></a><span data-ttu-id="b4c1a-102">如何配置转换形状</span><span class="sxs-lookup"><span data-stu-id="b4c1a-102">How to Configure the Transform Shape</span></span>
<span data-ttu-id="b4c1a-103">![](../core/media/ebiz-orch-transform.gif "ebiz_orch_transform")</span><span class="sxs-lookup"><span data-stu-id="b4c1a-103">![](../core/media/ebiz-orch-transform.gif "ebiz_orch_transform")</span></span>  
<span data-ttu-id="b4c1a-104">转换形状</span><span class="sxs-lookup"><span data-stu-id="b4c1a-104">Transform shape</span></span>  
  
 <span data-ttu-id="b4c1a-105">在构造消息，因此时才使用转换您**转换**形状内始终将显示**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-105">Transforms are only used when you construct messages, so your **Transform** shape always appears inside a **Construct Message** shape.</span></span> <span data-ttu-id="b4c1a-106">可以删除**构造消息**设计图面上形状，然后再删除**转换**形状内，或者也可以只是删除**转换**在设计上的形状图面上，并创建封闭的业务流程设计器将**构造消息**为你的形状。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-106">You can drop the **Construct Message** shape on the design surface and then drop the **Transform** shape inside it, or you can simply drop the **Transform** shape on the design surface, and Orchestration Designer will create the enclosing **Construct Message** shape for you.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4c1a-107">中的任何源或目标消息**转换**必须基于架构。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-107">Any source or destination message in a **Transform** must be based on a schema.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="b4c1a-108">过程</span><span class="sxs-lookup"><span data-stu-id="b4c1a-108">Procedure</span></span>  
  
#### <a name="to-configure-a-transform-shape"></a><span data-ttu-id="b4c1a-109">若要配置转换形状</span><span class="sxs-lookup"><span data-stu-id="b4c1a-109">To configure a Transform shape</span></span>  
  
1.  <span data-ttu-id="b4c1a-110">在属性窗口中，单击**省略号**(**...**) 按钮**输入消息**，**输出消息**，或**映射名称**属性。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-110">In the Properties Window, click the **Ellipsis** (**...**) button for the **Input Messages**, **Output Messages**, or **Map Name** property.</span></span>  
  
2.  <span data-ttu-id="b4c1a-111">使用**转换配置**对话框可以配置**转换**形状。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-111">Use the **Transform Configuration** dialog box to configure the **Transform** shape.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4c1a-112">一个**转换**形状可以仅在存在**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-112">A **Transform** shape can exist only within a **Construct Message** shape.</span></span> <span data-ttu-id="b4c1a-113">如果您拖动**消息赋值**形状在设计图面上的其他任何位置的新**构造消息**将创建形状。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-113">If you drag a **Message Assignment** shape anywhere else on the design surface, a new **Construct Message** shape will be created.</span></span>  
  
### <a name="important-performance-considerations"></a><span data-ttu-id="b4c1a-114">重要的性能注意事项</span><span class="sxs-lookup"><span data-stu-id="b4c1a-114">Important Performance Considerations</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="b4c1a-115">优化了对大消息执行转换，通过将文档流式处理到内存中同时应用转换，而不是一次性将整个文档加载到内存的能力。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-115">optimizes the ability to perform transforms on large messages by streaming the document into memory while applying the transform as opposed to loading the entire document into memory at once.</span></span> <span data-ttu-id="b4c1a-116">这种优化允许大得多文档比早期版本的 BizTalk Server 映射/转换。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-116">This optimization permits the mapping/transformation of much larger documents than was possible with earlier versions of BizTalk Server.</span></span> <span data-ttu-id="b4c1a-117">当业务流程接受多个输入和/或输出转换形状时，会发生这种优化的一个限制。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-117">A limitation of this optimization occurs when an orchestration accepts multiple inputs and/or outputs to transform shapes.</span></span>  
  
 <span data-ttu-id="b4c1a-118">如果业务流程接受多个输入和/或输出转换形状，则不执行文档流式处理和内存使用量会大幅增加。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-118">If an orchestration accepts multiple inputs and/or outputs to transform shapes then document streaming is not performed and memory use is increased considerably.</span></span> <span data-ttu-id="b4c1a-119">此问题的一种解决方法是，将转换或转换的接收管道中，以便该业务流程不会接受多个单个输入或单个输出为转换形状。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-119">One possible workaround to this issue would be to apply the transform or transforms in a receive pipeline so that the orchestration never accepts more than a single input or a single output to a transform shape.</span></span>  
  
### <a name="newexisting-map-file"></a><span data-ttu-id="b4c1a-120">新的/现有映射文件？</span><span class="sxs-lookup"><span data-stu-id="b4c1a-120">New/Existing Map File?</span></span>  
 <span data-ttu-id="b4c1a-121">在本部分中，可以单击**新的映射**或**现有映射**选项按钮以选择要分配给一个映射**转换**形状。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-121">In this section, you can click either the **New Map** or the **Existing Map** option button to select a map to assign to the **Transform** shape.</span></span>  
  
 <span data-ttu-id="b4c1a-122">使用**名称**字段可指定映射在所选的选项按钮的下面。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-122">Use the **Name** field below the selected option button to specify a map.</span></span> <span data-ttu-id="b4c1a-123">如果所选**新的映射**，可以键入你想要分配的映射的名称。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-123">If you selected **New Map**, you can type a designation for the map you want to assign.</span></span> <span data-ttu-id="b4c1a-124">当你使用**新的映射**选项，必须在文本框中指定映射的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-124">When you use the **New Map** option, you must specify the fully qualified name of the map in the text box.</span></span> <span data-ttu-id="b4c1a-125">在文本框中默认情况下显示此类名称的一个示例，因为它是基于项目命名空间的唯一标识符名称预先填充和**转换**形状名称：\<项目命名空间\>。\<转换形状名称\>_Map (例如，MyProject.Transform3_Map)。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-125">The text box displays an example of such a name by default, because it is pre-populated with a unique identifier name based on the project namespace and **Transform** shape name: \<Project namespace\>.\<Transform shape name\>_Map (for example, MyProject.Transform3_Map).</span></span>  
  
 <span data-ttu-id="b4c1a-126">如果所选**现有的映射**，单击中的下箭头**名称**字段来选择要使用的映射文件。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-126">If you selected **Existing Map**, click the Down arrow in the **Name** field to select which map file to use.</span></span> <span data-ttu-id="b4c1a-127">此列表框显示所有的现有映射的项目中提供的按字母顺序排序的列表。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-127">This list box displays an alphabetically sorted list of all the existing maps available in the project.</span></span> <span data-ttu-id="b4c1a-128">在此列表中，如果单击文本\<从引用的程序集中\>，则**选择项目类型**显示对话框。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-128">In this list, if you click the text \<Select from referenced assembly\>, the **Select Artifact Type** dialog box is displayed.</span></span> <span data-ttu-id="b4c1a-129">可通过其所选内容的详细信息，请参阅[如何使用选择项目类型对话框中](../core/how-to-use-the-select-artifact-type-dialog-box.md)。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-129">For more information about the selections it makes available, see [How to Use the Select Artifact Type Dialog Box](../core/how-to-use-the-select-artifact-type-dialog-box.md).</span></span>  
  
### <a name="select-source-and-destination-messages"></a><span data-ttu-id="b4c1a-130">选择源和目标消息</span><span class="sxs-lookup"><span data-stu-id="b4c1a-130">Select Source and Destination Messages</span></span>  
 <span data-ttu-id="b4c1a-131">使用此部分**转换配置**对话框可以配置在选定的映射**新建还是现有映射文件？** 部分。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-131">Use this part of the **Transform Configuration** dialog box to configure the map you selected in the **New/Existing Map File?** section.</span></span> <span data-ttu-id="b4c1a-132">如果所选**新的映射**部分中，创建映射通过在本部分中配置。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-132">If you selected **New Map** in that section, you create that map by configuring it in this section.</span></span>  
  
 <span data-ttu-id="b4c1a-133">如果所选**现有的映射**，可以使用本部分中执行两项操作之一：</span><span class="sxs-lookup"><span data-stu-id="b4c1a-133">If you selected **Existing Map**, you can use this section to do one of two things:</span></span>  
  
- <span data-ttu-id="b4c1a-134">选择现有的映射按原样重新使用的是在当前转换中。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-134">Select an existing map to reuse as-is in the current transform.</span></span>  
  
- <span data-ttu-id="b4c1a-135">若要更改 （配置） 选择一个现有映射，并使用它在当前转换中的新配置。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-135">Select an existing map in order to change (reconfigure) it, and then use it in its new configuration in the current transform.</span></span>  
  
  <span data-ttu-id="b4c1a-136">使用指定源和目标消息**源消息**并**目标消息**网格控件。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-136">Specify source and destination messages by using the **Source Messages** and **Destination Messages** grid controls.</span></span> <span data-ttu-id="b4c1a-137">可以使用这些网格控件来更改映射文件中有多种。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-137">You can use these grid controls to change the map file in several ways.</span></span> <span data-ttu-id="b4c1a-138">如果您删除一条消息 （任一网格控件中某行），添加一条消息，或选择不同类型的消息，您可以更改映射的结构。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-138">If you delete a message (a row in either grid control), add a message, or select a message of a different type, you alter the structure of the map.</span></span> <span data-ttu-id="b4c1a-139">当更改映射的结构时必须更改使用它的所有其他转换以匹配新映射的结构。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-139">When you alter the structure of a map, all other transforms that use it must be changed to match the new structure of the map.</span></span> <span data-ttu-id="b4c1a-140">其他更改，如删除一个消息并在其位置插入一条消息的相同的类型，不会改变映射的结构。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-140">Other changes, such as removing a message and inserting in its place a message of the same type, do not alter the structure of the map.</span></span>  
  
  <span data-ttu-id="b4c1a-141">**源消息**并**目标消息**网格控件是相同的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-141">The **Source Messages** and **Destination Messages** grid controls are identical in appearance and behavior.</span></span> <span data-ttu-id="b4c1a-142">每个网格控件具有两个列：消息和类型。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-142">Each grid control has two columns: Message and Type.</span></span> <span data-ttu-id="b4c1a-143">通过选择消息列中的消息填充网格控件。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-143">You populate the grid controls by selecting messages in the Message column.</span></span> <span data-ttu-id="b4c1a-144">（您数据只能添加到消息列中，因为类型列是只读的。）在消息列中的单元格都具有下拉列表，其中填充了当前业务流程的作用域内的消息实例。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-144">(You add data only into the Message column, because the Type column is read-only.) The cells in the Message column have drop-down lists populated with message instances that are within scope for the current orchestration.</span></span>  
  
  <span data-ttu-id="b4c1a-145">可以通过单击任一网格控件中选择某一行*向右箭头*(>) 按钮，位于左侧和右侧的网格控件。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-145">You can select a row in either grid control by clicking the *right arrow* (>) button at the left side of the grid control.</span></span> <span data-ttu-id="b4c1a-146">选择某一行后，可以通过按 DELETE 键删除它。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-146">After you have selected a row, you can delete it by pressing the DELETE key.</span></span> <span data-ttu-id="b4c1a-147">删除行 （消息） 会改变包含此行的映射文件的结构。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-147">Deleting a row (a message) alters the structure of the map file that contained it.</span></span> <span data-ttu-id="b4c1a-148">可以修改项目的本地添加的映射文件。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-148">You can modify only map files that are local to the project.</span></span>  
  
### <a name="when-i-click-ok-launch-the-biztalk-mapper"></a><span data-ttu-id="b4c1a-149">当我单击确定时，启动 BizTalk 映射器</span><span class="sxs-lookup"><span data-stu-id="b4c1a-149">When I click OK, launch the BizTalk Mapper</span></span>  
 <span data-ttu-id="b4c1a-150">单击**当我单击确定时，启动 BizTalk 映射器**单击时自动打开 BizTalk 映射器**确定**以关闭**转换配置**对话框框中并保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-150">Clicking **When I click OK, launch the BizTalk Mapper** opens BizTalk Mapper automatically when you click **OK** to close the **Transform Configuration** dialog box and save your changes.</span></span> <span data-ttu-id="b4c1a-151">但是，如果信息缺少必需的则无法保存更改。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-151">You cannot save changes, however, if required information is missing.</span></span> <span data-ttu-id="b4c1a-152">在这种情况下，完成填写对话框框中的字段，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b4c1a-152">In this case, finish filling out the fields in the dialog box and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4c1a-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4c1a-153">See Also</span></span>  
 <span data-ttu-id="b4c1a-154">[有关地图](../core/about-maps.md) </span><span class="sxs-lookup"><span data-stu-id="b4c1a-154">[About Maps](../core/about-maps.md) </span></span>  
 <span data-ttu-id="b4c1a-155">[构造消息](../core/constructing-messages.md) </span><span class="sxs-lookup"><span data-stu-id="b4c1a-155">[Constructing Messages](../core/constructing-messages.md) </span></span>  
 [<span data-ttu-id="b4c1a-156">如何使用表达式来动态转换消息</span><span class="sxs-lookup"><span data-stu-id="b4c1a-156">How to Use Expressions to Dynamic Transform Messages</span></span>](../core/how-to-use-expressions-to-dynamic-transform-messages.md)