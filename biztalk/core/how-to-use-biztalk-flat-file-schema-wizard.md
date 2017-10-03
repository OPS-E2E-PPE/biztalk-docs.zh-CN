---
title: "如何使用 BizTalk 平面文件架构向导 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7cb8b18-266d-422e-bdb8-1efefb6b4c8e
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff7d87959bd39b9040a495022c2b7bf352954848
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-biztalk-flat-file-schema-wizard"></a><span data-ttu-id="d2b19-102">如何使用“BizTalk 平面文件架构向导”</span><span class="sxs-lookup"><span data-stu-id="d2b19-102">How to Use BizTalk Flat File Schema Wizard</span></span>
<span data-ttu-id="d2b19-103">在以前的 BizTalk Server 版本中，您必须在 BizTalk 架构编辑器中手动向 XML 架构定义 (XSD) 语言架构添加批注，才能使平面文件管道组件（例如，平面文件拆装器和平面文件组装器）理解这些架构。</span><span class="sxs-lookup"><span data-stu-id="d2b19-103">In previous releases of BizTalk Server, you had to manually add the annotations to XML Schema Definition language (XSD) schemas in the BizTalk Schema Editor to make these schemas understandable to Flat File Pipeline components, such as Flat File Disassembler and Flat File Assembler.</span></span> <span data-ttu-id="d2b19-104">你仍然可以这样做使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]架构编辑器。</span><span class="sxs-lookup"><span data-stu-id="d2b19-104">You can still do this using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Schema Editor.</span></span> <span data-ttu-id="d2b19-105">为了减少创建解决方案的手动步骤和所需时间，您可以使用“BizTalk 平面文件架构向导”，该向导提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="d2b19-105">To reduce the number of manual steps and time needed to create solutions, you use the BizTalk Flat File Schema Wizard, which provides the following functionalities:</span></span>  
  
-   <span data-ttu-id="d2b19-106">将真实的平面文件实例用作输入内容。</span><span class="sxs-lookup"><span data-stu-id="d2b19-106">Uses real flat file instances as input.</span></span>  
  
-   <span data-ttu-id="d2b19-107">包括一个用于处理分隔平面文件架构和位置平面文件架构的可视化设计图面。</span><span class="sxs-lookup"><span data-stu-id="d2b19-107">Includes a visual design surface for working with delimited and positional flat file schemas.</span></span>  
  
-   <span data-ttu-id="d2b19-108">使用基于向导的重入过程以交互方式向架构添加元素和定义与平面文件相关的批注。</span><span class="sxs-lookup"><span data-stu-id="d2b19-108">Uses a re-entrant wizard-based process for adding elements to the schema and defining flat file related annotations interactively.</span></span>  
  
-   <span data-ttu-id="d2b19-109">支持标记标识符、字符分隔符和十六进制分隔符。</span><span class="sxs-lookup"><span data-stu-id="d2b19-109">Provides support for tag identifiers and character and hexadecimal delimiters.</span></span>  
  
-   <span data-ttu-id="d2b19-110">自动确定标记标识符的偏移量以及子级的分隔顺序。</span><span class="sxs-lookup"><span data-stu-id="d2b19-110">Automatically determines tag identifier offsets and child delimiting order.</span></span>  
  
-   <span data-ttu-id="d2b19-111">提供文件格式的预览功能。</span><span class="sxs-lookup"><span data-stu-id="d2b19-111">Provides preview capabilities for the file format.</span></span>  
  
-   <span data-ttu-id="d2b19-112">可用于选择交换实例中的首选子数据，以用于定义平面文件架构。</span><span class="sxs-lookup"><span data-stu-id="d2b19-112">Enables you to select preferred sub-data within the interchange instance to use to define the flat file schemas.</span></span>  
  
