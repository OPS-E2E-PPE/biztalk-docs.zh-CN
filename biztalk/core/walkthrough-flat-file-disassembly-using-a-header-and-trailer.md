---
title: 演练：使用标头和尾部拆装平面文件 |Microsoft Docs
description: 使用平面文件架构向导创建标头架构、 尾部架构和正文架构，然后拆装平面文件在 BizTalk Server 中
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715af9cc-d718-483d-b593-64462aa5a58b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a3e2739b50d19c867fa05744ab98735ffc90646
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395338"
---
# <a name="walkthrough-flat-file-disassembly-using-a-header-and-trailer"></a><span data-ttu-id="d033b-103">演练：使用标头和尾部拆装平面文件</span><span class="sxs-lookup"><span data-stu-id="d033b-103">Walkthrough: Flat File Disassembly Using a Header and Trailer</span></span>

## <a name="overview"></a><span data-ttu-id="d033b-104">概述</span><span class="sxs-lookup"><span data-stu-id="d033b-104">Overview</span></span>
<span data-ttu-id="d033b-105">本演练演示如何将执行包含头部、 尾部和重复的消息正文的文件的平面文件拆装平面文件架构向导创建的架构。</span><span class="sxs-lookup"><span data-stu-id="d033b-105">This walkthrough demonstrates the use of schemas created by the Flat File Schema Wizard to perform flat file disassembly of a file containing a header, a trailer, and a repeating message body.</span></span> <span data-ttu-id="d033b-106">在本演练中，我们将开发一个虚构的错误跟踪系统，满足以下要求的一部分：</span><span class="sxs-lookup"><span data-stu-id="d033b-106">In this walkthrough, you develop part of a fictitious error-tracking system that meets the following requirements:</span></span>  
  
- <span data-ttu-id="d033b-107">错误消息记录在公司内的各种物理站点，并发送到中央位置进行到各种后端系统的处理。</span><span class="sxs-lookup"><span data-stu-id="d033b-107">Error messages are logged at various physical sites within the company and sent to a central location for processing into various back-end systems.</span></span>  
  
- <span data-ttu-id="d033b-108">错误消息写入到包含标头指示的位置，正文，其中包含一个或多个错误消息和一个指明批号的尾部的平面文件格式。</span><span class="sxs-lookup"><span data-stu-id="d033b-108">Error messages are written into a flat file format that contains a header indicating location, a body containing one or more error messages, and a trailer indicating the batch number.</span></span>  
  
