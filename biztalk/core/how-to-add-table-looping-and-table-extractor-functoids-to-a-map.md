---
title: 如何添加表循环和表提取程序 Functoid 映射到 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c837ab8-55db-471a-af26-9fbd0497d7d4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dffd7d3f67d08a23a010ec533159e8648774e8c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012374"
---
# <a name="how-to-add-table-looping-and-table-extractor-functoids-to-a-map"></a><span data-ttu-id="cffcd-102">如何向映射添加“表循环”和“表提取程序”Functoid</span><span class="sxs-lookup"><span data-stu-id="cffcd-102">How to Add Table Looping and Table Extractor Functoids to a Map</span></span>
<span data-ttu-id="cffcd-103">**表循环**并**表提取程序**functoid 一起使用。</span><span class="sxs-lookup"><span data-stu-id="cffcd-103">The **Table Looping** and **Table Extractor** functoids are used together.</span></span> <span data-ttu-id="cffcd-104">**表循环**functoid 已配置的内部表。</span><span class="sxs-lookup"><span data-stu-id="cffcd-104">The **Table Looping** functoid has an internal table you configure.</span></span> <span data-ttu-id="cffcd-105">对于每个输入记录或字段中，**表循环**functoid 会输出表，一次一个的行。</span><span class="sxs-lookup"><span data-stu-id="cffcd-105">For each input record or field, the **Table Looping** functoid outputs the rows of the table, one at a time.</span></span> <span data-ttu-id="cffcd-106">**表提取程序**functoid 从行提取所需的项，并将其传递到输出实例消息。</span><span class="sxs-lookup"><span data-stu-id="cffcd-106">The **Table Extractor** functoid extracts the desired item from a row and passes it on to the output instance message.</span></span>  
  
 <span data-ttu-id="cffcd-107">有关概念性信息**表循环**并**表提取程序**functoid，请参阅[表循环和表提取程序 Functoid](../core/table-looping-and-table-extractor-functoids.md)。</span><span class="sxs-lookup"><span data-stu-id="cffcd-107">For conceptual information about the **Table Looping** and **Table Extractor** functoids, see [Table Looping and Table Extractor Functoids](../core/table-looping-and-table-extractor-functoids.md).</span></span>  
  
### <a name="to-add-the-table-looping-and-table-extractor-functoids-to-a-map-and-configure-them"></a><span data-ttu-id="cffcd-108">向映射添加“表循环”和“表提取程序”functoid 并对其进行配置</span><span class="sxs-lookup"><span data-stu-id="cffcd-108">To add the Table Looping and Table Extractor functoids to a map and configure them</span></span>  
  
1. <span data-ttu-id="cffcd-109">与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择该类别的 functoid。</span><span class="sxs-lookup"><span data-stu-id="cffcd-109">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
    <span data-ttu-id="cffcd-110">此时，将显示所选类别的高级 functoid 列表。</span><span class="sxs-lookup"><span data-stu-id="cffcd-110">The list of advanced functoids in the chosen category appears.</span></span>  
  