## <a name="how-to-start-the-biztalk-flat-file-schema-wizard"></a><span data-ttu-id="d2b19-113">如何启动“BizTalk 平面文件架构向导”</span><span class="sxs-lookup"><span data-stu-id="d2b19-113">How to Start the BizTalk Flat File Schema Wizard</span></span>  
 <span data-ttu-id="d2b19-114">您可以从 Microsoft Visual Studio 解决方案资源管理器或 BizTalk 架构编辑器启动该向导。</span><span class="sxs-lookup"><span data-stu-id="d2b19-114">You can start the wizard from either the Microsoft Visual Studio Solution Explorer or from the BizTalk Schema Editor.</span></span>  
  
#### <a name="to-start-the-wizard-from-solution-explorer"></a><span data-ttu-id="d2b19-115">从解决方案资源管理器启动向导</span><span class="sxs-lookup"><span data-stu-id="d2b19-115">To start the wizard from Solution Explorer</span></span>  
  
1.  <span data-ttu-id="d2b19-116">在 Microsoft 中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开**解决方案资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="d2b19-116">In Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="d2b19-117">若要添加新的平面文件架构，右键单击 BizTalk 项目，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="d2b19-117">To add the new flat-file schema, right-click the BizTalk project, and select **Add**.</span></span>  
  
3.  <span data-ttu-id="d2b19-118">单击**新项。**</span><span class="sxs-lookup"><span data-stu-id="d2b19-118">Click **New Item.**</span></span>  
  
     <span data-ttu-id="d2b19-119">![解决方案资源管理器菜单](../core/media/flatfileschemawizard-01.gif "FlatFileSchemaWizard_01")</span><span class="sxs-lookup"><span data-stu-id="d2b19-119">![Solution Explorer menu](../core/media/flatfileschemawizard-01.gif "FlatFileSchemaWizard_01")</span></span>  
  
4.  <span data-ttu-id="d2b19-120">在**添加新项**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d2b19-120">In the **Add New Item** window, do the following:</span></span>  
  
    1.  <span data-ttu-id="d2b19-121">在**类别**部分中，选择**架构文件**。</span><span class="sxs-lookup"><span data-stu-id="d2b19-121">In the **Categories** section, select **Schema Files**.</span></span>  
  
    2.  <span data-ttu-id="d2b19-122">在**模板**部分中，选择**平面文件架构向导**。</span><span class="sxs-lookup"><span data-stu-id="d2b19-122">In the **Templates** section, select **Flat File Schema Wizard**.</span></span>  
  
    3.  <span data-ttu-id="d2b19-123">在**名称**文本框中，键入一个新的架构的名称。</span><span class="sxs-lookup"><span data-stu-id="d2b19-123">In the **Name** text box, type a name for the new schema.</span></span>  
  
    4.  <span data-ttu-id="d2b19-124">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="d2b19-124">Click **Add**.</span></span>  
  
         <span data-ttu-id="d2b19-125">“BizTalk 平面文件架构向导”随即打开。</span><span class="sxs-lookup"><span data-stu-id="d2b19-125">The BizTalk Flat File Schema Wizard opens.</span></span>  
  
#### <a name="to-start-the-wizard-from-the-schema-editor"></a><span data-ttu-id="d2b19-126">从架构编辑器启动向导</span><span class="sxs-lookup"><span data-stu-id="d2b19-126">To start the Wizard from the Schema Editor</span></span>  
  
1.  <span data-ttu-id="d2b19-127">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开**解决方案资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="d2b19-127">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="d2b19-128">若要添加新的平面文件架构，右键单击 BizTalk 项目，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="d2b19-128">To add the new flat-file schema, right-click the BizTalk project, and select **Add**.</span></span> <span data-ttu-id="d2b19-129">选择**新项**单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="d2b19-129">Select **New Item** and click **New Item**.</span></span>  
  
