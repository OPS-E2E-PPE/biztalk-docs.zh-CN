---
title: "OperationsSamples （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c9e3f3e-a570-4edd-aa2e-3f8e2e37c8a0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3e190d06c084a6b1b3c9965856897e0df94daab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="operationssamples-biztalk-server-sample"></a><span data-ttu-id="e0380-102">OperationsSamples（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="e0380-102">OperationsSamples (BizTalk Server Sample)</span></span>
<span data-ttu-id="e0380-103">OperationsSamples 示例演示如何使用操作对象模型执行操作活动。</span><span class="sxs-lookup"><span data-stu-id="e0380-103">The OperationsSamples sample demonstrates how to perform operational activities using the Operations object model.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="e0380-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="e0380-104">What This Sample Does</span></span>  
 <span data-ttu-id="e0380-105">本示例演示下面几点：</span><span class="sxs-lookup"><span data-stu-id="e0380-105">This sample demonstrates the following:</span></span>  
  
-   <span data-ttu-id="e0380-106">如何使用跟踪配置文件通过活动注释业务流程。</span><span class="sxs-lookup"><span data-stu-id="e0380-106">How to use a tracking profile to comment an orchestration with activities.</span></span>  
  
-   <span data-ttu-id="e0380-107">如何使用 BAM 跟踪数据库查找活动 ID，然后使用此 ID 查找相关业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="e0380-107">How to use the BAM tracking database to find an activity ID and then use the ID to find a related orchestration instance.</span></span>  
  
-   <span data-ttu-id="e0380-108">如何查找和使用工作与消息流**MessageFlow**类和其他操作对象模型类和 Api。</span><span class="sxs-lookup"><span data-stu-id="e0380-108">How to find and work with message flows by using the **MessageFlow** class and other Operations object model classes and APIs.</span></span>  
  
-   <span data-ttu-id="e0380-109">如何访问端口，消息，并通过使用类的其他实例源自**实例**类。</span><span class="sxs-lookup"><span data-stu-id="e0380-109">How to access ports, messages, and other instances by using classes derived from the **Instance** class.</span></span>  
  
 <span data-ttu-id="e0380-110">本示例包含大量有用的助手类和方法来支持上面的操作。</span><span class="sxs-lookup"><span data-stu-id="e0380-110">The sample contains many useful helper classes and methods to support the operations above.</span></span> <span data-ttu-id="e0380-111">下一部分讨论了这些以及其他代码重点。</span><span class="sxs-lookup"><span data-stu-id="e0380-111">These and other code highlights are discussed in the next section.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="e0380-112">此示例应如何以及为何</span><span class="sxs-lookup"><span data-stu-id="e0380-112">How This Sample Is Designed and Why</span></span>  
 <span data-ttu-id="e0380-113">本示例旨在演示操作对象模型中的多个关键类和方法，并显示如何查询公用 BAM 跟踪数据库。</span><span class="sxs-lookup"><span data-stu-id="e0380-113">This sample is designed to demonstrate several of the key classes and methods in the Operations object model and to show how to query the publicly available BAM tracking database.</span></span>  
  
 <span data-ttu-id="e0380-114">操作对象模型包含的类可提供处理 BizTalk Server 中的消息和其他实例的功能。</span><span class="sxs-lookup"><span data-stu-id="e0380-114">The Operations object model contains classes that provide the ability to manipulate messages and other instances within BizTalk Server.</span></span>  
  
### <a name="using-a-bam-activity-id"></a><span data-ttu-id="e0380-115">使用 BAM 活动 ID</span><span class="sxs-lookup"><span data-stu-id="e0380-115">Using a BAM Activity ID</span></span>  
 <span data-ttu-id="e0380-116">本示例显示通过使用业务数据如何与 BAM 交互，以及如何使用跟踪数据库中的公用视图在消息框中查找实时消息。</span><span class="sxs-lookup"><span data-stu-id="e0380-116">This sample shows how to interact with BAM and how to use the publicly available views in the tracking database to locate a live message in the message box by using business data.</span></span> <span data-ttu-id="e0380-117">本示例通过检索与采购订单编号对应的业务流程 ID 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e0380-117">The sample does this by retrieving an orchestration ID corresponding to a purchase order number.</span></span> <span data-ttu-id="e0380-118">为成功执行此任务，本示例必须执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e0380-118">For this task to succeed, it must do the following:</span></span>  
  
