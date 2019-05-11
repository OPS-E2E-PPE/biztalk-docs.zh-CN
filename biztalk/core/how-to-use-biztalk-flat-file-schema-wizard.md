---
title: 如何使用 BizTalk 平面文件架构向导 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7cb8b18-266d-422e-bdb8-1efefb6b4c8e
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28e0c95087c3471e29d0d487171ce30ff92d46eb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383581"
---
# <a name="how-to-use-biztalk-flat-file-schema-wizard"></a><span data-ttu-id="cc17b-102">如何使用 BizTalk 平面文件架构向导</span><span class="sxs-lookup"><span data-stu-id="cc17b-102">How to Use BizTalk Flat File Schema Wizard</span></span>
<span data-ttu-id="cc17b-103">在以前版本的 BizTalk Server 中，您必须手动将批注添加到 XML 架构定义语言 (XSD) 架构在 BizTalk 架构编辑器中以使这些架构可以理解的平面文件管道组件，例如平面文件拆装器和平面文件组装器。</span><span class="sxs-lookup"><span data-stu-id="cc17b-103">In previous releases of BizTalk Server, you had to manually add the annotations to XML Schema Definition language (XSD) schemas in the BizTalk Schema Editor to make these schemas understandable to Flat File Pipeline components, such as Flat File Disassembler and Flat File Assembler.</span></span> <span data-ttu-id="cc17b-104">您仍然可以这样做使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]架构编辑器。</span><span class="sxs-lookup"><span data-stu-id="cc17b-104">You can still do this using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Schema Editor.</span></span> <span data-ttu-id="cc17b-105">若要减少的手动步骤和创建解决方案所需的时间，您可以使用 BizTalk 平面文件架构向导，它提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="cc17b-105">To reduce the number of manual steps and time needed to create solutions, you use the BizTalk Flat File Schema Wizard, which provides the following functionalities:</span></span>  
  
-   <span data-ttu-id="cc17b-106">使用真实的平面文件实例作为输入。</span><span class="sxs-lookup"><span data-stu-id="cc17b-106">Uses real flat file instances as input.</span></span>  
  
-   <span data-ttu-id="cc17b-107">包括用于处理分隔和位置平面文件架构的可视化设计图面。</span><span class="sxs-lookup"><span data-stu-id="cc17b-107">Includes a visual design surface for working with delimited and positional flat file schemas.</span></span>  
  
-   <span data-ttu-id="cc17b-108">向架构添加元素和定义平面文件相关的批注，以交互方式使用可重入的基于向导的过程。</span><span class="sxs-lookup"><span data-stu-id="cc17b-108">Uses a re-entrant wizard-based process for adding elements to the schema and defining flat file related annotations interactively.</span></span>  
  
-   <span data-ttu-id="cc17b-109">支持标记标识符、 字符分隔符和十六进制分隔符。</span><span class="sxs-lookup"><span data-stu-id="cc17b-109">Provides support for tag identifiers and character and hexadecimal delimiters.</span></span>  
  
-   <span data-ttu-id="cc17b-110">自动确定标记标识符的偏移量以及子级的分隔顺序。</span><span class="sxs-lookup"><span data-stu-id="cc17b-110">Automatically determines tag identifier offsets and child delimiting order.</span></span>  
  
-   <span data-ttu-id="cc17b-111">为文件格式提供预览功能。</span><span class="sxs-lookup"><span data-stu-id="cc17b-111">Provides preview capabilities for the file format.</span></span>  
  
-   <span data-ttu-id="cc17b-112">使您可以选择交换实例要用于定义平面文件架构中的首选子数据。</span><span class="sxs-lookup"><span data-stu-id="cc17b-112">Enables you to select preferred sub-data within the interchange instance to use to define the flat file schemas.</span></span>  
  
