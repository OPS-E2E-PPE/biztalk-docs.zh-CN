---
title: 如何配置转换形状 |Microsoft 文档
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
ms.openlocfilehash: 8da12d090ae0c14f30defc1d65850c609b964704
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972131"
---
# <a name="how-to-configure-the-transform-shape"></a><span data-ttu-id="d7eb8-102">如何配置转换形状</span><span class="sxs-lookup"><span data-stu-id="d7eb8-102">How to Configure the Transform Shape</span></span>
<span data-ttu-id="d7eb8-103">![](../core/media/ebiz-orch-transform.gif "ebiz_orch_transform")</span><span class="sxs-lookup"><span data-stu-id="d7eb8-103">![](../core/media/ebiz-orch-transform.gif "ebiz_orch_transform")</span></span>  
<span data-ttu-id="d7eb8-104">转换形状 (Transform shape)</span><span class="sxs-lookup"><span data-stu-id="d7eb8-104">Transform shape</span></span>  
  
 <span data-ttu-id="d7eb8-105">转换只用于在构造消息，因此你**转换**形状显示方式始终内**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-105">Transforms are only used when you construct messages, so your **Transform** shape always appears inside a **Construct Message** shape.</span></span> <span data-ttu-id="d7eb8-106">可以删除**构造消息**调整设计图面上，然后将放**转换**形状内，或者也可以只需删除**转换**对该设计的形状图面，并创建封闭的业务流程设计器将**构造消息**为你的形状。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-106">You can drop the **Construct Message** shape on the design surface and then drop the **Transform** shape inside it, or you can simply drop the **Transform** shape on the design surface, and Orchestration Designer will create the enclosing **Construct Message** shape for you.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7eb8-107">中的任何源或目标消息**转换**必须基于架构。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-107">Any source or destination message in a **Transform** must be based on a schema.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="d7eb8-108">过程</span><span class="sxs-lookup"><span data-stu-id="d7eb8-108">Procedure</span></span>  
  
#### <a name="to-configure-a-transform-shape"></a><span data-ttu-id="d7eb8-109">配置转换形状</span><span class="sxs-lookup"><span data-stu-id="d7eb8-109">To configure a Transform shape</span></span>  
  
1.  <span data-ttu-id="d7eb8-110">在属性窗口中，单击**省略号**(**...**) 按钮**输入消息**，**输出消息**，或**映射名称**属性。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-110">In the Properties Window, click the **Ellipsis** (**...**) button for the **Input Messages**, **Output Messages**, or **Map Name** property.</span></span>  
  
2.  <span data-ttu-id="d7eb8-111">使用**转换配置**对话框配置**转换**形状。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-111">Use the **Transform Configuration** dialog box to configure the **Transform** shape.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7eb8-112">A**转换**形状可以仅在存在**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-112">A **Transform** shape can exist only within a **Construct Message** shape.</span></span> <span data-ttu-id="d7eb8-113">如果将拖动**消息分配**调整设计图面上的其他任何位置新**构造消息**将创建形状。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-113">If you drag a **Message Assignment** shape anywhere else on the design surface, a new **Construct Message** shape will be created.</span></span>  
  
### <a name="important-performance-considerations"></a><span data-ttu-id="d7eb8-114">重要的性能注意事项</span><span class="sxs-lookup"><span data-stu-id="d7eb8-114">Important Performance Considerations</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d7eb8-115">可优化大型消息上执行转换，通过将应用而不是在一次加载到内存的整个文档转换时到内存流文档的能力。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-115"> optimizes the ability to perform transforms on large messages by streaming the document into memory while applying the transform as opposed to loading the entire document into memory at once.</span></span> <span data-ttu-id="d7eb8-116">这种优化允许对比早期版本的 BizTalk Server 所允许的文档大得多的文档进行映射/转换。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-116">This optimization permits the mapping/transformation of much larger documents than was possible with earlier versions of BizTalk Server.</span></span> <span data-ttu-id="d7eb8-117">如果业务流程为转换形状接受多个输入和/或输出，则会限制这一优化。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-117">A limitation of this optimization occurs when an orchestration accepts multiple inputs and/or outputs to transform shapes.</span></span>  
  
 <span data-ttu-id="d7eb8-118">如果业务流程为转移形状接受多个输入和/或输出，则不执行文档流式处理，并且内存使用量会大幅增加。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-118">If an orchestration accepts multiple inputs and/or outputs to transform shapes then document streaming is not performed and memory use is increased considerably.</span></span> <span data-ttu-id="d7eb8-119">此问题的一种可能的解决方法是，在接收管道中应用单个或多个转换，使业务流程不再为转换形状接受多个输入或多个输出。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-119">One possible workaround to this issue would be to apply the transform or transforms in a receive pipeline so that the orchestration never accepts more than a single input or a single output to a transform shape.</span></span>  
  
