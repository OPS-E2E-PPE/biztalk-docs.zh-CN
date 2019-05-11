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
ms.openlocfilehash: dfff362d6d12e68ad7c0ef9258cccfd68dff1a0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348200"
---
# <a name="error-handling-biztalk-server-samples-folder"></a><span data-ttu-id="7ec2f-102">错误处理 （BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="7ec2f-102">Error Handling (BizTalk Server Samples Folder)</span></span>
<span data-ttu-id="7ec2f-103">此示例的目的是生成基于内容的路由 (CBR) 应用程序时的错误处理功能。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-103">The purpose of this sample is to build an error-handling functionality for the content-based routing (CBR) application.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="7ec2f-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="7ec2f-104">Prerequisites</span></span>  
 <span data-ttu-id="7ec2f-105">若要运行示例，建议你安装 Microsoft Office InfoPath 2010 或更高版本安装。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-105">To run the sample, it is recommended that you have Microsoft Office InfoPath 2010 or later installed.</span></span> <span data-ttu-id="7ec2f-106">您可以运行该示例不使用 InfoPath，但在这种情况下不能查看费用报告以及通过 HTTP 适配器的费用报告的提交。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-106">You can run the sample without using InfoPath, but in that case you cannot see the expense reports and the submission of expense reports through the HTTP adapter.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="7ec2f-107">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="7ec2f-107">What This Sample Does</span></span>  
 <span data-ttu-id="7ec2f-108">此示例实现费用报告处理系统的一部分。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-108">The sample implements part of an expense report processing system.</span></span> <span data-ttu-id="7ec2f-109">具体而言，此示例执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="7ec2f-109">Specifically, this sample does the following:</span></span>  

1. <span data-ttu-id="7ec2f-110">定义包含有关费用报告和单个提交者包括部门名称信息的费用报表架构。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-110">Defines an expense report schema containing information about an expense report and the individual submitter including department name.</span></span>  

2. <span data-ttu-id="7ec2f-111">提供用于提交费用报表通过目录或通过使用 InfoPath 的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-111">Provides for the submission of the expense report through a directory or through a Web service using InfoPath.</span></span>  

3. <span data-ttu-id="7ec2f-112">促进**部门**并**correlationID**消息中的属性记录，以便它可用于在端口筛选器中控制路由。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-112">Promotes the **Department** and **correlationID** properties in the message document so that it can be used in a port filter to control routing.</span></span>  

4. <span data-ttu-id="7ec2f-113">路由的费用报告属于市场营销部到目录，从而模拟送达该部门的后端系统中的文件。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-113">Routes expense reports belonging to the Marketing department to a file in a directory, simulating delivery to the department's back-end system.</span></span>  

5. <span data-ttu-id="7ec2f-114">生成失败的消息的费用报告属于 Marketing 之外的部门。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-114">Generates a failed message for expense reports belonging to departments other than Marketing.</span></span> <span data-ttu-id="7ec2f-115">失败的消息包括有关错误包括错误代码和错误说明的信息。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-115">The failed message includes information about the error including error code and error description.</span></span>  

6. <span data-ttu-id="7ec2f-116">失败消息路由给接收方人员 (业务用户或应用程序操作员) 以进行更正和重新提交。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-116">Routes failed messages to a human recipient (a business user or application operator) for correction and resubmission.</span></span>  