2. <span data-ttu-id="cffcd-111">拖动**表循环**functoid (![](../core/media/advtablelooping.gif "advtablelooping")) 从工具箱拖到网格页上的适当位置。</span><span class="sxs-lookup"><span data-stu-id="cffcd-111">Drag the **Table Looping** functoid (![](../core/media/advtablelooping.gif "advtablelooping")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="cffcd-112">该 functoid 将放置到显示的网格页上。</span><span class="sxs-lookup"><span data-stu-id="cffcd-112">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="cffcd-113">如果你想要将该 functoid 放置到其他网格页上，您需要首先显示该网格页。</span><span class="sxs-lookup"><span data-stu-id="cffcd-113">If you want to put the functoid onto a different grid page, you need to display that grid page first.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="cffcd-114">因为的输出**表循环**functoid 将作为输入到一个或多个关联**表提取程序**functoid，请确保右侧留出空间**表循环**用于 functoid**表提取程序**functoid。</span><span class="sxs-lookup"><span data-stu-id="cffcd-114">Because the output of the **Table Looping** functoid serves as input to one or more associated **Table Extractor** functoids, make sure you leave room to the right of the **Table Looping** functoid for the **Table Extractor** functoids.</span></span>  
  
3. <span data-ttu-id="cffcd-115">将记录或字段从源架构拖到新添加**表循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="cffcd-115">Drag a record or field from the source schema to the newly added **Table Looping** functoid.</span></span> <span data-ttu-id="cffcd-116">作为第一个输入参数**表循环**functoid，此记录或字段的实例消息中的出现次数将控制此 functoid 生成输出的次数。</span><span class="sxs-lookup"><span data-stu-id="cffcd-116">As the first input parameter to the **Table Looping** functoid, the number of occurrences of this record or field in an instance message will control the number of times this functoid produces output.</span></span> <span data-ttu-id="cffcd-117">例如，如果循环记录拖至该 functoid，并处理具有 10 次的此记录的实例消息时，并且已具有一行的列数据源配置表网格**表循环**functoid 将迭代 10 次，生成 10 个输出行，用于通过提取**表提取程序**要可以轻松地构建的 functoid，并允许 10 个目标记录。</span><span class="sxs-lookup"><span data-stu-id="cffcd-117">For example, if a looping record is dragged to the functoid, and an instance message that has 10 occurrences of this record is processed, and the table grid has been configured with one row of sources of column data, the **Table Looping** functoid will iterate 10 times, producing 10 output rows for extraction by a **Table Extractor** functoid, and allowing 10 destination records to be easily constructed.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="cffcd-118">如果在表网格中配置多个行，会输出每个迭代的每个此类行**表循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="cffcd-118">If you configure multiple rows in the table grid, each such row will be output for each iteration of the **Table Looping** functoid.</span></span> <span data-ttu-id="cffcd-119">因此，输入记录出现的次数乘以表网格中所配置的行数将得出可用于进行数据提取的输出表行数。</span><span class="sxs-lookup"><span data-stu-id="cffcd-119">So, the number of occurrences of an input record times the number of rows configured in the table grid yields the number of output table rows available for data extraction.</span></span>  
  
4. <span data-ttu-id="cffcd-120">将记录或字段拖到目标架构中**表循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="cffcd-120">Drag a record or field from the destination schema to the **Table Looping** functoid.</span></span> <span data-ttu-id="cffcd-121">此链接可确保在目标架构中创建节点。</span><span class="sxs-lookup"><span data-stu-id="cffcd-121">This link ensures the creation of the node in the destination schema.</span></span>  
  
5. <span data-ttu-id="cffcd-122">选择新添加**表循环**functoid，然后在**属性**窗口中，单击省略号 (**...**) 与关联的按钮及其**输入参数**属性。</span><span class="sxs-lookup"><span data-stu-id="cffcd-122">Select the newly added **Table Looping** functoid, and in the **Properties** window, click the ellipsis (**...**) button associated with its **Input Parameters** property.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="cffcd-123">此外，还可以选择 functoid，然后在键盘上按 Ctrl+M、Ctrl+T。</span><span class="sxs-lookup"><span data-stu-id="cffcd-123">Alternatively, you can select the functoid and then press CTRL+M, CTRL+T from the keyboard.</span></span> <span data-ttu-id="cffcd-124">列表映射器的键盘快捷方式请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="cffcd-124">For a list of Mapper keyboard shortcuts see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
6. <span data-ttu-id="cffcd-125">在中**配置表循环 Functoid**对话框中，单击![将常数输入的参数添加到 functoid](../core/media/add-input-parameters.gif "Add_input_parameters")按钮以创建第二个输入的参数。</span><span class="sxs-lookup"><span data-stu-id="cffcd-125">In the **Configure Table Looping Functoid** dialog box, click the ![Adding constant input parameters to a functoid](../core/media/add-input-parameters.gif "Add_input_parameters") button to create the second input parameter.</span></span> <span data-ttu-id="cffcd-126">键入一个数字来表示将可创建此表中的列数**表循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="cffcd-126">Type a number that represents the number of columns that will be available in the table you are creating for this **Table Looping** functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="cffcd-127">表的最大列数为 228 列。</span><span class="sxs-lookup"><span data-stu-id="cffcd-127">The maximum number of columns in the table is 228.</span></span>  
  
7. <span data-ttu-id="cffcd-128">在中**配置表循环 Functoid**对话框中，单击![将常数输入的参数添加到 functoid](../core/media/add-input-parameters.gif "Add_input_parameters")按钮以输入的任何常量在配置的表网格中显示的值。</span><span class="sxs-lookup"><span data-stu-id="cffcd-128">In the **Configure Table Looping Functoid** dialog box, click the ![Adding constant input parameters to a functoid](../core/media/add-input-parameters.gif "Add_input_parameters") button to enter any constant values that appears in your configured table grid.</span></span> <span data-ttu-id="cffcd-129">只要第一个和第二个参数值、行数和列数分别位于输入参数列表的开始位置，这些常数在此对话框中的创建顺序并不重要。</span><span class="sxs-lookup"><span data-stu-id="cffcd-129">The order in which you create these constants is not important in this dialog box as long as the first and second parameter values, the number of rows and columns, respectively, retain their positions at the beginning of the input parameter list.</span></span> <span data-ttu-id="cffcd-130">完成后，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cffcd-130">When complete, click **OK**.</span></span>  
  
    <span data-ttu-id="cffcd-131">**配置表循环 Functoid**对话框将关闭。</span><span class="sxs-lookup"><span data-stu-id="cffcd-131">The **Configure Table Looping Functoid** dialog box closes.</span></span>  
  
8. <span data-ttu-id="cffcd-132">将零个或多个记录或字段节点从源架构拖**表循环**最近添加的 functoid。</span><span class="sxs-lookup"><span data-stu-id="cffcd-132">Drag zero or more record or field nodes from the source schema to the **Table Looping** functoid that you recently added.</span></span> <span data-ttu-id="cffcd-133">这些记录和字段节点的每一个记录或字段节点都将添加到输入参数列表的末尾，因此在后面的步骤中配置表网格时将可以使用这些记录和字段节点。</span><span class="sxs-lookup"><span data-stu-id="cffcd-133">Each of these record and field nodes is added to the end of the input parameter list, and therefore will be available when the table grid is configured in a latter step.</span></span> <span data-ttu-id="cffcd-134">与前面添加的表数据常数（不是行数和列数常数）一样，这些记录和字段节点的添加顺序并不重要。</span><span class="sxs-lookup"><span data-stu-id="cffcd-134">Like the table data constants added earlier (not the row and column count constants), the order in which these record and field nodes are added is not ultimately relevant.</span></span>  
  
9. <span data-ttu-id="cffcd-135">若要为链接加标签，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cffcd-135">To label a link, follow these steps:</span></span>  
  
   - <span data-ttu-id="cffcd-136">在显示的网格页中选择链接。</span><span class="sxs-lookup"><span data-stu-id="cffcd-136">Select a link in the displayed grid page.</span></span>  
  
   - <span data-ttu-id="cffcd-137">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，提供的描述性名称**标签**属性。</span><span class="sxs-lookup"><span data-stu-id="cffcd-137">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, provide a descriptive name for the **Label** property.</span></span> <span data-ttu-id="cffcd-138">例如，对于来自名为“第二作者”的字段的链接，可以将其命名为“link2ndAuthor”。</span><span class="sxs-lookup"><span data-stu-id="cffcd-138">For example, you might give a name like "link2ndAuthor" to a link coming from a field called "Second Author".</span></span>  
  
10. <span data-ttu-id="cffcd-139">选择新添加**表循环**functoid，然后在**属性**窗口中，单击省略号 (**...**) 按钮与相关联**表循环网格**与该 functoid 关联的属性。</span><span class="sxs-lookup"><span data-stu-id="cffcd-139">Select the newly added **Table Looping** functoid, and in the **Properties** window, click the ellipsis (**...**) button associated with the **Table Looping Grid** property associated with that functoid.</span></span>  
  
     <span data-ttu-id="cffcd-140">**配置表循环 Functoid**对话框中显示有**表循环网格**选定的选项卡。</span><span class="sxs-lookup"><span data-stu-id="cffcd-140">The **Configure Table Looping Functoid** dialog box appears with the **Table Looping Grid** tab selected.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cffcd-141">或者，您可以右键单击 functoid，然后单击**配置表循环网格**的上下文菜单中。</span><span class="sxs-lookup"><span data-stu-id="cffcd-141">Alternatively, you can right-click the functoid, and then click **Configure Table Looping Grid** in the context menu.</span></span> <span data-ttu-id="cffcd-142">**配置表循环 Functoid**对话框中显示有**表循环网格**选定的选项卡。</span><span class="sxs-lookup"><span data-stu-id="cffcd-142">The **Configure Table Looping Functoid** dialog box appears with the **Table Looping Grid** tab selected.</span></span>  
  
11. <span data-ttu-id="cffcd-143">使用与每个表单元格关联的下拉列表至少配置网格中的一个（可能多个）行。</span><span class="sxs-lookup"><span data-stu-id="cffcd-143">Use the drop-down lists associated with each table cell to configure at least one, and possibly multiple, rows in the grid.</span></span> <span data-ttu-id="cffcd-144">在下拉列表中可用选项包括的常数和链接已在步骤 6-8 中配置的作为输入参数 3 并且速度最多**表循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="cffcd-144">The choices available in the drop-down lists are the constants and links that you have configured in steps 6-8 as input parameters 3 and up to the **Table Looping** functoid.</span></span> <span data-ttu-id="cffcd-145">（输入参数 1 和 2 不显示在这些下拉列表中。）完成后，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cffcd-145">(Input parameters 1 and 2 do not appear in these drop-down lists.) When complete, click **OK**.</span></span>  
  
     <span data-ttu-id="cffcd-146">**配置表循环 Functoid**对话框将关闭。</span><span class="sxs-lookup"><span data-stu-id="cffcd-146">The **Configure Table Looping Functoid** dialog box closes.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cffcd-147">每个行构成的输出结构，与结合使用的出现次数的记录或字段的第一个输入参数指定的一次迭代**表循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="cffcd-147">Each row constitutes one iteration of the output structure, in combination with the number of occurrences of the record or field specified as the first input parameter of the **Table Looping** functoid.</span></span> <span data-ttu-id="cffcd-148">有关详细信息，请参阅步骤 3。</span><span class="sxs-lookup"><span data-stu-id="cffcd-148">For more information, see step 3.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cffcd-149">必须选择想要访问使用每个列的值**表提取程序**functoid。</span><span class="sxs-lookup"><span data-stu-id="cffcd-149">You must select a value for each column you intend to access using a **Table Extractor** functoid.</span></span> <span data-ttu-id="cffcd-150">如果未使用列**表提取程序**functoid，则应考虑删除，而不是维护，此列。</span><span class="sxs-lookup"><span data-stu-id="cffcd-150">If a column is not used by a **Table Extractor** functoid, you should consider removing, rather than maintaining, that column.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cffcd-151">表网格的填充顺序并不重要。</span><span class="sxs-lookup"><span data-stu-id="cffcd-151">The order of filling out the table grid is not important.</span></span>  
  
12. <span data-ttu-id="cffcd-152">将所需数量**表提取程序**functoid (![](../core/media/advtableextractor.gif "advtableextractor")) 从工具箱拖到显示的网格页根据需要。</span><span class="sxs-lookup"><span data-stu-id="cffcd-152">Drag as many **Table Extractor** functoids (![](../core/media/advtableextractor.gif "advtableextractor")) from the Toolbox to the displayed grid page as needed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cffcd-153">因为这些输入**表提取程序**functoid 来自**表循环**functoid 添加在上一步骤中，请确保您放置**表提取程序**functoid 的右侧**表循环**显示的网格页中的 functoid。</span><span class="sxs-lookup"><span data-stu-id="cffcd-153">Because the input of these **Table Extractor** functoids comes from the **Table Looping** functoid added in a previous step, make sure that you place the **Table Extractor** functoids to the right of the **Table Looping** functoid in the displayed grid page.</span></span>  
  
13. <span data-ttu-id="cffcd-154">若要创建第一个输入的参数之一**表提取程序**functoid 添加在步骤 9 中，将其拖到相关**表循环**至其左侧的 functoid。</span><span class="sxs-lookup"><span data-stu-id="cffcd-154">To create the first input parameter for one of the **Table Extractor** functoids added in step 9, drag it to the relevant **Table Looping** functoid to its left.</span></span>  
  
14. <span data-ttu-id="cffcd-155">若要创建第二个输入的参数的相同**表提取程序**functoid，选中该 functoid，然后在**属性**窗口中，单击省略号 (**...**) 与关联的按钮及其**输入参数**属性。</span><span class="sxs-lookup"><span data-stu-id="cffcd-155">To create the second input parameter for the same **Table Extractor** functoid, select the functoid, and in the **Properties** window, click the ellipsis (**...**) button associated with its **Input parameters** property.</span></span>  
  
     <span data-ttu-id="cffcd-156">**配置表提取程序 Functoid**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="cffcd-156">The **Configure Table Extractor Functoid** dialog box appears.</span></span>  
  
15. <span data-ttu-id="cffcd-157">单击![将常数输入的参数添加到 functoid](../core/media/add-input-parameters.gif "Add_input_parameters")按钮以创建第二个输入的参数。</span><span class="sxs-lookup"><span data-stu-id="cffcd-157">Click the ![Adding constant input parameters to a functoid](../core/media/add-input-parameters.gif "Add_input_parameters") button to create the second input parameter.</span></span> <span data-ttu-id="cffcd-158">相应的表网格中键入列数**表循环**functoid 要从中提取数据。</span><span class="sxs-lookup"><span data-stu-id="cffcd-158">Type the number of the column in the table grid of the corresponding **Table Looping** functoid from which you want to extract data.</span></span> <span data-ttu-id="cffcd-159">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="cffcd-159">Click **OK**.</span></span>  
  
     <span data-ttu-id="cffcd-160">**配置表提取程序 Functoid**对话框将关闭。</span><span class="sxs-lookup"><span data-stu-id="cffcd-160">The **Configure Table Extractor Functoid** dialog box closes.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cffcd-161">列数从 1 开始。</span><span class="sxs-lookup"><span data-stu-id="cffcd-161">Column numbers start at 1.</span></span>  
  
16. <span data-ttu-id="cffcd-162">若要使用的输出**表提取程序**functoid，拖动**表提取程序**到目标架构中的记录或字段节点拖或目标架构中的记录或字段节点到functoid**表提取程序**functoid。</span><span class="sxs-lookup"><span data-stu-id="cffcd-162">To use the output of the **Table Extractor** functoid, drag the **Table Extractor**  functoid to a record or field node in the destination schema, or drag a record or field node in the destination schema to the **Table Extractor** functoid.</span></span> <span data-ttu-id="cffcd-163">目标实例消息中与目标架构中的这一记录或字段节点相对应的元素或属性值将使用表网格中指定的单元格的值（如果为常熟）或该单元格所表示的值（如果为链接）填充。</span><span class="sxs-lookup"><span data-stu-id="cffcd-163">The element or attribute value in a destination instance message corresponding to this record or field node in the destination schema will be populated with the value from (in the case of constants), or the value indicated by (in the case of links), the specified cell in the table grid.</span></span>  
  
17. <span data-ttu-id="cffcd-164">为每个重复步骤 12、 13、 14 和 15**表提取程序**步骤 11 中添加 functoid。</span><span class="sxs-lookup"><span data-stu-id="cffcd-164">Repeat steps 12, 13, 14, and 15 for each of the **Table Extractor** functoids added in step 11.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cffcd-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="cffcd-165">See Also</span></span>  
 [<span data-ttu-id="cffcd-166">向映射添加高级 Functoid</span><span class="sxs-lookup"><span data-stu-id="cffcd-166">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)