### <a name="newexisting-map-file"></a><span data-ttu-id="d7eb8-120">是新建映射文件还是现有映射文件？</span><span class="sxs-lookup"><span data-stu-id="d7eb8-120">New/Existing Map File?</span></span>  
 <span data-ttu-id="d7eb8-121">在此部分中，可以单击**新图**或**现有映射**选项按钮以选择要分配给一个映射**转换**形状。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-121">In this section, you can click either the **New Map** or the **Existing Map** option button to select a map to assign to the **Transform** shape.</span></span>  
  
 <span data-ttu-id="d7eb8-122">使用**名称**字段在选定的选项按钮以指定地图的下面。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-122">Use the **Name** field below the selected option button to specify a map.</span></span> <span data-ttu-id="d7eb8-123">如果你选择**新图**，您可以键入你想要分配映射指定内容。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-123">If you selected **New Map**, you can type a designation for the map you want to assign.</span></span> <span data-ttu-id="d7eb8-124">当你使用**新图**选项，你必须在文本框中指定映射的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-124">When you use the **New Map** option, you must specify the fully qualified name of the map in the text box.</span></span> <span data-ttu-id="d7eb8-125">文本框中默认情况下，显示举例说明这样的名称，因为它是基于项目命名空间的唯一标识符名称预填充和**转换**形状名称：\<项目命名空间\>。\<转换形状名称\>_Map (例如，MyProject.Transform3_Map)。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-125">The text box displays an example of such a name by default, because it is pre-populated with a unique identifier name based on the project namespace and **Transform** shape name: \<Project namespace\>.\<Transform shape name\>_Map (for example, MyProject.Transform3_Map).</span></span>  
  
 <span data-ttu-id="d7eb8-126">如果你选择**现有映射**，单击中的向下箭头**名称**字段来选择要使用的映射文件。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-126">If you selected **Existing Map**, click the Down arrow in the **Name** field to select which map file to use.</span></span> <span data-ttu-id="d7eb8-127">此列表框会显示该项目中可用的所有现有映射的列表（按字母顺序排序）。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-127">This list box displays an alphabetically sorted list of all the existing maps available in the project.</span></span> <span data-ttu-id="d7eb8-128">在此列表中，如果您单击文本\<从引用的程序集选择\>、**选择项目类型**对话框随即显示。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-128">In this list, if you click the text \<Select from referenced assembly\>, the **Select Artifact Type** dialog box is displayed.</span></span> <span data-ttu-id="d7eb8-129">它使可选择的详细信息，请参阅[如何使用选择项目类型对话框中](../core/how-to-use-the-select-artifact-type-dialog-box.md)。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-129">For more information about the selections it makes available, see [How to Use the Select Artifact Type Dialog Box](../core/how-to-use-the-select-artifact-type-dialog-box.md).</span></span>  
  
### <a name="select-source-and-destination-messages"></a><span data-ttu-id="d7eb8-130">选择源消息和目标消息</span><span class="sxs-lookup"><span data-stu-id="d7eb8-130">Select Source and Destination Messages</span></span>  
 <span data-ttu-id="d7eb8-131">使用这一部分**转换配置**对话框可以配置在所选的映射**新建/现有映射文件？** 部分。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-131">Use this part of the **Transform Configuration** dialog box to configure the map you selected in the **New/Existing Map File?** section.</span></span> <span data-ttu-id="d7eb8-132">如果你选择**新图**在该部分中，创建该图通过将其配置在本部分中。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-132">If you selected **New Map** in that section, you create that map by configuring it in this section.</span></span>  
  
 <span data-ttu-id="d7eb8-133">如果你选择**现有映射**，你可以使用本部分执行两个操作之一：</span><span class="sxs-lookup"><span data-stu-id="d7eb8-133">If you selected **Existing Map**, you can use this section to do one of two things:</span></span>  
  
-   <span data-ttu-id="d7eb8-134">选择一个现有映射，在当前转换中按原样重新使用。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-134">Select an existing map to reuse as-is in the current transform.</span></span>  
  