3.  <span data-ttu-id="d2b19-130">在**添加新项**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d2b19-130">In the **Add New Item** window, do the following:</span></span>  
  
    1.  <span data-ttu-id="d2b19-131">在**类别**部分中，选择**架构文件**。</span><span class="sxs-lookup"><span data-stu-id="d2b19-131">In the **Categories** section, select **Schema Files**.</span></span>  
  
    2.  <span data-ttu-id="d2b19-132">在**模板**部分中，选择**平面文件架构**。</span><span class="sxs-lookup"><span data-stu-id="d2b19-132">In the **Templates** section, select **Flat File Schema**.</span></span>  
  
    3.  <span data-ttu-id="d2b19-133">在**名称**文本框中，键入一个新的架构的名称。</span><span class="sxs-lookup"><span data-stu-id="d2b19-133">In the **Name** text box, type a name for the new schema.</span></span>  
  
    4.  <span data-ttu-id="d2b19-134">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="d2b19-134">Click **Add**.</span></span>  
  
    5.  <span data-ttu-id="d2b19-135">右键单击**根**和选择**从平面文件实例定义记录**。</span><span class="sxs-lookup"><span data-stu-id="d2b19-135">Right-click **Root** and select **Define Record from Flat File Instance**.</span></span>  
  
         <span data-ttu-id="d2b19-136">此时“BizTalk 平面文件架构向导”启动。</span><span class="sxs-lookup"><span data-stu-id="d2b19-136">The BizTalk Flat File Schema Wizard now starts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d2b19-137">如果你具有在架构编辑器中打开的工作架构，你需要做是用鼠标右键单击所选的节点，然后选择**从平面文件实例定义记录**。</span><span class="sxs-lookup"><span data-stu-id="d2b19-137">If you have a working schema opened in the Schema Editor, all you need to do is right-click the selected node and then select **Define Record from Flat File Instance**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d2b19-138">**从平面文件实例定义记录**如果所选的节点没有子元素记录启用选项。</span><span class="sxs-lookup"><span data-stu-id="d2b19-138">The **Define Record from Flat File Instance** option is enabled if the selected node is a record without child elements.</span></span> <span data-ttu-id="d2b19-139">如果所选节点有子元素，该向导会删除所有当前子元素，然后生成新的子元素。</span><span class="sxs-lookup"><span data-stu-id="d2b19-139">If the selected node has child elements, the wizard deletes all current child elements and generates the new ones.</span></span> <span data-ttu-id="d2b19-140">在删除现有子元素之前，向导会提示您进行确认。</span><span class="sxs-lookup"><span data-stu-id="d2b19-140">The wizard prompts you to confirm before deleting the existing child elements.</span></span>  
  
## <a name="considerations-for-using-the-flat-file-schema-wizard"></a><span data-ttu-id="d2b19-141">使用平面文件架构向导的注意事项</span><span class="sxs-lookup"><span data-stu-id="d2b19-141">Considerations for Using the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="d2b19-142">本部分介绍您在使用“BizTalk 平面文件架构向导”时应注意的问题。</span><span class="sxs-lookup"><span data-stu-id="d2b19-142">This section describes issues you should consider when working with the BizTalk Flat File Schema Wizard.</span></span>  
  
### <a name="working-with-multibyte-character-set-mbcs"></a><span data-ttu-id="d2b19-143">使用多字节字符集 (MBCS)</span><span class="sxs-lookup"><span data-stu-id="d2b19-143">Working with Multibyte Character Set (MBCS)</span></span>  
 <span data-ttu-id="d2b19-144">默认情况下，**计数以字节为单位的位置**复选框未选中平面文件架构信息屏幕上。</span><span class="sxs-lookup"><span data-stu-id="d2b19-144">By default, the **Count positions in bytes** check box is unchecked on the Flat File Schema Information screen.</span></span> <span data-ttu-id="d2b19-145">该向导按字符来计算位置数，这意味着如果您的位置平面文件实例中有 MBCS 字符，则将无法正确计算位置数。</span><span class="sxs-lookup"><span data-stu-id="d2b19-145">The wizard counts the positions by characters; which mean that if you have MBCS characters in your positional flat file instance, the positions are not counted correctly.</span></span> <span data-ttu-id="d2b19-146">通过选择**计数以字节为单位的位置**复选框，向导显示 MBCS 字符替换其位置的长度的其他指示。</span><span class="sxs-lookup"><span data-stu-id="d2b19-146">By selecting the **Count positions in bytes** check box, the wizard displays MBCS characters with an additional indication of their positional length.</span></span> <span data-ttu-id="d2b19-147">字符占据屏幕的一个位置 ， 而剩下的长度将用圆点符号“•” 填充 。</span><span class="sxs-lookup"><span data-stu-id="d2b19-147">The character takes one position on the display and the remaining length is filled out with dot symbols, “•”.</span></span> <span data-ttu-id="d2b19-148">具体填充多少圆点符号取决于文件是以双字节字符集 (DBCS)、Unicode，还是 UTF-8 格式保存的。</span><span class="sxs-lookup"><span data-stu-id="d2b19-148">The number of dot symbols filled will be depending on the files that were saved in double byte character set (DBCS), Unicode or UTF-8 format.</span></span>  
  