7. <span data-ttu-id="7ec2f-117">路由重新提交费用报告，根据部门上文所述。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-117">Routes resubmitted expense reports based on department as described above.</span></span>  

   <span data-ttu-id="7ec2f-118">其中的大部分工作是通过 BizTalk 业务流程调度。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-118">Much of this work is done through a BizTalk orchestration schedule.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="7ec2f-119">此示例设计方式和原因</span><span class="sxs-lookup"><span data-stu-id="7ec2f-119">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="7ec2f-120">本设计依赖于默认发送和接收 XML 管道、 属性升级、 订阅筛选器和业务流程计划中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来路由消息。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-120">The design relies on the default send and receive XML pipelines, property promotion, subscription filters, and orchestration schedules within [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to route messages.</span></span> <span data-ttu-id="7ec2f-121">下表中列出的设计元素和及其选入理由。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-121">Design elements and their justification are listed in the following table.</span></span>  


|         <span data-ttu-id="7ec2f-122">设计元素</span><span class="sxs-lookup"><span data-stu-id="7ec2f-122">Design element</span></span>         |                                                                                                                                                                 <span data-ttu-id="7ec2f-123">选择的原因</span><span class="sxs-lookup"><span data-stu-id="7ec2f-123">Reason(s) selected</span></span>                                                                                                                                                                 |
|--------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7ec2f-124">默认 XML 接收管道</span><span class="sxs-lookup"><span data-stu-id="7ec2f-124">Default XML receive pipeline</span></span>  |                                                        <span data-ttu-id="7ec2f-125">XMLReceive 管道支持属性升级;PassThruReceive 管道却没有。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-125">-   The XMLReceive pipeline supports property promotion; the PassThruReceive pipeline does not.</span></span><br /><span data-ttu-id="7ec2f-126">-入站的消息已采用 XML 格式，并且不需要除基本拆装和参与方解析之外的处理。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-126">-   The inbound message is already in XML format and does not require processing beyond basic disassembly and party resolution.</span></span>                                                        |
|  <span data-ttu-id="7ec2f-127">为失败消息路由</span><span class="sxs-lookup"><span data-stu-id="7ec2f-127">Routing for failed messages</span></span>   | <span data-ttu-id="7ec2f-128">-接收端口挂起失败的消息并将默认情况下生成一个否定确认。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-128">-   Receive ports suspend failed messages and generate a negative acknowledgment by default.</span></span> <span data-ttu-id="7ec2f-129">启用路由后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]尝试将路由到某个订阅应用程序的处理失败的任何消息 （例如其他接收端口或业务流程计划）。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-129">When routing is enabled [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] attempts to route any message that fails processing to a subscribing application (such as another receive port or orchestration schedule).</span></span> |
|       <span data-ttu-id="7ec2f-130">属性升级</span><span class="sxs-lookup"><span data-stu-id="7ec2f-130">Property promotion</span></span>       |                                                                                                   <span data-ttu-id="7ec2f-131">BizTalk Server 根据属性字段进行路由。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-131">-   BizTalk Server depends upon property fields to do routing.</span></span> <span data-ttu-id="7ec2f-132">可分辨的字段由业务流程使用，并且不能用于路由。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-132">Distinguished fields are used by orchestrations and cannot be used for routing.</span></span>                                                                                                   |
|      <span data-ttu-id="7ec2f-133">订阅筛选器</span><span class="sxs-lookup"><span data-stu-id="7ec2f-133">Subscription filter</span></span>       |                                                                                                          <span data-ttu-id="7ec2f-134">-订阅筛选器来执行路由捕获满足一个或多个基于属性的字段的条件的消息。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-134">-   The subscription filter performs the routing by capturing messages that meet one or more criteria based on property fields.</span></span>                                                                                                           |
| <span data-ttu-id="7ec2f-135">BizTalk 业务流程调度</span><span class="sxs-lookup"><span data-stu-id="7ec2f-135">BizTalk orchestration schedule</span></span> |                                                                  <span data-ttu-id="7ec2f-136">-提供了将信息添加到失败的消息的机会。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-136">-   Provides the opportunity to add information to failed messages.</span></span><br /><span data-ttu-id="7ec2f-137">-启用失败消息路由到的人为干预的专用位置。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-137">-   Enables routing of failed messages to a dedicated location for human intervention.</span></span><br /><span data-ttu-id="7ec2f-138">-进程重新提交费用报告。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-138">-   Processes resubmitted expense reports.</span></span>                                                                   |
|          <span data-ttu-id="7ec2f-139">XMLTransmit</span><span class="sxs-lookup"><span data-stu-id="7ec2f-139">XMLTransmit</span></span>           |                                                                                                                <span data-ttu-id="7ec2f-140">-执行基本组装传出 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-140">-   Performs basic assembly of outgoing XML messages.</span></span> <span data-ttu-id="7ec2f-141">PassThruTransmit 管道未提供其他支持。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-141">The PassThruTransmit pipeline provides no additional support.</span></span>                                                                                                                 |

## <a name="where-to-find-this-sample"></a><span data-ttu-id="7ec2f-142">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="7ec2f-142">Where to Find This Sample</span></span>  
 <span data-ttu-id="7ec2f-143">此示例位于 <`Samples Path>`\Messaging\ErrorHandling\\。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-143">This sample is located at <`Samples Path>`\Messaging\ErrorHandling\\.</span></span>  

 <span data-ttu-id="7ec2f-144">下表列出了本示例的文件。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-144">The following table contains a list of files for this sample.</span></span>  

|<span data-ttu-id="7ec2f-145">文件</span><span class="sxs-lookup"><span data-stu-id="7ec2f-145">File</span></span>|<span data-ttu-id="7ec2f-146">Description</span><span class="sxs-lookup"><span data-stu-id="7ec2f-146">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="7ec2f-147">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="7ec2f-147">Cleanup.bat</span></span>|<span data-ttu-id="7ec2f-148">用于取消部署程序集并从全局程序集缓存中删除。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-148">Used to undeploy assemblies and remove them from the global assembly cache.</span></span><br /><br /> <span data-ttu-id="7ec2f-149">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-149">Removes send and receive ports.</span></span><br /><br /> <span data-ttu-id="7ec2f-150">根据需要删除 Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-150">Removes Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="7ec2f-151">ErrorHandling.sln</span><span class="sxs-lookup"><span data-stu-id="7ec2f-151">ErrorHandling.sln</span></span>|<span data-ttu-id="7ec2f-152">该示例的 visual Studio 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-152">Visual Studio solution file for the sample.</span></span>|  
|<span data-ttu-id="7ec2f-153">ErrorHandlingBinding.xml</span><span class="sxs-lookup"><span data-stu-id="7ec2f-153">ErrorHandlingBinding.xml</span></span>|<span data-ttu-id="7ec2f-154">该示例的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-154">Binding file for the sample.</span></span>|  
|<span data-ttu-id="7ec2f-155">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="7ec2f-155">Setup.bat</span></span>|<span data-ttu-id="7ec2f-156">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-156">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="7ec2f-157">费用报告-John Doe.xml</span><span class="sxs-lookup"><span data-stu-id="7ec2f-157">Expense Report – John Doe.xml</span></span>|<span data-ttu-id="7ec2f-158">示例费用报告 InfoPath 文档。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-158">Example expense report InfoPath document.</span></span>|  
|<span data-ttu-id="7ec2f-159">无效的费用报表-John Doe.xml</span><span class="sxs-lookup"><span data-stu-id="7ec2f-159">Invalid Expense Report – John Doe.xml</span></span>|<span data-ttu-id="7ec2f-160">使用无效的数据示例费用报告 InfoPath 文档。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-160">Example expense report InfoPath document with invalid data in it.</span></span>|  
|<span data-ttu-id="7ec2f-161">在 ErrorHandler 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="7ec2f-161">In ErrorHandler folder:</span></span><br /><br /> <span data-ttu-id="7ec2f-162">ErrorHandler.btproj</span><span class="sxs-lookup"><span data-stu-id="7ec2f-162">ErrorHandler.btproj</span></span>|<span data-ttu-id="7ec2f-163">业务流程的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-163">BizTalk project for orchestration.</span></span>|  
|<span data-ttu-id="7ec2f-164">在 ErrorHandler 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="7ec2f-164">In ErrorHandler folder:</span></span><br /><br /> <span data-ttu-id="7ec2f-165">ResubmitLogic.odx</span><span class="sxs-lookup"><span data-stu-id="7ec2f-165">ResubmitLogic.odx</span></span>|<span data-ttu-id="7ec2f-166">业务流程的订阅失败的消息、 将其发送到接收方人员进行更正，然后重新提交更正后返回到服务器进行路由的消息。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-166">Orchestration that subscribes to failed messages, sends them to the human recipient for correction, and then resubmits corrected messages back into the server for routing.</span></span>|  
|<span data-ttu-id="7ec2f-167">在 ErrorHandler 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="7ec2f-167">In ErrorHandler folder:</span></span><br /><br /> <span data-ttu-id="7ec2f-168">SuspendMessage.odx</span><span class="sxs-lookup"><span data-stu-id="7ec2f-168">SuspendMessage.odx</span></span>|<span data-ttu-id="7ec2f-169">用于挂起无法在错误处理业务流程内处理的消息的业务流程。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-169">Orchestration used for suspending messages that cannot be processed within the error-handling orchestration.</span></span>|  
|<span data-ttu-id="7ec2f-170">在 InfoPathForms 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="7ec2f-170">In InfoPathForms folder:</span></span><br /><br /> <span data-ttu-id="7ec2f-171">Expense Report.xsn</span><span class="sxs-lookup"><span data-stu-id="7ec2f-171">Expense Report.xsn</span></span><br /><br /> <span data-ttu-id="7ec2f-172">Expense Report-Resubmit.xsn</span><span class="sxs-lookup"><span data-stu-id="7ec2f-172">Expense Report - Resubmit.xsn</span></span>|<span data-ttu-id="7ec2f-173">费用报告 InfoPath 窗体和窗体用于查看和重新提交失败的消息。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-173">Expense report InfoPath form and form used for viewing and resubmitting failed messages.</span></span>|  
|<span data-ttu-id="7ec2f-174">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="7ec2f-174">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="7ec2f-175">ExpenseReportSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="7ec2f-175">ExpenseReportSchema.xsd</span></span>|<span data-ttu-id="7ec2f-176">费用报告文档的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-176">XML schema for the expense report document.</span></span>|  
|<span data-ttu-id="7ec2f-177">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="7ec2f-177">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="7ec2f-178">PipelinesAndSchemas.btproj</span><span class="sxs-lookup"><span data-stu-id="7ec2f-178">PipelinesAndSchemas.btproj</span></span>|<span data-ttu-id="7ec2f-179">该示例的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-179">BizTalk project for the sample.</span></span>|  
|<span data-ttu-id="7ec2f-180">在 PipelinesAndSchemas 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="7ec2f-180">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="7ec2f-181">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="7ec2f-181">PropertySchema.xsd</span></span>|<span data-ttu-id="7ec2f-182">该示例的属性架构。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-182">Property schema for the sample.</span></span>|  

## <a name="how-to-use-this-sample"></a><span data-ttu-id="7ec2f-183">如何使用此示例</span><span class="sxs-lookup"><span data-stu-id="7ec2f-183">How to Use This Sample</span></span>  
 <span data-ttu-id="7ec2f-184">此示例提供了用于创建你自己的错误处理过程的起始点。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-184">This sample provides a starting point for creating your own error handling procedure.</span></span>  

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="7ec2f-185">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="7ec2f-185">Building and Initializing This Sample</span></span>  

#### <a name="to-build-and-initialize-the-compose-sample"></a><span data-ttu-id="7ec2f-186">若要生成并初始化 Compose 示例</span><span class="sxs-lookup"><span data-stu-id="7ec2f-186">To build and initialize the Compose sample</span></span>  

1. <span data-ttu-id="7ec2f-187">在命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="7ec2f-187">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="7ec2f-188"><`Samples Path`>**\Messaging\ErrorHandling**</span><span class="sxs-lookup"><span data-stu-id="7ec2f-188"><`Samples Path`>**\Messaging\ErrorHandling**</span></span>  

2. <span data-ttu-id="7ec2f-189">运行**Setup.bat**，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7ec2f-189">Run **Setup.bat**, which performs the following actions:</span></span>  

   - <span data-ttu-id="7ec2f-190">创建三个文件夹：**ExpenseReportIn**， **ExpenseReportOut**，和**ResubmittedReportIn**以下路径下：</span><span class="sxs-lookup"><span data-stu-id="7ec2f-190">Creates three folders: **ExpenseReportIn**, **ExpenseReportOut**, and **ResubmittedReportIn** under the following path:</span></span>  

      <span data-ttu-id="7ec2f-191"><`Samples Path`>**\Messaging\ErrorHandling**</span><span class="sxs-lookup"><span data-stu-id="7ec2f-191"><`Samples Path`>**\Messaging\ErrorHandling**</span></span>  

   - <span data-ttu-id="7ec2f-192">复制并发布 InfoPath 窗体**Expense Report.xsn**并**Expense Report – Resubmit.xsn**到文件夹**C:\Temp\InfoPathForms**。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-192">Copies and publishes the InfoPath forms **Expense Report.xsn** and **Expense Report – Resubmit.xsn** into the folder **C:\Temp\InfoPathForms**.</span></span>  

   - <span data-ttu-id="7ec2f-193">编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]本示例项目。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-193">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  

   - <span data-ttu-id="7ec2f-194">创建一个名为的虚拟目录**为 ExpenseReports**。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-194">Creates a virtual directory called **ExpenseReports**.</span></span>  

   - <span data-ttu-id="7ec2f-195">创建新的 BizTalk 应用程序调用**Error Handling Sample**并部署到其中的示例程序集。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-195">Creates a new BizTalk application called **Error Handling Sample** and deploys the sample assemblies into it.</span></span>  

   - <span data-ttu-id="7ec2f-196">创建并绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置和发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-196">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive locations, and the send and receive ports.</span></span>  

   - <span data-ttu-id="7ec2f-197">登记和启动业务流程，启用接收位置，并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-197">Enlists and starts orchestrations, enables the receive locations, and starts the send ports.</span></span>  

      <span data-ttu-id="7ec2f-198">如果你选择打开并生成此示例中的项目不运行 Setup.bat 的情况下，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-198">If you choose to open and build the projects in this sample without running Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="7ec2f-199">使用此密钥对示例程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-199">Use this key pair to sign the sample assemblies.</span></span>  

