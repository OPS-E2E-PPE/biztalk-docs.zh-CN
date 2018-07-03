---
title: 错误处理 （BizTalk Server 示例文件夹） |Microsoft Docs
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
ms.openlocfilehash: 4e5df828fc8227030a2837bfdfe0aebff5b6f1d2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997702"
---
# <a name="error-handling-biztalk-server-samples-folder"></a><span data-ttu-id="0ca57-102">错误处理（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="0ca57-102">Error Handling (BizTalk Server Samples Folder)</span></span>
<span data-ttu-id="0ca57-103">本示例的目的是为基于内容的路由 (CBR) 应用程序生成错误处理功能。</span><span class="sxs-lookup"><span data-stu-id="0ca57-103">The purpose of this sample is to build an error-handling functionality for the content-based routing (CBR) application.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="0ca57-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="0ca57-104">Prerequisites</span></span>  
 <span data-ttu-id="0ca57-105">若要运行本示例，建议你安装 Microsoft Office InfoPath 2010 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="0ca57-105">To run the sample, it is recommended that you have Microsoft Office InfoPath 2010 or later installed.</span></span> <span data-ttu-id="0ca57-106">你可以在不使用 InfoPath 的情况下运行本示例，但在这种情况下，你无法通过 HTTP 适配器查看费用报告以及费用报告的提交。</span><span class="sxs-lookup"><span data-stu-id="0ca57-106">You can run the sample without using InfoPath, but in that case you cannot see the expense reports and the submission of expense reports through the HTTP adapter.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="0ca57-107">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="0ca57-107">What This Sample Does</span></span>  
 <span data-ttu-id="0ca57-108">本示例可实现费用报告处理系统部分。</span><span class="sxs-lookup"><span data-stu-id="0ca57-108">The sample implements part of an expense report processing system.</span></span> <span data-ttu-id="0ca57-109">具体而言，本示例执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="0ca57-109">Specifically, this sample does the following:</span></span>  

1. <span data-ttu-id="0ca57-110">定义费用报告架构，该架构包含有关费用报告和单个提交者（包括部门名称）的信息。</span><span class="sxs-lookup"><span data-stu-id="0ca57-110">Defines an expense report schema containing information about an expense report and the individual submitter including department name.</span></span>  

2. <span data-ttu-id="0ca57-111">使用 InfoPath 通过目录或 Web Services 提供费用报告的提交。</span><span class="sxs-lookup"><span data-stu-id="0ca57-111">Provides for the submission of the expense report through a directory or through a Web service using InfoPath.</span></span>  

3. <span data-ttu-id="0ca57-112">促进**部门**并**correlationID**消息中的属性记录，以便它可用于在端口筛选器中控制路由。</span><span class="sxs-lookup"><span data-stu-id="0ca57-112">Promotes the **Department** and **correlationID** properties in the message document so that it can be used in a port filter to control routing.</span></span>  

4. <span data-ttu-id="0ca57-113">将属于 Marketing 部门的费用报告路由到目录中的某个文件，从而模拟送达该部门的后端系统。</span><span class="sxs-lookup"><span data-stu-id="0ca57-113">Routes expense reports belonging to the Marketing department to a file in a directory, simulating delivery to the department's back-end system.</span></span>  

5. <span data-ttu-id="0ca57-114">对属于 Marketing 之外的部门的费用报告生成失败消息。</span><span class="sxs-lookup"><span data-stu-id="0ca57-114">Generates a failed message for expense reports belonging to departments other than Marketing.</span></span> <span data-ttu-id="0ca57-115">失败消息包括有关错误（包括错误代码和错误说明）的信息。</span><span class="sxs-lookup"><span data-stu-id="0ca57-115">The failed message includes information about the error including error code and error description.</span></span>  

6. <span data-ttu-id="0ca57-116">将失败消息路由给接收方人员（业务用户或应用程序操作员）以进行更正和重新提交。</span><span class="sxs-lookup"><span data-stu-id="0ca57-116">Routes failed messages to a human recipient (a business user or application operator) for correction and resubmission.</span></span>  