1.  <span data-ttu-id="e0380-119">使用业务数据（采购订单编号）查找活动 ID。</span><span class="sxs-lookup"><span data-stu-id="e0380-119">Use business data (a purchase order number) to find an activity ID.</span></span> <span data-ttu-id="e0380-120">该步骤将业务数据映射到可以用于查找其他信息的内部 ID。</span><span class="sxs-lookup"><span data-stu-id="e0380-120">This step maps business data to an internal ID that can be used to find additional information.</span></span>  
  
2.  <span data-ttu-id="e0380-121">检索与活动 ID 相关的 BAM 引用。</span><span class="sxs-lookup"><span data-stu-id="e0380-121">Retrieve the BAM references related to the activity ID.</span></span>  
  
3.  <span data-ttu-id="e0380-122">查找引用业务流程的揃“BizTalkService”类型的引用。</span><span class="sxs-lookup"><span data-stu-id="e0380-122">Find a reference that has a type of "BizTalkService" and refers to an orchestration.</span></span> <span data-ttu-id="e0380-123">如果找到，则返回其实例 ID。</span><span class="sxs-lookup"><span data-stu-id="e0380-123">If one is found, return its instance ID.</span></span>  
  
 <span data-ttu-id="e0380-124">此功能由**BAMWebService.GetOrchestrationID**静态方法和关联的帮助器方法包括 BamManagementService.cs 源文件中的类和方法。</span><span class="sxs-lookup"><span data-stu-id="e0380-124">This functionality is provided by the **BAMWebService.GetOrchestrationID** static method and associated helper methods including classes and methods in the BamManagementService.cs source file.</span></span>  
  
### <a name="suspending-terminating-and-resuming-an-instance"></a><span data-ttu-id="e0380-125">挂起、终止和恢复实例</span><span class="sxs-lookup"><span data-stu-id="e0380-125">Suspending, Terminating, and Resuming an Instance</span></span>  
 <span data-ttu-id="e0380-126">示例程序包含**Samples.OperateOnInstance**使用操作和实例 ID，并执行指定的操作的实例上的方法。</span><span class="sxs-lookup"><span data-stu-id="e0380-126">The sample program includes a **Samples.OperateOnInstance** method that takes an operation and instance ID and performs the specified operation on the instance.</span></span> <span data-ttu-id="e0380-127">有效的操作由定义**InstanceOperation**枚举并包含挂起、 终止和恢复。</span><span class="sxs-lookup"><span data-stu-id="e0380-127">Valid operations are defined by the **InstanceOperation** enumeration and include Suspend, Terminate, and Resume.</span></span> <span data-ttu-id="e0380-128">这些操作直接映射到 BizTalkOperations 类的方法-**SuspendInstance**， **TerminateInstance**，和**ResumeInstance**。</span><span class="sxs-lookup"><span data-stu-id="e0380-128">These operations map directly to methods of the BizTalkOperations class—**SuspendInstance**, **TerminateInstance**, and **ResumeInstance**.</span></span>  
  
 <span data-ttu-id="e0380-129">请注意，此方法可处理 ArgumentException 和 SqlException 异常。</span><span class="sxs-lookup"><span data-stu-id="e0380-129">Notice that the method handles both ArgumentException and SqlException exceptions.</span></span> <span data-ttu-id="e0380-130">处理操作对象模型中的类和方法时必须谨慎预测异常（包括 SqlException）。</span><span class="sxs-lookup"><span data-stu-id="e0380-130">You must be careful to anticipate exceptions—including SqlException—when working with the classes and methods in the Operations object model.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0380-131">许多操作方法都需要对数据库的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e0380-131">Many of the Operations methods require access to the database.</span></span> <span data-ttu-id="e0380-132">应预测这些方法引发的异常，并进行相应处理。</span><span class="sxs-lookup"><span data-stu-id="e0380-132">You should anticipate the exceptions thrown by these methods and handle them appropriately.</span></span>  
  