## <a name="how-to-start-the-biztalk-flat-file-schema-wizard"></a><span data-ttu-id="cc17b-113">如何启动 BizTalk 平面文件架构向导</span><span class="sxs-lookup"><span data-stu-id="cc17b-113">How to Start the BizTalk Flat File Schema Wizard</span></span>  
 <span data-ttu-id="cc17b-114">您可以从任一 Microsoft Visual Studio 解决方案资源管理器或从 BizTalk 架构编辑器启动向导。</span><span class="sxs-lookup"><span data-stu-id="cc17b-114">You can start the wizard from either the Microsoft Visual Studio Solution Explorer or from the BizTalk Schema Editor.</span></span>  
  
#### <a name="to-start-the-wizard-from-solution-explorer"></a><span data-ttu-id="cc17b-115">若要从解决方案资源管理器启动向导</span><span class="sxs-lookup"><span data-stu-id="cc17b-115">To start the wizard from Solution Explorer</span></span>  
  
1. <span data-ttu-id="cc17b-116">在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开**解决方案资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="cc17b-116">In Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the **Solution Explorer**.</span></span>  
  
2. <span data-ttu-id="cc17b-117">若要添加新的平面文件架构，右键单击 BizTalk 项目，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="cc17b-117">To add the new flat-file schema, right-click the BizTalk project, and select **Add**.</span></span>  
  
3. <span data-ttu-id="cc17b-118">单击**新项。**</span><span class="sxs-lookup"><span data-stu-id="cc17b-118">Click **New Item.**</span></span>  
  
    <span data-ttu-id="cc17b-119">![解决方案资源管理器菜单](../core/media/flatfileschemawizard-01.gif "FlatFileSchemaWizard_01")</span><span class="sxs-lookup"><span data-stu-id="cc17b-119">![Solution Explorer menu](../core/media/flatfileschemawizard-01.gif "FlatFileSchemaWizard_01")</span></span>  
  
4. <span data-ttu-id="cc17b-120">在中**添加新项**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cc17b-120">In the **Add New Item** window, do the following:</span></span>  
  
   1.  <span data-ttu-id="cc17b-121">在中**类别**部分中，选择**架构文件**。</span><span class="sxs-lookup"><span data-stu-id="cc17b-121">In the **Categories** section, select **Schema Files**.</span></span>  
  
   2.  <span data-ttu-id="cc17b-122">在中**模板**部分中，选择**平面文件架构向导**。</span><span class="sxs-lookup"><span data-stu-id="cc17b-122">In the **Templates** section, select **Flat File Schema Wizard**.</span></span>  
  
   3.  <span data-ttu-id="cc17b-123">在中**名称**文本框中，键入的新架构的名称。</span><span class="sxs-lookup"><span data-stu-id="cc17b-123">In the **Name** text box, type a name for the new schema.</span></span>  
  
   4.  <span data-ttu-id="cc17b-124">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="cc17b-124">Click **Add**.</span></span>  
  
        <span data-ttu-id="cc17b-125">BizTalk 平面文件架构向导将打开。</span><span class="sxs-lookup"><span data-stu-id="cc17b-125">The BizTalk Flat File Schema Wizard opens.</span></span>  
  
#### <a name="to-start-the-wizard-from-the-schema-editor"></a><span data-ttu-id="cc17b-126">从架构编辑器中启动向导</span><span class="sxs-lookup"><span data-stu-id="cc17b-126">To start the Wizard from the Schema Editor</span></span>  
  
1. <span data-ttu-id="cc17b-127">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开**解决方案资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="cc17b-127">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the **Solution Explorer**.</span></span>  
  
2. <span data-ttu-id="cc17b-128">若要添加新的平面文件架构，右键单击 BizTalk 项目，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="cc17b-128">To add the new flat-file schema, right-click the BizTalk project, and select **Add**.</span></span> <span data-ttu-id="cc17b-129">选择**新项**然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="cc17b-129">Select **New Item** and click **New Item**.</span></span>  
  