### <a name="code-pages-supported-in-the-flat-file-schema-wizard"></a><span data-ttu-id="d2b19-149">平面文件架构向导中支持的代码页</span><span class="sxs-lookup"><span data-stu-id="d2b19-149">Code Pages Supported in the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="d2b19-150">以下是该向导支持的代码页的列表：</span><span class="sxs-lookup"><span data-stu-id="d2b19-150">The following is a list of supported code pages for the wizard:</span></span>  
  
-   <span data-ttu-id="d2b19-151">阿拉伯语 (1256)</span><span class="sxs-lookup"><span data-stu-id="d2b19-151">Arabic (1256)</span></span>  
  
-   <span data-ttu-id="d2b19-152">ASCII (20127)</span><span class="sxs-lookup"><span data-stu-id="d2b19-152">ASCII (20127)</span></span>  
  
-   <span data-ttu-id="d2b19-153">波罗的语 (1257)</span><span class="sxs-lookup"><span data-stu-id="d2b19-153">Baltic (1257)</span></span>  
  
-   <span data-ttu-id="d2b19-154">Big-Endian-UTF16 (1201)</span><span class="sxs-lookup"><span data-stu-id="d2b19-154">Big-Endian-UTF16 (1201)</span></span>  
  
-   <span data-ttu-id="d2b19-155">中部欧洲 (1250)</span><span class="sxs-lookup"><span data-stu-id="d2b19-155">Central-European (1250)</span></span>  
  
-   <span data-ttu-id="d2b19-156">西里尔语 (1251)</span><span class="sxs-lookup"><span data-stu-id="d2b19-156">Cyrillic (1251)</span></span>  
  
-   <span data-ttu-id="d2b19-157">希腊语 (1253)</span><span class="sxs-lookup"><span data-stu-id="d2b19-157">Greek (1253)</span></span>  
  
-   <span data-ttu-id="d2b19-158">希伯来语 (1255)</span><span class="sxs-lookup"><span data-stu-id="d2b19-158">Hebrew (1255)</span></span>  
  
-   <span data-ttu-id="d2b19-159">日语 Shift JIS (932)</span><span class="sxs-lookup"><span data-stu-id="d2b19-159">Japanese-Shift-JIS (932)</span></span>  
  
-   <span data-ttu-id="d2b19-160">韩语 (949)</span><span class="sxs-lookup"><span data-stu-id="d2b19-160">Korean (949)</span></span>  
  
-   <span data-ttu-id="d2b19-161">Little-Endian-UTF16 (1200)</span><span class="sxs-lookup"><span data-stu-id="d2b19-161">Little-Endian-UTF16 (1200)</span></span>  
  
-   <span data-ttu-id="d2b19-162">简体中文 GBK (936)</span><span class="sxs-lookup"><span data-stu-id="d2b19-162">Simplified-Chinese-GBK (936)</span></span>  
  
-   <span data-ttu-id="d2b19-163">简体中文 GB18030 (54936)</span><span class="sxs-lookup"><span data-stu-id="d2b19-163">Simplified-Chinese-GB18030 (54936)</span></span>  
  
-   <span data-ttu-id="d2b19-164">泰语 (874)</span><span class="sxs-lookup"><span data-stu-id="d2b19-164">Thai (874)</span></span>  
  
-   <span data-ttu-id="d2b19-165">繁体中文 BIG5 (950)</span><span class="sxs-lookup"><span data-stu-id="d2b19-165">Traditional-Chinese-BIG5 (950)</span></span>  
  
