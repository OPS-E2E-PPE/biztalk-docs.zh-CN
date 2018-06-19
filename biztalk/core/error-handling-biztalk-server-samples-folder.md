---
title: 错误处理 （BizTalk Server 示例文件夹中） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, errors
- errors, examples
- examples, messages
- messages, examples
- messages, errors
ms.assetid: b39791ed-277b-4625-b9a9-72480a1b6ff6
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 386e9729ac32cb08863e2ac3e0699ecda7890dbc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971475"
---
# <a name="error-handling-biztalk-server-samples-folder"></a><span data-ttu-id="d543c-102">错误处理（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="d543c-102">Error Handling (BizTalk Server Samples Folder)</span></span>
<span data-ttu-id="d543c-103">本示例的目的是为基于内容的路由 (CBR) 应用程序生成错误处理功能。</span><span class="sxs-lookup"><span data-stu-id="d543c-103">The purpose of this sample is to build an error-handling functionality for the content-based routing (CBR) application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d543c-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="d543c-104">Prerequisites</span></span>  
 <span data-ttu-id="d543c-105">若要运行本示例，建议你安装 Microsoft Office InfoPath 2010 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d543c-105">To run the sample, it is recommended that you have Microsoft Office InfoPath 2010 or later installed.</span></span> <span data-ttu-id="d543c-106">你可以在不使用 InfoPath 的情况下运行本示例，但在这种情况下，你无法通过 HTTP 适配器查看费用报告以及费用报告的提交。</span><span class="sxs-lookup"><span data-stu-id="d543c-106">You can run the sample without using InfoPath, but in that case you cannot see the expense reports and the submission of expense reports through the HTTP adapter.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="d543c-107">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="d543c-107">What This Sample Does</span></span>  
 <span data-ttu-id="d543c-108">本示例可实现费用报告处理系统部分。</span><span class="sxs-lookup"><span data-stu-id="d543c-108">The sample implements part of an expense report processing system.</span></span> <span data-ttu-id="d543c-109">具体而言，本示例执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="d543c-109">Specifically, this sample does the following:</span></span>  
  
1.  <span data-ttu-id="d543c-110">定义费用报告架构，该架构包含有关费用报告和单个提交者（包括部门名称）的信息。</span><span class="sxs-lookup"><span data-stu-id="d543c-110">Defines an expense report schema containing information about an expense report and the individual submitter including department name.</span></span>  
  
2.  <span data-ttu-id="d543c-111">使用 InfoPath 通过目录或 Web Services 提供费用报告的提交。</span><span class="sxs-lookup"><span data-stu-id="d543c-111">Provides for the submission of the expense report through a directory or through a Web service using InfoPath.</span></span>  
  
3.  <span data-ttu-id="d543c-112">提升**部门**和**correlationID**消息中的属性文档，以便它可以用于端口筛选器中控制路由。</span><span class="sxs-lookup"><span data-stu-id="d543c-112">Promotes the **Department** and **correlationID** properties in the message document so that it can be used in a port filter to control routing.</span></span>  
  
4.  <span data-ttu-id="d543c-113">将属于 Marketing 部门的费用报告路由到目录中的某个文件，从而模拟送达该部门的后端系统。</span><span class="sxs-lookup"><span data-stu-id="d543c-113">Routes expense reports belonging to the Marketing department to a file in a directory, simulating delivery to the department's back-end system.</span></span>  
  
5.  <span data-ttu-id="d543c-114">对属于 Marketing 之外的部门的费用报告生成失败消息。</span><span class="sxs-lookup"><span data-stu-id="d543c-114">Generates a failed message for expense reports belonging to departments other than Marketing.</span></span> <span data-ttu-id="d543c-115">失败消息包括有关错误（包括错误代码和错误说明）的信息。</span><span class="sxs-lookup"><span data-stu-id="d543c-115">The failed message includes information about the error including error code and error description.</span></span>  
  
6.  <span data-ttu-id="d543c-116">将失败消息路由给接收方人员（业务用户或应用程序操作员）以进行更正和重新提交。</span><span class="sxs-lookup"><span data-stu-id="d543c-116">Routes failed messages to a human recipient (a business user or application operator) for correction and resubmission.</span></span>  
  