3. <span data-ttu-id="cc17b-130">在中**添加新项**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cc17b-130">In the **Add New Item** window, do the following:</span></span>  
  
   1.  <span data-ttu-id="cc17b-131">在中**类别**部分中，选择**架构文件**。</span><span class="sxs-lookup"><span data-stu-id="cc17b-131">In the **Categories** section, select **Schema Files**.</span></span>  
  
   2.  <span data-ttu-id="cc17b-132">在中**模板**部分中，选择**平面文件架构**。</span><span class="sxs-lookup"><span data-stu-id="cc17b-132">In the **Templates** section, select **Flat File Schema**.</span></span>  
  
   3.  <span data-ttu-id="cc17b-133">在中**名称**文本框中，键入的新架构的名称。</span><span class="sxs-lookup"><span data-stu-id="cc17b-133">In the **Name** text box, type a name for the new schema.</span></span>  
  
   4.  <span data-ttu-id="cc17b-134">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="cc17b-134">Click **Add**.</span></span>  
  
   5.  <span data-ttu-id="cc17b-135">右键单击**根**，然后选择**平面文件实例中定义的记录**。</span><span class="sxs-lookup"><span data-stu-id="cc17b-135">Right-click **Root** and select **Define Record from Flat File Instance**.</span></span>  
  
        <span data-ttu-id="cc17b-136">BizTalk 平面文件架构向导现在开始。</span><span class="sxs-lookup"><span data-stu-id="cc17b-136">The BizTalk Flat File Schema Wizard now starts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc17b-137">如果必须在架构编辑器中打开一个工作架构，您需要做是右键单击所选的节点，然后选择**平面文件实例中定义的记录**。</span><span class="sxs-lookup"><span data-stu-id="cc17b-137">If you have a working schema opened in the Schema Editor, all you need to do is right-click the selected node and then select **Define Record from Flat File Instance**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc17b-138">**平面文件实例中定义的记录**选项启用所选的节点是否不包含子元素的记录。</span><span class="sxs-lookup"><span data-stu-id="cc17b-138">The **Define Record from Flat File Instance** option is enabled if the selected node is a record without child elements.</span></span> <span data-ttu-id="cc17b-139">如果所选的节点具有子元素，该向导将删除所有当前的子元素，并生成新的。</span><span class="sxs-lookup"><span data-stu-id="cc17b-139">If the selected node has child elements, the wizard deletes all current child elements and generates the new ones.</span></span> <span data-ttu-id="cc17b-140">向导将提示您确认删除现有的子元素之前。</span><span class="sxs-lookup"><span data-stu-id="cc17b-140">The wizard prompts you to confirm before deleting the existing child elements.</span></span>  
  
## <a name="considerations-for-using-the-flat-file-schema-wizard"></a><span data-ttu-id="cc17b-141">使用平面文件架构向导的注意事项</span><span class="sxs-lookup"><span data-stu-id="cc17b-141">Considerations for Using the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="cc17b-142">本部分介绍使用 BizTalk 平面文件架构向导时应考虑的问题。</span><span class="sxs-lookup"><span data-stu-id="cc17b-142">This section describes issues you should consider when working with the BizTalk Flat File Schema Wizard.</span></span>  
  
### <a name="working-with-multibyte-character-set-mbcs"></a><span data-ttu-id="cc17b-143">使用多字节字符集 (MBCS)</span><span class="sxs-lookup"><span data-stu-id="cc17b-143">Working with Multibyte Character Set (MBCS)</span></span>  
 <span data-ttu-id="cc17b-144">默认情况下**单位计算位置以字节为单位**复选框处于未选中状态，在平面文件架构信息屏幕上。</span><span class="sxs-lookup"><span data-stu-id="cc17b-144">By default, the **Count positions in bytes** check box is unchecked on the Flat File Schema Information screen.</span></span> <span data-ttu-id="cc17b-145">该向导来计算位置数的字符;这意味着，如果你的位置平面文件实例中有 MBCS 字符，位置不正确计算位置数。</span><span class="sxs-lookup"><span data-stu-id="cc17b-145">The wizard counts the positions by characters; which mean that if you have MBCS characters in your positional flat file instance, the positions are not counted correctly.</span></span> <span data-ttu-id="cc17b-146">通过选择**单位计算位置以字节为单位**复选框，向导将显示 MBCS 字符，并指示其位置长度。</span><span class="sxs-lookup"><span data-stu-id="cc17b-146">By selecting the **Count positions in bytes** check box, the wizard displays MBCS characters with an additional indication of their positional length.</span></span> <span data-ttu-id="cc17b-147">字符占据一个位置上显示和圆点符号"•"填充剩余的长度。</span><span class="sxs-lookup"><span data-stu-id="cc17b-147">The character takes one position on the display and the remaining length is filled out with dot symbols, “•”.</span></span> <span data-ttu-id="cc17b-148">填充的圆点符号的数将取决于在双字节字符中保存的文件设置 (DBCS)、 Unicode 或 utf-8 格式。</span><span class="sxs-lookup"><span data-stu-id="cc17b-148">The number of dot symbols filled will be depending on the files that were saved in double byte character set (DBCS), Unicode or UTF-8 format.</span></span>  
  
