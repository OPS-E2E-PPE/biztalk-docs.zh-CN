---
title: "演练： 使用标头和尾的平面文件反汇编 |Microsoft 文档"
description: "使用平面文件架构向导创建标头架构、 电影预告片架构和正文架构，然后反汇编 BizTalk Server 中的平面文件"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 715af9cc-d718-483d-b593-64462aa5a58b
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7c1406367f047794c6d8931352104bb59e6ca5b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="walkthrough-flat-file-disassembly-using-a-header-and-trailer"></a><span data-ttu-id="29b3b-103">演练：使用头部和尾部拆装平面文件</span><span class="sxs-lookup"><span data-stu-id="29b3b-103">Walkthrough: Flat File Disassembly Using a Header and Trailer</span></span>

## <a name="overview"></a><span data-ttu-id="29b3b-104">概述</span><span class="sxs-lookup"><span data-stu-id="29b3b-104">Overview</span></span>
<span data-ttu-id="29b3b-105">本演练演示了如何使用平面文件架构向导创建的架构，对包含一个头部、一个尾部和一个重复消息正文的文件执行平面文件拆装。</span><span class="sxs-lookup"><span data-stu-id="29b3b-105">This walkthrough demonstrates the use of schemas created by the Flat File Schema Wizard to perform flat file disassembly of a file containing a header, a trailer, and a repeating message body.</span></span> <span data-ttu-id="29b3b-106">在本演练中，您将参与开发一个虚构的错误跟踪系统，它满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="29b3b-106">In this walkthrough, you develop part of a fictitious error-tracking system that meets the following requirements:</span></span>  
  
-   <span data-ttu-id="29b3b-107">错误消息记录在公司内部不同的物理地点，并发送到一个中央位置，供各种后端系统进行处理。</span><span class="sxs-lookup"><span data-stu-id="29b3b-107">Error messages are logged at various physical sites within the company and sent to a central location for processing into various back-end systems.</span></span>  
  
-   <span data-ttu-id="29b3b-108">错误消息以平面文件格式写入，该平面文件格式包含一个指明其位置的头部、含有一个或多个错误消息的正文，以及一个指明批号的尾部。</span><span class="sxs-lookup"><span data-stu-id="29b3b-108">Error messages are written into a flat file format that contains a header indicating location, a body containing one or more error messages, and a trailer indicating the batch number.</span></span>  
  