7.  <span data-ttu-id="d543c-117">如上所述，根据部门路由重新提交的费用报告。</span><span class="sxs-lookup"><span data-stu-id="d543c-117">Routes resubmitted expense reports based on department as described above.</span></span>  
  
 <span data-ttu-id="d543c-118">大部分工作都是通过 BizTalk 业务流程调度完成的。</span><span class="sxs-lookup"><span data-stu-id="d543c-118">Much of this work is done through a BizTalk orchestration schedule.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="d543c-119">本示例旨在如何以及为何</span><span class="sxs-lookup"><span data-stu-id="d543c-119">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="d543c-120">设计依赖 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的默认发送和接收 XML 管道、属性升级、订阅筛选器和业务流程调度来路由消息。</span><span class="sxs-lookup"><span data-stu-id="d543c-120">The design relies on the default send and receive XML pipelines, property promotion, subscription filters, and orchestration schedules within [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to route messages.</span></span> <span data-ttu-id="d543c-121">下表列出了设计元素及其选入理由。</span><span class="sxs-lookup"><span data-stu-id="d543c-121">Design elements and their justification are listed in the following table.</span></span>  
  
|<span data-ttu-id="d543c-122">设计元素</span><span class="sxs-lookup"><span data-stu-id="d543c-122">Design element</span></span>|<span data-ttu-id="d543c-123">选择的原因</span><span class="sxs-lookup"><span data-stu-id="d543c-123">Reason(s) selected</span></span>|  
|--------------------|--------------------------|  
|<span data-ttu-id="d543c-124">默认 XML 接收管道</span><span class="sxs-lookup"><span data-stu-id="d543c-124">Default XML receive pipeline</span></span>|<span data-ttu-id="d543c-125">-XMLReceive 管道支持属性提升;PassThruReceive 管道却没有。</span><span class="sxs-lookup"><span data-stu-id="d543c-125">-   The XMLReceive pipeline supports property promotion; the PassThruReceive pipeline does not.</span></span><br /><span data-ttu-id="d543c-126">-入站的消息已在 XML 格式，并且不需要基本反汇编和参与方解析之外的处理。</span><span class="sxs-lookup"><span data-stu-id="d543c-126">-   The inbound message is already in XML format and does not require processing beyond basic disassembly and party resolution.</span></span>|  
|<span data-ttu-id="d543c-127">针对失败消息的路由</span><span class="sxs-lookup"><span data-stu-id="d543c-127">Routing for failed messages</span></span>|<span data-ttu-id="d543c-128">接收端口挂起失败的消息和默认情况下生成否定确认。</span><span class="sxs-lookup"><span data-stu-id="d543c-128">-   Receive ports suspend failed messages and generate a negative acknowledgment by default.</span></span> <span data-ttu-id="d543c-129">启用路由后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会尝试将处理失败的所有消息路由到某个订阅应用程序（例如另一个接收端口或业务流程调度）。</span><span class="sxs-lookup"><span data-stu-id="d543c-129">When routing is enabled [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] attempts to route any message that fails processing to a subscribing application (such as another receive port or orchestration schedule).</span></span>|  
|<span data-ttu-id="d543c-130">属性提升</span><span class="sxs-lookup"><span data-stu-id="d543c-130">Property promotion</span></span>|<span data-ttu-id="d543c-131">-BizTalk Server 取决于要进行路由的属性字段。</span><span class="sxs-lookup"><span data-stu-id="d543c-131">-   BizTalk Server depends upon property fields to do routing.</span></span> <span data-ttu-id="d543c-132">业务流程使用可分辨字段，并且该字段不能用于路由。</span><span class="sxs-lookup"><span data-stu-id="d543c-132">Distinguished fields are used by orchestrations and cannot be used for routing.</span></span>|  
|<span data-ttu-id="d543c-133">订阅筛选器</span><span class="sxs-lookup"><span data-stu-id="d543c-133">Subscription filter</span></span>|<span data-ttu-id="d543c-134">-订阅筛选器执行通过捕获满足基于属性的字段的一个或多个条件的消息路由。</span><span class="sxs-lookup"><span data-stu-id="d543c-134">-   The subscription filter performs the routing by capturing messages that meet one or more criteria based on property fields.</span></span>|  
|<span data-ttu-id="d543c-135">BizTalk 业务流程调度</span><span class="sxs-lookup"><span data-stu-id="d543c-135">BizTalk orchestration schedule</span></span>|<span data-ttu-id="d543c-136">-提供了机会将信息添加到失败的消息。</span><span class="sxs-lookup"><span data-stu-id="d543c-136">-   Provides the opportunity to add information to failed messages.</span></span><br /><span data-ttu-id="d543c-137">-启用路由的失败消息人工干预的专用位置。</span><span class="sxs-lookup"><span data-stu-id="d543c-137">-   Enables routing of failed messages to a dedicated location for human intervention.</span></span><br /><span data-ttu-id="d543c-138">-进程重新提交费用报表。</span><span class="sxs-lookup"><span data-stu-id="d543c-138">-   Processes resubmitted expense reports.</span></span>|  
|<span data-ttu-id="d543c-139">XMLTransmit</span><span class="sxs-lookup"><span data-stu-id="d543c-139">XMLTransmit</span></span>|<span data-ttu-id="d543c-140">-执行基本的传出的 XML 消息的程序集。</span><span class="sxs-lookup"><span data-stu-id="d543c-140">-   Performs basic assembly of outgoing XML messages.</span></span> <span data-ttu-id="d543c-141">PassThruTransmit 管道不提供其他支持。</span><span class="sxs-lookup"><span data-stu-id="d543c-141">The PassThruTransmit pipeline provides no additional support.</span></span>|  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="d543c-142">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="d543c-142">Where to Find This Sample</span></span>  
 <span data-ttu-id="d543c-143">此示例位于 <`Samples Path>`\Messaging\ErrorHandling\\。</span><span class="sxs-lookup"><span data-stu-id="d543c-143">This sample is located at <`Samples Path>`\Messaging\ErrorHandling\\.</span></span>  
  
 <span data-ttu-id="d543c-144">下表包含本示例的文件列表。</span><span class="sxs-lookup"><span data-stu-id="d543c-144">The following table contains a list of files for this sample.</span></span>  
  
|<span data-ttu-id="d543c-145">文件</span><span class="sxs-lookup"><span data-stu-id="d543c-145">File</span></span>|<span data-ttu-id="d543c-146">Description</span><span class="sxs-lookup"><span data-stu-id="d543c-146">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="d543c-147">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="d543c-147">Cleanup.bat</span></span>|<span data-ttu-id="d543c-148">用于取消部署程序集并从全局程序集缓存中删除这些程序集。</span><span class="sxs-lookup"><span data-stu-id="d543c-148">Used to undeploy assemblies and remove them from the global assembly cache.</span></span><br /><br /> <span data-ttu-id="d543c-149">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="d543c-149">Removes send and receive ports.</span></span><br /><br /> <span data-ttu-id="d543c-150">根据需要删除 Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="d543c-150">Removes Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="d543c-151">ErrorHandling.sln</span><span class="sxs-lookup"><span data-stu-id="d543c-151">ErrorHandling.sln</span></span>|<span data-ttu-id="d543c-152">本示例的 Visual Studio 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="d543c-152">Visual Studio solution file for the sample.</span></span>|  
|<span data-ttu-id="d543c-153">ErrorHandlingBinding.xml</span><span class="sxs-lookup"><span data-stu-id="d543c-153">ErrorHandlingBinding.xml</span></span>|<span data-ttu-id="d543c-154">本示例的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="d543c-154">Binding file for the sample.</span></span>|  
|<span data-ttu-id="d543c-155">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="d543c-155">Setup.bat</span></span>|<span data-ttu-id="d543c-156">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="d543c-156">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="d543c-157">Expense Report – John Doe.xml</span><span class="sxs-lookup"><span data-stu-id="d543c-157">Expense Report – John Doe.xml</span></span>|<span data-ttu-id="d543c-158">示例费用报告 InfoPath 文档。</span><span class="sxs-lookup"><span data-stu-id="d543c-158">Example expense report InfoPath document.</span></span>|  
|<span data-ttu-id="d543c-159">Invalid Expense Report – John Doe.xml</span><span class="sxs-lookup"><span data-stu-id="d543c-159">Invalid Expense Report – John Doe.xml</span></span>|<span data-ttu-id="d543c-160">示例费用报告 InfoPath 文档，其中包含无效的数据。</span><span class="sxs-lookup"><span data-stu-id="d543c-160">Example expense report InfoPath document with invalid data in it.</span></span>|  
|<span data-ttu-id="d543c-161">在 ErrorHandler 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="d543c-161">In ErrorHandler folder:</span></span><br /><br /> <span data-ttu-id="d543c-162">ErrorHandler.btproj</span><span class="sxs-lookup"><span data-stu-id="d543c-162">ErrorHandler.btproj</span></span>|<span data-ttu-id="d543c-163">业务流程的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="d543c-163">BizTalk project for orchestration.</span></span>|  
|<span data-ttu-id="d543c-164">在 ErrorHandler 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="d543c-164">In ErrorHandler folder:</span></span><br /><br /> <span data-ttu-id="d543c-165">ResubmitLogic.odx</span><span class="sxs-lookup"><span data-stu-id="d543c-165">ResubmitLogic.odx</span></span>|<span data-ttu-id="d543c-166">订阅失败消息，将失败消息发送给接收方人员进行更正，然后将更正后的消息重新提交回服务器进行路由的业务流程。</span><span class="sxs-lookup"><span data-stu-id="d543c-166">Orchestration that subscribes to failed messages, sends them to the human recipient for correction, and then resubmits corrected messages back into the server for routing.</span></span>|  
|<span data-ttu-id="d543c-167">在 ErrorHandler 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="d543c-167">In ErrorHandler folder:</span></span><br /><br /> <span data-ttu-id="d543c-168">SuspendMessage.odx</span><span class="sxs-lookup"><span data-stu-id="d543c-168">SuspendMessage.odx</span></span>|<span data-ttu-id="d543c-169">用于挂起无法在错误处理业务流程中处理的消息的业务流程。</span><span class="sxs-lookup"><span data-stu-id="d543c-169">Orchestration used for suspending messages that cannot be processed within the error-handling orchestration.</span></span>|  
|<span data-ttu-id="d543c-170">在 InfoPathForms 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="d543c-170">In InfoPathForms folder:</span></span><br /><br /> <span data-ttu-id="d543c-171">Expense Report.xsn</span><span class="sxs-lookup"><span data-stu-id="d543c-171">Expense Report.xsn</span></span><br /><br /> <span data-ttu-id="d543c-172">Expense Report - Resubmit.xsn</span><span class="sxs-lookup"><span data-stu-id="d543c-172">Expense Report - Resubmit.xsn</span></span>|<span data-ttu-id="d543c-173">费用报告 InfoPath 表单以及用于查看和重新提交失败消息的表单。</span><span class="sxs-lookup"><span data-stu-id="d543c-173">Expense report InfoPath form and form used for viewing and resubmitting failed messages.</span></span>|  
|<span data-ttu-id="d543c-174">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="d543c-174">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="d543c-175">ExpenseReportSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="d543c-175">ExpenseReportSchema.xsd</span></span>|<span data-ttu-id="d543c-176">费用报告文档的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="d543c-176">XML schema for the expense report document.</span></span>|  
|<span data-ttu-id="d543c-177">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="d543c-177">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="d543c-178">PipelinesAndSchemas.btproj</span><span class="sxs-lookup"><span data-stu-id="d543c-178">PipelinesAndSchemas.btproj</span></span>|<span data-ttu-id="d543c-179">本示例的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="d543c-179">BizTalk project for the sample.</span></span>|  
|<span data-ttu-id="d543c-180">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="d543c-180">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="d543c-181">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="d543c-181">PropertySchema.xsd</span></span>|<span data-ttu-id="d543c-182">本示例的属性架构。</span><span class="sxs-lookup"><span data-stu-id="d543c-182">Property schema for the sample.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="d543c-183">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="d543c-183">How to Use This Sample</span></span>  
 <span data-ttu-id="d543c-184">本示例为创建自己的错误处理过程提供了一个起点。</span><span class="sxs-lookup"><span data-stu-id="d543c-184">This sample provides a starting point for creating your own error handling procedure.</span></span>  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="d543c-185">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="d543c-185">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-compose-sample"></a><span data-ttu-id="d543c-186">生成并初始化 Compose 示例</span><span class="sxs-lookup"><span data-stu-id="d543c-186">To build and initialize the Compose sample</span></span>  
  
1.  <span data-ttu-id="d543c-187">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="d543c-187">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="d543c-188"><`Samples Path`>**\Messaging\ErrorHandling**</span><span class="sxs-lookup"><span data-stu-id="d543c-188"><`Samples Path`>**\Messaging\ErrorHandling**</span></span>  
  
2.  <span data-ttu-id="d543c-189">运行**Setup.bat**，这将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d543c-189">Run **Setup.bat**, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="d543c-190">创建三个文件夹： **ExpenseReportIn**， **ExpenseReportOut**，和**ResubmittedReportIn**以下路径下：</span><span class="sxs-lookup"><span data-stu-id="d543c-190">Creates three folders: **ExpenseReportIn**, **ExpenseReportOut**, and **ResubmittedReportIn** under the following path:</span></span>  
  
         <span data-ttu-id="d543c-191"><`Samples Path`>**\Messaging\ErrorHandling**</span><span class="sxs-lookup"><span data-stu-id="d543c-191"><`Samples Path`>**\Messaging\ErrorHandling**</span></span>  
  
    -   <span data-ttu-id="d543c-192">将复制并发布 InfoPath 窗体**支出 Report.xsn**和**费用报表 – Resubmit.xsn**到文件夹**C:\Temp\InfoPathForms**。</span><span class="sxs-lookup"><span data-stu-id="d543c-192">Copies and publishes the InfoPath forms **Expense Report.xsn** and **Expense Report – Resubmit.xsn** into the folder **C:\Temp\InfoPathForms**.</span></span>  
  
    -   <span data-ttu-id="d543c-193">为本示例编译 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 项目。</span><span class="sxs-lookup"><span data-stu-id="d543c-193">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  
  
    -   <span data-ttu-id="d543c-194">创建一个名为的虚拟目录**ExpenseReports**。</span><span class="sxs-lookup"><span data-stu-id="d543c-194">Creates a virtual directory called **ExpenseReports**.</span></span>  
  
    -   <span data-ttu-id="d543c-195">创建新的 BizTalk 应用程序调用**错误处理示例**，并将部署到其中的示例程序集。</span><span class="sxs-lookup"><span data-stu-id="d543c-195">Creates a new BizTalk application called **Error Handling Sample** and deploys the sample assemblies into it.</span></span>  
  
    -   <span data-ttu-id="d543c-196">创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置以及发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="d543c-196">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive locations, and the send and receive ports.</span></span>  
  
    -   <span data-ttu-id="d543c-197">登记并启动业务流程，启用接收位置，然后启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="d543c-197">Enlists and starts orchestrations, enables the receive locations, and starts the send ports.</span></span>  
  
         <span data-ttu-id="d543c-198">如果选择在不运行 Setup.bat 的情况下打开并生成本示例中的项目，则必须首先使用 .NET Framework 强名称实用工具 (sn.exe) 创建一个强名称密钥对。</span><span class="sxs-lookup"><span data-stu-id="d543c-198">If you choose to open and build the projects in this sample without running Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="d543c-199">使用该密钥对可以对示例程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="d543c-199">Use this key pair to sign the sample assemblies.</span></span>  
  
3.  <span data-ttu-id="d543c-200">在尝试运行本示例之前，请确认在生成或初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="d543c-200">Before attempting to run this sample, confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build or initialization process.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d543c-201">若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="d543c-201">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="d543c-202">在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。</span><span class="sxs-lookup"><span data-stu-id="d543c-202">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
4.  <span data-ttu-id="d543c-203">如果使用的是 Internet Information Services (IIS) 7.0，则需要执行其他配置步骤，从而调整与本示例使用的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 接收位置对应的虚拟目录设置。</span><span class="sxs-lookup"><span data-stu-id="d543c-203">If you are using Internet Information Services (IIS) 7.0, you need to perform additional configuration steps to adjust the setting for the virtual directory that corresponds to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP receive location used by the sample.</span></span> <span data-ttu-id="d543c-204">通过执行以下操作配置 IIS：</span><span class="sxs-lookup"><span data-stu-id="d543c-204">Configure IIS by doing the following:</span></span>  
  
    1.  <span data-ttu-id="d543c-205">使用 IIS 7.0 管理器为 BizTalk Isolated Host Users 组创建新的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="d543c-205">Using IIS 7.0 Manager, create a new application pool for the BizTalk Isolated Host Users group.</span></span>  
  
    2.  <span data-ttu-id="d543c-206">将应用程序池配置为以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 独立主机用户的身份运行。</span><span class="sxs-lookup"><span data-stu-id="d543c-206">Configure the application pool to run under the identity of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Isolated Host user.</span></span> <span data-ttu-id="d543c-207">（如果你已为其他 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 接收位置配置应用程序池，则可以跳过此步骤。）</span><span class="sxs-lookup"><span data-stu-id="d543c-207">(You may skip this step if you already have an application pool configured for other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP receive locations.)</span></span>  
  
    3.  <span data-ttu-id="d543c-208">配置虚拟目录**ExpenseReport**为了使用 HTTP 接收在上一步中创建的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="d543c-208">Configure the virtual directory **ExpenseReport** to use the HTTP receive application pool created in the previous step.</span></span>  
  
     <span data-ttu-id="d543c-209">如果 BTSHTTPReceive.dll ISAPI 扩展尚不具有 Web 服务器扩展，则可通过将其状态设置为“允许”创建和启用该扩展。</span><span class="sxs-lookup"><span data-stu-id="d543c-209">If you do not already have a Web server extension for the BTSHTTPReceive.dll ISAPI extension, create and enable it by setting its status to "Allowed".</span></span> <span data-ttu-id="d543c-210">你可以在 IIS 7.0 中通过使用 IIS 管理控制台 (要么直接下**管理工具**，或者通过计算机管理控制台)，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d543c-210">You can do this in IIS 7.0 by using the IIS Management console (either directly under **Administrative Tools** or through the Computer Management console) as follows:</span></span>  
  
    1.  <span data-ttu-id="d543c-211">展开**Internet Information Services Manager**树。</span><span class="sxs-lookup"><span data-stu-id="d543c-211">Expand the **Internet Information Services Manager** tree.</span></span>  
  
    2.  <span data-ttu-id="d543c-212">单击**Web 服务扩展**文件夹。</span><span class="sxs-lookup"><span data-stu-id="d543c-212">Click the **Web Service Extensions** folder.</span></span>  
  
    3.  <span data-ttu-id="d543c-213">在管理控制台的右窗格中，单击**添加一个新的 Web 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="d543c-213">In the right pane of the management console, click **Add a new Web Service extension**.</span></span>  
  
    4.  <span data-ttu-id="d543c-214">在**新建 Web 服务扩展**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="d543c-214">In the **New Web Service Extension** dialog box, click **Add**.</span></span>  
  
    5.  <span data-ttu-id="d543c-215">在**Add file**对话框中，单击**浏览**选择的文件 <`BizTalkInstallPath>`**\HttpReceive\BTSHTTPReceive.dll**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="d543c-215">In the **Add file** dialog box, click **Browse** to select the file <`BizTalkInstallPath>`**\HttpReceive\BTSHTTPReceive.dll**, and then click **OK**.</span></span>  
  
    6.  <span data-ttu-id="d543c-216">配置虚拟目录**ExpenseReport**使用本地路径[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HTTPReceive</span><span class="sxs-lookup"><span data-stu-id="d543c-216">Configure the virtual directory **ExpenseReport** to use local path [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HTTPReceive</span></span>  
  
     <span data-ttu-id="d543c-217">有关详细信息，请参阅[如何将 IIS 配置的 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="d543c-217">For more information, see [How to Configure IIS for an HTTP Receive Location](../core/how-to-configure-iis-for-an-http-receive-location.md).</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="d543c-218">运行示例</span><span class="sxs-lookup"><span data-stu-id="d543c-218">Running the Sample</span></span>  
 <span data-ttu-id="d543c-219">在降本示例与正确的费用报告一起运行之前，请使用以下过程验证“无错误”情况下的示例是否正常运行。</span><span class="sxs-lookup"><span data-stu-id="d543c-219">Before running the sample with the correct expense report, use the following procedure to verify that the "no errors" case sample works correctly.</span></span>  
  
#### <a name="to-verify-that-the-no-errors-case-sample-works-correctly"></a><span data-ttu-id="d543c-220">验证“无错误”情况下的示例是否正常运行</span><span class="sxs-lookup"><span data-stu-id="d543c-220">To verify that the "no errors" case sample works correctly</span></span>  
  
1.  <span data-ttu-id="d543c-221">打开的 InfoPath 窗体**费用报表-John Doe.xml**。</span><span class="sxs-lookup"><span data-stu-id="d543c-221">Open the InfoPath form **Expense Report - John Doe.xml**.</span></span> <span data-ttu-id="d543c-222">查看**部门**字段在窗体。</span><span class="sxs-lookup"><span data-stu-id="d543c-222">Look at the **Department** field within the form.</span></span> <span data-ttu-id="d543c-223">此字段应设置为“Marketing”。</span><span class="sxs-lookup"><span data-stu-id="d543c-223">This field should be set to "Marketing".</span></span>  
  
2.  <span data-ttu-id="d543c-224">在的 InfoPath 窗口的左上角，单击**提交**或单击**重新提交费用报表**。</span><span class="sxs-lookup"><span data-stu-id="d543c-224">In the upper-left corner of the InfoPath window, click **Submit** or click **Resubmit Expense Report**.</span></span> <span data-ttu-id="d543c-225">等待出现确认窗口，指示已成功提交费用报告。</span><span class="sxs-lookup"><span data-stu-id="d543c-225">Wait for a confirmation window that says the expense report was successfully submitted.</span></span>  
  
     <span data-ttu-id="d543c-226">-或者-</span><span class="sxs-lookup"><span data-stu-id="d543c-226">-OR-</span></span>  
  
     <span data-ttu-id="d543c-227">复制并粘贴到此文件**ExpenseReportIn**文件夹。</span><span class="sxs-lookup"><span data-stu-id="d543c-227">Copy and paste this file into the **ExpenseReportIn** folder.</span></span>  
  
3.  <span data-ttu-id="d543c-228">你应看到新的文件中放入**ExpenseReportOut**文件夹。</span><span class="sxs-lookup"><span data-stu-id="d543c-228">You should see a new file dropped into the **ExpenseReportOut** folder.</span></span> <span data-ttu-id="d543c-229">此文件即为上述步骤中提交的费用报告表单。</span><span class="sxs-lookup"><span data-stu-id="d543c-229">This file is the same expense report form that was submitted during previous steps.</span></span>  
  
 <span data-ttu-id="d543c-230">在确认“无错误”的情况后，使用以下过程将本示例与不正确的费用报告一起运行，从而触发错误处理功能。</span><span class="sxs-lookup"><span data-stu-id="d543c-230">After you confirm the "no errors" case, use the following procedure to run the sample with an incorrect expense report to trigger error-handling functionality.</span></span>  
  
#### <a name="to-trigger-error-handling"></a><span data-ttu-id="d543c-231">触发错误处理</span><span class="sxs-lookup"><span data-stu-id="d543c-231">To trigger error handling</span></span>  
  
1.  <span data-ttu-id="d543c-232">打开的 InfoPath 窗体**无效费用报表-John Doe.xml**。</span><span class="sxs-lookup"><span data-stu-id="d543c-232">Open the InfoPath form **Invalid Expense Report - John Doe.xml**.</span></span> <span data-ttu-id="d543c-233">查看**部门**字段在窗体。</span><span class="sxs-lookup"><span data-stu-id="d543c-233">Look at the **Department** field within the form.</span></span> <span data-ttu-id="d543c-234">此字段设置为某个无效的值。</span><span class="sxs-lookup"><span data-stu-id="d543c-234">This field is set to some invalid value.</span></span>  
  
2.  <span data-ttu-id="d543c-235">在的 InfoPath 窗口的左上角，单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="d543c-235">In the upper-left corner of the InfoPath window, click **Submit**.</span></span> <span data-ttu-id="d543c-236">等待出现确认窗口，指示已成功提交费用报告。</span><span class="sxs-lookup"><span data-stu-id="d543c-236">Wait for a confirmation window that says the expense report was successfully submitted.</span></span>  
  
     <span data-ttu-id="d543c-237">-或者-</span><span class="sxs-lookup"><span data-stu-id="d543c-237">-OR-</span></span>  
  
     <span data-ttu-id="d543c-238">复制并粘贴到此文件**ExpenseReportIn**文件夹。</span><span class="sxs-lookup"><span data-stu-id="d543c-238">Copy and paste this file into the **ExpenseReportIn** folder.</span></span>  
  
3.  <span data-ttu-id="d543c-239">你应看到名的新文件**ErrorReport_\<***日期*_*时间***\>.xml**中放入**ExpenseReportOut**文件夹。</span><span class="sxs-lookup"><span data-stu-id="d543c-239">You should see a new file called **ErrorReport_\<***date*_*time***\>.xml** dropped into the **ExpenseReportOut** folder.</span></span>  
  
     <span data-ttu-id="d543c-240">打开此文件，然后会观察到这是在前面步骤中提交的费用报告，但在开头添加了错误信息。</span><span class="sxs-lookup"><span data-stu-id="d543c-240">Open this file and observe that this is the expense report submitted in the previous step but with the error information added at the beginning.</span></span>  
  
4.  <span data-ttu-id="d543c-241">将错误部门值替换为"Marketing"，然后单击**提交**的 InfoPath 窗口的左上角。</span><span class="sxs-lookup"><span data-stu-id="d543c-241">Replace the erroneous department value with "Marketing", and then click **Submit** in the upper-left corner of the InfoPath window.</span></span>  
  
     <span data-ttu-id="d543c-242">-或者-</span><span class="sxs-lookup"><span data-stu-id="d543c-242">-OR-</span></span>  
  
     <span data-ttu-id="d543c-243">复制并粘贴到此文件**ResubmittedReportIn**文件夹。</span><span class="sxs-lookup"><span data-stu-id="d543c-243">Copy and paste this file into the **ResubmittedReportIn** folder.</span></span>  
  
5.  <span data-ttu-id="d543c-244">你应看到在中创建的新文件**ExpenseReportOut**文件夹。</span><span class="sxs-lookup"><span data-stu-id="d543c-244">You should see a new file created in the **ExpenseReportOut** folder.</span></span> <span data-ttu-id="d543c-245">此文件即为重新提交到服务器的更正后的费用报告。</span><span class="sxs-lookup"><span data-stu-id="d543c-245">This file is the corrected expense report that was resubmitted into the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d543c-246">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d543c-246">See Also</span></span>  
 <span data-ttu-id="d543c-247">[使用失败的邮件路由](../core/using-failed-message-routing.md) </span><span class="sxs-lookup"><span data-stu-id="d543c-247">[Using Failed Message Routing](../core/using-failed-message-routing.md) </span></span>  
 [<span data-ttu-id="d543c-248">消息传送（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="d543c-248">Messaging (BizTalk Server Samples Folder)</span></span>](../core/messaging-biztalk-server-samples-folder.md)