### <a name="code-pages-supported-in-the-flat-file-schema-wizard"></a><span data-ttu-id="cc17b-149">支持在平面文件架构向导中的代码页</span><span class="sxs-lookup"><span data-stu-id="cc17b-149">Code Pages Supported in the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="cc17b-150">下面是在向导的受支持的代码页的列表：</span><span class="sxs-lookup"><span data-stu-id="cc17b-150">The following is a list of supported code pages for the wizard:</span></span>  
  
-   <span data-ttu-id="cc17b-151">阿拉伯语 (1256)</span><span class="sxs-lookup"><span data-stu-id="cc17b-151">Arabic (1256)</span></span>  
  
-   <span data-ttu-id="cc17b-152">ASCII (20127)</span><span class="sxs-lookup"><span data-stu-id="cc17b-152">ASCII (20127)</span></span>  
  
-   <span data-ttu-id="cc17b-153">波罗的语 (1257)</span><span class="sxs-lookup"><span data-stu-id="cc17b-153">Baltic (1257)</span></span>  
  
-   <span data-ttu-id="cc17b-154">大 Endian UTF16 (1201)</span><span class="sxs-lookup"><span data-stu-id="cc17b-154">Big-Endian-UTF16 (1201)</span></span>  
  
-   <span data-ttu-id="cc17b-155">中部语 (1250)</span><span class="sxs-lookup"><span data-stu-id="cc17b-155">Central-European (1250)</span></span>  
  
-   <span data-ttu-id="cc17b-156">西里尔语 (1251)</span><span class="sxs-lookup"><span data-stu-id="cc17b-156">Cyrillic (1251)</span></span>  
  
-   <span data-ttu-id="cc17b-157">希腊语 (1253)</span><span class="sxs-lookup"><span data-stu-id="cc17b-157">Greek (1253)</span></span>  
  
-   <span data-ttu-id="cc17b-158">希伯来语 (1255)</span><span class="sxs-lookup"><span data-stu-id="cc17b-158">Hebrew (1255)</span></span>  
  
-   <span data-ttu-id="cc17b-159">日语 Shift JIS (932)</span><span class="sxs-lookup"><span data-stu-id="cc17b-159">Japanese-Shift-JIS (932)</span></span>  
  
-   <span data-ttu-id="cc17b-160">朝鲜语 (949)</span><span class="sxs-lookup"><span data-stu-id="cc17b-160">Korean (949)</span></span>  
  
-   <span data-ttu-id="cc17b-161">小 Endian UTF16 (1200)</span><span class="sxs-lookup"><span data-stu-id="cc17b-161">Little-Endian-UTF16 (1200)</span></span>  
  
-   <span data-ttu-id="cc17b-162">简化的中文-GBK (936)</span><span class="sxs-lookup"><span data-stu-id="cc17b-162">Simplified-Chinese-GBK (936)</span></span>  
  
-   <span data-ttu-id="cc17b-163">简体中文 GB18030 (54936)</span><span class="sxs-lookup"><span data-stu-id="cc17b-163">Simplified-Chinese-GB18030 (54936)</span></span>  
  
-   <span data-ttu-id="cc17b-164">泰语 (874)</span><span class="sxs-lookup"><span data-stu-id="cc17b-164">Thai (874)</span></span>  
  
-   <span data-ttu-id="cc17b-165">传统-Chinese-BIG5 (950)</span><span class="sxs-lookup"><span data-stu-id="cc17b-165">Traditional-Chinese-BIG5 (950)</span></span>  
  