### <a name="retrieving-all-live-messages"></a><span data-ttu-id="e0380-133">检索所有实时消息</span><span class="sxs-lookup"><span data-stu-id="e0380-133">Retrieving All Live Messages</span></span>  
 <span data-ttu-id="e0380-134">使用操作对象模型迭代所有可用实时消息非常简单，如以下代码段所示：</span><span class="sxs-lookup"><span data-stu-id="e0380-134">The Operations object model makes it straightforward to iterate over all of the available live messages, as shown in the following code fragment:</span></span>  
  
```  
BizTalkOperations _operations = new BizTalkOperations()  
IEnumerable messages = _operations.GetMessages();  
foreach (BizTalkMessage msg in messages)  
…  
```  
  
 <span data-ttu-id="e0380-135">OperationsSamples 程序进一步演示如何访问每个消息的相关信息，包括消息 ID、消息类型以及消息部分的数目和类型。</span><span class="sxs-lookup"><span data-stu-id="e0380-135">The OperationsSamples program takes this a step further by demonstrating how to access information about each message, including message ID and message type along with the number and types of message parts.</span></span> <span data-ttu-id="e0380-136">你可以修改此代码，并将其用于必须在 BizTalk Server 中循环访问大多数或所有可用实时消息的情况。</span><span class="sxs-lookup"><span data-stu-id="e0380-136">You can modify this code and use it in scenarios where you have to iterate through many or all of the available live messages in BizTalk Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0380-137">可能有成百上千个可用消息。</span><span class="sxs-lookup"><span data-stu-id="e0380-137">There may be hundreds or thousands of messages available.</span></span> <span data-ttu-id="e0380-138">扫描整个列表可能会对性能产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="e0380-138">Scanning the entire list may adversely affect performance.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="e0380-139">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="e0380-139">Where to Find This Sample</span></span>  
 <span data-ttu-id="e0380-140">本示例位于以下 SDK 位置中：</span><span class="sxs-lookup"><span data-stu-id="e0380-140">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="e0380-141">\<*示例路径*> \Admin\OperationsOM\OperationsSamples\\</span><span class="sxs-lookup"><span data-stu-id="e0380-141">\<*Samples Path*>\Admin\OperationsOM\OperationsSamples\\</span></span>  
  
 <span data-ttu-id="e0380-142">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="e0380-142">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="e0380-143">文件</span><span class="sxs-lookup"><span data-stu-id="e0380-143">File(s)</span></span>|<span data-ttu-id="e0380-144">Description</span><span class="sxs-lookup"><span data-stu-id="e0380-144">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e0380-145">BamManagementService.cs</span><span class="sxs-lookup"><span data-stu-id="e0380-145">BamManagementService.cs</span></span>|<span data-ttu-id="e0380-146">BAM Web Services 的 Web 代理类。</span><span class="sxs-lookup"><span data-stu-id="e0380-146">Web proxy class for the BAM Web service.</span></span>|  