3. <span data-ttu-id="7ec2f-200">在尝试运行此示例之前, 确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成或初始化过程中未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-200">Before attempting to run this sample, confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build or initialization process.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="7ec2f-201">若要撤消 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-201">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="7ec2f-202">必须运行 Setup.bat 前运行 Cleanup.bat 时间。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-202">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

4. <span data-ttu-id="7ec2f-203">如果使用 Internet 信息服务 (IIS) 7.0，需要执行其他配置步骤，从而调整与相对应的虚拟目录的设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HTTP 接收位置使用的示例。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-203">If you are using Internet Information Services (IIS) 7.0, you need to perform additional configuration steps to adjust the setting for the virtual directory that corresponds to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP receive location used by the sample.</span></span> <span data-ttu-id="7ec2f-204">通过执行以下操作配置 IIS:</span><span class="sxs-lookup"><span data-stu-id="7ec2f-204">Configure IIS by doing the following:</span></span>  

   1. <span data-ttu-id="7ec2f-205">使用 IIS 7.0 管理器，创建一个新的应用程序池，为 BizTalk Isolated Host Users 组。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-205">Using IIS 7.0 Manager, create a new application pool for the BizTalk Isolated Host Users group.</span></span>  

   2. <span data-ttu-id="7ec2f-206">配置应用程序池的标识下运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]独立主机用户。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-206">Configure the application pool to run under the identity of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Isolated Host user.</span></span> <span data-ttu-id="7ec2f-207">(如果已配置为其他应用程序池，可以跳过此步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HTTP 接收位置。)</span><span class="sxs-lookup"><span data-stu-id="7ec2f-207">(You may skip this step if you already have an application pool configured for other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP receive locations.)</span></span>  

   3. <span data-ttu-id="7ec2f-208">配置虚拟目录**ExpenseReport**使用 HTTP 接收在上一步中创建的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-208">Configure the virtual directory **ExpenseReport** to use the HTTP receive application pool created in the previous step.</span></span>  

      <span data-ttu-id="7ec2f-209">如果你还没有使用 BTSHTTPReceive.dll ISAPI 扩展插件的 Web 服务器扩展插件，创建并启用通过设置其状态为"允许"。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-209">If you do not already have a Web server extension for the BTSHTTPReceive.dll ISAPI extension, create and enable it by setting its status to "Allowed".</span></span> <span data-ttu-id="7ec2f-210">你可以在 IIS 7.0 中使用 IIS 管理控制台 (要么直接下**管理工具**或通过计算机管理控制台)，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7ec2f-210">You can do this in IIS 7.0 by using the IIS Management console (either directly under **Administrative Tools** or through the Computer Management console) as follows:</span></span>  

   4. <span data-ttu-id="7ec2f-211">展开**Internet Information Services Manager**树。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-211">Expand the **Internet Information Services Manager** tree.</span></span>  

   5. <span data-ttu-id="7ec2f-212">单击**Web 服务扩展**文件夹。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-212">Click the **Web Service Extensions** folder.</span></span>  

   6. <span data-ttu-id="7ec2f-213">在管理控制台的右窗格中，单击**添加一个新的 Web 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-213">In the right pane of the management console, click **Add a new Web Service extension**.</span></span>  

   7. <span data-ttu-id="7ec2f-214">在中**新的 Web 服务扩展**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-214">In the **New Web Service Extension** dialog box, click **Add**.</span></span>  

   8. <span data-ttu-id="7ec2f-215">在**添加文件**对话框中，单击**浏览**若要选择的文件 <`BizTalkInstallPath>`**\HttpReceive\BTSHTTPReceive.dll**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="7ec2f-215">In the **Add file** dialog box, click **Browse** to select the file <`BizTalkInstallPath>`**\HttpReceive\BTSHTTPReceive.dll**, and then click **OK**.</span></span>  

   9. <span data-ttu-id="7ec2f-216">配置虚拟目录**ExpenseReport**以使用本地路径[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HTTPReceive</span><span class="sxs-lookup"><span data-stu-id="7ec2f-216">Configure the virtual directory **ExpenseReport** to use local path [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HTTPReceive</span></span>  

      <span data-ttu-id="7ec2f-217">有关详细信息，请参阅[如何配置 IIS 以实现 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-217">For more information, see [How to Configure IIS for an HTTP Receive Location](../core/how-to-configure-iis-for-an-http-receive-location.md).</span></span>  

## <a name="running-the-sample"></a><span data-ttu-id="7ec2f-218">运行示例</span><span class="sxs-lookup"><span data-stu-id="7ec2f-218">Running the Sample</span></span>  
 <span data-ttu-id="7ec2f-219">在之前与正确的费用报告一起运行示例，使用以下过程以验证"无错误"case 示例正常运行。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-219">Before running the sample with the correct expense report, use the following procedure to verify that the "no errors" case sample works correctly.</span></span>  

#### <a name="to-verify-that-the-no-errors-case-sample-works-correctly"></a><span data-ttu-id="7ec2f-220">若要验证"无错误"正确 case 示例的工作机制</span><span class="sxs-lookup"><span data-stu-id="7ec2f-220">To verify that the "no errors" case sample works correctly</span></span>  

1. <span data-ttu-id="7ec2f-221">打开 InfoPath 表单**Expense Report-John Doe.xml**。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-221">Open the InfoPath form **Expense Report - John Doe.xml**.</span></span> <span data-ttu-id="7ec2f-222">看看**部门**字段在窗体中。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-222">Look at the **Department** field within the form.</span></span> <span data-ttu-id="7ec2f-223">此字段应设置为"Marketing"。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-223">This field should be set to "Marketing".</span></span>  

2. <span data-ttu-id="7ec2f-224">在 InfoPath 窗口的左上角，单击**提交**或单击**重新提交费用报告**。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-224">In the upper-left corner of the InfoPath window, click **Submit** or click **Resubmit Expense Report**.</span></span> <span data-ttu-id="7ec2f-225">等待确认窗口，指示已成功提交费用报表。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-225">Wait for a confirmation window that says the expense report was successfully submitted.</span></span>  

    <span data-ttu-id="7ec2f-226">-或-</span><span class="sxs-lookup"><span data-stu-id="7ec2f-226">-OR-</span></span>  

    <span data-ttu-id="7ec2f-227">复制并粘贴到此文件**ExpenseReportIn**文件夹。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-227">Copy and paste this file into the **ExpenseReportIn** folder.</span></span>  

3. <span data-ttu-id="7ec2f-228">应看到新的文件放入**ExpenseReportOut**文件夹。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-228">You should see a new file dropped into the **ExpenseReportOut** folder.</span></span> <span data-ttu-id="7ec2f-229">此文件是相同上述步骤中提交的费用报告表单。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-229">This file is the same expense report form that was submitted during previous steps.</span></span>  

   <span data-ttu-id="7ec2f-230">确认"无错误"用例后，使用以下过程使用不正确的费用报表来触发错误处理功能运行此示例。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-230">After you confirm the "no errors" case, use the following procedure to run the sample with an incorrect expense report to trigger error-handling functionality.</span></span>  

#### <a name="to-trigger-error-handling"></a><span data-ttu-id="7ec2f-231">若要触发错误处理</span><span class="sxs-lookup"><span data-stu-id="7ec2f-231">To trigger error handling</span></span>  

1. <span data-ttu-id="7ec2f-232">打开 InfoPath 表单**Invalid Expense Report-John Doe.xml**。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-232">Open the InfoPath form **Invalid Expense Report - John Doe.xml**.</span></span> <span data-ttu-id="7ec2f-233">看看**部门**字段在窗体中。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-233">Look at the **Department** field within the form.</span></span> <span data-ttu-id="7ec2f-234">此字段设置为某个无效的值。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-234">This field is set to some invalid value.</span></span>  

2. <span data-ttu-id="7ec2f-235">在 InfoPath 窗口的左上角，单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-235">In the upper-left corner of the InfoPath window, click **Submit**.</span></span> <span data-ttu-id="7ec2f-236">等待确认窗口，指示已成功提交费用报表。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-236">Wait for a confirmation window that says the expense report was successfully submitted.</span></span>  

    <span data-ttu-id="7ec2f-237">-或-</span><span class="sxs-lookup"><span data-stu-id="7ec2f-237">-OR-</span></span>  

    <span data-ttu-id="7ec2f-238">复制并粘贴到此文件**ExpenseReportIn**文件夹。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-238">Copy and paste this file into the **ExpenseReportIn** folder.</span></span>  

3. <span data-ttu-id="7ec2f-239">您应看到名为的新文件**ErrorReport_\<**<em>日期</em>_<em>时间</em>**\>.xml**放到**ExpenseReportOut**文件夹。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-239">You should see a new file called **ErrorReport_\<**<em>date</em>_<em>time</em>**\>.xml** dropped into the **ExpenseReportOut** folder.</span></span>  

    <span data-ttu-id="7ec2f-240">打开此文件并观察，这是上一步中，但在开头添加错误信息提交的费用报告。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-240">Open this file and observe that this is the expense report submitted in the previous step but with the error information added at the beginning.</span></span>  

4. <span data-ttu-id="7ec2f-241">错误的部门值替换为"Marketing"，然后依次**提交**在 InfoPath 窗口的左上角。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-241">Replace the erroneous department value with "Marketing", and then click **Submit** in the upper-left corner of the InfoPath window.</span></span>  

    <span data-ttu-id="7ec2f-242">-或-</span><span class="sxs-lookup"><span data-stu-id="7ec2f-242">-OR-</span></span>  

    <span data-ttu-id="7ec2f-243">复制并粘贴到此文件**ResubmittedReportIn**文件夹。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-243">Copy and paste this file into the **ResubmittedReportIn** folder.</span></span>  

5. <span data-ttu-id="7ec2f-244">应看到新的文件中创建**ExpenseReportOut**文件夹。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-244">You should see a new file created in the **ExpenseReportOut** folder.</span></span> <span data-ttu-id="7ec2f-245">此文件是为重新提交到服务器的更正后的费用报告。</span><span class="sxs-lookup"><span data-stu-id="7ec2f-245">This file is the corrected expense report that was resubmitted into the server.</span></span>  

## <a name="see-also"></a><span data-ttu-id="7ec2f-246">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ec2f-246">See Also</span></span>  
 <span data-ttu-id="7ec2f-247">[使用失败的消息路由](../core/using-failed-message-routing.md) </span><span class="sxs-lookup"><span data-stu-id="7ec2f-247">[Using Failed Message Routing](../core/using-failed-message-routing.md) </span></span>  
 [<span data-ttu-id="7ec2f-248">消息传送（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="7ec2f-248">Messaging (BizTalk Server Samples Folder)</span></span>](../core/messaging-biztalk-server-samples-folder.md)