-   <span data-ttu-id="cc17b-166">土耳其语 (1254)</span><span class="sxs-lookup"><span data-stu-id="cc17b-166">Turkish (1254)</span></span>  
  
-   <span data-ttu-id="cc17b-167">UTF-7 (65000)</span><span class="sxs-lookup"><span data-stu-id="cc17b-167">UTF-7 (65000)</span></span>  
  
-   <span data-ttu-id="cc17b-168">UTF-8 (65001)</span><span class="sxs-lookup"><span data-stu-id="cc17b-168">UTF-8 (65001)</span></span>  
  
-   <span data-ttu-id="cc17b-169">越南语 (1258)</span><span class="sxs-lookup"><span data-stu-id="cc17b-169">Vietnamese (1258)</span></span>  
  
-   <span data-ttu-id="cc17b-170">西欧 (1252)</span><span class="sxs-lookup"><span data-stu-id="cc17b-170">Western-European (1252)</span></span>  
  
### <a name="record-types-in-the-flat-file-schema-wizard"></a><span data-ttu-id="cc17b-171">平面文件架构向导中的记录类型</span><span class="sxs-lookup"><span data-stu-id="cc17b-171">Record Types in the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="cc17b-172">平面文件不能包含在位置记录内的分隔的记录。</span><span class="sxs-lookup"><span data-stu-id="cc17b-172">Flat files cannot contain delimited records within positional records.</span></span> <span data-ttu-id="cc17b-173">该向导是基于重入，因为中的定义的类型的单选按钮**按分隔符符号**并**按相对位置**启用或禁用的父记录的格式在向导中所定义子级。</span><span class="sxs-lookup"><span data-stu-id="cc17b-173">Because the wizard is re-entrant based, the radio buttons that define the type of the **By delimiter symbol** and **By relative positions** are enabled or disabled based on the format of the parent records for the child which you define in the wizard.</span></span> <span data-ttu-id="cc17b-174">例如，</span><span class="sxs-lookup"><span data-stu-id="cc17b-174">For example,</span></span>  
  
-   <span data-ttu-id="cc17b-175">如果针对分隔记录的子级运行该向导，将选择这两个单选按钮。</span><span class="sxs-lookup"><span data-stu-id="cc17b-175">If the wizard is run for a child of a delimited record, both radio buttons are selected.</span></span>  
  
-   <span data-ttu-id="cc17b-176">如果针对位置记录的子级运行该向导**按分隔符符号**单选按钮被清除。</span><span class="sxs-lookup"><span data-stu-id="cc17b-176">If the wizard is run for a child of a positional record, the **By delimiter symbol** radio button is cleared.</span></span>  
  
### <a name="delimiter-symbols-in-the-flat-file-schema-wizard"></a><span data-ttu-id="cc17b-177">平面文件架构向导中的分隔符符号</span><span class="sxs-lookup"><span data-stu-id="cc17b-177">Delimiter Symbols in the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="cc17b-178">子分隔符属性下拉列表包含具有以下常见的分隔符：</span><span class="sxs-lookup"><span data-stu-id="cc17b-178">The child delimiter property drop-down list contains with the following common delimiters:</span></span>  
  
- <span data-ttu-id="cc17b-179">{CR}{LF}</span><span class="sxs-lookup"><span data-stu-id="cc17b-179">{CR}{LF}</span></span>  
  
- <span data-ttu-id="cc17b-180">{CR}</span><span class="sxs-lookup"><span data-stu-id="cc17b-180">{CR}</span></span>  
  
- <span data-ttu-id="cc17b-181">{LF}</span><span class="sxs-lookup"><span data-stu-id="cc17b-181">{LF}</span></span>  
  
- <span data-ttu-id="cc17b-182">{TAB}</span><span class="sxs-lookup"><span data-stu-id="cc17b-182">{TAB}</span></span>  
  
- <span data-ttu-id="cc17b-183">{SPACE}</span><span class="sxs-lookup"><span data-stu-id="cc17b-183">{SPACE}</span></span>  
  