7. <span data-ttu-id="0ca57-117">如上所述，根据部门路由重新提交的费用报告。</span><span class="sxs-lookup"><span data-stu-id="0ca57-117">Routes resubmitted expense reports based on department as described above.</span></span>  

   <span data-ttu-id="0ca57-118">大部分工作都是通过 BizTalk 业务流程调度完成的。</span><span class="sxs-lookup"><span data-stu-id="0ca57-118">Much of this work is done through a BizTalk orchestration schedule.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="0ca57-119">此示例设计方式和原因</span><span class="sxs-lookup"><span data-stu-id="0ca57-119">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="0ca57-120">设计依赖 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的默认发送和接收 XML 管道、属性升级、订阅筛选器和业务流程调度来路由消息。</span><span class="sxs-lookup"><span data-stu-id="0ca57-120">The design relies on the default send and receive XML pipelines, property promotion, subscription filters, and orchestration schedules within [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to route messages.</span></span> <span data-ttu-id="0ca57-121">下表列出了设计元素及其选入理由。</span><span class="sxs-lookup"><span data-stu-id="0ca57-121">Design elements and their justification are listed in the following table.</span></span>  


|         <span data-ttu-id="0ca57-122">设计元素</span><span class="sxs-lookup"><span data-stu-id="0ca57-122">Design element</span></span>         |                                                                                                                                                                 <span data-ttu-id="0ca57-123">选择的原因</span><span class="sxs-lookup"><span data-stu-id="0ca57-123">Reason(s) selected</span></span>                                                                                                                                                                 |
|--------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0ca57-124">默认 XML 接收管道</span><span class="sxs-lookup"><span data-stu-id="0ca57-124">Default XML receive pipeline</span></span>  |                                                        <span data-ttu-id="0ca57-125">XMLReceive 管道支持属性升级;PassThruReceive 管道却没有。</span><span class="sxs-lookup"><span data-stu-id="0ca57-125">-   The XMLReceive pipeline supports property promotion; the PassThruReceive pipeline does not.</span></span><br /><span data-ttu-id="0ca57-126">-入站的消息已采用 XML 格式，并且不需要除基本拆装和参与方解析之外的处理。</span><span class="sxs-lookup"><span data-stu-id="0ca57-126">-   The inbound message is already in XML format and does not require processing beyond basic disassembly and party resolution.</span></span>                                                        |
|  <span data-ttu-id="0ca57-127">针对失败消息的路由</span><span class="sxs-lookup"><span data-stu-id="0ca57-127">Routing for failed messages</span></span>   | <span data-ttu-id="0ca57-128">-接收端口挂起失败的消息并将默认情况下生成一个否定确认。</span><span class="sxs-lookup"><span data-stu-id="0ca57-128">-   Receive ports suspend failed messages and generate a negative acknowledgment by default.</span></span> <span data-ttu-id="0ca57-129">启用路由后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会尝试将处理失败的所有消息路由到某个订阅应用程序（例如另一个接收端口或业务流程调度）。</span><span class="sxs-lookup"><span data-stu-id="0ca57-129">When routing is enabled [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] attempts to route any message that fails processing to a subscribing application (such as another receive port or orchestration schedule).</span></span> |
|       <span data-ttu-id="0ca57-130">属性升级</span><span class="sxs-lookup"><span data-stu-id="0ca57-130">Property promotion</span></span>       |                                                                                                   <span data-ttu-id="0ca57-131">BizTalk Server 根据属性字段进行路由。</span><span class="sxs-lookup"><span data-stu-id="0ca57-131">-   BizTalk Server depends upon property fields to do routing.</span></span> <span data-ttu-id="0ca57-132">业务流程使用可分辨字段，并且该字段不能用于路由。</span><span class="sxs-lookup"><span data-stu-id="0ca57-132">Distinguished fields are used by orchestrations and cannot be used for routing.</span></span>                                                                                                   |
|      <span data-ttu-id="0ca57-133">订阅筛选器</span><span class="sxs-lookup"><span data-stu-id="0ca57-133">Subscription filter</span></span>       |                                                                                                          <span data-ttu-id="0ca57-134">-订阅筛选器来执行路由捕获满足一个或多个基于属性的字段的条件的消息。</span><span class="sxs-lookup"><span data-stu-id="0ca57-134">-   The subscription filter performs the routing by capturing messages that meet one or more criteria based on property fields.</span></span>                                                                                                           |
| <span data-ttu-id="0ca57-135">BizTalk 业务流程调度</span><span class="sxs-lookup"><span data-stu-id="0ca57-135">BizTalk orchestration schedule</span></span> |                                                                  <span data-ttu-id="0ca57-136">-提供了将信息添加到失败的消息的机会。</span><span class="sxs-lookup"><span data-stu-id="0ca57-136">-   Provides the opportunity to add information to failed messages.</span></span><br /><span data-ttu-id="0ca57-137">-启用失败消息路由到的人为干预的专用位置。</span><span class="sxs-lookup"><span data-stu-id="0ca57-137">-   Enables routing of failed messages to a dedicated location for human intervention.</span></span><br /><span data-ttu-id="0ca57-138">-进程重新提交费用报告。</span><span class="sxs-lookup"><span data-stu-id="0ca57-138">-   Processes resubmitted expense reports.</span></span>                                                                   |
|          <span data-ttu-id="0ca57-139">XMLTransmit</span><span class="sxs-lookup"><span data-stu-id="0ca57-139">XMLTransmit</span></span>           |                                                                                                                <span data-ttu-id="0ca57-140">-执行基本组装传出 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="0ca57-140">-   Performs basic assembly of outgoing XML messages.</span></span> <span data-ttu-id="0ca57-141">PassThruTransmit 管道不提供其他支持。</span><span class="sxs-lookup"><span data-stu-id="0ca57-141">The PassThruTransmit pipeline provides no additional support.</span></span>                                                                                                                 |

## <a name="where-to-find-this-sample"></a><span data-ttu-id="0ca57-142">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="0ca57-142">Where to Find This Sample</span></span>  
 <span data-ttu-id="0ca57-143">此示例位于 <`Samples Path>`\Messaging\ErrorHandling\\。</span><span class="sxs-lookup"><span data-stu-id="0ca57-143">This sample is located at <`Samples Path>`\Messaging\ErrorHandling\\.</span></span>  

 <span data-ttu-id="0ca57-144">下表包含本示例的文件列表。</span><span class="sxs-lookup"><span data-stu-id="0ca57-144">The following table contains a list of files for this sample.</span></span>  

|<span data-ttu-id="0ca57-145">文件</span><span class="sxs-lookup"><span data-stu-id="0ca57-145">File</span></span>|<span data-ttu-id="0ca57-146">Description</span><span class="sxs-lookup"><span data-stu-id="0ca57-146">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="0ca57-147">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="0ca57-147">Cleanup.bat</span></span>|<span data-ttu-id="0ca57-148">用于取消部署程序集并从全局程序集缓存中删除这些程序集。</span><span class="sxs-lookup"><span data-stu-id="0ca57-148">Used to undeploy assemblies and remove them from the global assembly cache.</span></span><br /><br /> <span data-ttu-id="0ca57-149">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="0ca57-149">Removes send and receive ports.</span></span><br /><br /> <span data-ttu-id="0ca57-150">根据需要删除 Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="0ca57-150">Removes Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="0ca57-151">ErrorHandling.sln</span><span class="sxs-lookup"><span data-stu-id="0ca57-151">ErrorHandling.sln</span></span>|<span data-ttu-id="0ca57-152">本示例的 Visual Studio 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="0ca57-152">Visual Studio solution file for the sample.</span></span>|  
|<span data-ttu-id="0ca57-153">ErrorHandlingBinding.xml</span><span class="sxs-lookup"><span data-stu-id="0ca57-153">ErrorHandlingBinding.xml</span></span>|<span data-ttu-id="0ca57-154">本示例的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="0ca57-154">Binding file for the sample.</span></span>|  
|<span data-ttu-id="0ca57-155">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="0ca57-155">Setup.bat</span></span>|<span data-ttu-id="0ca57-156">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="0ca57-156">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="0ca57-157">Expense Report – John Doe.xml</span><span class="sxs-lookup"><span data-stu-id="0ca57-157">Expense Report – John Doe.xml</span></span>|<span data-ttu-id="0ca57-158">示例费用报告 InfoPath 文档。</span><span class="sxs-lookup"><span data-stu-id="0ca57-158">Example expense report InfoPath document.</span></span>|  
|<span data-ttu-id="0ca57-159">Invalid Expense Report – John Doe.xml</span><span class="sxs-lookup"><span data-stu-id="0ca57-159">Invalid Expense Report – John Doe.xml</span></span>|<span data-ttu-id="0ca57-160">示例费用报告 InfoPath 文档，其中包含无效的数据。</span><span class="sxs-lookup"><span data-stu-id="0ca57-160">Example expense report InfoPath document with invalid data in it.</span></span>|  
|<span data-ttu-id="0ca57-161">在 ErrorHandler 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="0ca57-161">In ErrorHandler folder:</span></span><br /><br /> <span data-ttu-id="0ca57-162">ErrorHandler.btproj</span><span class="sxs-lookup"><span data-stu-id="0ca57-162">ErrorHandler.btproj</span></span>|<span data-ttu-id="0ca57-163">业务流程的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="0ca57-163">BizTalk project for orchestration.</span></span>|  
|<span data-ttu-id="0ca57-164">在 ErrorHandler 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="0ca57-164">In ErrorHandler folder:</span></span><br /><br /> <span data-ttu-id="0ca57-165">ResubmitLogic.odx</span><span class="sxs-lookup"><span data-stu-id="0ca57-165">ResubmitLogic.odx</span></span>|<span data-ttu-id="0ca57-166">订阅失败消息，将失败消息发送给接收方人员进行更正，然后将更正后的消息重新提交回服务器进行路由的业务流程。</span><span class="sxs-lookup"><span data-stu-id="0ca57-166">Orchestration that subscribes to failed messages, sends them to the human recipient for correction, and then resubmits corrected messages back into the server for routing.</span></span>|  
|<span data-ttu-id="0ca57-167">在 ErrorHandler 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="0ca57-167">In ErrorHandler folder:</span></span><br /><br /> <span data-ttu-id="0ca57-168">SuspendMessage.odx</span><span class="sxs-lookup"><span data-stu-id="0ca57-168">SuspendMessage.odx</span></span>|<span data-ttu-id="0ca57-169">用于挂起无法在错误处理业务流程中处理的消息的业务流程。</span><span class="sxs-lookup"><span data-stu-id="0ca57-169">Orchestration used for suspending messages that cannot be processed within the error-handling orchestration.</span></span>|  
|<span data-ttu-id="0ca57-170">在 InfoPathForms 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="0ca57-170">In InfoPathForms folder:</span></span><br /><br /> <span data-ttu-id="0ca57-171">Expense Report.xsn</span><span class="sxs-lookup"><span data-stu-id="0ca57-171">Expense Report.xsn</span></span><br /><br /> <span data-ttu-id="0ca57-172">Expense Report - Resubmit.xsn</span><span class="sxs-lookup"><span data-stu-id="0ca57-172">Expense Report - Resubmit.xsn</span></span>|<span data-ttu-id="0ca57-173">费用报告 InfoPath 表单以及用于查看和重新提交失败消息的表单。</span><span class="sxs-lookup"><span data-stu-id="0ca57-173">Expense report InfoPath form and form used for viewing and resubmitting failed messages.</span></span>|  
|<span data-ttu-id="0ca57-174">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="0ca57-174">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="0ca57-175">ExpenseReportSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="0ca57-175">ExpenseReportSchema.xsd</span></span>|<span data-ttu-id="0ca57-176">费用报告文档的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="0ca57-176">XML schema for the expense report document.</span></span>|  
|<span data-ttu-id="0ca57-177">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="0ca57-177">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="0ca57-178">PipelinesAndSchemas.btproj</span><span class="sxs-lookup"><span data-stu-id="0ca57-178">PipelinesAndSchemas.btproj</span></span>|<span data-ttu-id="0ca57-179">本示例的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="0ca57-179">BizTalk project for the sample.</span></span>|  
|<span data-ttu-id="0ca57-180">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="0ca57-180">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="0ca57-181">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="0ca57-181">PropertySchema.xsd</span></span>|<span data-ttu-id="0ca57-182">本示例的属性架构。</span><span class="sxs-lookup"><span data-stu-id="0ca57-182">Property schema for the sample.</span></span>|  

## <a name="how-to-use-this-sample"></a><span data-ttu-id="0ca57-183">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="0ca57-183">How to Use This Sample</span></span>  
 <span data-ttu-id="0ca57-184">本示例为创建自己的错误处理过程提供了一个起点。</span><span class="sxs-lookup"><span data-stu-id="0ca57-184">This sample provides a starting point for creating your own error handling procedure.</span></span>  

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="0ca57-185">生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="0ca57-185">Building and Initializing This Sample</span></span>  

#### <a name="to-build-and-initialize-the-compose-sample"></a><span data-ttu-id="0ca57-186">生成并初始化 Compose 示例</span><span class="sxs-lookup"><span data-stu-id="0ca57-186">To build and initialize the Compose sample</span></span>  

1. <span data-ttu-id="0ca57-187">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="0ca57-187">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="0ca57-188"><`Samples Path`>**\Messaging\ErrorHandling**</span><span class="sxs-lookup"><span data-stu-id="0ca57-188"><`Samples Path`>**\Messaging\ErrorHandling**</span></span>  

2. <span data-ttu-id="0ca57-189">运行**Setup.bat**，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0ca57-189">Run **Setup.bat**, which performs the following actions:</span></span>  

   - <span data-ttu-id="0ca57-190">创建三个文件夹： **ExpenseReportIn**， **ExpenseReportOut**，并**ResubmittedReportIn**以下路径下：</span><span class="sxs-lookup"><span data-stu-id="0ca57-190">Creates three folders: **ExpenseReportIn**, **ExpenseReportOut**, and **ResubmittedReportIn** under the following path:</span></span>  

      <span data-ttu-id="0ca57-191"><`Samples Path`>**\Messaging\ErrorHandling**</span><span class="sxs-lookup"><span data-stu-id="0ca57-191"><`Samples Path`>**\Messaging\ErrorHandling**</span></span>  

   - <span data-ttu-id="0ca57-192">复制并发布 InfoPath 窗体**Expense Report.xsn**并**Expense Report – Resubmit.xsn**到文件夹**C:\Temp\InfoPathForms**。</span><span class="sxs-lookup"><span data-stu-id="0ca57-192">Copies and publishes the InfoPath forms **Expense Report.xsn** and **Expense Report – Resubmit.xsn** into the folder **C:\Temp\InfoPathForms**.</span></span>  

   - <span data-ttu-id="0ca57-193">为本示例编译 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 项目。</span><span class="sxs-lookup"><span data-stu-id="0ca57-193">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  

   - <span data-ttu-id="0ca57-194">创建一个名为的虚拟目录**为 ExpenseReports**。</span><span class="sxs-lookup"><span data-stu-id="0ca57-194">Creates a virtual directory called **ExpenseReports**.</span></span>  

   - <span data-ttu-id="0ca57-195">创建新的 BizTalk 应用程序调用**Error Handling Sample**并部署到其中的示例程序集。</span><span class="sxs-lookup"><span data-stu-id="0ca57-195">Creates a new BizTalk application called **Error Handling Sample** and deploys the sample assemblies into it.</span></span>  

   - <span data-ttu-id="0ca57-196">创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置以及发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="0ca57-196">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive locations, and the send and receive ports.</span></span>  

   - <span data-ttu-id="0ca57-197">登记并启动业务流程，启用接收位置，然后启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="0ca57-197">Enlists and starts orchestrations, enables the receive locations, and starts the send ports.</span></span>  

      <span data-ttu-id="0ca57-198">如果选择在不运行 Setup.bat 的情况下打开并生成本示例中的项目，则必须首先使用 .NET Framework 强名称实用工具 (sn.exe) 创建一个强名称密钥对。</span><span class="sxs-lookup"><span data-stu-id="0ca57-198">If you choose to open and build the projects in this sample without running Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="0ca57-199">使用该密钥对可以对示例程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="0ca57-199">Use this key pair to sign the sample assemblies.</span></span>  

3. <span data-ttu-id="0ca57-200">在尝试运行本示例之前，请确认在生成或初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="0ca57-200">Before attempting to run this sample, confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build or initialization process.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="0ca57-201">若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="0ca57-201">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="0ca57-202">必须运行 Setup.bat 前运行 Cleanup.bat 时间。</span><span class="sxs-lookup"><span data-stu-id="0ca57-202">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

4. <span data-ttu-id="0ca57-203">如果使用的是 Internet Information Services (IIS) 7.0，则需要执行其他配置步骤，从而调整与本示例使用的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 接收位置对应的虚拟目录设置。</span><span class="sxs-lookup"><span data-stu-id="0ca57-203">If you are using Internet Information Services (IIS) 7.0, you need to perform additional configuration steps to adjust the setting for the virtual directory that corresponds to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP receive location used by the sample.</span></span> <span data-ttu-id="0ca57-204">通过执行以下操作配置 IIS：</span><span class="sxs-lookup"><span data-stu-id="0ca57-204">Configure IIS by doing the following:</span></span>  

   1. <span data-ttu-id="0ca57-205">使用 IIS 7.0 管理器为 BizTalk Isolated Host Users 组创建新的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="0ca57-205">Using IIS 7.0 Manager, create a new application pool for the BizTalk Isolated Host Users group.</span></span>  

   2. <span data-ttu-id="0ca57-206">将应用程序池配置为以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 独立主机用户的身份运行。</span><span class="sxs-lookup"><span data-stu-id="0ca57-206">Configure the application pool to run under the identity of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Isolated Host user.</span></span> <span data-ttu-id="0ca57-207">（如果你已为其他 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 接收位置配置应用程序池，则可以跳过此步骤。）</span><span class="sxs-lookup"><span data-stu-id="0ca57-207">(You may skip this step if you already have an application pool configured for other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP receive locations.)</span></span>  

   3. <span data-ttu-id="0ca57-208">配置虚拟目录**ExpenseReport**使用 HTTP 接收在上一步中创建的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="0ca57-208">Configure the virtual directory **ExpenseReport** to use the HTTP receive application pool created in the previous step.</span></span>  

      <span data-ttu-id="0ca57-209">如果 BTSHTTPReceive.dll ISAPI 扩展尚不具有 Web 服务器扩展，则可通过将其状态设置为“允许”创建和启用该扩展。</span><span class="sxs-lookup"><span data-stu-id="0ca57-209">If you do not already have a Web server extension for the BTSHTTPReceive.dll ISAPI extension, create and enable it by setting its status to "Allowed".</span></span> <span data-ttu-id="0ca57-210">你可以在 IIS 7.0 中使用 IIS 管理控制台 (要么直接下**管理工具**或通过计算机管理控制台)，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0ca57-210">You can do this in IIS 7.0 by using the IIS Management console (either directly under **Administrative Tools** or through the Computer Management console) as follows:</span></span>  

   4. <span data-ttu-id="0ca57-211">展开**Internet Information Services Manager**树。</span><span class="sxs-lookup"><span data-stu-id="0ca57-211">Expand the **Internet Information Services Manager** tree.</span></span>  

   5. <span data-ttu-id="0ca57-212">单击**Web 服务扩展**文件夹。</span><span class="sxs-lookup"><span data-stu-id="0ca57-212">Click the **Web Service Extensions** folder.</span></span>  

   6. <span data-ttu-id="0ca57-213">在管理控制台的右窗格中，单击**添加一个新的 Web 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="0ca57-213">In the right pane of the management console, click **Add a new Web Service extension**.</span></span>  

   7. <span data-ttu-id="0ca57-214">在中**新的 Web 服务扩展**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="0ca57-214">In the **New Web Service Extension** dialog box, click **Add**.</span></span>  

   8. <span data-ttu-id="0ca57-215">在**添加文件**对话框中，单击**浏览**若要选择的文件 <`BizTalkInstallPath>`**\HttpReceive\BTSHTTPReceive.dll**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="0ca57-215">In the **Add file** dialog box, click **Browse** to select the file <`BizTalkInstallPath>`**\HttpReceive\BTSHTTPReceive.dll**, and then click **OK**.</span></span>  

   9. <span data-ttu-id="0ca57-216">配置虚拟目录**ExpenseReport**以使用本地路径[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HTTPReceive</span><span class="sxs-lookup"><span data-stu-id="0ca57-216">Configure the virtual directory **ExpenseReport** to use local path [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HTTPReceive</span></span>  

      <span data-ttu-id="0ca57-217">有关详细信息，请参阅[如何配置 IIS 以实现 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="0ca57-217">For more information, see [How to Configure IIS for an HTTP Receive Location](../core/how-to-configure-iis-for-an-http-receive-location.md).</span></span>  

## <a name="running-the-sample"></a><span data-ttu-id="0ca57-218">运行示例</span><span class="sxs-lookup"><span data-stu-id="0ca57-218">Running the Sample</span></span>  
 <span data-ttu-id="0ca57-219">在降本示例与正确的费用报告一起运行之前，请使用以下过程验证“无错误”情况下的示例是否正常运行。</span><span class="sxs-lookup"><span data-stu-id="0ca57-219">Before running the sample with the correct expense report, use the following procedure to verify that the "no errors" case sample works correctly.</span></span>  

#### <a name="to-verify-that-the-no-errors-case-sample-works-correctly"></a><span data-ttu-id="0ca57-220">验证“无错误”情况下的示例是否正常运行</span><span class="sxs-lookup"><span data-stu-id="0ca57-220">To verify that the "no errors" case sample works correctly</span></span>  

1. <span data-ttu-id="0ca57-221">打开 InfoPath 表单**Expense Report-John Doe.xml**。</span><span class="sxs-lookup"><span data-stu-id="0ca57-221">Open the InfoPath form **Expense Report - John Doe.xml**.</span></span> <span data-ttu-id="0ca57-222">看看**部门**字段在窗体中。</span><span class="sxs-lookup"><span data-stu-id="0ca57-222">Look at the **Department** field within the form.</span></span> <span data-ttu-id="0ca57-223">此字段应设置为“Marketing”。</span><span class="sxs-lookup"><span data-stu-id="0ca57-223">This field should be set to "Marketing".</span></span>  

2. <span data-ttu-id="0ca57-224">在 InfoPath 窗口的左上角，单击**提交**或单击**重新提交费用报告**。</span><span class="sxs-lookup"><span data-stu-id="0ca57-224">In the upper-left corner of the InfoPath window, click **Submit** or click **Resubmit Expense Report**.</span></span> <span data-ttu-id="0ca57-225">等待出现确认窗口，指示已成功提交费用报告。</span><span class="sxs-lookup"><span data-stu-id="0ca57-225">Wait for a confirmation window that says the expense report was successfully submitted.</span></span>  

    <span data-ttu-id="0ca57-226">-或-</span><span class="sxs-lookup"><span data-stu-id="0ca57-226">-OR-</span></span>  

    <span data-ttu-id="0ca57-227">复制并粘贴到此文件**ExpenseReportIn**文件夹。</span><span class="sxs-lookup"><span data-stu-id="0ca57-227">Copy and paste this file into the **ExpenseReportIn** folder.</span></span>  

3. <span data-ttu-id="0ca57-228">应看到新的文件放入**ExpenseReportOut**文件夹。</span><span class="sxs-lookup"><span data-stu-id="0ca57-228">You should see a new file dropped into the **ExpenseReportOut** folder.</span></span> <span data-ttu-id="0ca57-229">此文件即为上述步骤中提交的费用报告表单。</span><span class="sxs-lookup"><span data-stu-id="0ca57-229">This file is the same expense report form that was submitted during previous steps.</span></span>  

   <span data-ttu-id="0ca57-230">在确认“无错误”的情况后，使用以下过程将本示例与不正确的费用报告一起运行，从而触发错误处理功能。</span><span class="sxs-lookup"><span data-stu-id="0ca57-230">After you confirm the "no errors" case, use the following procedure to run the sample with an incorrect expense report to trigger error-handling functionality.</span></span>  

#### <a name="to-trigger-error-handling"></a><span data-ttu-id="0ca57-231">触发错误处理</span><span class="sxs-lookup"><span data-stu-id="0ca57-231">To trigger error handling</span></span>  

1. <span data-ttu-id="0ca57-232">打开 InfoPath 表单**Invalid Expense Report-John Doe.xml**。</span><span class="sxs-lookup"><span data-stu-id="0ca57-232">Open the InfoPath form **Invalid Expense Report - John Doe.xml**.</span></span> <span data-ttu-id="0ca57-233">看看**部门**字段在窗体中。</span><span class="sxs-lookup"><span data-stu-id="0ca57-233">Look at the **Department** field within the form.</span></span> <span data-ttu-id="0ca57-234">此字段设置为某个无效的值。</span><span class="sxs-lookup"><span data-stu-id="0ca57-234">This field is set to some invalid value.</span></span>  

2. <span data-ttu-id="0ca57-235">在 InfoPath 窗口的左上角，单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="0ca57-235">In the upper-left corner of the InfoPath window, click **Submit**.</span></span> <span data-ttu-id="0ca57-236">等待出现确认窗口，指示已成功提交费用报告。</span><span class="sxs-lookup"><span data-stu-id="0ca57-236">Wait for a confirmation window that says the expense report was successfully submitted.</span></span>  

    <span data-ttu-id="0ca57-237">-或-</span><span class="sxs-lookup"><span data-stu-id="0ca57-237">-OR-</span></span>  

    <span data-ttu-id="0ca57-238">复制并粘贴到此文件**ExpenseReportIn**文件夹。</span><span class="sxs-lookup"><span data-stu-id="0ca57-238">Copy and paste this file into the **ExpenseReportIn** folder.</span></span>  

3. <span data-ttu-id="0ca57-239">您应看到名为的新文件**ErrorReport_\<**<em>日期</em>_<em>时间</em>**\>.xml**放到**ExpenseReportOut**文件夹。</span><span class="sxs-lookup"><span data-stu-id="0ca57-239">You should see a new file called **ErrorReport_\<**<em>date</em>_<em>time</em>**\>.xml** dropped into the **ExpenseReportOut** folder.</span></span>  

    <span data-ttu-id="0ca57-240">打开此文件，然后会观察到这是在前面步骤中提交的费用报告，但在开头添加了错误信息。</span><span class="sxs-lookup"><span data-stu-id="0ca57-240">Open this file and observe that this is the expense report submitted in the previous step but with the error information added at the beginning.</span></span>  

4. <span data-ttu-id="0ca57-241">错误的部门值替换为"Marketing"，然后依次**提交**在 InfoPath 窗口的左上角。</span><span class="sxs-lookup"><span data-stu-id="0ca57-241">Replace the erroneous department value with "Marketing", and then click **Submit** in the upper-left corner of the InfoPath window.</span></span>  

    <span data-ttu-id="0ca57-242">-或-</span><span class="sxs-lookup"><span data-stu-id="0ca57-242">-OR-</span></span>  

    <span data-ttu-id="0ca57-243">复制并粘贴到此文件**ResubmittedReportIn**文件夹。</span><span class="sxs-lookup"><span data-stu-id="0ca57-243">Copy and paste this file into the **ResubmittedReportIn** folder.</span></span>  

5. <span data-ttu-id="0ca57-244">应看到新的文件中创建**ExpenseReportOut**文件夹。</span><span class="sxs-lookup"><span data-stu-id="0ca57-244">You should see a new file created in the **ExpenseReportOut** folder.</span></span> <span data-ttu-id="0ca57-245">此文件即为重新提交到服务器的更正后的费用报告。</span><span class="sxs-lookup"><span data-stu-id="0ca57-245">This file is the corrected expense report that was resubmitted into the server.</span></span>  

## <a name="see-also"></a><span data-ttu-id="0ca57-246">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ca57-246">See Also</span></span>  
 <span data-ttu-id="0ca57-247">[使用失败的消息路由](../core/using-failed-message-routing.md) </span><span class="sxs-lookup"><span data-stu-id="0ca57-247">[Using Failed Message Routing](../core/using-failed-message-routing.md) </span></span>  
 [<span data-ttu-id="0ca57-248">消息传送（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="0ca57-248">Messaging (BizTalk Server Samples Folder)</span></span>](../core/messaging-biztalk-server-samples-folder.md)