-   <span data-ttu-id="d2b19-166">土耳其语 (1254)</span><span class="sxs-lookup"><span data-stu-id="d2b19-166">Turkish (1254)</span></span>  
  
-   <span data-ttu-id="d2b19-167">UTF-7 (65000)</span><span class="sxs-lookup"><span data-stu-id="d2b19-167">UTF-7 (65000)</span></span>  
  
-   <span data-ttu-id="d2b19-168">UTF-8 (65001)</span><span class="sxs-lookup"><span data-stu-id="d2b19-168">UTF-8 (65001)</span></span>  
  
-   <span data-ttu-id="d2b19-169">越南语 (1258)</span><span class="sxs-lookup"><span data-stu-id="d2b19-169">Vietnamese (1258)</span></span>  
  
-   <span data-ttu-id="d2b19-170">西欧语 (1252)</span><span class="sxs-lookup"><span data-stu-id="d2b19-170">Western-European (1252)</span></span>  
  
### <a name="record-types-in-the-flat-file-schema-wizard"></a><span data-ttu-id="d2b19-171">平面文件架构向导中的记录类型</span><span class="sxs-lookup"><span data-stu-id="d2b19-171">Record Types in the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="d2b19-172">平面文件不能将分隔记录包含在位置记录中。</span><span class="sxs-lookup"><span data-stu-id="d2b19-172">Flat files cannot contain delimited records within positional records.</span></span> <span data-ttu-id="d2b19-173">由于该向导后可重入基于中的定义的类型的单选按钮**按分隔符符号**和**按相对位置**启用或禁用的父记录的格式在向导中定义子级。</span><span class="sxs-lookup"><span data-stu-id="d2b19-173">Because the wizard is re-entrant based, the radio buttons that define the type of the **By delimiter symbol** and **By relative positions** are enabled or disabled based on the format of the parent records for the child which you define in the wizard.</span></span> <span data-ttu-id="d2b19-174">例如：</span><span class="sxs-lookup"><span data-stu-id="d2b19-174">For example,</span></span>  
  
-   <span data-ttu-id="d2b19-175">如果针对分隔记录的子级运行该向导，则两个单选按钮都是选中的。</span><span class="sxs-lookup"><span data-stu-id="d2b19-175">If the wizard is run for a child of a delimited record, both radio buttons are selected.</span></span>  
  
-   <span data-ttu-id="d2b19-176">如果子级的位置的记录，运行该向导**按分隔符符号**单选按钮处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="d2b19-176">If the wizard is run for a child of a positional record, the **By delimiter symbol** radio button is cleared.</span></span>  
  
### <a name="delimiter-symbols-in-the-flat-file-schema-wizard"></a><span data-ttu-id="d2b19-177">平面文件架构向导中的分隔符符号</span><span class="sxs-lookup"><span data-stu-id="d2b19-177">Delimiter Symbols in the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="d2b19-178">子分隔符属性的下拉列表包含以下常见的分隔符：</span><span class="sxs-lookup"><span data-stu-id="d2b19-178">The child delimiter property drop-down list contains with the following common delimiters:</span></span>  
  
-   <span data-ttu-id="d2b19-179">{CR}{LF}</span><span class="sxs-lookup"><span data-stu-id="d2b19-179">{CR}{LF}</span></span>  
  
-   <span data-ttu-id="d2b19-180">{CR}</span><span class="sxs-lookup"><span data-stu-id="d2b19-180">{CR}</span></span>  
  
-   <span data-ttu-id="d2b19-181">{LF}</span><span class="sxs-lookup"><span data-stu-id="d2b19-181">{LF}</span></span>  
  
-   <span data-ttu-id="d2b19-182">{TAB}</span><span class="sxs-lookup"><span data-stu-id="d2b19-182">{TAB}</span></span>  
  
-   <span data-ttu-id="d2b19-183">{SPACE}</span><span class="sxs-lookup"><span data-stu-id="d2b19-183">{SPACE}</span></span>  
  