- <span data-ttu-id="cc17b-184">{0x1A}</span><span class="sxs-lookup"><span data-stu-id="cc17b-184">{0x1A}</span></span>  
  
- <span data-ttu-id="cc17b-185">&#124;</span><span class="sxs-lookup"><span data-stu-id="cc17b-185">&#124;</span></span>  
  
- <span data-ttu-id="cc17b-186">、</span><span class="sxs-lookup"><span data-stu-id="cc17b-186">,</span></span>  
  
- <span data-ttu-id="cc17b-187">;</span><span class="sxs-lookup"><span data-stu-id="cc17b-187">;</span></span>  
  
  <span data-ttu-id="cc17b-188">此属性的默认值为 {CR} {LF}。</span><span class="sxs-lookup"><span data-stu-id="cc17b-188">The default value for this property is {CR}{LF}.</span></span> <span data-ttu-id="cc17b-189">属性也是一个可编辑的文本框，以便可以将子分隔符指定为一系列字符或字符的十六进制值。</span><span class="sxs-lookup"><span data-stu-id="cc17b-189">The property is also an editable text box, so that you can specify the child delimiter as a sequence of characters or as hexadecimal values of the characters.</span></span> <span data-ttu-id="cc17b-190">使用子分隔符的字符的一个示例是"a"或"street"。</span><span class="sxs-lookup"><span data-stu-id="cc17b-190">An example of using characters for the child delimiter would be "a" or "street."</span></span> <span data-ttu-id="cc17b-191">使用以下格式指定十六进制分隔符：</span><span class="sxs-lookup"><span data-stu-id="cc17b-191">Hexadecimal delimiters are specified using the following format:</span></span>  
  
- <span data-ttu-id="cc17b-192">{0xnnnn}。</span><span class="sxs-lookup"><span data-stu-id="cc17b-192">{0xnnnn}.</span></span> <span data-ttu-id="cc17b-193">例如，{0x0D} {0x0A}、 {0x09} 或 {0x20}。</span><span class="sxs-lookup"><span data-stu-id="cc17b-193">For example, {0x0D}{0x0A}, {0x09} or {0x20}.</span></span>  
  
  <span data-ttu-id="cc17b-194">使用十六进制值序列的示例是 {0x0D} {0x0A}、 {0x09} {0x20}。</span><span class="sxs-lookup"><span data-stu-id="cc17b-194">An example of using sequence of hexadecimal values is {0x0D}{0x0A}, {0x09}{0x20}.</span></span>  
  
  <span data-ttu-id="cc17b-195">如果使用的符号\\，{，或} 用作分隔符，您还必须放置分隔符符号前面一个反斜杠符号，否则将收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="cc17b-195">If you use the symbols \\, {, or } as the delimiter, you must place an additional backslash symbol in front of the delimiter symbol, otherwise you will receive an error message.</span></span> <span data-ttu-id="cc17b-196">例如，</span><span class="sxs-lookup"><span data-stu-id="cc17b-196">For example,</span></span>  
  
- <span data-ttu-id="cc17b-197">\\\\\\{，或\\}。</span><span class="sxs-lookup"><span data-stu-id="cc17b-197">\\\\, \\{, or \\}.</span></span>  
  
### <a name="relative-positions-in-the-flat-file-schema-wizard"></a><span data-ttu-id="cc17b-198">平面文件架构向导中的相对位置</span><span class="sxs-lookup"><span data-stu-id="cc17b-198">Relative Positions in the Flat File Schema Wizard</span></span>  
  