-   <span data-ttu-id="d7eb8-135">选择一个现有映射以便对它进行更改（配置），然后在当前转换的新配置中使用该映射。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-135">Select an existing map in order to change (reconfigure) it, and then use it in its new configuration in the current transform.</span></span>  
  
 <span data-ttu-id="d7eb8-136">通过使用指定源和目标消息**源消息**和**目标消息**网格控件。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-136">Specify source and destination messages by using the **Source Messages** and **Destination Messages** grid controls.</span></span> <span data-ttu-id="d7eb8-137">可以使用这些网格控件以多种方式更改映射文件。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-137">You can use these grid controls to change the map file in several ways.</span></span> <span data-ttu-id="d7eb8-138">如果删除的消息（任一网格控件中的一行）、添加的消息或选择的消息是另一种类型，则会改变映射的结构。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-138">If you delete a message (a row in either grid control), add a message, or select a message of a different type, you alter the structure of the map.</span></span> <span data-ttu-id="d7eb8-139">改变映射的结构后，必须更改使用此映射的所有其他转换，使其与映射的新结构相匹配。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-139">When you alter the structure of a map, all other transforms that use it must be changed to match the new structure of the map.</span></span> <span data-ttu-id="d7eb8-140">其他更改（如删除一个消息并在其位置插入同种类型的消息）不会改变映射的结构。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-140">Other changes, such as removing a message and inserting in its place a message of the same type, do not alter the structure of the map.</span></span>  
  
 <span data-ttu-id="d7eb8-141">**源消息**和**目标消息**网格控件是在外观和行为完全相同。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-141">The **Source Messages** and **Destination Messages** grid controls are identical in appearance and behavior.</span></span> <span data-ttu-id="d7eb8-142">每个网格控件都有两列：消息和类型。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-142">Each grid control has two columns: Message and Type.</span></span> <span data-ttu-id="d7eb8-143">通过在消息列中选择消息来填充网格控件。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-143">You populate the grid controls by selecting messages in the Message column.</span></span> <span data-ttu-id="d7eb8-144">（数据只能添加到消息列中，因为类型列是只读的。）消息列中的单元格具有下拉列表，其中填充了当前业务流程范围内的消息实例。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-144">(You add data only into the Message column, because the Type column is read-only.) The cells in the Message column have drop-down lists populated with message instances that are within scope for the current orchestration.</span></span>  
  
 <span data-ttu-id="d7eb8-145">可以通过单击任一网格控件中选择一行*右箭头*网格控件的左侧 (>) 按钮。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-145">You can select a row in either grid control by clicking the *right arrow* (>) button at the left side of the grid control.</span></span> <span data-ttu-id="d7eb8-146">选定一行后，可以按 Delete 键删除此行。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-146">After you have selected a row, you can delete it by pressing the DELETE key.</span></span> <span data-ttu-id="d7eb8-147">删除一行（一个消息）会改变包含此行的映射文件的结构。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-147">Deleting a row (a message) alters the structure of the map file that contained it.</span></span> <span data-ttu-id="d7eb8-148">只能修改项目的本地映射文件。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-148">You can modify only map files that are local to the project.</span></span>  
  
### <a name="when-i-click-ok-launch-the-biztalk-mapper"></a><span data-ttu-id="d7eb8-149">单击“确定”即启动 Biztalk 映射器</span><span class="sxs-lookup"><span data-stu-id="d7eb8-149">When I click OK, launch the BizTalk Mapper</span></span>  
 <span data-ttu-id="d7eb8-150">单击**时我单击确定，启动 BizTalk 映射程序**将 BizTalk 映射程序自动打开，当你单击**确定**关闭**转换配置**对话框框中，并保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-150">Clicking **When I click OK, launch the BizTalk Mapper** opens BizTalk Mapper automatically when you click **OK** to close the **Transform Configuration** dialog box and save your changes.</span></span> <span data-ttu-id="d7eb8-151">但如果必需的信息丢失，则无法保存更改。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-151">You cannot save changes, however, if required information is missing.</span></span> <span data-ttu-id="d7eb8-152">在这种情况下，完成填写对话框中的字段，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d7eb8-152">In this case, finish filling out the fields in the dialog box and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7eb8-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7eb8-153">See Also</span></span>  
 <span data-ttu-id="d7eb8-154">[有关映射](../core/about-maps.md) </span><span class="sxs-lookup"><span data-stu-id="d7eb8-154">[About Maps](../core/about-maps.md) </span></span>  
 <span data-ttu-id="d7eb8-155">[构造消息](../core/constructing-messages.md) </span><span class="sxs-lookup"><span data-stu-id="d7eb8-155">[Constructing Messages](../core/constructing-messages.md) </span></span>  
 [<span data-ttu-id="d7eb8-156">如何使用动态转换消息的表达式</span><span class="sxs-lookup"><span data-stu-id="d7eb8-156">How to Use Expressions to Dynamic Transform Messages</span></span>](../core/how-to-use-expressions-to-dynamic-transform-messages.md)