|<span data-ttu-id="e0380-147">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="e0380-147">Cleanup.bat</span></span>|<span data-ttu-id="e0380-148">删除示例业务流程，并将 HelloWorld 示例还原为其原始状态。</span><span class="sxs-lookup"><span data-stu-id="e0380-148">Removes the sample orchestration and restores the HelloWorld sample to its original state.</span></span>|  
|<span data-ttu-id="e0380-149">HelloOrchestration.btt</span><span class="sxs-lookup"><span data-stu-id="e0380-149">HelloOrchestration.btt</span></span>|<span data-ttu-id="e0380-150">用于将 BizTalk 事件源映射到 BAM 目标活动的跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="e0380-150">Tracking profile used to map BizTalk event sources to BAM target activities.</span></span>|  
|<span data-ttu-id="e0380-151">HelloOrchestration.xls</span><span class="sxs-lookup"><span data-stu-id="e0380-151">HelloOrchestration.xls</span></span>|<span data-ttu-id="e0380-152">BAM 定义样式表。</span><span class="sxs-lookup"><span data-stu-id="e0380-152">BAM definition style sheet.</span></span>|  
|<span data-ttu-id="e0380-153">OperationsSamples.cs</span><span class="sxs-lookup"><span data-stu-id="e0380-153">OperationsSamples.cs</span></span>|<span data-ttu-id="e0380-154">包含演示操作对象模型的各个方面的代码的 C# 源文件。</span><span class="sxs-lookup"><span data-stu-id="e0380-154">C# source file containing code that demonstrates various aspects of the Operations object model.</span></span>|  
|<span data-ttu-id="e0380-155">OperationsSamples.csproj、OperationsSamples.sln 和 AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="e0380-155">OperationsSamples.csproj, OperationsSamples.sln, AssemblyInfo.cs</span></span>|<span data-ttu-id="e0380-156">本示例的项目、解决方案和程序集信息文件。</span><span class="sxs-lookup"><span data-stu-id="e0380-156">Project, solution, and assembly information files for this sample.</span></span>|  
|<span data-ttu-id="e0380-157">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="e0380-157">Setup.bat</span></span>|<span data-ttu-id="e0380-158">用于通过修改 HelloWorld 业务流程示例来生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="e0380-158">Used to build and initialize this sample by modifying the HelloWorld orchestration sample.</span></span> <span data-ttu-id="e0380-159">该文件将安装示例业务流程、部署 BAM 活动定义和跟踪配置文件编辑器文件、配置端口并将示例文件放置到接收位置中。</span><span class="sxs-lookup"><span data-stu-id="e0380-159">It installs a sample orchestration, deploys a BAM Activity Definition and a Tracking Profile Editor file, configures ports, and drops a sample file into the receive location.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="e0380-160">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="e0380-160">How to Use This Sample</span></span>  
 <span data-ttu-id="e0380-161">使用本示例可以浏览可在操作对象模型中使用的功能。</span><span class="sxs-lookup"><span data-stu-id="e0380-161">Use this sample to explore the functionality available in the Operations object model.</span></span> <span data-ttu-id="e0380-162">修改现有例程以查找消息，并以不同方式处理消息，或者添加复制 BizTalk Server 管理控制台中的部分组中心的新代码。</span><span class="sxs-lookup"><span data-stu-id="e0380-162">Modify existing routines to find and work with messages differently or add new code that replicates portions of the Group Hub in the BizTalk Server Management console.</span></span>  
  
 <span data-ttu-id="e0380-163">你也可以考虑下面一些任务：</span><span class="sxs-lookup"><span data-stu-id="e0380-163">You may also consider some of the following tasks:</span></span>  
  
-   <span data-ttu-id="e0380-164">编写用于将组中心页的最常用子集复制到自定义应用程序的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e0380-164">Write an application that replicates the most-used subset of the Group Hub into a custom application.</span></span>  
  
-   <span data-ttu-id="e0380-165">编写用于创建端口并为新贸易合作伙伴发送测试消息的自定义快速部署应用程序。</span><span class="sxs-lookup"><span data-stu-id="e0380-165">Write a custom provisioning application that creates ports and sends a test message through for new trading partners.</span></span>  
  
-   <span data-ttu-id="e0380-166">将示例程序修改为向屏幕、XML 文件或文本报告提供单个或一系列采购订单的相关信息的命令行实用工具。</span><span class="sxs-lookup"><span data-stu-id="e0380-166">Modify the sample program into a command-line utility that provides information about a single purchase order or a range of purchase orders to the screen, an XML file, or a text report.</span></span>  
  
## <a name="installing-sample-support-files"></a><span data-ttu-id="e0380-167">安装示例支持文件</span><span class="sxs-lookup"><span data-stu-id="e0380-167">Installing Sample Support Files</span></span>  
 <span data-ttu-id="e0380-168">本部分可引导你完成安装和运行本示例所需的过程。</span><span class="sxs-lookup"><span data-stu-id="e0380-168">This section walks through the procedures required to install and run the sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0380-169">在安装和运行本示例之前，必须验证是否已安装并且正在运行 BAM。</span><span class="sxs-lookup"><span data-stu-id="e0380-169">Before installing and running this sample, you must verify that BAM has been installed and is functioning.</span></span> <span data-ttu-id="e0380-170">如果尚未安装 BAM，本示例将不会运行。</span><span class="sxs-lookup"><span data-stu-id="e0380-170">If BAM has not been installed, this sample will not work.</span></span>  
  
#### <a name="to-compile-and-install-the-support-files-for-this-sample"></a><span data-ttu-id="e0380-171">编译和安装本示例的支持文件</span><span class="sxs-lookup"><span data-stu-id="e0380-171">To compile and install the support files for this sample</span></span>  
  