#### <a name="setting-position-markers"></a><span data-ttu-id="cc17b-199">设置位置标记</span><span class="sxs-lookup"><span data-stu-id="cc17b-199">Setting Position Markers</span></span>  
 <span data-ttu-id="cc17b-200">用鼠标左键单击位置选择框中，若要设置新的位置标记线的位置标记。</span><span class="sxs-lookup"><span data-stu-id="cc17b-200">Use the left mouse button to click a position marker in the position selection box to set the new position marker line.</span></span> <span data-ttu-id="cc17b-201">位置标记表示为一条实线。</span><span class="sxs-lookup"><span data-stu-id="cc17b-201">The position marker is represented as a solid line.</span></span> <span data-ttu-id="cc17b-202">默认情况下，位置标记线位于位置 0 处的记录的开头。</span><span class="sxs-lookup"><span data-stu-id="cc17b-202">By default, a position marker line exists at the beginning of the record at position zero.</span></span> <span data-ttu-id="cc17b-203">若要删除现有的位置标记线，用鼠标左键单击它。</span><span class="sxs-lookup"><span data-stu-id="cc17b-203">To remove an existing position marker line, use the left mouse button to click  it.</span></span>  
  
### <a name="escape-characters-in-the-flat-file-schema-wizard"></a><span data-ttu-id="cc17b-204">平面文件架构向导中的字符进行转义</span><span class="sxs-lookup"><span data-stu-id="cc17b-204">Escape Characters in the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="cc17b-205">转义符是字符的取消其后的任何特殊含义的单个字符。</span><span class="sxs-lookup"><span data-stu-id="cc17b-205">An escape character is a single character that suppresses any special meaning of the character that follows it.</span></span> <span data-ttu-id="cc17b-206">有关详细信息，请参阅[转义符](../core/escape-characters.md)下的主题[方式解释的特殊字符作为字段值的一部分](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)。</span><span class="sxs-lookup"><span data-stu-id="cc17b-206">For more information, see [Escape Characters](../core/escape-characters.md) topic under [Ways to Interpret Special Characters as Part of a Field Value](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md).</span></span> <span data-ttu-id="cc17b-207">使用向导中的转义符属性，以指定要分析的平面文件实例时使用的转义字符。</span><span class="sxs-lookup"><span data-stu-id="cc17b-207">You use the escape character property in the wizard to specify the escape character to use when parsing the flat file instance.</span></span> <span data-ttu-id="cc17b-208">默认值为 null，表示使用默认的转义符在架构级别定义。</span><span class="sxs-lookup"><span data-stu-id="cc17b-208">The default is null, meaning that the default escape character defined at the schema level is used.</span></span>  
  
 <span data-ttu-id="cc17b-209">为字符或十六进制值，可以指定转义符。</span><span class="sxs-lookup"><span data-stu-id="cc17b-209">The escape character can be specified as a character or as a hexadecimal value.</span></span> <span data-ttu-id="cc17b-210">使用以下格式指定十六进制值：</span><span class="sxs-lookup"><span data-stu-id="cc17b-210">The hexadecimal value is specified using the following format:</span></span>  
  
- <span data-ttu-id="cc17b-211">{0xnnnn}。</span><span class="sxs-lookup"><span data-stu-id="cc17b-211">{0xnnnn}.</span></span> <span data-ttu-id="cc17b-212">例如，{0x0D} {0x0A}、 {0x09} 或 {0x20}。</span><span class="sxs-lookup"><span data-stu-id="cc17b-212">For example, {0x0D}{0x0A}, {0x09}, or {0x20}.</span></span>  
  
  <span data-ttu-id="cc17b-213">如果使用的符号\\，{，或} 用作转义字符，您必须放置分隔符符号前面一个反斜杠符号，否则将收到一条错误消息等</span><span class="sxs-lookup"><span data-stu-id="cc17b-213">If you use the symbols \\, {, or } as the escape character, you must place an additional backslash symbol in front of the delimiter symbol, otherwise you will receive an error message For example,</span></span>  
  
- <span data-ttu-id="cc17b-214">\\\\, \\{, \\}.</span><span class="sxs-lookup"><span data-stu-id="cc17b-214">\\\\, \\{, \\}.</span></span>  
  