-   <span data-ttu-id="29b3b-109">如果消息不包含头部、正文和尾部，则被视为无效。</span><span class="sxs-lookup"><span data-stu-id="29b3b-109">Messages are considered invalid if they do not have a header, body, and trailer.</span></span>  
  
 <span data-ttu-id="29b3b-110">本演练结束时，会创建一个 BizTalk Server 应用程序，它可处理平面文件，并将其输出为 XML 格式，以供后端系统处理。</span><span class="sxs-lookup"><span data-stu-id="29b3b-110">When the walkthrough is completed you will have a BizTalk Server application that processes flat files and writes them out as XML for processing by a back-end system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="29b3b-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="29b3b-111">Prerequisites</span></span>  
 <span data-ttu-id="29b3b-112">对于本示例，您需要熟悉以下操作：创建 BizTalk Server 项目、签署程序集、使用 BizTalk Server 管理控制台查看应用程序和端口。</span><span class="sxs-lookup"><span data-stu-id="29b3b-112">For this example you need to be comfortable with creating BizTalk Server projects, signing an assembly, and using the BizTalk Server Administration console to view applications and ports.</span></span> <span data-ttu-id="29b3b-113">你还应与中提供的想法[演练： 将基本的 BizTalk 应用程序部署](../core/walkthrough-deploying-a-basic-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="29b3b-113">You should also be comfortable with the ideas presented in [Walkthrough: Deploying a Basic BizTalk Application](../core/walkthrough-deploying-a-basic-biztalk-application.md).</span></span> <span data-ttu-id="29b3b-114">对平面文件架构向导有个基本了解也有帮助，但不是必需的。</span><span class="sxs-lookup"><span data-stu-id="29b3b-114">Basic familiarity with the Flat File Schema Wizard is also helpful but not required.</span></span>  
  
## <a name="what-this-example-does"></a><span data-ttu-id="29b3b-115">此示例的执行</span><span class="sxs-lookup"><span data-stu-id="29b3b-115">What This Example Does</span></span>  
 <span data-ttu-id="29b3b-116">本示例使用自定义管道和平面文件拆装器组件来处理入站平面文件消息。</span><span class="sxs-lookup"><span data-stu-id="29b3b-116">This example processes inbound flat file messages using a custom pipeline and the Flat File Disassembler component.</span></span> <span data-ttu-id="29b3b-117">解析消息使用头部、尾部和正文架构，然后将消息写到一个发送位置，以进行后端处理。</span><span class="sxs-lookup"><span data-stu-id="29b3b-117">Messages are parsed using header, trailer, and body schemas and then written out to a send location for back-end processing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29b3b-118">示例</span><span class="sxs-lookup"><span data-stu-id="29b3b-118">Example</span></span>  
 <span data-ttu-id="29b3b-119">若要创建该示例，请按照下述步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="29b3b-119">To create the example, follow the steps outlined in the following sections.</span></span>  
  
### <a name="create-a-new-biztalk-project"></a><span data-ttu-id="29b3b-120">创建新 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="29b3b-120">Create a New BizTalk Project</span></span>  
 <span data-ttu-id="29b3b-121">生成解决方案前，需要先创建一个 BizTalk 项目，确保要对其进行强命名，并为其指定一个应用程序名。</span><span class="sxs-lookup"><span data-stu-id="29b3b-121">Before building a solution you need to create a BizTalk project, ensure that it is strongly named, and assign it an application name.</span></span> <span data-ttu-id="29b3b-122">指定应用程序名可防止 BizTalk Server 将该解决方案部署到默认 BizTalk 应用程序中。</span><span class="sxs-lookup"><span data-stu-id="29b3b-122">Assigning an application name prevents BizTalk Server from deploying the solution into the default BizTalk application.</span></span>  
  
1.  <span data-ttu-id="29b3b-123">使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]创建新的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="29b3b-123">Use [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to create a new BizTalk project.</span></span> <span data-ttu-id="29b3b-124">调用项目**FFDisassemblerWalkthrough**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-124">Call the project **FFDisassemblerWalkthrough**.</span></span>  
  
2.  <span data-ttu-id="29b3b-125">生成密钥文件，并将其分配给该项目。</span><span class="sxs-lookup"><span data-stu-id="29b3b-125">Generate a key file and assign it to the project.</span></span> <span data-ttu-id="29b3b-126">有关此任务的详细信息，请参阅[签名页上，项目设计器](http://go.microsoft.com/fwlink/?LinkId=125876)。</span><span class="sxs-lookup"><span data-stu-id="29b3b-126">For more information about this task, see [Signing Page, Project Designer](http://go.microsoft.com/fwlink/?LinkId=125876).</span></span>  
  
3.  <span data-ttu-id="29b3b-127">在项目的部署属性，设置**应用程序名称**到"FlatFileExample"和集**重新启动主机实例**到`True`。</span><span class="sxs-lookup"><span data-stu-id="29b3b-127">In the deployment properties for the project, set **Application Name** to “FlatFileExample” and set **Restart Host Instances** to `True`.</span></span> <span data-ttu-id="29b3b-128">设置此标志的作用是通知主机清除该程序集的所有缓存的实例。</span><span class="sxs-lookup"><span data-stu-id="29b3b-128">Setting this flag tells the host to clear any cached instances of the assembly.</span></span>  
  
### <a name="create-the-sample-data-file"></a><span data-ttu-id="29b3b-129">创建示例数据文件</span><span class="sxs-lookup"><span data-stu-id="29b3b-129">Create the Sample Data File</span></span>  
<span data-ttu-id="29b3b-130">生成架构前，您需要创建测试文件。</span><span class="sxs-lookup"><span data-stu-id="29b3b-130">Before generating schemas, you need to create a test file.</span></span>   
  
1.  <span data-ttu-id="29b3b-131">启动记事本或其他文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="29b3b-131">Start Notepad or another text editor.</span></span>  
  
2.  <span data-ttu-id="29b3b-132">创建测试文件示例。</span><span class="sxs-lookup"><span data-stu-id="29b3b-132">Create a sample test file.</span></span> <span data-ttu-id="29b3b-133">该文件由头部、尾部和正文组成，头部用来指明报告错误的位置，尾部含有此批的批 ID，正文包含一个或多个错误记录。</span><span class="sxs-lookup"><span data-stu-id="29b3b-133">The file consists of a header indicating the location reporting the error(s), a trailer with a batch ID for this batch, and a body consisting of one or more error records.</span></span> <span data-ttu-id="29b3b-134">该文件的格式如下：</span><span class="sxs-lookup"><span data-stu-id="29b3b-134">The format of the file is as follows:</span></span>  
  
    ```  
    Location  
    ERRORid|type|priority|description|errorDateTime  
    …additional error records   
    BatchID  
    ```  
  
    <span data-ttu-id="29b3b-135">标记有文本"错误"错误记录并将其用分隔"&#124;"字符 （而非位置）。</span><span class="sxs-lookup"><span data-stu-id="29b3b-135">The ERROR record is tagged with the text “ERROR” and delimited with the “&#124;” character (versus positional).</span></span> <span data-ttu-id="29b3b-136">下表对 ERROR 记录的数据元素进行了描述。</span><span class="sxs-lookup"><span data-stu-id="29b3b-136">The data elements of the ERROR record are described in the following table.</span></span>  
  
    |<span data-ttu-id="29b3b-137">元素</span><span class="sxs-lookup"><span data-stu-id="29b3b-137">Element</span></span>|<span data-ttu-id="29b3b-138">数据类型</span><span class="sxs-lookup"><span data-stu-id="29b3b-138">Data type</span></span>|<span data-ttu-id="29b3b-139">Description</span><span class="sxs-lookup"><span data-stu-id="29b3b-139">Description</span></span>|  
    |---|---|---|  
    |<span data-ttu-id="29b3b-140">ID</span><span class="sxs-lookup"><span data-stu-id="29b3b-140">ID</span></span>|<span data-ttu-id="29b3b-141">integer</span><span class="sxs-lookup"><span data-stu-id="29b3b-141">integer</span></span>|<span data-ttu-id="29b3b-142">此错误 ID。</span><span class="sxs-lookup"><span data-stu-id="29b3b-142">ID for this error.</span></span>|  
    |<span data-ttu-id="29b3b-143">类型</span><span class="sxs-lookup"><span data-stu-id="29b3b-143">Type</span></span>|<span data-ttu-id="29b3b-144">integer</span><span class="sxs-lookup"><span data-stu-id="29b3b-144">integer</span></span>|<span data-ttu-id="29b3b-145">错误类型。</span><span class="sxs-lookup"><span data-stu-id="29b3b-145">Type of error.</span></span>|  
    |<span data-ttu-id="29b3b-146">Priority</span><span class="sxs-lookup"><span data-stu-id="29b3b-146">Priority</span></span>|<span data-ttu-id="29b3b-147">string</span><span class="sxs-lookup"><span data-stu-id="29b3b-147">string</span></span>|<span data-ttu-id="29b3b-148">优先级指示器：低、中或高。</span><span class="sxs-lookup"><span data-stu-id="29b3b-148">Priority indicator: Low, Medium, or High.</span></span>|  
    |<span data-ttu-id="29b3b-149">Description</span><span class="sxs-lookup"><span data-stu-id="29b3b-149">Description</span></span>|<span data-ttu-id="29b3b-150">string</span><span class="sxs-lookup"><span data-stu-id="29b3b-150">string</span></span>|<span data-ttu-id="29b3b-151">错误的说明。</span><span class="sxs-lookup"><span data-stu-id="29b3b-151">Description of the error.</span></span>|  
    |<span data-ttu-id="29b3b-152">ErrorDateTime</span><span class="sxs-lookup"><span data-stu-id="29b3b-152">ErrorDateTime</span></span>|<span data-ttu-id="29b3b-153">DateTime</span><span class="sxs-lookup"><span data-stu-id="29b3b-153">DateTime</span></span>|<span data-ttu-id="29b3b-154">发生错误的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="29b3b-154">Date and time that the error occurred.</span></span>|  
  
    <span data-ttu-id="29b3b-155">该文件可拥有一个或多个 ERROR 记录。</span><span class="sxs-lookup"><span data-stu-id="29b3b-155">The file can have one or more ERROR records.</span></span>  
  
     <span data-ttu-id="29b3b-156">* *-或者--* *</span><span class="sxs-lookup"><span data-stu-id="29b3b-156">**-- OR --  **</span></span>
  
     <span data-ttu-id="29b3b-157">将下面的示例数据复制到新文件。</span><span class="sxs-lookup"><span data-stu-id="29b3b-157">Copy the following sample data into the new file.</span></span> <span data-ttu-id="29b3b-158">最后一行包含尾随的换行符：</span><span class="sxs-lookup"><span data-stu-id="29b3b-158">The last line contains a trailing linefeed:</span></span>
  
    ```  
    East Coast Facility  
    ERROR102|0|High|Sprocket query fails.|1999-05-31T13:20:00.000-05:00  
    ERROR16502|2|Low|Time threshold exceeded.|1999-05-31T13:20:00.000-05:00  
    8675309  
  
    ```  
  
3.  <span data-ttu-id="29b3b-159">将新示例文件保存到项目目录中。</span><span class="sxs-lookup"><span data-stu-id="29b3b-159">Save the new sample file in the project directory.</span></span> <span data-ttu-id="29b3b-160">请使用带有说明性的名称，如“ErrorFile.txt”，以便查找。</span><span class="sxs-lookup"><span data-stu-id="29b3b-160">Use a descriptive name like "ErrorFile.txt" so it can be located easily.</span></span>  
  
### <a name="create-and-test-the-header-trailer-and-body-schemas"></a><span data-ttu-id="29b3b-161">创建头部、尾部和正文架构并进行测试</span><span class="sxs-lookup"><span data-stu-id="29b3b-161">Create and Test the Header, Trailer, and Body Schemas</span></span>  
 <span data-ttu-id="29b3b-162">创建示例数据文件后，下一步就是创建头部、尾部和正文架构。</span><span class="sxs-lookup"><span data-stu-id="29b3b-162">After the sample data file is created, the next step is to create the header, trailer, and body schemas.</span></span> <span data-ttu-id="29b3b-163">平面文件拆装器接收管道组件使用这些架构来处理接收到的消息。</span><span class="sxs-lookup"><span data-stu-id="29b3b-163">These schemas are used with the Flat File Disassembler receive pipeline component to process received messages.</span></span>  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-header-schema"></a><span data-ttu-id="29b3b-164">使用平面文件架构向导创建的标头架构</span><span class="sxs-lookup"><span data-stu-id="29b3b-164">Use the Flat File Schema Wizard to create the header schema</span></span>  
  
1.  <span data-ttu-id="29b3b-165">向项目添加新架构。</span><span class="sxs-lookup"><span data-stu-id="29b3b-165">Add a new schema to the project.</span></span> <span data-ttu-id="29b3b-166">在解决方案资源管理器，右键单击**FFDisassemblerWalkthrough**，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-166">In Solution Explorer, right-click **FFDisassemblerWalkthrough**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="29b3b-167">在**添加新项**对话框中，单击**架构文件**和选择**平面文件架构向导**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-167">In the **Add New Item** dialog box, click **Schema Files** and select **Flat File Schema Wizard**.</span></span> <span data-ttu-id="29b3b-168">将新架构"Header.xsd"，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-168">Name the new schema "Header.xsd" and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="29b3b-169">上**欢迎 BizTalk 平面文件架构向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-169">On the **Welcome to the BizTalk Flat File Schema Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="29b3b-170">上**平面文件架构信息**页上，单击**浏览**并找到之前创建的示例数据文件。</span><span class="sxs-lookup"><span data-stu-id="29b3b-170">On the **Flat File Schema Information** page, click **Browse** and locate the sample data file created earlier.</span></span> <span data-ttu-id="29b3b-171">更改**记录名称**to"标头"，验证的代码页;，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-171">Change the **Record Name** to "Header", verify the code page, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="29b3b-172">如果您将该示例文件保存为 Unicode 格式，则代码页将为 Little-Endian-UTF16 (1200)。</span><span class="sxs-lookup"><span data-stu-id="29b3b-172">If you saved the sample file in Unicode format the code page will be Little-Endian-UTF16 (1200).</span></span> <span data-ttu-id="29b3b-173">这不会对该示例产生不利影响。</span><span class="sxs-lookup"><span data-stu-id="29b3b-173">This will not adversely affect the example.</span></span>  
  
5.  <span data-ttu-id="29b3b-174">然后，选择文档数据。</span><span class="sxs-lookup"><span data-stu-id="29b3b-174">Next select the document data.</span></span> <span data-ttu-id="29b3b-175">上**选择文档数据**页上，突出显示的第一个行的数据，包括新行字符 {CR} 和 {LF} 所示：</span><span class="sxs-lookup"><span data-stu-id="29b3b-175">On the **Select Document Data** page, highlight the first line of data including the new-line characters {CR} and {LF} as shown:</span></span>  
  
     <span data-ttu-id="29b3b-176">![标头架构用于所选数据](../core/media/ffwiz-header-select-document-data.gif "ffwiz_header_select_document_data")</span><span class="sxs-lookup"><span data-stu-id="29b3b-176">![Data selected for header schema](../core/media/ffwiz-header-select-document-data.gif "ffwiz_header_select_document_data")</span></span>  
  
     <span data-ttu-id="29b3b-177">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-177">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="29b3b-178">上**选择记录格式**页上，单击**下一步**以接受默认值。</span><span class="sxs-lookup"><span data-stu-id="29b3b-178">On the **Select Record Format** page, click **Next** to accept the default.</span></span> <span data-ttu-id="29b3b-179">您可以接受默认的“按分隔符符号”是因为数据文件不使用相对位置。</span><span class="sxs-lookup"><span data-stu-id="29b3b-179">You can accept the default "by delimiter symbol" because the data file does not use relative position.</span></span>  
  
7.  <span data-ttu-id="29b3b-180">上**分隔记录**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-180">On the **Delimited Record** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="29b3b-181">现在，您可以指定子元素了。</span><span class="sxs-lookup"><span data-stu-id="29b3b-181">Now you specify child elements.</span></span> <span data-ttu-id="29b3b-182">头部包含一个名为“Location”的元素：</span><span class="sxs-lookup"><span data-stu-id="29b3b-182">The header contains one element named "Location":</span></span>  
  
     <span data-ttu-id="29b3b-183">![标头定义的位置节点](../core/media/ffwiz-header-child-elements.gif "ffwiz_header_child_elements")</span><span class="sxs-lookup"><span data-stu-id="29b3b-183">![Location node defined for header](../core/media/ffwiz-header-child-elements.gif "ffwiz_header_child_elements")</span></span>  
  
     <span data-ttu-id="29b3b-184">单击 **“下一步”** 继续。</span><span class="sxs-lookup"><span data-stu-id="29b3b-184">Click **Next** to continue.</span></span>  
  
9. <span data-ttu-id="29b3b-185">上**架构视图**页上，验证架构。</span><span class="sxs-lookup"><span data-stu-id="29b3b-185">On the **Schema View** page, verify the schema.</span></span>  
  
     <span data-ttu-id="29b3b-186">![架构视图显示完成标头架构](../core/media/ffwiz-header-schema-view.gif "ffwiz_header_schema_view")</span><span class="sxs-lookup"><span data-stu-id="29b3b-186">![Schema view showing completed Header schema](../core/media/ffwiz-header-schema-view.gif "ffwiz_header_schema_view")</span></span>  
  
     <span data-ttu-id="29b3b-187">当满足要求，单击**完成**以完成向导。</span><span class="sxs-lookup"><span data-stu-id="29b3b-187">When you are satisfied, click **Finish** to complete the wizard.</span></span>  
  
10. <span data-ttu-id="29b3b-188">单击**\<架构\>**在标头的架构窗格中的节点。</span><span class="sxs-lookup"><span data-stu-id="29b3b-188">Click the **\<Schema\>** node in the Header schema pane.</span></span> <span data-ttu-id="29b3b-189">在属性窗格中，更改**元素 FormDefault**到**合格**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-189">In the Properties pane, change **Element FormDefault** to **Qualified**.</span></span> <span data-ttu-id="29b3b-190">这指明本地声明的元素必须受到实例文档中的目标命名空间的限定。</span><span class="sxs-lookup"><span data-stu-id="29b3b-190">This indicates that locally declared elements must be qualified by the target namespace in an instance document.</span></span>  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-trailer-schema"></a><span data-ttu-id="29b3b-191">使用平面文件架构向导创建尾部架构</span><span class="sxs-lookup"><span data-stu-id="29b3b-191">Use the Flat File Schema Wizard to create the trailer schema</span></span>  
  
1.  <span data-ttu-id="29b3b-192">向项目添加新架构。</span><span class="sxs-lookup"><span data-stu-id="29b3b-192">Add a new schema to the project.</span></span> <span data-ttu-id="29b3b-193">在解决方案资源管理器，右键单击**FFDisassemblerWalkthrough**，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-193">In Solution Explorer, right-click **FFDisassemblerWalkthrough**, point to **Add** , and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="29b3b-194">在**添加新项**对话框中，单击**架构文件**和选择**平面文件架构向导**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-194">In the **Add New Item** dialog box, click **Schema Files** and select **Flat File Schema Wizard**.</span></span> <span data-ttu-id="29b3b-195">将新架构"Trailer.xsd"，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-195">Name the new schema "Trailer.xsd" and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="29b3b-196">上**欢迎 BizTalk 平面文件架构向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-196">On the **Welcome to the BizTalk Flat File Schema Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="29b3b-197">上**平面文件架构信息**页上，单击**浏览**并找到之前创建的示例数据文件。</span><span class="sxs-lookup"><span data-stu-id="29b3b-197">On the **Flat File Schema Information** page, click **Browse** and locate the sample data file created earlier.</span></span> <span data-ttu-id="29b3b-198">更改**记录名称**到"预告片"，验证的代码页;，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-198">Change the **Record Name** to "Trailer", verify the code page, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="29b3b-199">如果您将该示例文件保存为 Unicode 格式，则代码页将为 Little-Endian-UTF16 (1200)。</span><span class="sxs-lookup"><span data-stu-id="29b3b-199">If you saved the sample file in Unicode format the code page will be Little-Endian-UTF16 (1200).</span></span> <span data-ttu-id="29b3b-200">这不会对该示例产生不利影响。</span><span class="sxs-lookup"><span data-stu-id="29b3b-200">This will not adversely affect the example.</span></span>  
  
5.  <span data-ttu-id="29b3b-201">然后，选择文档数据。</span><span class="sxs-lookup"><span data-stu-id="29b3b-201">Next select the document data.</span></span> <span data-ttu-id="29b3b-202">上**选择文档数据**页上，突出显示的最后一行的数据，包括新行字符 {CR} 和 {LF} 所示：</span><span class="sxs-lookup"><span data-stu-id="29b3b-202">On the **Select Document Data** page, highlight the last line of data including the new-line characters {CR} and {LF} as shown:</span></span>  
  
     <span data-ttu-id="29b3b-203">![尾部架构用于所选数据](../core/media/ffwiz-trailer-select-document-data.gif "ffwiz_trailer_select_document_data")</span><span class="sxs-lookup"><span data-stu-id="29b3b-203">![Data selected for trailer schema](../core/media/ffwiz-trailer-select-document-data.gif "ffwiz_trailer_select_document_data")</span></span>  
  
     <span data-ttu-id="29b3b-204">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-204">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="29b3b-205">上**选择记录格式**页上，单击**下一步**以接受默认值。</span><span class="sxs-lookup"><span data-stu-id="29b3b-205">On the **Select Record Format** page, click **Next** to accept the default.</span></span> <span data-ttu-id="29b3b-206">您可以接受默认的“按分隔符符号”是因为数据文件不使用相对位置。</span><span class="sxs-lookup"><span data-stu-id="29b3b-206">You can accept the default "by delimiter symbol" because the data file does not use relative position.</span></span>  
  
7.  <span data-ttu-id="29b3b-207">上**分隔记录**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-207">On the **Delimited Record** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="29b3b-208">现在，您可以指定子元素了。</span><span class="sxs-lookup"><span data-stu-id="29b3b-208">Now you specify child elements.</span></span> <span data-ttu-id="29b3b-209">头部包含一个名为“BatchID”的元素：</span><span class="sxs-lookup"><span data-stu-id="29b3b-209">The header contains one element named "BatchID":</span></span>  
  
     <span data-ttu-id="29b3b-210">![位置节点为预告片定义](../core/media/ffwiz-trailer-child-elements.gif "ffwiz_trailer_child_elements")</span><span class="sxs-lookup"><span data-stu-id="29b3b-210">![Location node defined for trailer](../core/media/ffwiz-trailer-child-elements.gif "ffwiz_trailer_child_elements")</span></span>  
  
     <span data-ttu-id="29b3b-211">单击 **“下一步”** 继续。</span><span class="sxs-lookup"><span data-stu-id="29b3b-211">Click **Next** to continue.</span></span>  
  
9. <span data-ttu-id="29b3b-212">上**架构视图**页上，验证架构。</span><span class="sxs-lookup"><span data-stu-id="29b3b-212">On the **Schema View** page, verify the schema.</span></span>  
  
     <span data-ttu-id="29b3b-213">![架构视图显示完成预告片架构](../core/media/ffwiz-trailer-schema-view.gif "ffwiz_trailer_schema_view")</span><span class="sxs-lookup"><span data-stu-id="29b3b-213">![Schema view showing completed Trailer schema](../core/media/ffwiz-trailer-schema-view.gif "ffwiz_trailer_schema_view")</span></span>  
  
     <span data-ttu-id="29b3b-214">当满足要求，单击**完成**以完成向导。</span><span class="sxs-lookup"><span data-stu-id="29b3b-214">When you are satisfied, click **Finish** to complete the wizard.</span></span>  
  
10. <span data-ttu-id="29b3b-215">单击**\<架构\>**预告片架构窗格中的节点。</span><span class="sxs-lookup"><span data-stu-id="29b3b-215">Click the **\<Schema\>** node in the Trailer schema pane.</span></span> <span data-ttu-id="29b3b-216">在属性窗格中，更改**elementFormDefault**到**合格**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-216">In the Properties pane, change **elementFormDefault** to **Qualified**.</span></span> <span data-ttu-id="29b3b-217">这指明本地声明的元素必须受到实例文档中的目标命名空间的限定。</span><span class="sxs-lookup"><span data-stu-id="29b3b-217">This indicates that locally declared elements must be qualified by the target namespace in an instance document.</span></span>  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-body-schema"></a><span data-ttu-id="29b3b-218">使用平面文件架构向导创建正文架构</span><span class="sxs-lookup"><span data-stu-id="29b3b-218">Use the Flat File Schema Wizard to create the body schema</span></span>  
  
1.  <span data-ttu-id="29b3b-219">向项目添加新架构。</span><span class="sxs-lookup"><span data-stu-id="29b3b-219">Add a new schema to the project.</span></span> <span data-ttu-id="29b3b-220">在解决方案资源管理器，右键单击**FFDisassemblerWalkthrough**，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-220">In Solution Explorer, right-click **FFDisassemblerWalkthrough**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="29b3b-221">在**添加新项**对话框中，单击**架构文件**和选择**平面文件架构向导**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-221">In the **Add New Item** dialog box, click **Schema Files** and select **Flat File Schema Wizard**.</span></span> <span data-ttu-id="29b3b-222">将新架构"Body.xsd"，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-222">Name the new schema "Body.xsd" and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="29b3b-223">上**欢迎 BizTalk 平面文件架构向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-223">On the **Welcome to the BizTalk Flat File Schema Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="29b3b-224">上**平面文件架构信息**页上，单击**浏览**并找到之前创建的示例数据文件。</span><span class="sxs-lookup"><span data-stu-id="29b3b-224">On the **Flat File Schema Information** page, click **Browse** and locate the sample data file created earlier.</span></span> <span data-ttu-id="29b3b-225">更改**记录名称**到"正文"中，验证的代码页;，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-225">Change the **Record Name** to "Body", verify the code page, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="29b3b-226">如果您将该示例文件保存为 Unicode 格式，则代码页将为 Little-Endian-UTF16 (1200)。</span><span class="sxs-lookup"><span data-stu-id="29b3b-226">If you saved the sample file in Unicode format the code page will be Little-Endian-UTF16 (1200).</span></span> <span data-ttu-id="29b3b-227">这不会对该示例产生不利影响。</span><span class="sxs-lookup"><span data-stu-id="29b3b-227">This will not adversely affect the example.</span></span>  
  
5.  <span data-ttu-id="29b3b-228">然后，选择文档数据。</span><span class="sxs-lookup"><span data-stu-id="29b3b-228">Next select the document data.</span></span> <span data-ttu-id="29b3b-229">上**选择文档数据**页上，突出显示两个和第三行的数据，包括新行字符 {CR} 和 {LF} 所示：</span><span class="sxs-lookup"><span data-stu-id="29b3b-229">On the **Select Document Data** page, highlight lines two and three of data including the new-line characters {CR} and {LF} as shown:</span></span>  
  
     <span data-ttu-id="29b3b-230">![正文架构用于所选数据](../core/media/ffwiz-body-select-document-data.gif "ffwiz_body_select_document_data")</span><span class="sxs-lookup"><span data-stu-id="29b3b-230">![Data selected for body schema](../core/media/ffwiz-body-select-document-data.gif "ffwiz_body_select_document_data")</span></span>  
  
     <span data-ttu-id="29b3b-231">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-231">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="29b3b-232">上**选择记录格式**页上，单击**下一步**以接受默认值。</span><span class="sxs-lookup"><span data-stu-id="29b3b-232">On the **Select Record Format** page, click **Next** to accept the default.</span></span> <span data-ttu-id="29b3b-233">您可以接受默认的“按分隔符符号”是因为数据文件不使用相对位置。</span><span class="sxs-lookup"><span data-stu-id="29b3b-233">You can accept the default "by delimiter symbol" because the data file does not use relative position.</span></span>  
  
7.  <span data-ttu-id="29b3b-234">上**分隔记录**页上，选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-234">On the **Delimited Record** page, select **Next**.</span></span>  
  
8.  <span data-ttu-id="29b3b-235">下面定义子元素。</span><span class="sxs-lookup"><span data-stu-id="29b3b-235">Next define the child elements.</span></span> <span data-ttu-id="29b3b-236">更改**Body_Child1**到**错误**并将其元素类型设置为**重复记录**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-236">Change **Body_Child1** to **Error**and set its element type to **Repeating record**.</span></span> <span data-ttu-id="29b3b-237">设置**Body_Child2**元素记录类型设置为**忽略**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-237">Set the **Body_Child2** element record type to **Ignore**.</span></span>  
  
9. <span data-ttu-id="29b3b-238">上**架构视图**页上，单击**下一步**定义的错误记录的子元素。</span><span class="sxs-lookup"><span data-stu-id="29b3b-238">On the **Schema View** page, click **Next** to define the child elements of the Error record.</span></span>  
  
10. <span data-ttu-id="29b3b-239">上**选择文档数据**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-239">On the **Select Document Data** page, click **Next**.</span></span> <span data-ttu-id="29b3b-240">该向导可正确地选择记录定义的数据。</span><span class="sxs-lookup"><span data-stu-id="29b3b-240">The wizard chooses the record-defining data correctly.</span></span>  
  
11. <span data-ttu-id="29b3b-241">上**选择记录格式**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-241">On the **Select Record Format** page, click **Next**.</span></span> <span data-ttu-id="29b3b-242">由分隔符设置数据格式。</span><span class="sxs-lookup"><span data-stu-id="29b3b-242">The data is formatted by delimiter symbol.</span></span>  
  
12. <span data-ttu-id="29b3b-243">上**分隔记录**页上，选择**&#124;**为**子分隔符**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-243">On the **Delimited Record** page, select **&#124;** for the **Child delimiter**.</span></span> <span data-ttu-id="29b3b-244">接下来，选择**记录带有标记标识符**复选框，并键入**错误**的标记值。</span><span class="sxs-lookup"><span data-stu-id="29b3b-244">Next, select the **Record has a tag identifier** check box and type **ERROR** for the tag value.</span></span>  
  
     <span data-ttu-id="29b3b-245">![配置分隔记录具有标记标识符](../core/media/ffwiz-bodyerror-delimited-record.gif "ffwiz_bodyerror_delimited_record")</span><span class="sxs-lookup"><span data-stu-id="29b3b-245">![Configuring delimited record with tag identifier](../core/media/ffwiz-bodyerror-delimited-record.gif "ffwiz_bodyerror_delimited_record")</span></span>  
  
     <span data-ttu-id="29b3b-246">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-246">Click **Next**.</span></span>  
  
13. <span data-ttu-id="29b3b-247">现在，定义错误记录的子元素。</span><span class="sxs-lookup"><span data-stu-id="29b3b-247">Now define the child elements of the Error record.</span></span>  
  
     <span data-ttu-id="29b3b-248">![使用五个元素定义的错误记录](../core/media/ffwiz-bodyerror-child-elements.gif "ffwiz_bodyerror_child_elements")</span><span class="sxs-lookup"><span data-stu-id="29b3b-248">![Error record defined with five elements](../core/media/ffwiz-bodyerror-child-elements.gif "ffwiz_bodyerror_child_elements")</span></span>  
  
     <span data-ttu-id="29b3b-249">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-249">Click **Next**.</span></span>  
  
14. <span data-ttu-id="29b3b-250">上**架构视图**页上，验证架构。</span><span class="sxs-lookup"><span data-stu-id="29b3b-250">On the **Schema View** page, verify the schema.</span></span>  
  
     <span data-ttu-id="29b3b-251">![架构视图显示完成正文架构](../core/media/ffwiz-bodyerror-schema-view.gif "ffwiz_bodyerror_schema_view")</span><span class="sxs-lookup"><span data-stu-id="29b3b-251">![Schema view showing completed Body schema](../core/media/ffwiz-bodyerror-schema-view.gif "ffwiz_bodyerror_schema_view")</span></span>  
  
     <span data-ttu-id="29b3b-252">如果所做的任何错误，请单击**回**并进行必要的更正。</span><span class="sxs-lookup"><span data-stu-id="29b3b-252">If you have made any mistakes, click **Back** and make the necessary corrections.</span></span> <span data-ttu-id="29b3b-253">当满足要求，单击**完成**以完成向导。</span><span class="sxs-lookup"><span data-stu-id="29b3b-253">When you are satisfied, click **Finish** to complete the wizard.</span></span>  
  
15. <span data-ttu-id="29b3b-254">单击**\<架构\>**正文架构窗格中的节点。</span><span class="sxs-lookup"><span data-stu-id="29b3b-254">Click the **\<Schema\>** node in the Body schema pane.</span></span> <span data-ttu-id="29b3b-255">在属性窗格中，更改**元素 FormDefault**到**合格**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-255">In the Properties pane, change **Element FormDefault** to **Qualified**.</span></span> <span data-ttu-id="29b3b-256">这指明本地声明的元素必须受到实例文档中的目标命名空间的限定。</span><span class="sxs-lookup"><span data-stu-id="29b3b-256">This indicates that locally declared elements must be qualified by the target namespace in an instance document.</span></span>  
  
16. <span data-ttu-id="29b3b-257">单击**\<错误\>**正文架构窗格上的节点。</span><span class="sxs-lookup"><span data-stu-id="29b3b-257">Click the **\<Error\>** node on the Body schema pane.</span></span> <span data-ttu-id="29b3b-258">在属性窗格中，更改**Max Occurs**到**1**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-258">In the Properties pane, change **Max Occurs** to **1**.</span></span> <span data-ttu-id="29b3b-259">这将使平面文件拆装器把每个错误拆分到各自的消息中。</span><span class="sxs-lookup"><span data-stu-id="29b3b-259">This causes the Flat File Disassembler to split each error into its own message.</span></span>  
  
##### <a name="test-the-schemas-using-ffdasm"></a><span data-ttu-id="29b3b-260">测试使用 FFDasm 的架构</span><span class="sxs-lookup"><span data-stu-id="29b3b-260">Test the schemas using FFDasm</span></span>  
  
1.  <span data-ttu-id="29b3b-261">打开命令提示符，将目录改到您的项目目录。</span><span class="sxs-lookup"><span data-stu-id="29b3b-261">Open a command prompt and change the directory to your project directory.</span></span>  
  
2.  <span data-ttu-id="29b3b-262">在命令提示符下，运行 FFDasm.exe，如下所示。</span><span class="sxs-lookup"><span data-stu-id="29b3b-262">From the command prompt, run FFDasm.exe as shown below.</span></span>  
  
    ```  
    <Samples Path>\SDK\Utilities\PipelineTools\FFDasm ErrorFile.txt  -hs header.xsd -bs body.xsd -ts Trailer.xsd  
    ```  
  
     <span data-ttu-id="29b3b-263">有关此产品及其他管道工具的位置的信息，请参阅[管道工具](../core/pipeline-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="29b3b-263">For information about the location of this and other pipeline tools, see [Pipeline Tools](../core/pipeline-tools.md).</span></span>  
  
3.  <span data-ttu-id="29b3b-264">FFDasm.exe 将产生两个名称为 {GUID}.xml 的输出文件，分别对应测试文件中的每个 ERROR 记录。</span><span class="sxs-lookup"><span data-stu-id="29b3b-264">FFDasm.exe should produce two output files named {GUID}.xml, one for each ERROR record in the test file.</span></span> <span data-ttu-id="29b3b-265">高优先级错误记录与以下类似：</span><span class="sxs-lookup"><span data-stu-id="29b3b-265">The high-priority error record looks like the following:</span></span>  
  
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
  
### <a name="create-a-custom-receive-pipeline"></a><span data-ttu-id="29b3b-266">创建自定义接收管道</span><span class="sxs-lookup"><span data-stu-id="29b3b-266">Create a Custom Receive Pipeline</span></span>  
 <span data-ttu-id="29b3b-267">现在已定义了平面文件架构，下面需要创建一个使用平面文件拆装器组件的自定义管道。</span><span class="sxs-lookup"><span data-stu-id="29b3b-267">Now that the flat file schemas are defined, you need to create a custom pipeline that uses the Flat File Disassembler component.</span></span> <span data-ttu-id="29b3b-268">然后，就可将平面文件拆装器组件配置为使用头部、正文和尾部架构来分解消息。</span><span class="sxs-lookup"><span data-stu-id="29b3b-268">The Flat File Disassembler component can then be configured to use the header, body, and trailer schemas to break up messages.</span></span>    
 
1.  <span data-ttu-id="29b3b-269">向项目添加新接收管道。</span><span class="sxs-lookup"><span data-stu-id="29b3b-269">Add a new receive pipeline to the project.</span></span> <span data-ttu-id="29b3b-270">在解决方案资源管理器，右键单击**FFDisassemblerWalkthrough**项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-270">In Solution Explorer, right-click the **FFDisassemblerWalkthrough** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="29b3b-271">在**添加新项**对话框中，指向**管道文件**，然后单击**接收管道**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-271">In the **Add New Item** dialog box, point to **Pipeline Files** and then click **Receive Pipeline**.</span></span> <span data-ttu-id="29b3b-272">命名新管道"FFReceivePipeline"，再单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-272">Name the new pipeline "FFReceivePipeline" and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="29b3b-273">通过将平面文件拆装器组件从“工具箱”窗格拖至“拆装”步骤来配置新管道。</span><span class="sxs-lookup"><span data-stu-id="29b3b-273">Configure the new pipeline by dragging the Flat File Disassembler component from the Toolbox pane to the Disassemble step.</span></span>  
  
4.  <span data-ttu-id="29b3b-274">在属性窗格中，设置**文档架构**到**FFDisassemblerWalkthrough.Body**、**标头架构**到**FFDisassemblerWalkthrough.Header**和**尾部架构**到**FFDisassemblerWalkthrough.Trailer**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-274">In the Properties pane, set the **Document schema** to **FFDisassemblerWalkthrough.Body**, the **Header schema** to **FFDisassemblerWalkthrough.Header** and the **Trailer schema** to **FFDisassemblerWalkthrough.Trailer**.</span></span>  
  
### <a name="deploy-the-application-and-configure-the-send-and-receive-ports"></a><span data-ttu-id="29b3b-275">部署应用程序并配置发送端口和接收端口</span><span class="sxs-lookup"><span data-stu-id="29b3b-275">Deploy the Application and Configure the Send and Receive Ports</span></span>  
 <span data-ttu-id="29b3b-276">创建了架构和自定义接收管道后，需要编译和部署项目。</span><span class="sxs-lookup"><span data-stu-id="29b3b-276">With the schemas and custom receive pipeline created, you need to compile and deploy the project.</span></span> <span data-ttu-id="29b3b-277">部署完毕后，就可使用 BizTalk Server 管理控制台来配置发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="29b3b-277">After it is deployed, you can use the BizTalk Server Administration console to configure the send and receive ports.</span></span>  

##### <a name="deploy"></a><span data-ttu-id="29b3b-278">部署</span><span class="sxs-lookup"><span data-stu-id="29b3b-278">Deploy</span></span>  
1.  <span data-ttu-id="29b3b-279">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，通过右键单击项目，然后单击部署解决方案**部署**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-279">From within [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], deploy the solution by right-clicking on the project and then clicking **Deploy**.</span></span>  
  
2.  <span data-ttu-id="29b3b-280">使用 BizTalk Server 管理控制台中，展开**应用程序**组以便确认**FlatFileExample**显示为自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="29b3b-280">Using the BizTalk Server Administration console, expand the **Applications** group to verify that **FlatFileExample** is present as a custom application.</span></span>  
  
##### <a name="configure-the-receive-port"></a><span data-ttu-id="29b3b-281">配置接收端口</span><span class="sxs-lookup"><span data-stu-id="29b3b-281">Configure the receive port</span></span>  
  
1.  <span data-ttu-id="29b3b-282">使用 Windows 资源管理器下创建一个名为"接收"目录**FFDisassemblerWalkthrough**项目目录。</span><span class="sxs-lookup"><span data-stu-id="29b3b-282">Use Windows Explorer to create a directory named "Receive" under the **FFDisassemblerWalkthrough** project directory.</span></span>  
  
2.  <span data-ttu-id="29b3b-283">在 BizTalk Server 管理控制台中，展开**FlatFileExample**应用程序中，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-283">In the BizTalk Server Administration console, expand the **FlatFileExample** application, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
3.  <span data-ttu-id="29b3b-284">在**接收端口属性**对话框框中，设置为"ReceiveError"的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="29b3b-284">In the **Receive Port Properties** dialog box, set the name of the port to "ReceiveError".</span></span>  
  
4.  <span data-ttu-id="29b3b-285">单击**接收位置**，然后单击**新建**添加接收位置。</span><span class="sxs-lookup"><span data-stu-id="29b3b-285">Click **Receive Locations**, and then click **New** to add a receive location.</span></span> <span data-ttu-id="29b3b-286">将新的接收位置命名为“ReceiveErrorLocation”。</span><span class="sxs-lookup"><span data-stu-id="29b3b-286">Name the new receive location "ReceiveErrorLocation".</span></span> <span data-ttu-id="29b3b-287">设置**接收管道**到**FFReceivePipeline**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-287">Set the **Receive Pipeline** to **FFReceivePipeline**.</span></span> <span data-ttu-id="29b3b-288">有关**传输类型**，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-288">For **Transport Type**, select **FILE**, and then click **Configure**.</span></span> <span data-ttu-id="29b3b-289">选择接收目录创建，并将**文件掩码**到 *.txt。</span><span class="sxs-lookup"><span data-stu-id="29b3b-289">Select the receive directory you created, and then set the **File mask** to *.txt.</span></span>  
  
5.  <span data-ttu-id="29b3b-290">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-290">Click **OK**.</span></span> <span data-ttu-id="29b3b-291">现在接收端口配置完毕。</span><span class="sxs-lookup"><span data-stu-id="29b3b-291">Your receive port should now be configured.</span></span> <span data-ttu-id="29b3b-292">单击**确定**关闭。</span><span class="sxs-lookup"><span data-stu-id="29b3b-292">Click **OK** to close.</span></span>  
  
##### <a name="configure-the-send-port"></a><span data-ttu-id="29b3b-293">配置发送端口</span><span class="sxs-lookup"><span data-stu-id="29b3b-293">Configure the send port</span></span>  
  
1.  <span data-ttu-id="29b3b-294">使用 Windows 资源管理器下创建一个名为"发送"目录**FFDisassemblerWalkthrough**项目目录。</span><span class="sxs-lookup"><span data-stu-id="29b3b-294">Use Windows Explorer to create a directory named "Send" under the **FFDisassemblerWalkthrough** project directory.</span></span>  
  
2.  <span data-ttu-id="29b3b-295">在 BizTalk Server 管理控制台中，展开**FlatFileExample**应用程序中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口...**.</span><span class="sxs-lookup"><span data-stu-id="29b3b-295">In the BizTalk Server Administration console, expand the **FlatFileExample** application, right-click **Send Ports**, point to **New**, and then click **Static One-Way  Send Port…**.</span></span>  
  
3.  <span data-ttu-id="29b3b-296">在**发送端口属性**对话框框中，设置"发送"的端口的名称。</span><span class="sxs-lookup"><span data-stu-id="29b3b-296">In the **Send Port Properties** dialog box, set the name of the port to "Send".</span></span>  
  
4.  <span data-ttu-id="29b3b-297">对于传输类型，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-297">For transport type, select **FILE**, and then click **Configure**.</span></span> <span data-ttu-id="29b3b-298">将目标文件夹设置为前面创建的发送目录。</span><span class="sxs-lookup"><span data-stu-id="29b3b-298">Set the destination folder to the send directory you created earlier.</span></span>  
  
5.  <span data-ttu-id="29b3b-299">现在配置筛选器。</span><span class="sxs-lookup"><span data-stu-id="29b3b-299">Now configure the filter.</span></span> <span data-ttu-id="29b3b-300">单击**筛选器**并添加一个表达式：</span><span class="sxs-lookup"><span data-stu-id="29b3b-300">Click **Filters** and add one expression:</span></span>  
  
    -   <span data-ttu-id="29b3b-301">BTS。MessageType = = **http://FFDisassemblerWalkthrough.Body#Body**</span><span class="sxs-lookup"><span data-stu-id="29b3b-301">BTS.MessageType == **http://FFDisassemblerWalkthrough.Body#Body**</span></span>  
  
6.  <span data-ttu-id="29b3b-302">单击**确定**以完成发送端口配置。</span><span class="sxs-lookup"><span data-stu-id="29b3b-302">Click **OK** to complete the send port configuration.</span></span> <span data-ttu-id="29b3b-303">现在发送端口配置完毕。</span><span class="sxs-lookup"><span data-stu-id="29b3b-303">Your send port should be configured.</span></span>  
  
### <a name="run-the-example"></a><span data-ttu-id="29b3b-304">运行示例</span><span class="sxs-lookup"><span data-stu-id="29b3b-304">Run the Example</span></span>  
 <span data-ttu-id="29b3b-305">现在该运行示例了。</span><span class="sxs-lookup"><span data-stu-id="29b3b-305">It is now time to run the example.</span></span> <span data-ttu-id="29b3b-306">使用 BizTalk Server 管理控制台中启动应用程序之后, 将测试文件复制到接收位置和观察在发送位置生成的内容。</span><span class="sxs-lookup"><span data-stu-id="29b3b-306">After using the BizTalk Server Management console to start the application, copy the test files to the receive location and observe what is produced in the send location.</span></span>  
  
1.  <span data-ttu-id="29b3b-307">在 BizTalk Server 管理控制台中，右键单击**FlatFileExample**应用程序，，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="29b3b-307">In the BizTalk Server Administration console, right-click the **FlatFileExample** application, and then click **Start**.</span></span> <span data-ttu-id="29b3b-308">这登记和启动发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="29b3b-308">This enlists and starts the send and receive ports.</span></span>  
  
2.  <span data-ttu-id="29b3b-309">将示例 Errorfile.txt 的副本放入接收目录中。</span><span class="sxs-lookup"><span data-stu-id="29b3b-309">Drop the copy of the sample Errorfile.txt into the receive directory.</span></span> <span data-ttu-id="29b3b-310">应有两个输出文件写入到发送目录中。</span><span class="sxs-lookup"><span data-stu-id="29b3b-310">Two output files should be written to the send directory.</span></span>  
  