- <span data-ttu-id="d033b-109">消息将被视为无效，如果它们没有标头、 正文和尾部。</span><span class="sxs-lookup"><span data-stu-id="d033b-109">Messages are considered invalid if they do not have a header, body, and trailer.</span></span>  
  
  <span data-ttu-id="d033b-110">在本演练结束时必须处理平面文件并将其输出为 XML 进行处理后端系统的 BizTalk Server 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d033b-110">When the walkthrough is completed you will have a BizTalk Server application that processes flat files and writes them out as XML for processing by a back-end system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d033b-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="d033b-111">Prerequisites</span></span>  
 <span data-ttu-id="d033b-112">对于此示例，您需要熟悉创建 BizTalk Server 项目中，为程序集签名并使用 BizTalk Server 管理控制台查看应用程序和端口。</span><span class="sxs-lookup"><span data-stu-id="d033b-112">For this example you need to be comfortable with creating BizTalk Server projects, signing an assembly, and using the BizTalk Server Administration console to view applications and ports.</span></span> <span data-ttu-id="d033b-113">您还应熟悉中列出的观点与[演练：部署基本 BizTalk 应用程序](../core/walkthrough-deploying-a-basic-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="d033b-113">You should also be comfortable with the ideas presented in [Walkthrough: Deploying a Basic BizTalk Application](../core/walkthrough-deploying-a-basic-biztalk-application.md).</span></span> <span data-ttu-id="d033b-114">平面文件架构向导的基本熟悉也是有所帮助，但并不是必需的。</span><span class="sxs-lookup"><span data-stu-id="d033b-114">Basic familiarity with the Flat File Schema Wizard is also helpful but not required.</span></span>  
  
## <a name="what-this-example-does"></a><span data-ttu-id="d033b-115">此示例的用途</span><span class="sxs-lookup"><span data-stu-id="d033b-115">What This Example Does</span></span>  
 <span data-ttu-id="d033b-116">此示例中处理入站平面文件消息使用自定义管道和平面文件拆装器组件。</span><span class="sxs-lookup"><span data-stu-id="d033b-116">This example processes inbound flat file messages using a custom pipeline and the Flat File Disassembler component.</span></span> <span data-ttu-id="d033b-117">使用头部、 尾部和正文架构分析消息，然后写出到发送位置进行后端处理。</span><span class="sxs-lookup"><span data-stu-id="d033b-117">Messages are parsed using header, trailer, and body schemas and then written out to a send location for back-end processing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d033b-118">示例</span><span class="sxs-lookup"><span data-stu-id="d033b-118">Example</span></span>  
 <span data-ttu-id="d033b-119">若要创建该示例，请执行以下各节中所述的步骤。</span><span class="sxs-lookup"><span data-stu-id="d033b-119">To create the example, follow the steps outlined in the following sections.</span></span>  
  
### <a name="create-a-new-biztalk-project"></a><span data-ttu-id="d033b-120">创建新的 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="d033b-120">Create a New BizTalk Project</span></span>  
 <span data-ttu-id="d033b-121">在生成解决方案之前需要创建 BizTalk 项目，请确保它具有强名称，并将其分配应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="d033b-121">Before building a solution you need to create a BizTalk project, ensure that it is strongly named, and assign it an application name.</span></span> <span data-ttu-id="d033b-122">指定应用程序名可防止 BizTalk Server 将解决方案部署到默认 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d033b-122">Assigning an application name prevents BizTalk Server from deploying the solution into the default BizTalk application.</span></span>  
  
1. <span data-ttu-id="d033b-123">使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]若要创建新的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="d033b-123">Use [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to create a new BizTalk project.</span></span> <span data-ttu-id="d033b-124">调用项目**FFDisassemblerWalkthrough**。</span><span class="sxs-lookup"><span data-stu-id="d033b-124">Call the project **FFDisassemblerWalkthrough**.</span></span>  
  
2. <span data-ttu-id="d033b-125">生成密钥文件并将其分配到项目。</span><span class="sxs-lookup"><span data-stu-id="d033b-125">Generate a key file and assign it to the project.</span></span> <span data-ttu-id="d033b-126">有关此任务的详细信息，请参阅[签名页，项目设计器](http://go.microsoft.com/fwlink/?LinkId=125876)。</span><span class="sxs-lookup"><span data-stu-id="d033b-126">For more information about this task, see [Signing Page, Project Designer](http://go.microsoft.com/fwlink/?LinkId=125876).</span></span>  
  
3. <span data-ttu-id="d033b-127">在项目的部署属性，设置**应用程序名称**为"FlatFileExample"，将**重新启动主机实例**到`True`。</span><span class="sxs-lookup"><span data-stu-id="d033b-127">In the deployment properties for the project, set **Application Name** to “FlatFileExample” and set **Restart Host Instances** to `True`.</span></span> <span data-ttu-id="d033b-128">设置此标志指示要清除的程序集的所有缓存的实例的主机。</span><span class="sxs-lookup"><span data-stu-id="d033b-128">Setting this flag tells the host to clear any cached instances of the assembly.</span></span>  
  
### <a name="create-the-sample-data-file"></a><span data-ttu-id="d033b-129">创建示例数据文件</span><span class="sxs-lookup"><span data-stu-id="d033b-129">Create the Sample Data File</span></span>  
<span data-ttu-id="d033b-130">生成架构前，需要创建一个测试文件。</span><span class="sxs-lookup"><span data-stu-id="d033b-130">Before generating schemas, you need to create a test file.</span></span>   
  
1.  <span data-ttu-id="d033b-131">启动记事本或其他文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="d033b-131">Start Notepad or another text editor.</span></span>  
  
2.  <span data-ttu-id="d033b-132">创建测试文件示例。</span><span class="sxs-lookup"><span data-stu-id="d033b-132">Create a sample test file.</span></span> <span data-ttu-id="d033b-133">该文件由头部用来指明报告错误，尾部含有此批和正文包含一个或多个错误记录的批 ID 的位置。</span><span class="sxs-lookup"><span data-stu-id="d033b-133">The file consists of a header indicating the location reporting the error(s), a trailer with a batch ID for this batch, and a body consisting of one or more error records.</span></span> <span data-ttu-id="d033b-134">文件的格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="d033b-134">The format of the file is as follows:</span></span>  
  
    ```  
    Location  
    ERRORid|type|priority|description|errorDateTime  
    …additional error records   
    BatchID  
    ```  
  
    <span data-ttu-id="d033b-135">使用文本"ERROR"标记错误记录并将其与分隔"&#124;"字符 （而不是位置）。</span><span class="sxs-lookup"><span data-stu-id="d033b-135">The ERROR record is tagged with the text “ERROR” and delimited with the “&#124;” character (versus positional).</span></span> <span data-ttu-id="d033b-136">下表所述的错误记录的数据元素。</span><span class="sxs-lookup"><span data-stu-id="d033b-136">The data elements of the ERROR record are described in the following table.</span></span>  
  
    |<span data-ttu-id="d033b-137">元素</span><span class="sxs-lookup"><span data-stu-id="d033b-137">Element</span></span>|<span data-ttu-id="d033b-138">数据类型</span><span class="sxs-lookup"><span data-stu-id="d033b-138">Data type</span></span>|<span data-ttu-id="d033b-139">Description</span><span class="sxs-lookup"><span data-stu-id="d033b-139">Description</span></span>|  
    |---|---|---|  
    |<span data-ttu-id="d033b-140">ID</span><span class="sxs-lookup"><span data-stu-id="d033b-140">ID</span></span>|<span data-ttu-id="d033b-141">integer</span><span class="sxs-lookup"><span data-stu-id="d033b-141">integer</span></span>|<span data-ttu-id="d033b-142">此错误的 ID。</span><span class="sxs-lookup"><span data-stu-id="d033b-142">ID for this error.</span></span>|  
    |<span data-ttu-id="d033b-143">类型</span><span class="sxs-lookup"><span data-stu-id="d033b-143">Type</span></span>|<span data-ttu-id="d033b-144">integer</span><span class="sxs-lookup"><span data-stu-id="d033b-144">integer</span></span>|<span data-ttu-id="d033b-145">错误的类型。</span><span class="sxs-lookup"><span data-stu-id="d033b-145">Type of error.</span></span>|  
    |<span data-ttu-id="d033b-146">Priority</span><span class="sxs-lookup"><span data-stu-id="d033b-146">Priority</span></span>|<span data-ttu-id="d033b-147">string</span><span class="sxs-lookup"><span data-stu-id="d033b-147">string</span></span>|<span data-ttu-id="d033b-148">优先级指示器：低、 中或高。</span><span class="sxs-lookup"><span data-stu-id="d033b-148">Priority indicator: Low, Medium, or High.</span></span>|  
    |<span data-ttu-id="d033b-149">Description</span><span class="sxs-lookup"><span data-stu-id="d033b-149">Description</span></span>|<span data-ttu-id="d033b-150">string</span><span class="sxs-lookup"><span data-stu-id="d033b-150">string</span></span>|<span data-ttu-id="d033b-151">错误的说明。</span><span class="sxs-lookup"><span data-stu-id="d033b-151">Description of the error.</span></span>|  
    |<span data-ttu-id="d033b-152">ErrorDateTime</span><span class="sxs-lookup"><span data-stu-id="d033b-152">ErrorDateTime</span></span>|<span data-ttu-id="d033b-153">DateTime</span><span class="sxs-lookup"><span data-stu-id="d033b-153">DateTime</span></span>|<span data-ttu-id="d033b-154">日期和时间，出现了错误。</span><span class="sxs-lookup"><span data-stu-id="d033b-154">Date and time that the error occurred.</span></span>|  
  
    <span data-ttu-id="d033b-155">该文件可以具有一个或多个错误记录。</span><span class="sxs-lookup"><span data-stu-id="d033b-155">The file can have one or more ERROR records.</span></span>  
  
     <span data-ttu-id="d033b-156">\* *--或者-* \*</span><span class="sxs-lookup"><span data-stu-id="d033b-156">\*\*-- OR --  \*\*</span></span>
  
     <span data-ttu-id="d033b-157">将下面的示例数据复制到新的文件。</span><span class="sxs-lookup"><span data-stu-id="d033b-157">Copy the following sample data into the new file.</span></span> <span data-ttu-id="d033b-158">最后一行包含一个尾随的换行符：</span><span class="sxs-lookup"><span data-stu-id="d033b-158">The last line contains a trailing linefeed:</span></span>
  
    ```  
    East Coast Facility  
    ERROR102|0|High|Sprocket query fails.|1999-05-31T13:20:00.000-05:00  
    ERROR16502|2|Low|Time threshold exceeded.|1999-05-31T13:20:00.000-05:00  
    8675309  
  
    ```  
  
3.  <span data-ttu-id="d033b-159">将新的示例文件保存在项目目录。</span><span class="sxs-lookup"><span data-stu-id="d033b-159">Save the new sample file in the project directory.</span></span> <span data-ttu-id="d033b-160">使用一个描述性名称，如"ErrorFile.txt"，因此它能轻松地找到。</span><span class="sxs-lookup"><span data-stu-id="d033b-160">Use a descriptive name like "ErrorFile.txt" so it can be located easily.</span></span>  
  
### <a name="create-and-test-the-header-trailer-and-body-schemas"></a><span data-ttu-id="d033b-161">创建和测试头部、 尾部和正文架构</span><span class="sxs-lookup"><span data-stu-id="d033b-161">Create and Test the Header, Trailer, and Body Schemas</span></span>  
 <span data-ttu-id="d033b-162">创建示例数据文件后下, 一步是创建头部、 尾部和正文架构。</span><span class="sxs-lookup"><span data-stu-id="d033b-162">After the sample data file is created, the next step is to create the header, trailer, and body schemas.</span></span> <span data-ttu-id="d033b-163">使用平面文件拆装器使用这些架构来接收管道组件处理接收的消息。</span><span class="sxs-lookup"><span data-stu-id="d033b-163">These schemas are used with the Flat File Disassembler receive pipeline component to process received messages.</span></span>  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-header-schema"></a><span data-ttu-id="d033b-164">使用平面文件架构向导创建头部架构</span><span class="sxs-lookup"><span data-stu-id="d033b-164">Use the Flat File Schema Wizard to create the header schema</span></span>  
  
1.  <span data-ttu-id="d033b-165">向项目添加新架构。</span><span class="sxs-lookup"><span data-stu-id="d033b-165">Add a new schema to the project.</span></span> <span data-ttu-id="d033b-166">在解决方案资源管理器中右键单击**FFDisassemblerWalkthrough**，依次指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="d033b-166">In Solution Explorer, right-click **FFDisassemblerWalkthrough**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="d033b-167">在中**添加新项**对话框中，单击**架构文件**，然后选择**平面文件架构向导**。</span><span class="sxs-lookup"><span data-stu-id="d033b-167">In the **Add New Item** dialog box, click **Schema Files** and select **Flat File Schema Wizard**.</span></span> <span data-ttu-id="d033b-168">命名新的架构"为 Header.xsd"，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="d033b-168">Name the new schema "Header.xsd" and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="d033b-169">上**欢迎使用 BizTalk 平面文件架构向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d033b-169">On the **Welcome to the BizTalk Flat File Schema Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="d033b-170">上**平面文件架构信息**页上，单击**浏览**并找到前面创建的示例数据文件。</span><span class="sxs-lookup"><span data-stu-id="d033b-170">On the **Flat File Schema Information** page, click **Browse** and locate the sample data file created earlier.</span></span> <span data-ttu-id="d033b-171">更改**记录名称**为"Header"，验证代码页，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d033b-171">Change the **Record Name** to "Header", verify the code page, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d033b-172">如果以 Unicode 格式保存示例文件的代码页将小 Endian UTF16 (1200)。</span><span class="sxs-lookup"><span data-stu-id="d033b-172">If you saved the sample file in Unicode format the code page will be Little-Endian-UTF16 (1200).</span></span> <span data-ttu-id="d033b-173">这不会产生负面影响的示例。</span><span class="sxs-lookup"><span data-stu-id="d033b-173">This will not adversely affect the example.</span></span>  
  
5.  <span data-ttu-id="d033b-174">接下来选择文档数据。</span><span class="sxs-lookup"><span data-stu-id="d033b-174">Next select the document data.</span></span> <span data-ttu-id="d033b-175">上**选择文档数据**页上，突出显示的第一个行的数据，包括新行字符 {CR} 和 {LF} 所示：</span><span class="sxs-lookup"><span data-stu-id="d033b-175">On the **Select Document Data** page, highlight the first line of data including the new-line characters {CR} and {LF} as shown:</span></span>  
  
     <span data-ttu-id="d033b-176">![选用于头部架构的数据](../core/media/ffwiz-header-select-document-data.gif "ffwiz_header_select_document_data")</span><span class="sxs-lookup"><span data-stu-id="d033b-176">![Data selected for header schema](../core/media/ffwiz-header-select-document-data.gif "ffwiz_header_select_document_data")</span></span>  
  
     <span data-ttu-id="d033b-177">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="d033b-177">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="d033b-178">上**选择记录格式**页上，单击**下一步**接受默认值。</span><span class="sxs-lookup"><span data-stu-id="d033b-178">On the **Select Record Format** page, click **Next** to accept the default.</span></span> <span data-ttu-id="d033b-179">你可以接受默认值"按分隔符符号"，因为数据文件不使用相对位置。</span><span class="sxs-lookup"><span data-stu-id="d033b-179">You can accept the default "by delimiter symbol" because the data file does not use relative position.</span></span>  
  
7.  <span data-ttu-id="d033b-180">上**分隔记录**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d033b-180">On the **Delimited Record** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="d033b-181">现在，您指定子元素。</span><span class="sxs-lookup"><span data-stu-id="d033b-181">Now you specify child elements.</span></span> <span data-ttu-id="d033b-182">标头包含一个名为"位置"元素：</span><span class="sxs-lookup"><span data-stu-id="d033b-182">The header contains one element named "Location":</span></span>  
  
     <span data-ttu-id="d033b-183">![标头定义的位置节点](../core/media/ffwiz-header-child-elements.gif "ffwiz_header_child_elements")</span><span class="sxs-lookup"><span data-stu-id="d033b-183">![Location node defined for header](../core/media/ffwiz-header-child-elements.gif "ffwiz_header_child_elements")</span></span>  
  
     <span data-ttu-id="d033b-184">单击 **“下一步”** 继续。</span><span class="sxs-lookup"><span data-stu-id="d033b-184">Click **Next** to continue.</span></span>  
  
9. <span data-ttu-id="d033b-185">上**架构视图**页上，验证架构。</span><span class="sxs-lookup"><span data-stu-id="d033b-185">On the **Schema View** page, verify the schema.</span></span>  
  
     <span data-ttu-id="d033b-186">![已完成的架构视图显示标头架构](../core/media/ffwiz-header-schema-view.gif "ffwiz_header_schema_view")</span><span class="sxs-lookup"><span data-stu-id="d033b-186">![Schema view showing completed Header schema](../core/media/ffwiz-header-schema-view.gif "ffwiz_header_schema_view")</span></span>  
  
     <span data-ttu-id="d033b-187">完成后，单击**完成**以完成向导。</span><span class="sxs-lookup"><span data-stu-id="d033b-187">When you are satisfied, click **Finish** to complete the wizard.</span></span>  
  
10. <span data-ttu-id="d033b-188">单击**\<架构\>** 标头架构窗格中的节点。</span><span class="sxs-lookup"><span data-stu-id="d033b-188">Click the **\<Schema\>** node in the Header schema pane.</span></span> <span data-ttu-id="d033b-189">在属性窗格中更改**Element FormDefault**到**限定**。</span><span class="sxs-lookup"><span data-stu-id="d033b-189">In the Properties pane, change **Element FormDefault** to **Qualified**.</span></span> <span data-ttu-id="d033b-190">这表示必须在实例文档中的目标命名空间限定本地声明的元素。</span><span class="sxs-lookup"><span data-stu-id="d033b-190">This indicates that locally declared elements must be qualified by the target namespace in an instance document.</span></span>  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-trailer-schema"></a><span data-ttu-id="d033b-191">使用平面文件架构向导创建尾部架构</span><span class="sxs-lookup"><span data-stu-id="d033b-191">Use the Flat File Schema Wizard to create the trailer schema</span></span>  
  
1.  <span data-ttu-id="d033b-192">向项目添加新架构。</span><span class="sxs-lookup"><span data-stu-id="d033b-192">Add a new schema to the project.</span></span> <span data-ttu-id="d033b-193">在解决方案资源管理器中右键单击**FFDisassemblerWalkthrough**，依次指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="d033b-193">In Solution Explorer, right-click **FFDisassemblerWalkthrough**, point to **Add** , and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="d033b-194">在中**添加新项**对话框中，单击**架构文件**，然后选择**平面文件架构向导**。</span><span class="sxs-lookup"><span data-stu-id="d033b-194">In the **Add New Item** dialog box, click **Schema Files** and select **Flat File Schema Wizard**.</span></span> <span data-ttu-id="d033b-195">命名新架构"Trailer.xsd"，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="d033b-195">Name the new schema "Trailer.xsd" and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="d033b-196">上**欢迎使用 BizTalk 平面文件架构向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d033b-196">On the **Welcome to the BizTalk Flat File Schema Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="d033b-197">上**平面文件架构信息**页上，单击**浏览**并找到前面创建的示例数据文件。</span><span class="sxs-lookup"><span data-stu-id="d033b-197">On the **Flat File Schema Information** page, click **Browse** and locate the sample data file created earlier.</span></span> <span data-ttu-id="d033b-198">更改**记录名称**为"Trailer"，验证代码页，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d033b-198">Change the **Record Name** to "Trailer", verify the code page, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d033b-199">如果以 Unicode 格式保存示例文件的代码页将小 Endian UTF16 (1200)。</span><span class="sxs-lookup"><span data-stu-id="d033b-199">If you saved the sample file in Unicode format the code page will be Little-Endian-UTF16 (1200).</span></span> <span data-ttu-id="d033b-200">这不会产生负面影响的示例。</span><span class="sxs-lookup"><span data-stu-id="d033b-200">This will not adversely affect the example.</span></span>  
  
5.  <span data-ttu-id="d033b-201">接下来选择文档数据。</span><span class="sxs-lookup"><span data-stu-id="d033b-201">Next select the document data.</span></span> <span data-ttu-id="d033b-202">上**选择文档数据**页上，突出显示的最后一行的数据，包括新行字符 {CR} 和 {LF} 所示：</span><span class="sxs-lookup"><span data-stu-id="d033b-202">On the **Select Document Data** page, highlight the last line of data including the new-line characters {CR} and {LF} as shown:</span></span>  
  
     <span data-ttu-id="d033b-203">![选用于尾部架构的数据](../core/media/ffwiz-trailer-select-document-data.gif "ffwiz_trailer_select_document_data")</span><span class="sxs-lookup"><span data-stu-id="d033b-203">![Data selected for trailer schema](../core/media/ffwiz-trailer-select-document-data.gif "ffwiz_trailer_select_document_data")</span></span>  
  
     <span data-ttu-id="d033b-204">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="d033b-204">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="d033b-205">上**选择记录格式**页上，单击**下一步**接受默认值。</span><span class="sxs-lookup"><span data-stu-id="d033b-205">On the **Select Record Format** page, click **Next** to accept the default.</span></span> <span data-ttu-id="d033b-206">你可以接受默认值"按分隔符符号"，因为数据文件不使用相对位置。</span><span class="sxs-lookup"><span data-stu-id="d033b-206">You can accept the default "by delimiter symbol" because the data file does not use relative position.</span></span>  
  
7.  <span data-ttu-id="d033b-207">上**分隔记录**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d033b-207">On the **Delimited Record** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="d033b-208">现在，您指定子元素。</span><span class="sxs-lookup"><span data-stu-id="d033b-208">Now you specify child elements.</span></span> <span data-ttu-id="d033b-209">标头包含一个名为"BatchID"元素：</span><span class="sxs-lookup"><span data-stu-id="d033b-209">The header contains one element named "BatchID":</span></span>  
  
     <span data-ttu-id="d033b-210">![为尾部定义的位置节点](../core/media/ffwiz-trailer-child-elements.gif "ffwiz_trailer_child_elements")</span><span class="sxs-lookup"><span data-stu-id="d033b-210">![Location node defined for trailer](../core/media/ffwiz-trailer-child-elements.gif "ffwiz_trailer_child_elements")</span></span>  
  
     <span data-ttu-id="d033b-211">单击 **“下一步”** 继续。</span><span class="sxs-lookup"><span data-stu-id="d033b-211">Click **Next** to continue.</span></span>  
  
9. <span data-ttu-id="d033b-212">上**架构视图**页上，验证架构。</span><span class="sxs-lookup"><span data-stu-id="d033b-212">On the **Schema View** page, verify the schema.</span></span>  
  
     <span data-ttu-id="d033b-213">![架构视图显示完成尾部架构](../core/media/ffwiz-trailer-schema-view.gif "ffwiz_trailer_schema_view")</span><span class="sxs-lookup"><span data-stu-id="d033b-213">![Schema view showing completed Trailer schema](../core/media/ffwiz-trailer-schema-view.gif "ffwiz_trailer_schema_view")</span></span>  
  
     <span data-ttu-id="d033b-214">完成后，单击**完成**以完成向导。</span><span class="sxs-lookup"><span data-stu-id="d033b-214">When you are satisfied, click **Finish** to complete the wizard.</span></span>  
  
10. <span data-ttu-id="d033b-215">单击**\<架构\>** 尾部架构窗格中的节点。</span><span class="sxs-lookup"><span data-stu-id="d033b-215">Click the **\<Schema\>** node in the Trailer schema pane.</span></span> <span data-ttu-id="d033b-216">在属性窗格中更改**elementFormDefault**到**限定**。</span><span class="sxs-lookup"><span data-stu-id="d033b-216">In the Properties pane, change **elementFormDefault** to **Qualified**.</span></span> <span data-ttu-id="d033b-217">这表示必须在实例文档中的目标命名空间限定本地声明的元素。</span><span class="sxs-lookup"><span data-stu-id="d033b-217">This indicates that locally declared elements must be qualified by the target namespace in an instance document.</span></span>  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-body-schema"></a><span data-ttu-id="d033b-218">使用平面文件架构向导创建正文架构</span><span class="sxs-lookup"><span data-stu-id="d033b-218">Use the Flat File Schema Wizard to create the body schema</span></span>  
  
1.  <span data-ttu-id="d033b-219">向项目添加新架构。</span><span class="sxs-lookup"><span data-stu-id="d033b-219">Add a new schema to the project.</span></span> <span data-ttu-id="d033b-220">在解决方案资源管理器中右键单击**FFDisassemblerWalkthrough**，依次指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="d033b-220">In Solution Explorer, right-click **FFDisassemblerWalkthrough**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="d033b-221">在中**添加新项**对话框中，单击**架构文件**，然后选择**平面文件架构向导**。</span><span class="sxs-lookup"><span data-stu-id="d033b-221">In the **Add New Item** dialog box, click **Schema Files** and select **Flat File Schema Wizard**.</span></span> <span data-ttu-id="d033b-222">命名新架构"Body.xsd"，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="d033b-222">Name the new schema "Body.xsd" and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="d033b-223">上**欢迎使用 BizTalk 平面文件架构向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d033b-223">On the **Welcome to the BizTalk Flat File Schema Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="d033b-224">上**平面文件架构信息**页上，单击**浏览**并找到前面创建的示例数据文件。</span><span class="sxs-lookup"><span data-stu-id="d033b-224">On the **Flat File Schema Information** page, click **Browse** and locate the sample data file created earlier.</span></span> <span data-ttu-id="d033b-225">更改**记录名称**为"Body"，验证代码页，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d033b-225">Change the **Record Name** to "Body", verify the code page, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d033b-226">如果以 Unicode 格式保存示例文件的代码页将小 Endian UTF16 (1200)。</span><span class="sxs-lookup"><span data-stu-id="d033b-226">If you saved the sample file in Unicode format the code page will be Little-Endian-UTF16 (1200).</span></span> <span data-ttu-id="d033b-227">这不会产生负面影响的示例。</span><span class="sxs-lookup"><span data-stu-id="d033b-227">This will not adversely affect the example.</span></span>  
  
5.  <span data-ttu-id="d033b-228">接下来选择文档数据。</span><span class="sxs-lookup"><span data-stu-id="d033b-228">Next select the document data.</span></span> <span data-ttu-id="d033b-229">上**选择文档数据**页上，突出显示两个和第三行的数据，包括新行字符 {CR} 和 {LF} 所示：</span><span class="sxs-lookup"><span data-stu-id="d033b-229">On the **Select Document Data** page, highlight lines two and three of data including the new-line characters {CR} and {LF} as shown:</span></span>  
  
     <span data-ttu-id="d033b-230">![为正文架构选择的数据](../core/media/ffwiz-body-select-document-data.gif "ffwiz_body_select_document_data")</span><span class="sxs-lookup"><span data-stu-id="d033b-230">![Data selected for body schema](../core/media/ffwiz-body-select-document-data.gif "ffwiz_body_select_document_data")</span></span>  
  
     <span data-ttu-id="d033b-231">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="d033b-231">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="d033b-232">上**选择记录格式**页上，单击**下一步**接受默认值。</span><span class="sxs-lookup"><span data-stu-id="d033b-232">On the **Select Record Format** page, click **Next** to accept the default.</span></span> <span data-ttu-id="d033b-233">你可以接受默认值"按分隔符符号"，因为数据文件不使用相对位置。</span><span class="sxs-lookup"><span data-stu-id="d033b-233">You can accept the default "by delimiter symbol" because the data file does not use relative position.</span></span>  
  
7.  <span data-ttu-id="d033b-234">上**分隔记录**页上，选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d033b-234">On the **Delimited Record** page, select **Next**.</span></span>  
  
8.  <span data-ttu-id="d033b-235">接下来定义的子元素。</span><span class="sxs-lookup"><span data-stu-id="d033b-235">Next define the child elements.</span></span> <span data-ttu-id="d033b-236">更改**Body_Child1**到**错误**并将其元素类型设置为**重复记录**。</span><span class="sxs-lookup"><span data-stu-id="d033b-236">Change **Body_Child1** to **Error**and set its element type to **Repeating record**.</span></span> <span data-ttu-id="d033b-237">设置**Body_Child2**元素记录类型设置为**忽略**。</span><span class="sxs-lookup"><span data-stu-id="d033b-237">Set the **Body_Child2** element record type to **Ignore**.</span></span>  
  
9. <span data-ttu-id="d033b-238">上**架构视图**页上，单击**下一步**定义的错误记录的子元素。</span><span class="sxs-lookup"><span data-stu-id="d033b-238">On the **Schema View** page, click **Next** to define the child elements of the Error record.</span></span>  
  
10. <span data-ttu-id="d033b-239">上**选择文档数据**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d033b-239">On the **Select Document Data** page, click **Next**.</span></span> <span data-ttu-id="d033b-240">该向导将正确地选择记录定义的数据。</span><span class="sxs-lookup"><span data-stu-id="d033b-240">The wizard chooses the record-defining data correctly.</span></span>  
  
11. <span data-ttu-id="d033b-241">上**选择记录格式**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d033b-241">On the **Select Record Format** page, click **Next**.</span></span> <span data-ttu-id="d033b-242">按分隔符符号设置数据的格式。</span><span class="sxs-lookup"><span data-stu-id="d033b-242">The data is formatted by delimiter symbol.</span></span>  
  
12. <span data-ttu-id="d033b-243">上**分隔记录**页上，选择 **&#124;** 有关**子分隔符**。</span><span class="sxs-lookup"><span data-stu-id="d033b-243">On the **Delimited Record** page, select **&#124;** for the **Child delimiter**.</span></span> <span data-ttu-id="d033b-244">接下来，选择**记录带有标记标识符**复选框，键入**错误**标记值。</span><span class="sxs-lookup"><span data-stu-id="d033b-244">Next, select the **Record has a tag identifier** check box and type **ERROR** for the tag value.</span></span>  
  
     <span data-ttu-id="d033b-245">![配置分隔记录具有标记标识符](../core/media/ffwiz-bodyerror-delimited-record.gif "ffwiz_bodyerror_delimited_record")</span><span class="sxs-lookup"><span data-stu-id="d033b-245">![Configuring delimited record with tag identifier](../core/media/ffwiz-bodyerror-delimited-record.gif "ffwiz_bodyerror_delimited_record")</span></span>  
  
     <span data-ttu-id="d033b-246">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="d033b-246">Click **Next**.</span></span>  
  
13. <span data-ttu-id="d033b-247">现在定义的错误记录的子元素。</span><span class="sxs-lookup"><span data-stu-id="d033b-247">Now define the child elements of the Error record.</span></span>  
  
     <span data-ttu-id="d033b-248">![使用五个元素定义的错误记录](../core/media/ffwiz-bodyerror-child-elements.gif "ffwiz_bodyerror_child_elements")</span><span class="sxs-lookup"><span data-stu-id="d033b-248">![Error record defined with five elements](../core/media/ffwiz-bodyerror-child-elements.gif "ffwiz_bodyerror_child_elements")</span></span>  
  
     <span data-ttu-id="d033b-249">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="d033b-249">Click **Next**.</span></span>  
  
14. <span data-ttu-id="d033b-250">上**架构视图**页上，验证架构。</span><span class="sxs-lookup"><span data-stu-id="d033b-250">On the **Schema View** page, verify the schema.</span></span>  
  
     <span data-ttu-id="d033b-251">![架构视图显示完成正文架构](../core/media/ffwiz-bodyerror-schema-view.gif "ffwiz_bodyerror_schema_view")</span><span class="sxs-lookup"><span data-stu-id="d033b-251">![Schema view showing completed Body schema](../core/media/ffwiz-bodyerror-schema-view.gif "ffwiz_bodyerror_schema_view")</span></span>  
  
     <span data-ttu-id="d033b-252">如果所做的任何错误，请单击**回**并进行必要的更正。</span><span class="sxs-lookup"><span data-stu-id="d033b-252">If you have made any mistakes, click **Back** and make the necessary corrections.</span></span> <span data-ttu-id="d033b-253">完成后，单击**完成**以完成向导。</span><span class="sxs-lookup"><span data-stu-id="d033b-253">When you are satisfied, click **Finish** to complete the wizard.</span></span>  
  
15. <span data-ttu-id="d033b-254">单击**\<架构\>** 正文架构窗格中的节点。</span><span class="sxs-lookup"><span data-stu-id="d033b-254">Click the **\<Schema\>** node in the Body schema pane.</span></span> <span data-ttu-id="d033b-255">在属性窗格中更改**Element FormDefault**到**限定**。</span><span class="sxs-lookup"><span data-stu-id="d033b-255">In the Properties pane, change **Element FormDefault** to **Qualified**.</span></span> <span data-ttu-id="d033b-256">这表示必须在实例文档中的目标命名空间限定本地声明的元素。</span><span class="sxs-lookup"><span data-stu-id="d033b-256">This indicates that locally declared elements must be qualified by the target namespace in an instance document.</span></span>  
  
16. <span data-ttu-id="d033b-257">单击**\<错误\>** 正文架构窗格上的节点。</span><span class="sxs-lookup"><span data-stu-id="d033b-257">Click the **\<Error\>** node on the Body schema pane.</span></span> <span data-ttu-id="d033b-258">在属性窗格中更改**Max Occurs**到**1**。</span><span class="sxs-lookup"><span data-stu-id="d033b-258">In the Properties pane, change **Max Occurs** to **1**.</span></span> <span data-ttu-id="d033b-259">这将导致平面文件拆装器将每个错误拆分为其自己的消息。</span><span class="sxs-lookup"><span data-stu-id="d033b-259">This causes the Flat File Disassembler to split each error into its own message.</span></span>  
  
##### <a name="test-the-schemas-using-ffdasm"></a><span data-ttu-id="d033b-260">测试使用 FFDasm 架构</span><span class="sxs-lookup"><span data-stu-id="d033b-260">Test the schemas using FFDasm</span></span>  
  
1.  <span data-ttu-id="d033b-261">打开命令提示符处，并将目录更改为你的项目目录。</span><span class="sxs-lookup"><span data-stu-id="d033b-261">Open a command prompt and change the directory to your project directory.</span></span>  
  
2.  <span data-ttu-id="d033b-262">从命令提示符处，运行 FFDasm.exe，如下所示。</span><span class="sxs-lookup"><span data-stu-id="d033b-262">From the command prompt, run FFDasm.exe as shown below.</span></span>  
  
    ```  
    <Samples Path>\SDK\Utilities\PipelineTools\FFDasm ErrorFile.txt  -hs header.xsd -bs body.xsd -ts Trailer.xsd  
    ```  
  
     <span data-ttu-id="d033b-263">此文档及其他管道工具的位置有关的信息，请参阅[管道工具](../core/pipeline-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d033b-263">For information about the location of this and other pipeline tools, see [Pipeline Tools](../core/pipeline-tools.md).</span></span>  
  
3.  <span data-ttu-id="d033b-264">FFDasm.exe 将产生两个名为 {GUID}.xml，一个用于测试文件中每个错误记录的输出文件。</span><span class="sxs-lookup"><span data-stu-id="d033b-264">FFDasm.exe should produce two output files named {GUID}.xml, one for each ERROR record in the test file.</span></span> <span data-ttu-id="d033b-265">高优先级错误记录看起来如下所示：</span><span class="sxs-lookup"><span data-stu-id="d033b-265">The high-priority error record looks like the following:</span></span>  
  
    ```  
    <Body xmlns="http://FFDisassemblerWalkthrough.Body">  
      <Error>  
        <ID>102</ID>  
        <Type>0</Type>  
        <Priority>High</Priority>  
        <Description>Sprocket query fails.</Description>  
        <DateTime>1999-05-31T13:20:00.000-05:00</DateTime>  
      </Error>  
    </Body>  
    ```  
  
### <a name="create-a-custom-receive-pipeline"></a><span data-ttu-id="d033b-266">创建自定义接收管道</span><span class="sxs-lookup"><span data-stu-id="d033b-266">Create a Custom Receive Pipeline</span></span>  
 <span data-ttu-id="d033b-267">现在，定义平面文件架构，您需要创建自定义管道使用平面文件拆装器组件。</span><span class="sxs-lookup"><span data-stu-id="d033b-267">Now that the flat file schemas are defined, you need to create a custom pipeline that uses the Flat File Disassembler component.</span></span> <span data-ttu-id="d033b-268">然后可以配置平面文件拆装器组件为使用头部、 正文和尾部架构来分解消息。</span><span class="sxs-lookup"><span data-stu-id="d033b-268">The Flat File Disassembler component can then be configured to use the header, body, and trailer schemas to break up messages.</span></span>    
 
1.  <span data-ttu-id="d033b-269">向项目添加新的接收管道。</span><span class="sxs-lookup"><span data-stu-id="d033b-269">Add a new receive pipeline to the project.</span></span> <span data-ttu-id="d033b-270">在解决方案资源管理器中右键单击**FFDisassemblerWalkthrough**项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="d033b-270">In Solution Explorer, right-click the **FFDisassemblerWalkthrough** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="d033b-271">在中**添加新项**对话框中，依次指向**管道文件**，然后单击**接收管道**。</span><span class="sxs-lookup"><span data-stu-id="d033b-271">In the **Add New Item** dialog box, point to **Pipeline Files** and then click **Receive Pipeline**.</span></span> <span data-ttu-id="d033b-272">命名新管道"FFReceivePipeline"，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="d033b-272">Name the new pipeline "FFReceivePipeline" and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="d033b-273">通过将平面文件拆装器组件从工具箱窗格拖至拆装步骤中配置新的管道。</span><span class="sxs-lookup"><span data-stu-id="d033b-273">Configure the new pipeline by dragging the Flat File Disassembler component from the Toolbox pane to the Disassemble step.</span></span>  
  
4.  <span data-ttu-id="d033b-274">在属性窗格中设置**文档架构**到**FFDisassemblerWalkthrough.Body**，则**标头架构**到**FFDisassemblerWalkthrough.Header**并**尾部架构**到**FFDisassemblerWalkthrough.Trailer**。</span><span class="sxs-lookup"><span data-stu-id="d033b-274">In the Properties pane, set the **Document schema** to **FFDisassemblerWalkthrough.Body**, the **Header schema** to **FFDisassemblerWalkthrough.Header** and the **Trailer schema** to **FFDisassemblerWalkthrough.Trailer**.</span></span>  
  
### <a name="deploy-the-application-and-configure-the-send-and-receive-ports"></a><span data-ttu-id="d033b-275">部署应用程序并配置发送和接收端口</span><span class="sxs-lookup"><span data-stu-id="d033b-275">Deploy the Application and Configure the Send and Receive Ports</span></span>  
 <span data-ttu-id="d033b-276">接收管道创建架构和自定义，您需要编译和部署项目。</span><span class="sxs-lookup"><span data-stu-id="d033b-276">With the schemas and custom receive pipeline created, you need to compile and deploy the project.</span></span> <span data-ttu-id="d033b-277">在部署后，可以使用 BizTalk Server 管理控制台来配置发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="d033b-277">After it is deployed, you can use the BizTalk Server Administration console to configure the send and receive ports.</span></span>  

##### <a name="deploy"></a><span data-ttu-id="d033b-278">部署</span><span class="sxs-lookup"><span data-stu-id="d033b-278">Deploy</span></span>  
1. <span data-ttu-id="d033b-279">从内部[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，右键单击项目，然后单击部署解决方案**部署**。</span><span class="sxs-lookup"><span data-stu-id="d033b-279">From within [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], deploy the solution by right-clicking on the project and then clicking **Deploy**.</span></span>  
  
2. <span data-ttu-id="d033b-280">使用 BizTalk Server 管理控制台中，展开**应用程序**组，以验证**FlatFileExample**是显示为自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="d033b-280">Using the BizTalk Server Administration console, expand the **Applications** group to verify that **FlatFileExample** is present as a custom application.</span></span>  
  
##### <a name="configure-the-receive-port"></a><span data-ttu-id="d033b-281">配置接收端口</span><span class="sxs-lookup"><span data-stu-id="d033b-281">Configure the receive port</span></span>  
  
1.  <span data-ttu-id="d033b-282">使用 Windows 资源管理器下创建一个名为"Receive"目录**FFDisassemblerWalkthrough**项目目录。</span><span class="sxs-lookup"><span data-stu-id="d033b-282">Use Windows Explorer to create a directory named "Receive" under the **FFDisassemblerWalkthrough** project directory.</span></span>  
  
2.  <span data-ttu-id="d033b-283">在 BizTalk Server 管理控制台中，展开**FlatFileExample**应用程序中，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="d033b-283">In the BizTalk Server Administration console, expand the **FlatFileExample** application, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
3.  <span data-ttu-id="d033b-284">在中**接收端口属性**对话框框中，设置为"ReceiveError"的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="d033b-284">In the **Receive Port Properties** dialog box, set the name of the port to "ReceiveError".</span></span>  
  
4.  <span data-ttu-id="d033b-285">单击**接收位置**，然后单击**新建**添加接收位置。</span><span class="sxs-lookup"><span data-stu-id="d033b-285">Click **Receive Locations**, and then click **New** to add a receive location.</span></span> <span data-ttu-id="d033b-286">新的接收位置"命名为 ReceiveErrorLocation"。</span><span class="sxs-lookup"><span data-stu-id="d033b-286">Name the new receive location "ReceiveErrorLocation".</span></span> <span data-ttu-id="d033b-287">设置**接收管道**到**FFReceivePipeline**。</span><span class="sxs-lookup"><span data-stu-id="d033b-287">Set the **Receive Pipeline** to **FFReceivePipeline**.</span></span> <span data-ttu-id="d033b-288">有关**传输类型**，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d033b-288">For **Transport Type**, select **FILE**, and then click **Configure**.</span></span> <span data-ttu-id="d033b-289">选择接收目录创建，并将**文件掩码**到 \*.txt。</span><span class="sxs-lookup"><span data-stu-id="d033b-289">Select the receive directory you created, and then set the **File mask** to \*.txt.</span></span>  
  
5.  <span data-ttu-id="d033b-290">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="d033b-290">Click **OK**.</span></span> <span data-ttu-id="d033b-291">在接收端口应现在已配置。</span><span class="sxs-lookup"><span data-stu-id="d033b-291">Your receive port should now be configured.</span></span> <span data-ttu-id="d033b-292">单击**确定**关闭。</span><span class="sxs-lookup"><span data-stu-id="d033b-292">Click **OK** to close.</span></span>  
  
##### <a name="configure-the-send-port"></a><span data-ttu-id="d033b-293">配置发送端口</span><span class="sxs-lookup"><span data-stu-id="d033b-293">Configure the send port</span></span>  
  
1.  <span data-ttu-id="d033b-294">使用 Windows 资源管理器下创建一个名为"发送" **FFDisassemblerWalkthrough**项目目录。</span><span class="sxs-lookup"><span data-stu-id="d033b-294">Use Windows Explorer to create a directory named "Send" under the **FFDisassemblerWalkthrough** project directory.</span></span>  
  
2.  <span data-ttu-id="d033b-295">在 BizTalk Server 管理控制台中，展开**FlatFileExample**应用程序中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口...**.</span><span class="sxs-lookup"><span data-stu-id="d033b-295">In the BizTalk Server Administration console, expand the **FlatFileExample** application, right-click **Send Ports**, point to **New**, and then click **Static One-Way  Send Port…**.</span></span>  
  
3.  <span data-ttu-id="d033b-296">在中**发送端口属性**对话框框中，设置为"Send"的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="d033b-296">In the **Send Port Properties** dialog box, set the name of the port to "Send".</span></span>  
  
4.  <span data-ttu-id="d033b-297">对于传输类型，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d033b-297">For transport type, select **FILE**, and then click **Configure**.</span></span> <span data-ttu-id="d033b-298">将目标文件夹设置为前面创建的发送目录。</span><span class="sxs-lookup"><span data-stu-id="d033b-298">Set the destination folder to the send directory you created earlier.</span></span>  
  
5.  <span data-ttu-id="d033b-299">现在配置筛选器。</span><span class="sxs-lookup"><span data-stu-id="d033b-299">Now configure the filter.</span></span> <span data-ttu-id="d033b-300">单击**筛选器**并添加下面的表达式：</span><span class="sxs-lookup"><span data-stu-id="d033b-300">Click **Filters** and add one expression:</span></span>  
  
    -   <span data-ttu-id="d033b-301">BTS.MessageType == **http://FFDisassemblerWalkthrough.Body#Body**</span><span class="sxs-lookup"><span data-stu-id="d033b-301">BTS.MessageType == **http://FFDisassemblerWalkthrough.Body#Body**</span></span>  
  
6.  <span data-ttu-id="d033b-302">单击**确定**完成发送端口配置。</span><span class="sxs-lookup"><span data-stu-id="d033b-302">Click **OK** to complete the send port configuration.</span></span> <span data-ttu-id="d033b-303">应配置您的发送端口。</span><span class="sxs-lookup"><span data-stu-id="d033b-303">Your send port should be configured.</span></span>  
  
### <a name="run-the-example"></a><span data-ttu-id="d033b-304">运行示例</span><span class="sxs-lookup"><span data-stu-id="d033b-304">Run the Example</span></span>  
 <span data-ttu-id="d033b-305">它现在是要运行该示例的时间。</span><span class="sxs-lookup"><span data-stu-id="d033b-305">It is now time to run the example.</span></span> <span data-ttu-id="d033b-306">使用 BizTalk Server 管理控制台启动应用程序之后, 将测试文件复制到接收位置和观察发送位置生成的内容。</span><span class="sxs-lookup"><span data-stu-id="d033b-306">After using the BizTalk Server Management console to start the application, copy the test files to the receive location and observe what is produced in the send location.</span></span>  
  
1.  <span data-ttu-id="d033b-307">在 BizTalk Server 管理控制台中，右键单击**FlatFileExample**应用程序，，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="d033b-307">In the BizTalk Server Administration console, right-click the **FlatFileExample** application, and then click **Start**.</span></span> <span data-ttu-id="d033b-308">这将登记并启动发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="d033b-308">This enlists and starts the send and receive ports.</span></span>  
  
2.  <span data-ttu-id="d033b-309">拖放入接收目录将示例 Errorfile.txt 的复制。</span><span class="sxs-lookup"><span data-stu-id="d033b-309">Drop the copy of the sample Errorfile.txt into the receive directory.</span></span> <span data-ttu-id="d033b-310">两个输出文件应写入到的发送目录。</span><span class="sxs-lookup"><span data-stu-id="d033b-310">Two output files should be written to the send directory.</span></span>  
  