### <a name="child-elements-in-the-flat-file-schema-wizard"></a><span data-ttu-id="cc17b-215">平面文件架构向导中的子元素</span><span class="sxs-lookup"><span data-stu-id="cc17b-215">Child Elements in the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="cc17b-216">每个子元素包含**元素名称**，**元素类型**，**数据类型**并**内容**。</span><span class="sxs-lookup"><span data-stu-id="cc17b-216">Each child element contains **Element Name**, **Element Type**, **Data Type** and **Content**.</span></span> <span data-ttu-id="cc17b-217">您使用**元素名称**文本框中键入有意义的名称的节点。</span><span class="sxs-lookup"><span data-stu-id="cc17b-217">You use the **Element Name** text box to type a meaningful name for the node.</span></span> <span data-ttu-id="cc17b-218">**元素类型**是以下值的下拉列表：</span><span class="sxs-lookup"><span data-stu-id="cc17b-218">The **Element Type** is a drop-down list with the following values:</span></span>  
  
- <span data-ttu-id="cc17b-219">**字段元素**:指定将在架构中作为元素创建此节点。</span><span class="sxs-lookup"><span data-stu-id="cc17b-219">**Field element**: Specifies that this node will be created in the schema as an element.</span></span>  
  
- <span data-ttu-id="cc17b-220">**字段属性**:指定将在架构中作为属性创建此节点。</span><span class="sxs-lookup"><span data-stu-id="cc17b-220">**Field attribute**: Specifies that this node will be created in the schema as an attribute.</span></span>  
  
- <span data-ttu-id="cc17b-221">**记录**:指定将在架构中创建无子级的记录。</span><span class="sxs-lookup"><span data-stu-id="cc17b-221">**Record**: Specifies that a record without children will be created in the schema.</span></span>  
  
- <span data-ttu-id="cc17b-222">**重复记录**:指定将在架构中创建无子级的记录和其最大出现次数设置为**Unbounded**。</span><span class="sxs-lookup"><span data-stu-id="cc17b-222">**Repeating record**: Specifies that a record without children will be created in the schema and its max occurrence is set to **Unbounded**.</span></span>  
  
- <span data-ttu-id="cc17b-223">**忽略**:执行任何操作将为此节点在架构中创建。</span><span class="sxs-lookup"><span data-stu-id="cc17b-223">**Ignore**: Nothing will be created in the schema for this node.</span></span>  
  
  <span data-ttu-id="cc17b-224">默认情况下的所有元素都属于类型**Field 元素**是其数据类型**字符串**。</span><span class="sxs-lookup"><span data-stu-id="cc17b-224">By default all elements are of type **Field element** and their data type is **string**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc17b-225">子元素可以声明为**字段属性**仅在没有任何子级之前它声明为**字段元素**，**记录**或**重复记录**。</span><span class="sxs-lookup"><span data-stu-id="cc17b-225">A child element can be declared as a **Field attribute** only if there are no children before it that are declared as **Field elements**, **Record** or **Repeating record**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc17b-226">您将看到的前面一个感叹号**子节点**如下例所示：</span><span class="sxs-lookup"><span data-stu-id="cc17b-226">You will see an exclamation mark in front of the **child nodes** in the following instances:</span></span>  
  
-   <span data-ttu-id="cc17b-227">**字段属性**定义后**Field 元素**，**记录，** 或者**重复记录**。</span><span class="sxs-lookup"><span data-stu-id="cc17b-227">The **Field attribute** is defined after **Field element**, **Record,** or **Repeating record**.</span></span>  
  
-   <span data-ttu-id="cc17b-228">子元素不具有一个名称。</span><span class="sxs-lookup"><span data-stu-id="cc17b-228">The child element does not have a name.</span></span>  
  
-   <span data-ttu-id="cc17b-229">子元素具有重复的名称。</span><span class="sxs-lookup"><span data-stu-id="cc17b-229">The child element has a duplicate name.</span></span>  
  
-   <span data-ttu-id="cc17b-230">子元素的所选的数据类型不适合的内容。</span><span class="sxs-lookup"><span data-stu-id="cc17b-230">The selected data type for the child element is not suitable for the content.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc17b-231">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc17b-231">See Also</span></span>  
 [<span data-ttu-id="cc17b-232">“BizTalk 平面文件架构向导”演练</span><span class="sxs-lookup"><span data-stu-id="cc17b-232">BizTalk Flat File Schema Wizard Walkthrough</span></span>](../core/biztalk-flat-file-schema-wizard-walkthrough.md)