-   <span data-ttu-id="d2b19-184">{0x1A}</span><span class="sxs-lookup"><span data-stu-id="d2b19-184">{0x1A}</span></span>  
  
-   <span data-ttu-id="d2b19-185">&#124;</span><span class="sxs-lookup"><span data-stu-id="d2b19-185">&#124;</span></span>  
  
-   <span data-ttu-id="d2b19-186">、</span><span class="sxs-lookup"><span data-stu-id="d2b19-186">,</span></span>  
  
-   <span data-ttu-id="d2b19-187">;</span><span class="sxs-lookup"><span data-stu-id="d2b19-187">;</span></span>  
  
 <span data-ttu-id="d2b19-188">此属性的默认值为 {CR}{LF}。</span><span class="sxs-lookup"><span data-stu-id="d2b19-188">The default value for this property is {CR}{LF}.</span></span> <span data-ttu-id="d2b19-189">该属性还有一个可编辑的文本框，这样您就可以将子分隔符指定为字符序列或字符的十六进制值。</span><span class="sxs-lookup"><span data-stu-id="d2b19-189">The property is also an editable text box, so that you can specify the child delimiter as a sequence of characters or as hexadecimal values of the characters.</span></span> <span data-ttu-id="d2b19-190">例如，将字符“a”或“street”用作子分隔符。</span><span class="sxs-lookup"><span data-stu-id="d2b19-190">An example of using characters for the child delimiter would be "a" or "street."</span></span> <span data-ttu-id="d2b19-191">十六进制分隔符用以下格式指定：</span><span class="sxs-lookup"><span data-stu-id="d2b19-191">Hexadecimal delimiters are specified using the following format:</span></span>  
  
-   <span data-ttu-id="d2b19-192">{0xnnnn}。</span><span class="sxs-lookup"><span data-stu-id="d2b19-192">{0xnnnn}.</span></span> <span data-ttu-id="d2b19-193">例如，{0x0D} {0x0A}，{为 0x09} 或 {0x20}。</span><span class="sxs-lookup"><span data-stu-id="d2b19-193">For example, {0x0D}{0x0A}, {0x09} or {0x20}.</span></span>  
  
 <span data-ttu-id="d2b19-194">例如，使用十六进制值序列 {0x0D}{0x0A}, {0x09}{0x20}。</span><span class="sxs-lookup"><span data-stu-id="d2b19-194">An example of using sequence of hexadecimal values is {0x0D}{0x0A}, {0x09}{0x20}.</span></span>  
  
 <span data-ttu-id="d2b19-195">如果使用符号\\，{，或} 作为分隔符，则必须将放置分隔符符号的前面附加的反斜杠符号，否则您将收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="d2b19-195">If you use the symbols \\, {, or } as the delimiter, you must place an additional backslash symbol in front of the delimiter symbol, otherwise you will receive an error message.</span></span> <span data-ttu-id="d2b19-196">例如：</span><span class="sxs-lookup"><span data-stu-id="d2b19-196">For example,</span></span>  
  
-   <span data-ttu-id="d2b19-197">\\\\\\{，或\\}。</span><span class="sxs-lookup"><span data-stu-id="d2b19-197">\\\\, \\{, or \\}.</span></span>  
  
### <a name="relative-positions-in-the-flat-file-schema-wizard"></a><span data-ttu-id="d2b19-198">平面文件架构向导中的相对位置</span><span class="sxs-lookup"><span data-stu-id="d2b19-198">Relative Positions in the Flat File Schema Wizard</span></span>  
  
#### <a name="setting-position-markers"></a><span data-ttu-id="d2b19-199">设置位置标记</span><span class="sxs-lookup"><span data-stu-id="d2b19-199">Setting Position Markers</span></span>  
 <span data-ttu-id="d2b19-200">用鼠标左键单击位置选择框中的某个位置标记来设置新的位置标记线。</span><span class="sxs-lookup"><span data-stu-id="d2b19-200">Use the left mouse button to click a position marker in the position selection box to set the new position marker line.</span></span> <span data-ttu-id="d2b19-201">位置标记用实线表示。</span><span class="sxs-lookup"><span data-stu-id="d2b19-201">The position marker is represented as a solid line.</span></span> <span data-ttu-id="d2b19-202">默认情况下，位置标记线位于记录开头的位置 0 处。</span><span class="sxs-lookup"><span data-stu-id="d2b19-202">By default, a position marker line exists at the beginning of the record at position zero.</span></span> <span data-ttu-id="d2b19-203">若要删除某一现有位置标记行，用鼠标右键单击它。</span><span class="sxs-lookup"><span data-stu-id="d2b19-203">To remove an existing position marker line, use the left mouse button to click  it.</span></span>  
  
