---
title: 演练： 从文档实例创建平面文件架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5e1453f-0380-4505-97a9-9d3526db0923
caps.latest.revision: 47
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faa79ea6784df39bb2f06b32b289837093a04919
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983422"
---
# <a name="walkthrough-creating-a-flat-file-schema-from-a-document-instance"></a><span data-ttu-id="e2ab6-102">演练：从文档实例创建平面文件架构</span><span class="sxs-lookup"><span data-stu-id="e2ab6-102">Walkthrough: Creating a Flat File Schema From a Document Instance</span></span>
<span data-ttu-id="e2ab6-103">此演练演示如何根据以下示例采购订单，使用“BizTalk 平面文件架构向导”从文档实例创建平面文件架构。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-103">This walkthrough shows you how to create a flat file schema from a document instance using the BizTalk Flat File Schema Wizard based on the following sample purchase order.</span></span> <span data-ttu-id="e2ab6-104">BizTalk 平面文件架构向导的介绍，请参阅[如何使用 BizTalk 平面文件架构向导](../core/how-to-use-biztalk-flat-file-schema-wizard.md)。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-104">For an introduction to the BizTalk Flat File Schema Wizard, see [How to Use BizTalk Flat File Schema Wizard](../core/how-to-use-biztalk-flat-file-schema-wizard.md).</span></span>  

 <span data-ttu-id="e2ab6-105">![示例采购订单](../core/media/flatfileschema-samplepurchaseorder.gif "FlatFileSchema_SamplePurchaseOrder")</span><span class="sxs-lookup"><span data-stu-id="e2ab6-105">![Sample Purchase Order](../core/media/flatfileschema-samplepurchaseorder.gif "FlatFileSchema_SamplePurchaseOrder")</span></span>  

 <span data-ttu-id="e2ab6-106">该采购订单的每行都以一个用绿色标记的回车换行符 (CRLF) 结束。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-106">Each line of the purchase order ends with a carriage return line feed (CRLF), marked in green.</span></span> <span data-ttu-id="e2ab6-107">采购订单以红色 PO 标记后跟日期开头。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-107">The purchase order starts with a PO tag shown in red and followed by a date.</span></span> <span data-ttu-id="e2ab6-108">两个重复的固定位置字段包含客户信息，以紫色显示。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-108">Two repeating fixed positional fields contain customer information and are shown in purple.</span></span> <span data-ttu-id="e2ab6-109">注释字段中之后，没有重复的域开头包含多个由逗号 （，） 分隔的记录和数据值之间用竖线分隔的项标记 (&#124;)，其中显示为蓝色。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-109">After the comment field, there is a repeating field starting with an ITEMS tag that contains multiple records delimited by commas (,) and data values separated by pipes (&#124;), which are shown in blue.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="e2ab6-110">必要條件</span><span class="sxs-lookup"><span data-stu-id="e2ab6-110">Prerequisites</span></span>  
 <span data-ttu-id="e2ab6-111">在进行此演练之前，请确保您的服务器上安装并配置了以下软件：</span><span class="sxs-lookup"><span data-stu-id="e2ab6-111">Before exercising this walkthrough, make sure the following software is installed and configured on your server:</span></span>  

- <span data-ttu-id="e2ab6-112">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2ab6-112">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]</span></span>  

- <span data-ttu-id="e2ab6-113">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与**开发人员工具**安装</span><span class="sxs-lookup"><span data-stu-id="e2ab6-113">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with the **Developer tools** installed</span></span>

  <span data-ttu-id="e2ab6-114">若要为本演练准备文档实例，将以下内容复制到文本编辑器，并将其保存为文本文件。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-114">To prepare the document instance for the walkthrough, copy the following into a text editor, and save it as a text file.</span></span> <span data-ttu-id="e2ab6-115">请确保将所有行都复制源的步骤，并返回回车符。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-115">Be sure to copy all line feeds and carriage returns.</span></span>  

```
PO1999-10-20
US        Alice Smith         123 Maple Street    Mill Valley    CA 90952
US        Robert Smith        8 Oak Avenue        Old Town       PA 95819
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Confirm this is electric,ITEM926-AA|Baby Monitor|1|39.98|Confirm this is electric
```


## <a name="start-the-wizard"></a><span data-ttu-id="e2ab6-116">启动向导</span><span class="sxs-lookup"><span data-stu-id="e2ab6-116">Start the wizard</span></span>  

1. <span data-ttu-id="e2ab6-117">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开**解决方案资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-117">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the **Solution Explorer**.</span></span>  

2. <span data-ttu-id="e2ab6-118">若要添加新的平面文件架构，请右键单击项目，并选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-118">To add the new flat file schema, right-click the project, and select **Add**.</span></span> <span data-ttu-id="e2ab6-119">单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-119">Click **New Item**.</span></span>  

3. <span data-ttu-id="e2ab6-120">在中**添加新项**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e2ab6-120">In the **Add New Item** window, do the following:</span></span>  

   1.  <span data-ttu-id="e2ab6-121">在中**类别**部分中，选择**架构文件**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-121">In the **Categories** section, select **Schema Files**.</span></span>  

   2.  <span data-ttu-id="e2ab6-122">在中**模板**部分中，选择**平面文件架构向导**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-122">In the **Templates** section, select **Flat File Schema Wizard**.</span></span>  

   3.  <span data-ttu-id="e2ab6-123">在中**名称**字段中，输入**PurchaseOrder.xsd**新架构。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-123">In the **Name** field, enter **PurchaseOrder.xsd** for the new schema.</span></span>  

   4.  <span data-ttu-id="e2ab6-124">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-124">Click **Add**.</span></span>  

4. <span data-ttu-id="e2ab6-125">“BizTalk 平面文件架构向导”打开后，将显示“欢迎”页。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-125">When the BizTalk Flat File Schema Wizard opens, the Welcome Page appears.</span></span>   
   <span data-ttu-id="e2ab6-126">若要在以后运行该向导时跳过此屏幕，请选择**不再显示此简介页面**框。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-126">To skip this screen when running the wizard in the future, select the **Do not show this introduction page again** box.</span></span> <span data-ttu-id="e2ab6-127">单击 **“下一步”** 继续。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-127">Click **Next** to continue.</span></span>  

## <a name="selecting-purchase-order-instance"></a><span data-ttu-id="e2ab6-128">选择采购订单实例</span><span class="sxs-lookup"><span data-stu-id="e2ab6-128">Selecting purchase order instance</span></span>  

-   <span data-ttu-id="e2ab6-129">上**平面文件架构信息**屏幕上，选择你的实例并输入以下信息。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-129">On the **Flat File Schema Information** screen, select your instance and enter the following information.</span></span> <span data-ttu-id="e2ab6-130">完成后，单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-130">When you are done, click **Next** to continue.</span></span>  

    -   <span data-ttu-id="e2ab6-131">**实例文件：** 单击**浏览**按钮以查找将从其生成架构的平面文件。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-131">**Instance file:** Click the **Browse** button to locate the flat file from which the schema will be generated.</span></span> <span data-ttu-id="e2ab6-132">浏览到包含演练先决条件部分中创建的文本文件的文件夹： 平面文件架构从文档实例创建。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-132">Browse to the folder containing the text file you created in the Prerequisites section of Walkthrough: Creating a Flat File Schema From a Document Instance.</span></span>  

    -   <span data-ttu-id="e2ab6-133">**记录名称：** 类型**PO**一点，这是架构根名称。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-133">**Record name:** Type **PO** as it will be the schema root name.</span></span>  

    -   <span data-ttu-id="e2ab6-134">**目标命名空间：** 类型**http://Flat_File_Project.PurchaseOrder**架构目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-134">**Target namespace:** Type **http://Flat_File_Project.PurchaseOrder** for schema target namespace.</span></span>  

    -   <span data-ttu-id="e2ab6-135">**代码页：** 选择**utf-8 (65001)** 的下拉列表选择列表中。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-135">**Code page:** Select **UTF-8 (65001)** from the drop down selection list.</span></span>  

    -   <span data-ttu-id="e2ab6-136">**计算以字节为单位的位置：** 选中此框，如果你想要通过字节来计算位置数据字段。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-136">**Count positions in bytes:** Check this box if you wish to count the positional data fields by bytes.</span></span> <span data-ttu-id="e2ab6-137">默认情况下，位置数据字段以字符为单位计算。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-137">By default, the positional data fields are counted in characters.</span></span> <span data-ttu-id="e2ab6-138">在本演练中，保留**单位计算位置以字节为单位**复选框未选中状态。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-138">In this walkthrough, leave the **Count positions in bytes** check box unchecked.</span></span>  

## <a name="select-purchase-order-data"></a><span data-ttu-id="e2ab6-139">选择采购订单数据</span><span class="sxs-lookup"><span data-stu-id="e2ab6-139">Select purchase order data</span></span>  

-   <span data-ttu-id="e2ab6-140">上**选择文档数据**显示屏幕中，平面文件的内容。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-140">On the **Select Document Data** screen, the contents of the flat file are displayed.</span></span> <span data-ttu-id="e2ab6-141">选择用于创建架构，所需的数据，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-141">Select the data needed for creating the schema, and then click **Next**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="e2ab6-142">如果你想要使用整个文档实例，可以按**CTRL-A**全。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-142">If you would like to use the entire document instance, you can press **Ctrl-A** to select all.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="e2ab6-143">检查**折长行**框如果想要查看整个文档实例内容在整个向导的编辑框中换行。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-143">Check **Wrap long lines** box if you want to view the entire document instance content wrapped into the edit box throughout the wizard.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="e2ab6-144">如果从交换实例创建架构，请只选择表示单个文档结构的部分。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-144">If you are creating the schema from an interchange instance, select only the part that represents the individual document structure.</span></span>  

## <a name="delimit-purchase-order-record"></a><span data-ttu-id="e2ab6-145">分隔采购订单记录</span><span class="sxs-lookup"><span data-stu-id="e2ab6-145">Delimit purchase order record</span></span>  

-   <span data-ttu-id="e2ab6-146">如采购订单的每一行结尾回车换行符 (CRLF) 中，选择**按分隔符符号**，然后单击**下一步**上**选择记录格式**屏幕。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-146">As each line of the purchase order ends with a carriage return line feed (CRLF), select **By delimiter symbol**, and then click **Next** on **Select Record Format** screen.</span></span>  

## <a name="specify-purchase-order-record-property"></a><span data-ttu-id="e2ab6-147">指定采购订单记录属性</span><span class="sxs-lookup"><span data-stu-id="e2ab6-147">Specify purchase order record property</span></span>  

- <span data-ttu-id="e2ab6-148">上**分隔记录**屏幕中，输入以下命令以定义架构的第一级，完成后，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-148">On the **Delimited Record** screen, enter the following to define the first level of the schema and when you are done, click **Next**.</span></span>  

  - <span data-ttu-id="e2ab6-149">**子分隔符：** 选择 **{CR} {LF}**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-149">**Child delimiter:** Select **{CR}{LF}**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="e2ab6-150">**子分隔符**属性是一个可编辑具有下拉选择列表框包含一组默认值。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-150">**Child delimiter** property is an editable box with drop down selection list contains a set of default values.</span></span> <span data-ttu-id="e2ab6-151">**子分隔符**可以指定为字符或十六进制值。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-151">The **Child delimiter** can be specified as a character or as a hexadecimal value.</span></span> <span data-ttu-id="e2ab6-152">例如，  **\\{** 或 **{0x0D0A}**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-152">For example, **\\{** or **{0x0D0A}**.</span></span>  

  - <span data-ttu-id="e2ab6-153">**转义符：** 转义符是取消其后的字符的任何特殊含义的单个字符。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-153">**Escape character:** An escape character is a single character that suppresses any special meaning of the character that follows it.</span></span> <span data-ttu-id="e2ab6-154">请参阅[转义符](../core/escape-characters.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-154">See [Escape Characters](../core/escape-characters.md) for more information.</span></span> <span data-ttu-id="e2ab6-155">将它保留为空，以用于演练。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-155">Leave it blank for the walkthrough.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="e2ab6-156">使用时**\\**， **{，** 并 **}** 对于**子分隔符**或**转义符**、必须使用反斜杠。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-156">When using **\\**, **{,** and **}** for **Child delimiter** or **Escape character**, a back slash must be used.</span></span> <span data-ttu-id="e2ab6-157">例如，  **\\ \\，** 并 **\\{**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-157">For example, **\\\\,** and **\\{**.</span></span>  

  - <span data-ttu-id="e2ab6-158">检查**记录带有标记标识符**框，然后输入**PO**中**标记**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-158">Check **Record has a tag identifier** box and type **PO** in **Tag**.</span></span> <span data-ttu-id="e2ab6-159">在多个记录文件中， **PO**将用于标识各个记录。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-159">In a multiple records file, **PO** will be used to identify each individual record.</span></span> <span data-ttu-id="e2ab6-160">单击 **“下一步”** 继续。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-160">Click **Next** to continue.</span></span>  

    <span data-ttu-id="e2ab6-161">![分隔的记录屏幕](../core/media/flatfileschemawizard-delimitedrecord1.gif "FlatFileSchemaWizard_DelimitedRecord1")</span><span class="sxs-lookup"><span data-stu-id="e2ab6-161">![Delimited Record screen](../core/media/flatfileschemawizard-delimitedrecord1.gif "FlatFileSchemaWizard_DelimitedRecord1")</span></span>  

## <a name="define-the-element-in-the-purchase-order-record"></a><span data-ttu-id="e2ab6-162">定义采购订单记录中的元素</span><span class="sxs-lookup"><span data-stu-id="e2ab6-162">Define the element in the purchase order record</span></span>  

1.  <span data-ttu-id="e2ab6-163">向导已标识了采购订单记录中的四个元素；您现在必须定义元素属性。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-163">The wizard has identified four elements in the purchase order record; you must now define the element property.</span></span> <span data-ttu-id="e2ab6-164">在第一行中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e2ab6-164">In the first row, do the following:</span></span>  

    1.  <span data-ttu-id="e2ab6-165">类型**日期**有关**元素名称**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-165">Type **date** for the **Element Name**.</span></span>  

    2.  <span data-ttu-id="e2ab6-166">选择**Field 元素**有关**元素类型**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-166">Select **Field element** for **Element Type**.</span></span>  

    3.  <span data-ttu-id="e2ab6-167">选择**日期**从下拉选择列表中为**数据类型**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-167">Select **date** from the drop-down selection list for **Data Type**.</span></span>  

2.  <span data-ttu-id="e2ab6-168">对以下元素重复执行步骤 a 至 c。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-168">Repeat Steps a to c for the following elements.</span></span> <span data-ttu-id="e2ab6-169">完成后，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-169">When you are done, click **Next**.</span></span>  

    |<span data-ttu-id="e2ab6-170">元素名称</span><span class="sxs-lookup"><span data-stu-id="e2ab6-170">Element Name</span></span>|<span data-ttu-id="e2ab6-171">元素类型</span><span class="sxs-lookup"><span data-stu-id="e2ab6-171">Element Type</span></span>|<span data-ttu-id="e2ab6-172">数据类型</span><span class="sxs-lookup"><span data-stu-id="e2ab6-172">Data Type</span></span>|  
    |------------------|------------------|---------------|  
    |<span data-ttu-id="e2ab6-173">**客户**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-173">**customer**</span></span>|<span data-ttu-id="e2ab6-174">**重复记录**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-174">**Repeating record**</span></span>||  
    ||<span data-ttu-id="e2ab6-175">**忽略**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-175">**Ignore**</span></span>||  
    |<span data-ttu-id="e2ab6-176">**项**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-176">**items**</span></span>|<span data-ttu-id="e2ab6-177">**记录**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-177">**Record**</span></span>||  

     <span data-ttu-id="e2ab6-178">![子元素屏幕](../core/media/flatfileschemawizard-childelements.gif "FlatFileSchemaWizard_ChildElements")</span><span class="sxs-lookup"><span data-stu-id="e2ab6-178">![Child Elements screen](../core/media/flatfileschemawizard-childelements.gif "FlatFileSchemaWizard_ChildElements")</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="e2ab6-179">您可以选择多个行，然后更改其**元素类型**为单个类型通过使用鼠标和 SHIFT 或 CTRL 键。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-179">You can select multiple rows and then change their **Element Type** to a single type by using the mouse and the SHIFT or CTRL key.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="e2ab6-180">单击后**下一步**上**子元素**屏幕中，您将无法再单击**回**重新定义或更改的子元素。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-180">After you click **Next** on the **Child Elements** screen, you will not be able to click **Back** to redefine or make any changes to the child elements.</span></span> <span data-ttu-id="e2ab6-181">您需要关闭该向导，然后重新启动它来定义平面文件架构。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-181">You may need to close the wizard and launch the wizard again to define the flat file schema.</span></span>  

3.  <span data-ttu-id="e2ab6-182">完成此过程的各个步骤后，将生成该架构的第一级，如以下屏幕快照所示。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-182">After you complete the steps in this procedure, the first level of the schema is generated as shown in the following screenshot.</span></span> <span data-ttu-id="e2ab6-183">现在已定义了三个唯一的元素，您还需要进一步定义采购订单记录中元素的子记录。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-183">Three unique elements are defined, and you will continue to further define the child records for the elements in the purchase order record.</span></span> <span data-ttu-id="e2ab6-184">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-184">Click **Next**.</span></span>  

     <span data-ttu-id="e2ab6-185">![示例架构屏幕](../core/media/flatfileschemawizard-schema1.gif "FlatFileSchemaWizard_Schema1")</span><span class="sxs-lookup"><span data-stu-id="e2ab6-185">![Sample Schema screen](../core/media/flatfileschemawizard-schema1.gif "FlatFileSchemaWizard_Schema1")</span></span>  

## <a name="define-the-customer-record"></a><span data-ttu-id="e2ab6-186">定义客户记录</span><span class="sxs-lookup"><span data-stu-id="e2ab6-186">Define the customer record</span></span>  

1.  <span data-ttu-id="e2ab6-187">因为我们定义**客户**元素作为**重复记录**类型并**项**元素作为**记录**键入 BizTalk平面文件架构向导现在将进一步定义这两个元素。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-187">Because we defined the **customer** element as the **Repeating record** type and the **items** element as the **Record** type, the BizTalk Flat File Schema Wizard now continues to further define these two elements.</span></span> <span data-ttu-id="e2ab6-188">上**架构视图**屏幕上，选择**客户**，然后单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-188">On the **Schema View** screen, select **customer**, and then click **Next** to continue.</span></span>  

2.  <span data-ttu-id="e2ab6-189">若要使用客户记录，您必须选择表示客户元素的数据。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-189">To work with the customer record, you need to select the data that represents that element.</span></span> <span data-ttu-id="e2ab6-190">由于客户记录是重复记录，因此客户记录的任何一行都可用于定义该记录。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-190">Because it is a repeating record, either of the lines can be used to define the record.</span></span> <span data-ttu-id="e2ab6-191">选择客户数据的第一行，然后单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-191">Select the first line of customer data and click **Next** to continue.</span></span>  

3.  <span data-ttu-id="e2ab6-192">上**选择记录格式**页上，选择**按相对位置**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-192">On the **Select Record Format** page, select **By relative positions**, and then click **Next**.</span></span>  

4.  <span data-ttu-id="e2ab6-193">该向导提供了一个用于显示和计算字段之间距离的可视化工具。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-193">The wizard provides a visual tool for showing and calculating the distance between the fields.</span></span> <span data-ttu-id="e2ab6-194">上**位置记录**页上，使用鼠标左键单击位置标记 10 来表示，名称字段的开始。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-194">On the **Positional Record** page, use the left mouse button to click the position marker 10 to represent where the name field begins.</span></span> <span data-ttu-id="e2ab6-195">单击要表示其余数据字段的以下位置标记：</span><span class="sxs-lookup"><span data-stu-id="e2ab6-195">Click the following position markers to represent the rest of the data fields:</span></span>  

    |<span data-ttu-id="e2ab6-196">字段名</span><span class="sxs-lookup"><span data-stu-id="e2ab6-196">Field Name</span></span>|<span data-ttu-id="e2ab6-197">位置标记</span><span class="sxs-lookup"><span data-stu-id="e2ab6-197">Position Marker</span></span>|  
    |----------------|---------------------|  
    |<span data-ttu-id="e2ab6-198">street</span><span class="sxs-lookup"><span data-stu-id="e2ab6-198">street</span></span>|<span data-ttu-id="e2ab6-199">30</span><span class="sxs-lookup"><span data-stu-id="e2ab6-199">30</span></span>|  
    |<span data-ttu-id="e2ab6-200">城市</span><span class="sxs-lookup"><span data-stu-id="e2ab6-200">city</span></span>|<span data-ttu-id="e2ab6-201">50</span><span class="sxs-lookup"><span data-stu-id="e2ab6-201">50</span></span>|  
    |<span data-ttu-id="e2ab6-202">state</span><span class="sxs-lookup"><span data-stu-id="e2ab6-202">state</span></span>|<span data-ttu-id="e2ab6-203">65</span><span class="sxs-lookup"><span data-stu-id="e2ab6-203">65</span></span>|  
    |<span data-ttu-id="e2ab6-204">邮政编码</span><span class="sxs-lookup"><span data-stu-id="e2ab6-204">postalcode</span></span>|<span data-ttu-id="e2ab6-205">68</span><span class="sxs-lookup"><span data-stu-id="e2ab6-205">68</span></span>|  

     <span data-ttu-id="e2ab6-206">单击 **“下一步”** 继续。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-206">Click **Next** to continue.</span></span>  

     <span data-ttu-id="e2ab6-207">![位置记录屏幕](../core/media/flatfileschemawizard-positionalrecord.gif "FlatFileSchemaWizard_PositionalRecord")</span><span class="sxs-lookup"><span data-stu-id="e2ab6-207">![Positional Record screen](../core/media/flatfileschemawizard-positionalrecord.gif "FlatFileSchemaWizard_PositionalRecord")</span></span>  

5.  <span data-ttu-id="e2ab6-208">上**子元素**页上，指定的子元素的属性。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-208">On the **Child Elements** page, you specify the properties of the child elements.</span></span> <span data-ttu-id="e2ab6-209">选择第一个行并键入**国家/地区**作为**元素名称**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-209">Select the first row and type **country** as the **Element Name**.</span></span> <span data-ttu-id="e2ab6-210">对于其他列，保留默认值。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-210">Leave the default values in the other columns.</span></span> <span data-ttu-id="e2ab6-211">键入以下值的其他属性**元素名称**:</span><span class="sxs-lookup"><span data-stu-id="e2ab6-211">Type the following values for the other properties for the **Element Name**:</span></span>  

    |<span data-ttu-id="e2ab6-212">元素名称</span><span class="sxs-lookup"><span data-stu-id="e2ab6-212">Element Name</span></span>|<span data-ttu-id="e2ab6-213">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="e2ab6-213">Value</span></span>|  
    |------------------|-----------|  
    |<span data-ttu-id="e2ab6-214">**customer_Child2**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-214">**customer_Child2**</span></span>|<span data-ttu-id="e2ab6-215">**fullName**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-215">**fullName**</span></span>|  
    |<span data-ttu-id="e2ab6-216">**customer_Child3**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-216">**customer_Child3**</span></span>|<span data-ttu-id="e2ab6-217">**街道**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-217">**street**</span></span>|  
    |<span data-ttu-id="e2ab6-218">**customer_Child4**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-218">**customer_Child4**</span></span>|<span data-ttu-id="e2ab6-219">**城市**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-219">**city**</span></span>|  
    |<span data-ttu-id="e2ab6-220">**customer_Child5**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-220">**customer_Child5**</span></span>|<span data-ttu-id="e2ab6-221">State</span><span class="sxs-lookup"><span data-stu-id="e2ab6-221">**state**</span></span>|  
    |<span data-ttu-id="e2ab6-222">**customer_Child6**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-222">**customer_Child6**</span></span>|<span data-ttu-id="e2ab6-223">**邮政编码**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-223">**postalcode**</span></span>|  

     <span data-ttu-id="e2ab6-224">单击 **“下一步”** 继续。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-224">Click **Next** to continue.</span></span>  

     <span data-ttu-id="e2ab6-225">![子元素屏幕](../core/media/flatfileschemawizard-childelements2.gif "FlatFileSchemaWizard_ChildElements2")</span><span class="sxs-lookup"><span data-stu-id="e2ab6-225">![Child Elements screen](../core/media/flatfileschemawizard-childelements2.gif "FlatFileSchemaWizard_ChildElements2")</span></span>  

6.  <span data-ttu-id="e2ab6-226">客户记录的子元素随即创建，如以下屏幕快照所示。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-226">The child elements of the customer record are created as shown in the following screenshot.</span></span> <span data-ttu-id="e2ab6-227">单击**下一步**定义物品记录的子元素。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-227">Click **Next** to define the child elements for the items record.</span></span>  

     <span data-ttu-id="e2ab6-228">![示例架构屏幕](../core/media/flatfileschemawizard-schema2.gif "FlatFileSchemaWizard_Schema2")</span><span class="sxs-lookup"><span data-stu-id="e2ab6-228">![Sample Schema screen](../core/media/flatfileschemawizard-schema2.gif "FlatFileSchemaWizard_Schema2")</span></span>  

#### <a name="define-the-items-record"></a><span data-ttu-id="e2ab6-229">定义物品记录</span><span class="sxs-lookup"><span data-stu-id="e2ab6-229">Define the items record</span></span>  

1. <span data-ttu-id="e2ab6-230">上**架构视图**页上，选择**项**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-230">On the **Schema View** page, select **items**, and then click **Next**.</span></span>  

2. <span data-ttu-id="e2ab6-231">上**选择文档数据**页上，选择整行开头的项，然后单击**下一步**以定义其子元素。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-231">On the **Select Document Data** page, select the entire line begins with ITEMS, and then click **Next** to define its child elements.</span></span>  

3. <span data-ttu-id="e2ab6-232">上**选择记录格式**页上，选择**按分隔符符号**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-232">On the **Select Record Format** page, select **By delimiter symbol**, and then click **Next**.</span></span>  

4. <span data-ttu-id="e2ab6-233">在“物品”记录中，逗号用于分隔各个物品。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-233">In the Items record, commas are used to delimit the individual items.</span></span> <span data-ttu-id="e2ab6-234">因此，在**分隔记录**页上，输入以下内容定义物品记录。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-234">Therefore, on the **Delimited Record** page, enter the following to define the items record.</span></span> <span data-ttu-id="e2ab6-235">完成后，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-235">When you are done, click **Next**.</span></span>  

   -   <span data-ttu-id="e2ab6-236">选择 **，** 从**子分隔符**下拉选择列表。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-236">Select **,** from **Child delimiter** drop-down selection list.</span></span>  

   -   <span data-ttu-id="e2ab6-237">将保留**转义符**文本框保留为空。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-237">Leave the **Escape character** text box blank.</span></span>  

   -   <span data-ttu-id="e2ab6-238">选择**记录带有标记标识符**并键入**项**中**标记**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-238">Select **Record has a tag identifier** and type **ITEMS** in **Tag**.</span></span>  

        <span data-ttu-id="e2ab6-239">在多个项记录中，**项**用于标识各个记录。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-239">In a multiple items record, **ITEMS** is used to identify each individual record.</span></span>  

5. <span data-ttu-id="e2ab6-240">使用中的值**分隔记录**页上，向导标识两个子元素。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-240">Using the values from the **Delimited Record** page, the wizard identifies two child elements.</span></span> <span data-ttu-id="e2ab6-241">由于其中一个是重复记录，选择第一个元素，并输入**项**作为元素名称，然后选择**重复记录**从下拉列表选择列表**元素类型**.</span><span class="sxs-lookup"><span data-stu-id="e2ab6-241">Because one of them is a repeating record, select the first element and enter **item** for Element Name, and then select **Repeating Record** from the drop down selection list for **Element Type**.</span></span> <span data-ttu-id="e2ab6-242">列中保留其余默认值。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-242">Leave the rest of the default values in the columns.</span></span> <span data-ttu-id="e2ab6-243">选择第二行，然后选择**忽略**从**元素类型**列表。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-243">Select the second row and select the **Ignore** from **Element Type** list.</span></span> <span data-ttu-id="e2ab6-244">当您单击**下一步**，在架构中创建项记录的下一级别。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-244">When you click **Next**, the next level for the items record is created in the schema.</span></span> <span data-ttu-id="e2ab6-245">您还需要定义采购订单架构的最后一部分。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-245">You continue to define the final part of the purchase order schema.</span></span>  

6. <span data-ttu-id="e2ab6-246">选择**项**，然后单击**下一步**继续**架构视图**页。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-246">Select **item** and then click **Next** to continue on the **Schema View** page.</span></span>  

7. <span data-ttu-id="e2ab6-247">上**选择文档数据**页上，选择**ITEM872 AA&#124;Lawnmower&#124;1&#124;148.95&#124;确认这是电力**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-247">On the **Select Document Data** page, select **ITEM872-AA&#124;Lawnmower&#124;1&#124;148.95&#124;Confirm this is electric**.</span></span> <span data-ttu-id="e2ab6-248">单击 **“下一步”** 继续。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-248">Click **Next** to continue.</span></span>  

8. <span data-ttu-id="e2ab6-249">上**选择记录格式**页上，选择**按分隔符符号**选项，因为由竖线分隔单个项 (&#124;)。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-249">On the **Select Record Format** page, select the **By delimiter symbol** option because the individual item is delimited by a pipe (&#124;).</span></span>  

9. <span data-ttu-id="e2ab6-250">上**分隔记录**页上，输入以下内容定义物品记录。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-250">On the **Delimited Record** page, enter the following to define the item record.</span></span> <span data-ttu-id="e2ab6-251">完成后，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-251">When you are done, click **Next**.</span></span>  

    -   <span data-ttu-id="e2ab6-252">选择 **&#124;** 从**子分隔符**下拉选择列表。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-252">Select **&#124;** from the **Child delimiter** drop down selection list.</span></span>  

    -   <span data-ttu-id="e2ab6-253">将保留**转义符**文本框保留为空。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-253">Leave the **Escape character** text box blank.</span></span>  

10. <span data-ttu-id="e2ab6-254">上**子元素**页上，向导已标识五个子元素。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-254">On the **Child Elements** page, the wizard has identified five child elements.</span></span> <span data-ttu-id="e2ab6-255">选择第一行，并输入**productCode**有关**元素名称**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-255">Select the first row and enter **productCode** for **Element name**.</span></span> <span data-ttu-id="e2ab6-256">对于其他列，请保留默认值。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-256">Leave the default values in the rest of the columns.</span></span> <span data-ttu-id="e2ab6-257">为其余**元素名称属性**，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="e2ab6-257">For the rest of the **Element Name properties**, type the following:</span></span>  

    |<span data-ttu-id="e2ab6-258">元素名称</span><span class="sxs-lookup"><span data-stu-id="e2ab6-258">Element Name</span></span>|<span data-ttu-id="e2ab6-259">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="e2ab6-259">Value</span></span>|  
    |------------------|-----------|  
    |<span data-ttu-id="e2ab6-260">**item_Child2**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-260">**item_Child2**</span></span>|<span data-ttu-id="e2ab6-261">**description**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-261">**description**</span></span>|  
    |<span data-ttu-id="e2ab6-262">**item_Child3**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-262">**item_Child3**</span></span>|<span data-ttu-id="e2ab6-263">**数量**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-263">**quantity**</span></span>|  
    |<span data-ttu-id="e2ab6-264">**item_Child4**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-264">**item_Child4**</span></span>|<span data-ttu-id="e2ab6-265">**单价**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-265">**unitPrice**</span></span>|  
    |<span data-ttu-id="e2ab6-266">**item_Child5**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-266">**item_Child5**</span></span>|<span data-ttu-id="e2ab6-267">**说明**</span><span class="sxs-lookup"><span data-stu-id="e2ab6-267">**notes**</span></span>|  

     <span data-ttu-id="e2ab6-268">单击 **“下一步”** 继续。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-268">Click **Next** to continue.</span></span>  

11. <span data-ttu-id="e2ab6-269">您现在已定义了采购订单架构的所有节点。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-269">You have defined all the nodes for the purchase order schema.</span></span> <span data-ttu-id="e2ab6-270">上**架构视图**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-270">On the **Schema View** page, click **Finish**.</span></span>  

12. <span data-ttu-id="e2ab6-271">您现在可以查看最终的采购订单架构了。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-271">You can now view the final purchase order schema.</span></span> <span data-ttu-id="e2ab6-272">您还可以使用 BizTalk 架构编辑器优化该架构。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-272">You can also refine the schema by using the BizTalk Schema Editor.</span></span> <span data-ttu-id="e2ab6-273">请参阅平面文件属性名表和属性表中的**Schema 节点属性**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-273">See Flat file property name table and the Property tables in **Schema Node Properties**.</span></span> <span data-ttu-id="e2ab6-274">此属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-274">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="summary"></a><span data-ttu-id="e2ab6-275">“摘要”</span><span class="sxs-lookup"><span data-stu-id="e2ab6-275">Summary</span></span>  
 <span data-ttu-id="e2ab6-276">在此演练中，您学习了如何使用“BizTalk 平面文件架构向导”从文档实例创建平面文件架构。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-276">In this walkthrough you have learned how to use the BizTalk Flat File Schema Wizard to create a flat file schema from a document instance.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="e2ab6-277">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e2ab6-277">Next Steps</span></span>  

### <a name="validate-po-instance"></a><span data-ttu-id="e2ab6-278">验证 PO 实例</span><span class="sxs-lookup"><span data-stu-id="e2ab6-278">Validate PO Instance</span></span>  
 <span data-ttu-id="e2ab6-279">为了确保 PurchaseOrder.xsd 架构能够正确解析 PO 实例，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e2ab6-279">To ensure that the PurchaseOrder.xsd schema can correctly parse the PO instance, do the following:</span></span>  

1.  <span data-ttu-id="e2ab6-280">在解决方案资源管理器中右键单击**PurchaseOrder.xsd** ，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-280">In Solution Explorer, right-click the **PurchaseOrder.xsd** and then select **Properties**.</span></span>  

2.  <span data-ttu-id="e2ab6-281">在中**属性页**，请确保**输入实例文件名**字段指向演练先决条件部分中创建的 PO 实例的位置： 创建平面文件从文档实例的架构。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-281">In the **Property Pages**, make sure that the **Input Instance Filename** field is pointing to the location of the PO instance you created in the Prerequisites section of Walkthrough: Creating a Flat File Schema From a Document Instance.</span></span> <span data-ttu-id="e2ab6-282">单击**确定**关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-282">Click **OK** to close the dialog.</span></span>  

3.  <span data-ttu-id="e2ab6-283">在解决方案资源管理器中右键单击**PurchaseOrder.xsd**，然后选择**验证实例**。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-283">In Solution Explorer, right-click **PurchaseOrder.xsd**, and then select **Validate Instance**.</span></span> <span data-ttu-id="e2ab6-284">验证组件随即打开。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-284">The validation component opens.</span></span>  

4.  <span data-ttu-id="e2ab6-285">验证完成后，将向您提供一个链接，使用该链接可以查看基于用 PurchaseOrder.xsd 架构解析 PO 实例所得结果的 XML 输出。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-285">After validation is completed, a link is provided to you for viewing the XML output based on parsing result on PO instance using the PurchaseOrder.xsd schema.</span></span> <span data-ttu-id="e2ab6-286">若要查看 XML 输出，请按住 Ctrl，然后单击该链接。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-286">To view the XML output, press Ctrl and click the link.</span></span>  

### <a name="create-pipelines-for-the-schema"></a><span data-ttu-id="e2ab6-287">为架构创建管道</span><span class="sxs-lookup"><span data-stu-id="e2ab6-287">Create Pipelines for the Schema</span></span>  
 <span data-ttu-id="e2ab6-288">现在，您可以基于 PurchaseOrder.xsd 架构创建 BizTalk 应用程序使用的接收管道或发送管道。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-288">Now you can create a receive or send pipeline based on the PurchaseOrder.xsd schema to use with your BizTalk application.</span></span>  

 <span data-ttu-id="e2ab6-289">若要创建新的管道，请参阅[如何创建新的管道](../core/how-to-create-a-new-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-289">To create a new pipeline, see [How to Create a New Pipeline](../core/how-to-create-a-new-pipeline.md).</span></span> <span data-ttu-id="e2ab6-290">若要配置平面文件管道组件，请参阅[如何配置平面文件组装器管道组件](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)并[如何配置平面文件拆装器管道组件](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="e2ab6-290">To configure the Flat File Pipeline components, see [How to Configure the Flat File Assembler Pipeline Component](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md) and [How to Configure the Flat File Disassembler Pipeline Component](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="e2ab6-291">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2ab6-291">See Also</span></span>  
 <span data-ttu-id="e2ab6-292">[如何使用 BizTalk 平面文件架构向导](../core/how-to-use-biztalk-flat-file-schema-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="e2ab6-292">[How to Use BizTalk Flat File Schema Wizard](../core/how-to-use-biztalk-flat-file-schema-wizard.md) </span></span>  
 [<span data-ttu-id="e2ab6-293">使用“BizTalk 平面文件架构向导”创建架构</span><span class="sxs-lookup"><span data-stu-id="e2ab6-293">Creating Schemas Using BizTalk Flat File Schema Wizard</span></span>](../core/creating-schemas-using-biztalk-flat-file-schema-wizard.md)