1.  <span data-ttu-id="e0380-172">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="e0380-172">In a command window, navigate to the following folder:</span></span>  
  
     `<Samples Path>\Admin\OperationsOM\OperationSamples`  
  
2.  <span data-ttu-id="e0380-173">运行 Setup.bat，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e0380-173">Run Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="e0380-174">创建发送目录和接收目录。</span><span class="sxs-lookup"><span data-stu-id="e0380-174">Creates send and receive directories</span></span>  
  
    -   <span data-ttu-id="e0380-175">创建并启动发送端口和接收端口</span><span class="sxs-lookup"><span data-stu-id="e0380-175">Creates and starts send and receive ports</span></span>  
  
    -   <span data-ttu-id="e0380-176">编译和部署 `<Samples Path>` \Orchestrations\HelloWorld 文件夹中的 HelloWorld 业务流程。</span><span class="sxs-lookup"><span data-stu-id="e0380-176">Compiles and deploys the HelloWorld orchestration in the `<Samples Path>`\Orchestrations\HelloWorld folder.</span></span>  
  
    -   <span data-ttu-id="e0380-177">修改 HelloWorld 业务流程的公钥标记</span><span class="sxs-lookup"><span data-stu-id="e0380-177">Modifies the public key token for the HelloWorld orchestration</span></span>  
  
    -   <span data-ttu-id="e0380-178">部署 BAM 活动定义和跟踪配置文件编辑器文件</span><span class="sxs-lookup"><span data-stu-id="e0380-178">Deploys the BAM Activity Definition and Tracking Profile Editor file</span></span>  
  
    -   <span data-ttu-id="e0380-179">重命名输出目录</span><span class="sxs-lookup"><span data-stu-id="e0380-179">Renames the out directory</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0380-180">若要中止安装，请在第一个“按任意键继续”提示下按 Ctrl+C。</span><span class="sxs-lookup"><span data-stu-id="e0380-180">To abort the installation, press CTRL+C at the first "press any key to continue" prompt.</span></span> <span data-ttu-id="e0380-181">此操作将停止脚本，并将 HelloWorld 示例保留在其原始状态。</span><span class="sxs-lookup"><span data-stu-id="e0380-181">This stops the script and leaves the HelloWorld sample in its original state.</span></span> <span data-ttu-id="e0380-182">在第二个和最终提示下按 Ctrl+C 不会停止安装。</span><span class="sxs-lookup"><span data-stu-id="e0380-182">Pressing CTRL+C on the second and final prompt does not stop the installation.</span></span> <span data-ttu-id="e0380-183">在这种情况下，请运行 Cleanup.bat 卸载 OperationsOM 示例并还原 HelloWorld 示例。</span><span class="sxs-lookup"><span data-stu-id="e0380-183">In this case, run Cleanup.bat to uninstall the OperationsOM sample and restore the HelloWorld sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="e0380-184">运行本示例</span><span class="sxs-lookup"><span data-stu-id="e0380-184">Running This Sample</span></span>  
 <span data-ttu-id="e0380-185">使用以下过程运行 OperationsOM 示例。</span><span class="sxs-lookup"><span data-stu-id="e0380-185">Use the following procedure to run the OperationsOM sample.</span></span>  
  
#### <a name="to-compile-and-run-the-sample"></a><span data-ttu-id="e0380-186">编译并运行本示例</span><span class="sxs-lookup"><span data-stu-id="e0380-186">To compile and run the sample</span></span>  
  
1.  <span data-ttu-id="e0380-187">单击**启动**，选择**所有程序**，选择**Microsoft BizTalk Server**，然后选择**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="e0380-187">Click **Start**, select **All Programs**, select **Microsoft BizTalk Server**, and then select **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="e0380-188">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**托管实例**。</span><span class="sxs-lookup"><span data-stu-id="e0380-188">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Host Instances**.</span></span>  
  
3.  <span data-ttu-id="e0380-189">右键单击**BizTalkServerApplication**，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="e0380-189">Right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0380-190">如果自从配置产品以来尚未重新启动 BizTalkServerApplication 主机实例，可能需要重新启动此主机实例以便为 BAM 设置正确的工作数据库。</span><span class="sxs-lookup"><span data-stu-id="e0380-190">Restarting the BizTalkServerApplication host instance may be necessary to set the correct working database for BAM if you have not restarted the host instance since configuring the product.</span></span>  
  