### <a name="escape-characters-in-the-flat-file-schema-wizard"></a><span data-ttu-id="d2b19-204">平面文件架构向导中的转义符</span><span class="sxs-lookup"><span data-stu-id="d2b19-204">Escape Characters in the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="d2b19-205">：转义符是取消其后紧跟字符的任何特殊意义的单个字符。</span><span class="sxs-lookup"><span data-stu-id="d2b19-205">An escape character is a single character that suppresses any special meaning of the character that follows it.</span></span> <span data-ttu-id="d2b19-206">有关详细信息，请参阅[转义字符](../core/escape-characters.md)下的主题[如何解释的特殊字符作为字段值的一部分](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)。</span><span class="sxs-lookup"><span data-stu-id="d2b19-206">For more information, see [Escape Characters](../core/escape-characters.md) topic under [Ways to Interpret Special Characters as Part of a Field Value](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md).</span></span> <span data-ttu-id="d2b19-207">您可以在向导中使用转义符属性指定在解析平面文件实例时使用的转义符。</span><span class="sxs-lookup"><span data-stu-id="d2b19-207">You use the escape character property in the wizard to specify the escape character to use when parsing the flat file instance.</span></span> <span data-ttu-id="d2b19-208">默认值为空，这表示将使用在架构级别定义的默认转义符。</span><span class="sxs-lookup"><span data-stu-id="d2b19-208">The default is null, meaning that the default escape character defined at the schema level is used.</span></span>  
  
 <span data-ttu-id="d2b19-209">转义符可指定为字符或十六进制值。</span><span class="sxs-lookup"><span data-stu-id="d2b19-209">The escape character can be specified as a character or as a hexadecimal value.</span></span> <span data-ttu-id="d2b19-210">十六进制值用以下格式指定：</span><span class="sxs-lookup"><span data-stu-id="d2b19-210">The hexadecimal value is specified using the following format:</span></span>  
  
-   <span data-ttu-id="d2b19-211">{0xnnnn}。</span><span class="sxs-lookup"><span data-stu-id="d2b19-211">{0xnnnn}.</span></span> <span data-ttu-id="d2b19-212">例如，{0x0D}{0x0A}、{0x09} 或 {0x20}。</span><span class="sxs-lookup"><span data-stu-id="d2b19-212">For example, {0x0D}{0x0A}, {0x09}, or {0x20}.</span></span>  
  
 <span data-ttu-id="d2b19-213">如果使用符号\\，{，或} 用作转义字符，则必须将放置分隔符符号的前面附加的反斜杠符号，否则将收到一条错误消息例如，</span><span class="sxs-lookup"><span data-stu-id="d2b19-213">If you use the symbols \\, {, or } as the escape character, you must place an additional backslash symbol in front of the delimiter symbol, otherwise you will receive an error message For example,</span></span>  
  
-   <span data-ttu-id="d2b19-214">\\\\, \\{, \\}.</span><span class="sxs-lookup"><span data-stu-id="d2b19-214">\\\\, \\{, \\}.</span></span>  
  
### <a name="child-elements-in-the-flat-file-schema-wizard"></a><span data-ttu-id="d2b19-215">平面文件架构向导中的子元素</span><span class="sxs-lookup"><span data-stu-id="d2b19-215">Child Elements in the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="d2b19-216">每个子元素包含**元素名称**，**元素类型**，**数据类型**和**内容**。</span><span class="sxs-lookup"><span data-stu-id="d2b19-216">Each child element contains **Element Name**, **Element Type**, **Data Type** and **Content**.</span></span> <span data-ttu-id="d2b19-217">你使用**元素名称**文本框中键入有意义的名称的节点。</span><span class="sxs-lookup"><span data-stu-id="d2b19-217">You use the **Element Name** text box to type a meaningful name for the node.</span></span> <span data-ttu-id="d2b19-218">**元素类型**是使用以下值的下拉列表：</span><span class="sxs-lookup"><span data-stu-id="d2b19-218">The **Element Type** is a drop-down list with the following values:</span></span>  
  
-   <span data-ttu-id="d2b19-219">**字段元素**： 指定将一个元素的架构中创建此节点。</span><span class="sxs-lookup"><span data-stu-id="d2b19-219">**Field element**: Specifies that this node will be created in the schema as an element.</span></span>  
  
-   <span data-ttu-id="d2b19-220">**字段特性**： 指定将属性的架构中创建此节点。</span><span class="sxs-lookup"><span data-stu-id="d2b19-220">**Field attribute**: Specifies that this node will be created in the schema as an attribute.</span></span>  
  
-   <span data-ttu-id="d2b19-221">**记录**： 指定将在架构中创建包含无子级的记录。</span><span class="sxs-lookup"><span data-stu-id="d2b19-221">**Record**: Specifies that a record without children will be created in the schema.</span></span>  
  
-   <span data-ttu-id="d2b19-222">**重复记录**： 指定将在架构中创建包含无子级的记录，并且其最大值的匹配项设置为**Unbounded**。</span><span class="sxs-lookup"><span data-stu-id="d2b19-222">**Repeating record**: Specifies that a record without children will be created in the schema and its max occurrence is set to **Unbounded**.</span></span>  
  
-   <span data-ttu-id="d2b19-223">**忽略**： 执行任何操作将在此节点的架构中创建。</span><span class="sxs-lookup"><span data-stu-id="d2b19-223">**Ignore**: Nothing will be created in the schema for this node.</span></span>  
  
 <span data-ttu-id="d2b19-224">默认情况下所有元素的类型都是**Field 元素**和它们的数据类型是**字符串**。</span><span class="sxs-lookup"><span data-stu-id="d2b19-224">By default all elements are of type **Field element** and their data type is **string**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d2b19-225">子元素可以声明为**字段特性**仅在没有任何子级才将其声明为**字段元素**，**记录**或**重复记录**。</span><span class="sxs-lookup"><span data-stu-id="d2b19-225">A child element can be declared as a **Field attribute** only if there are no children before it that are declared as **Field elements**, **Record** or **Repeating record**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d2b19-226">你将看到前端中的叹号**子节点**如下例所示：</span><span class="sxs-lookup"><span data-stu-id="d2b19-226">You will see an exclamation mark in front of the **child nodes** in the following instances:</span></span>  
  
-   <span data-ttu-id="d2b19-227">**字段特性**后定义**Field 元素**，**记录，**或**重复记录**。</span><span class="sxs-lookup"><span data-stu-id="d2b19-227">The **Field attribute** is defined after **Field element**, **Record,** or **Repeating record**.</span></span>  
  
-   <span data-ttu-id="d2b19-228">子元素没有名称。</span><span class="sxs-lookup"><span data-stu-id="d2b19-228">The child element does not have a name.</span></span>  
  
-   <span data-ttu-id="d2b19-229">子元素有重复的名称。</span><span class="sxs-lookup"><span data-stu-id="d2b19-229">The child element has a duplicate name.</span></span>  
  
-   <span data-ttu-id="d2b19-230">子元素的选定数据类型对内容不合适。</span><span class="sxs-lookup"><span data-stu-id="d2b19-230">The selected data type for the child element is not suitable for the content.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2b19-231">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2b19-231">See Also</span></span>  
 [<span data-ttu-id="d2b19-232">BizTalk 平面文件架构向导演练</span><span class="sxs-lookup"><span data-stu-id="d2b19-232">BizTalk Flat File Schema Wizard Walkthrough</span></span>](../core/biztalk-flat-file-schema-wizard-walkthrough.md)