4.  <span data-ttu-id="e0380-191">从 Windows 资源管理器，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="e0380-191">From Windows Explorer, navigate to the following folder:</span></span>  
  
     `<Samples Path>\Admin\OperationsOM\OperationSamples`  
  
5.  <span data-ttu-id="e0380-192">双击**OperationsOM.sln**项目文件以将其加载到[!INCLUDE[vs2010](../includes/vs2010-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e0380-192">Double-click the **OperationsOM.sln** project file to load it into [!INCLUDE[vs2010](../includes/vs2010-md.md)].</span></span>  
  
6.  <span data-ttu-id="e0380-193">按 F5 键运行本示例。</span><span class="sxs-lookup"><span data-stu-id="e0380-193">Press F5 to run the sample.</span></span>  
  
     <span data-ttu-id="e0380-194">-或者-</span><span class="sxs-lookup"><span data-stu-id="e0380-194">-- OR --</span></span>  
  
     <span data-ttu-id="e0380-195">上**生成**菜单上，单击**重新生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="e0380-195">On the **Build** menu, click **Rebuild Solution**.</span></span> <span data-ttu-id="e0380-196">生成完成后，使用 Windows 资源管理器导航到`<Samples Path>\Admin\OperationsOM\OperationSamples\bin\Debug,`然后双击**OperationsSamples.exe**。</span><span class="sxs-lookup"><span data-stu-id="e0380-196">When the build is complete, use Windows Explorer to navigate to `<Samples Path>\Admin\OperationsOM\OperationSamples\bin\Debug,` and then double-click **OperationsSamples.exe**.</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="e0380-197">本示例中使用的类或方法</span><span class="sxs-lookup"><span data-stu-id="e0380-197">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="e0380-198">[Microsoft.BizTalk.Operations.BizTalkOperations](http://msdn.microsoft.com/library/microsoft.biztalk.operations.biztalkoperations.aspx)&#124;[Microsoft.BizTalk.Operations.MessageFlow](http://msdn.microsoft.com/library/microsoft.biztalk.operations.messageflow.aspx)&#124;[Microsoft.BizTalk.Operations.SendPortInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.sendportinstance.aspx)&#124;[Microsoft.BizTalk.Operations.RoutingFailureInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.routingfailureinstance.aspx)&#124;[Microsoft.BizTalk.Operations.OrchestrationInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.orchestrationinstance.aspx)&#124;[Microsoft.BizTalk.Operations.MSMQtInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.msmqtinstance.aspx)&#124;[Microsoft.BizTalk.Operations.TrackedServiceInstance](http://msdn.microsoft.com/library/Microsoft.BizTalk.Operations.TrackedServiceInstance.aspx)</span><span class="sxs-lookup"><span data-stu-id="e0380-198">[Microsoft.BizTalk.Operations.BizTalkOperations](http://msdn.microsoft.com/library/microsoft.biztalk.operations.biztalkoperations.aspx)&#124; [Microsoft.BizTalk.Operations.MessageFlow](http://msdn.microsoft.com/library/microsoft.biztalk.operations.messageflow.aspx)&#124; [Microsoft.BizTalk.Operations.SendPortInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.sendportinstance.aspx)&#124; [Microsoft.BizTalk.Operations.RoutingFailureInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.routingfailureinstance.aspx)&#124; [Microsoft.BizTalk.Operations.OrchestrationInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.orchestrationinstance.aspx)&#124; [Microsoft.BizTalk.Operations.MSMQtInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.msmqtinstance.aspx)&#124; [Microsoft.BizTalk.Operations.TrackedServiceInstance](http://msdn.microsoft.com/library/Microsoft.BizTalk.Operations.TrackedServiceInstance.aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0380-199">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0380-199">See Also</span></span>  
 [<span data-ttu-id="e0380-200">管理员-OperationsOM （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="e0380-200">Admin-OperationsOM (BizTalk Server Samples Folder)</span></span>](../core/admin-operationsom-biztalk-server-samples-folder.md)