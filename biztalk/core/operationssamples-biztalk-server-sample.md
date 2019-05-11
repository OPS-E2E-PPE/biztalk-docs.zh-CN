---
title: OperationsSamples （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c9e3f3e-a570-4edd-aa2e-3f8e2e37c8a0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5101e047c41e12f322639986179b4b87504da75f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262936"
---
# <a name="operationssamples-biztalk-server-sample"></a><span data-ttu-id="f7d18-102">OperationsSamples （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="f7d18-102">OperationsSamples (BizTalk Server Sample)</span></span>
<span data-ttu-id="f7d18-103">OperationsSamples 示例演示如何使用操作对象模型执行操作活动。</span><span class="sxs-lookup"><span data-stu-id="f7d18-103">The OperationsSamples sample demonstrates how to perform operational activities using the Operations object model.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="f7d18-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="f7d18-104">What This Sample Does</span></span>  
 <span data-ttu-id="f7d18-105">此示例将演示如下：</span><span class="sxs-lookup"><span data-stu-id="f7d18-105">This sample demonstrates the following:</span></span>  
  
- <span data-ttu-id="f7d18-106">如何使用跟踪配置文件注释与活动的业务流程。</span><span class="sxs-lookup"><span data-stu-id="f7d18-106">How to use a tracking profile to comment an orchestration with activities.</span></span>  
  
- <span data-ttu-id="f7d18-107">如何使用 BAM 跟踪数据库查找活动 ID，然后使用该 ID 来查找相关业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="f7d18-107">How to use the BAM tracking database to find an activity ID and then use the ID to find a related orchestration instance.</span></span>  
  
- <span data-ttu-id="f7d18-108">如何查找和处理消息流通过使用**MessageFlow**类和其他操作对象模型类和 Api。</span><span class="sxs-lookup"><span data-stu-id="f7d18-108">How to find and work with message flows by using the **MessageFlow** class and other Operations object model classes and APIs.</span></span>  
  
- <span data-ttu-id="f7d18-109">如何访问端口、 消息和其他实例使用的类派生自**实例**类。</span><span class="sxs-lookup"><span data-stu-id="f7d18-109">How to access ports, messages, and other instances by using classes derived from the **Instance** class.</span></span>  
  
  <span data-ttu-id="f7d18-110">该示例包含很多有用的帮助器类和方法以支持更高版本的操作。</span><span class="sxs-lookup"><span data-stu-id="f7d18-110">The sample contains many useful helper classes and methods to support the operations above.</span></span> <span data-ttu-id="f7d18-111">下一节中讨论这些和其他代码重点。</span><span class="sxs-lookup"><span data-stu-id="f7d18-111">These and other code highlights are discussed in the next section.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="f7d18-112">此示例设计方式和原因</span><span class="sxs-lookup"><span data-stu-id="f7d18-112">How This Sample Is Designed and Why</span></span>  
 <span data-ttu-id="f7d18-113">本示例旨在演示的几个关键类和操作对象模型中的方法并显示如何查询公用 BAM 跟踪数据库。</span><span class="sxs-lookup"><span data-stu-id="f7d18-113">This sample is designed to demonstrate several of the key classes and methods in the Operations object model and to show how to query the publicly available BAM tracking database.</span></span>  
  
 <span data-ttu-id="f7d18-114">操作对象模型包含提供的功能来处理消息和 BizTalk Server 中的其他实例的类。</span><span class="sxs-lookup"><span data-stu-id="f7d18-114">The Operations object model contains classes that provide the ability to manipulate messages and other instances within BizTalk Server.</span></span>  
  
### <a name="using-a-bam-activity-id"></a><span data-ttu-id="f7d18-115">使用 BAM 活动 ID</span><span class="sxs-lookup"><span data-stu-id="f7d18-115">Using a BAM Activity ID</span></span>  
 <span data-ttu-id="f7d18-116">此示例演示如何与 BAM 交互以及如何使用跟踪数据库中的公用视图通过使用业务数据在消息框中查找实时消息。</span><span class="sxs-lookup"><span data-stu-id="f7d18-116">This sample shows how to interact with BAM and how to use the publicly available views in the tracking database to locate a live message in the message box by using business data.</span></span> <span data-ttu-id="f7d18-117">此示例通过检索与采购订单号相对应的业务流程 ID 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="f7d18-117">The sample does this by retrieving an orchestration ID corresponding to a purchase order number.</span></span> <span data-ttu-id="f7d18-118">若要成功执行此任务，必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f7d18-118">For this task to succeed, it must do the following:</span></span>  
  
1. <span data-ttu-id="f7d18-119">使用业务数据 （采购订单编号） 查找活动 id。</span><span class="sxs-lookup"><span data-stu-id="f7d18-119">Use business data (a purchase order number) to find an activity ID.</span></span> <span data-ttu-id="f7d18-120">此步骤将业务数据映射到可用于查找其他信息的内部 ID。</span><span class="sxs-lookup"><span data-stu-id="f7d18-120">This step maps business data to an internal ID that can be used to find additional information.</span></span>  
  
2. <span data-ttu-id="f7d18-121">检索活动 id。 与相关的 BAM 引用。</span><span class="sxs-lookup"><span data-stu-id="f7d18-121">Retrieve the BAM references related to the activity ID.</span></span>  
  
3. <span data-ttu-id="f7d18-122">找到的揃"BizTalkService"类型，而是指业务流程的引用。</span><span class="sxs-lookup"><span data-stu-id="f7d18-122">Find a reference that has a type of "BizTalkService" and refers to an orchestration.</span></span> <span data-ttu-id="f7d18-123">如果找到一个对象，返回其实例 id。</span><span class="sxs-lookup"><span data-stu-id="f7d18-123">If one is found, return its instance ID.</span></span>  
  
   <span data-ttu-id="f7d18-124">提供此功能**BAMWebService.GetOrchestrationID**静态方法和关联的帮助程序方法包括 BamManagementService.cs 源文件中的类和方法。</span><span class="sxs-lookup"><span data-stu-id="f7d18-124">This functionality is provided by the **BAMWebService.GetOrchestrationID** static method and associated helper methods including classes and methods in the BamManagementService.cs source file.</span></span>  
  
### <a name="suspending-terminating-and-resuming-an-instance"></a><span data-ttu-id="f7d18-125">挂起、 终止和恢复实例</span><span class="sxs-lookup"><span data-stu-id="f7d18-125">Suspending, Terminating, and Resuming an Instance</span></span>  
 <span data-ttu-id="f7d18-126">示例程序包含**Samples.OperateOnInstance**操作和实例 ID，并执行指定的操作的实例上的方法。</span><span class="sxs-lookup"><span data-stu-id="f7d18-126">The sample program includes a **Samples.OperateOnInstance** method that takes an operation and instance ID and performs the specified operation on the instance.</span></span> <span data-ttu-id="f7d18-127">由定义有效的操作**InstanceOperation**枚举并包括挂起、 终止和恢复。</span><span class="sxs-lookup"><span data-stu-id="f7d18-127">Valid operations are defined by the **InstanceOperation** enumeration and include Suspend, Terminate, and Resume.</span></span> <span data-ttu-id="f7d18-128">这些操作直接映射到 BizTalkOperations 类的方法 —**: SuspendInstance**， **TerminateInstance**，并**ResumeInstance**。</span><span class="sxs-lookup"><span data-stu-id="f7d18-128">These operations map directly to methods of the BizTalkOperations class—**SuspendInstance**, **TerminateInstance**, and **ResumeInstance**.</span></span>  
  
 <span data-ttu-id="f7d18-129">请注意，该方法处理 ArgumentException 和 SqlException 异常。</span><span class="sxs-lookup"><span data-stu-id="f7d18-129">Notice that the method handles both ArgumentException and SqlException exceptions.</span></span> <span data-ttu-id="f7d18-130">您必须谨慎预测异常 — 包括 SqlException — 时使用的类和操作对象模型中的方法。</span><span class="sxs-lookup"><span data-stu-id="f7d18-130">You must be careful to anticipate exceptions—including SqlException—when working with the classes and methods in the Operations object model.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7d18-131">很多的操作方法需要对数据库的访问。</span><span class="sxs-lookup"><span data-stu-id="f7d18-131">Many of the Operations methods require access to the database.</span></span> <span data-ttu-id="f7d18-132">应预测这些方法引发的异常并进行相应处理。</span><span class="sxs-lookup"><span data-stu-id="f7d18-132">You should anticipate the exceptions thrown by these methods and handle them appropriately.</span></span>  
  
### <a name="retrieving-all-live-messages"></a><span data-ttu-id="f7d18-133">检索所有实时消息</span><span class="sxs-lookup"><span data-stu-id="f7d18-133">Retrieving All Live Messages</span></span>  
 <span data-ttu-id="f7d18-134">操作对象模型可以直观地循环访问所有可用实时消息，如下面的代码段中所示可以：</span><span class="sxs-lookup"><span data-stu-id="f7d18-134">The Operations object model makes it straightforward to iterate over all of the available live messages, as shown in the following code fragment:</span></span>  
  
```  
BizTalkOperations _operations = new BizTalkOperations()  
IEnumerable messages = _operations.GetMessages();  
foreach (BizTalkMessage msg in messages)  
…  
```  
  
 <span data-ttu-id="f7d18-135">OperationsSamples 程序采用这一步演示了如何访问有关每个消息，包括消息 ID、 消息类型以及数量和类型的消息部分的信息。</span><span class="sxs-lookup"><span data-stu-id="f7d18-135">The OperationsSamples program takes this a step further by demonstrating how to access information about each message, including message ID and message type along with the number and types of message parts.</span></span> <span data-ttu-id="f7d18-136">您可以修改此代码，并使用它在方案中需要循环访问大多数或所有可用实时消息在 BizTalk Server 中。</span><span class="sxs-lookup"><span data-stu-id="f7d18-136">You can modify this code and use it in scenarios where you have to iterate through many or all of the available live messages in BizTalk Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7d18-137">可能有数百或数千个消息可用。</span><span class="sxs-lookup"><span data-stu-id="f7d18-137">There may be hundreds or thousands of messages available.</span></span> <span data-ttu-id="f7d18-138">扫描整个列表可能会影响性能。</span><span class="sxs-lookup"><span data-stu-id="f7d18-138">Scanning the entire list may adversely affect performance.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="f7d18-139">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="f7d18-139">Where to Find This Sample</span></span>  
 <span data-ttu-id="f7d18-140">本示例位于以下 SDK 位置中：</span><span class="sxs-lookup"><span data-stu-id="f7d18-140">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="f7d18-141">\<*Samples Path*\>\Admin\OperationsOM\OperationsSamples\\</span><span class="sxs-lookup"><span data-stu-id="f7d18-141">\<*Samples Path*\>\Admin\OperationsOM\OperationsSamples\\</span></span>  
  
 <span data-ttu-id="f7d18-142">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="f7d18-142">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="f7d18-143">文件</span><span class="sxs-lookup"><span data-stu-id="f7d18-143">File(s)</span></span>|<span data-ttu-id="f7d18-144">Description</span><span class="sxs-lookup"><span data-stu-id="f7d18-144">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f7d18-145">BamManagementService.cs</span><span class="sxs-lookup"><span data-stu-id="f7d18-145">BamManagementService.cs</span></span>|<span data-ttu-id="f7d18-146">BAM Web 服务的 web 代理类。</span><span class="sxs-lookup"><span data-stu-id="f7d18-146">Web proxy class for the BAM Web service.</span></span>|  
|<span data-ttu-id="f7d18-147">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="f7d18-147">Cleanup.bat</span></span>|<span data-ttu-id="f7d18-148">删除示例业务流程，并将 HelloWorld 示例还原到其原始状态。</span><span class="sxs-lookup"><span data-stu-id="f7d18-148">Removes the sample orchestration and restores the HelloWorld sample to its original state.</span></span>|  
|<span data-ttu-id="f7d18-149">HelloOrchestration.btt</span><span class="sxs-lookup"><span data-stu-id="f7d18-149">HelloOrchestration.btt</span></span>|<span data-ttu-id="f7d18-150">跟踪配置文件用于将 BizTalk 事件源映射到 BAM 目标活动。</span><span class="sxs-lookup"><span data-stu-id="f7d18-150">Tracking profile used to map BizTalk event sources to BAM target activities.</span></span>|  
|<span data-ttu-id="f7d18-151">HelloOrchestration.xls</span><span class="sxs-lookup"><span data-stu-id="f7d18-151">HelloOrchestration.xls</span></span>|<span data-ttu-id="f7d18-152">BAM 定义样式表。</span><span class="sxs-lookup"><span data-stu-id="f7d18-152">BAM definition style sheet.</span></span>|  
|<span data-ttu-id="f7d18-153">OperationsSamples.cs</span><span class="sxs-lookup"><span data-stu-id="f7d18-153">OperationsSamples.cs</span></span>|<span data-ttu-id="f7d18-154">C#包含演示操作对象模型的各个方面的代码的源文件。</span><span class="sxs-lookup"><span data-stu-id="f7d18-154">C# source file containing code that demonstrates various aspects of the Operations object model.</span></span>|  
|<span data-ttu-id="f7d18-155">OperationsSamples.csproj、 operationssamples.sln 和 AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="f7d18-155">OperationsSamples.csproj, OperationsSamples.sln, AssemblyInfo.cs</span></span>|<span data-ttu-id="f7d18-156">此示例的项目、 解决方案和程序集信息文件。</span><span class="sxs-lookup"><span data-stu-id="f7d18-156">Project, solution, and assembly information files for this sample.</span></span>|  
|<span data-ttu-id="f7d18-157">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="f7d18-157">Setup.bat</span></span>|<span data-ttu-id="f7d18-158">用于生成和初始化本示例通过修改 HelloWorld 业务流程示例。</span><span class="sxs-lookup"><span data-stu-id="f7d18-158">Used to build and initialize this sample by modifying the HelloWorld orchestration sample.</span></span> <span data-ttu-id="f7d18-159">它安装示例业务流程，将部署 BAM 活动定义和跟踪配置文件编辑器文件、 配置端口，并将示例文件放入接收位置。</span><span class="sxs-lookup"><span data-stu-id="f7d18-159">It installs a sample orchestration, deploys a BAM Activity Definition and a Tracking Profile Editor file, configures ports, and drops a sample file into the receive location.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="f7d18-160">如何使用此示例</span><span class="sxs-lookup"><span data-stu-id="f7d18-160">How to Use This Sample</span></span>  
 <span data-ttu-id="f7d18-161">此示例用于浏览操作对象模型中可用的功能。</span><span class="sxs-lookup"><span data-stu-id="f7d18-161">Use this sample to explore the functionality available in the Operations object model.</span></span> <span data-ttu-id="f7d18-162">修改现有例程以查找并以不同方式处理消息，或添加复制 BizTalk Server 管理控制台中的组中心的某些部分的新代码。</span><span class="sxs-lookup"><span data-stu-id="f7d18-162">Modify existing routines to find and work with messages differently or add new code that replicates portions of the Group Hub in the BizTalk Server Management console.</span></span>  
  
 <span data-ttu-id="f7d18-163">您也可以考虑的一些以下任务：</span><span class="sxs-lookup"><span data-stu-id="f7d18-163">You may also consider some of the following tasks:</span></span>  
  
-   <span data-ttu-id="f7d18-164">编写的应用程序复制到自定义应用程序的组中心最常用的子集。</span><span class="sxs-lookup"><span data-stu-id="f7d18-164">Write an application that replicates the most-used subset of the Group Hub into a custom application.</span></span>  
  
-   <span data-ttu-id="f7d18-165">编写自定义的预配应用程序创建端口并为新贸易合作伙伴发送测试消息。</span><span class="sxs-lookup"><span data-stu-id="f7d18-165">Write a custom provisioning application that creates ports and sends a test message through for new trading partners.</span></span>  
  
-   <span data-ttu-id="f7d18-166">将示例程序修改为提供有关单个采购订单或一系列屏幕、 XML 文件或文本报告到的采购订单信息的命令行实用工具。</span><span class="sxs-lookup"><span data-stu-id="f7d18-166">Modify the sample program into a command-line utility that provides information about a single purchase order or a range of purchase orders to the screen, an XML file, or a text report.</span></span>  
  
## <a name="installing-sample-support-files"></a><span data-ttu-id="f7d18-167">安装示例支持文件</span><span class="sxs-lookup"><span data-stu-id="f7d18-167">Installing Sample Support Files</span></span>  
 <span data-ttu-id="f7d18-168">本部分将指导完成安装和运行示例所需的过程。</span><span class="sxs-lookup"><span data-stu-id="f7d18-168">This section walks through the procedures required to install and run the sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7d18-169">在安装和运行此示例之前, 必须验证 BAM 已安装并且正常工作。</span><span class="sxs-lookup"><span data-stu-id="f7d18-169">Before installing and running this sample, you must verify that BAM has been installed and is functioning.</span></span> <span data-ttu-id="f7d18-170">如果尚未安装 BAM，本示例不起作用。</span><span class="sxs-lookup"><span data-stu-id="f7d18-170">If BAM has not been installed, this sample will not work.</span></span>  
  
#### <a name="to-compile-and-install-the-support-files-for-this-sample"></a><span data-ttu-id="f7d18-171">若要编译并安装此示例的支持文件</span><span class="sxs-lookup"><span data-stu-id="f7d18-171">To compile and install the support files for this sample</span></span>  
  
1.  <span data-ttu-id="f7d18-172">在命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="f7d18-172">In a command window, navigate to the following folder:</span></span>  
  
     `<Samples Path>\Admin\OperationsOM\OperationSamples`  
  
2.  <span data-ttu-id="f7d18-173">运行 Setup.bat，将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f7d18-173">Run Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="f7d18-174">创建发送端口和接收目录</span><span class="sxs-lookup"><span data-stu-id="f7d18-174">Creates send and receive directories</span></span>  
  
    -   <span data-ttu-id="f7d18-175">创建并启动发送端口和接收端口</span><span class="sxs-lookup"><span data-stu-id="f7d18-175">Creates and starts send and receive ports</span></span>  
  
    -   <span data-ttu-id="f7d18-176">编译并部署中的 HelloWorld 业务流程`<Samples Path>`\Orchestrations\HelloWorld 文件夹。</span><span class="sxs-lookup"><span data-stu-id="f7d18-176">Compiles and deploys the HelloWorld orchestration in the `<Samples Path>`\Orchestrations\HelloWorld folder.</span></span>  
  
    -   <span data-ttu-id="f7d18-177">修改 HelloWorld 业务流程的公钥标记</span><span class="sxs-lookup"><span data-stu-id="f7d18-177">Modifies the public key token for the HelloWorld orchestration</span></span>  
  
    -   <span data-ttu-id="f7d18-178">部署 BAM 活动定义和跟踪配置文件编辑器文件</span><span class="sxs-lookup"><span data-stu-id="f7d18-178">Deploys the BAM Activity Definition and Tracking Profile Editor file</span></span>  
  
    -   <span data-ttu-id="f7d18-179">重命名输出目录</span><span class="sxs-lookup"><span data-stu-id="f7d18-179">Renames the out directory</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f7d18-180">若要中止安装，请在第一个"按任意键继续"提示符处按 CTRL + C。</span><span class="sxs-lookup"><span data-stu-id="f7d18-180">To abort the installation, press CTRL+C at the first "press any key to continue" prompt.</span></span> <span data-ttu-id="f7d18-181">这会停止该脚本并将 HelloWorld 示例保留在其原始状态。</span><span class="sxs-lookup"><span data-stu-id="f7d18-181">This stops the script and leaves the HelloWorld sample in its original state.</span></span> <span data-ttu-id="f7d18-182">在第二个和最后一个提示符处按 CTRL + C 不会停止安装。</span><span class="sxs-lookup"><span data-stu-id="f7d18-182">Pressing CTRL+C on the second and final prompt does not stop the installation.</span></span> <span data-ttu-id="f7d18-183">在这种情况下，运行 Cleanup.bat 卸载 OperationsOM 示例并还原 HelloWorld 示例。</span><span class="sxs-lookup"><span data-stu-id="f7d18-183">In this case, run Cleanup.bat to uninstall the OperationsOM sample and restore the HelloWorld sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="f7d18-184">运行本示例</span><span class="sxs-lookup"><span data-stu-id="f7d18-184">Running This Sample</span></span>  
 <span data-ttu-id="f7d18-185">使用以下过程运行 OperationsOM 示例。</span><span class="sxs-lookup"><span data-stu-id="f7d18-185">Use the following procedure to run the OperationsOM sample.</span></span>  
  
#### <a name="to-compile-and-run-the-sample"></a><span data-ttu-id="f7d18-186">若要编译并运行示例</span><span class="sxs-lookup"><span data-stu-id="f7d18-186">To compile and run the sample</span></span>  
  
1.  <span data-ttu-id="f7d18-187">单击**启动**，选择**所有程序**，选择**Microsoft BizTalk Server**，然后选择**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="f7d18-187">Click **Start**, select **All Programs**, select **Microsoft BizTalk Server**, and then select **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="f7d18-188">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="f7d18-188">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Host Instances**.</span></span>  
  
3.  <span data-ttu-id="f7d18-189">右键单击**BizTalkServerApplication**，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="f7d18-189">Right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f7d18-190">重新启动 BizTalkServerApplication 主机实例可能有必要; 如果不重新启动主机实例配置产品以来，则为 BAM 设置正确的工作数据库。</span><span class="sxs-lookup"><span data-stu-id="f7d18-190">Restarting the BizTalkServerApplication host instance may be necessary to set the correct working database for BAM if you have not restarted the host instance since configuring the product.</span></span>  
  
4.  <span data-ttu-id="f7d18-191">从 Windows 资源管理器，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="f7d18-191">From Windows Explorer, navigate to the following folder:</span></span>  
  
     `<Samples Path>\Admin\OperationsOM\OperationSamples`  
  
5.  <span data-ttu-id="f7d18-192">双击**OperationsOM.sln**要加载到 Visual Studio 项目文件。</span><span class="sxs-lookup"><span data-stu-id="f7d18-192">Double-click the **OperationsOM.sln** project file to load it into Visual Studio.</span></span>  
  
6.  <span data-ttu-id="f7d18-193">按 F5 以运行示例。</span><span class="sxs-lookup"><span data-stu-id="f7d18-193">Press F5 to run the sample.</span></span>  
  
     <span data-ttu-id="f7d18-194">-- OR --</span><span class="sxs-lookup"><span data-stu-id="f7d18-194">-- OR --</span></span>  
  
     <span data-ttu-id="f7d18-195">上**构建**菜单上，单击**重新生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="f7d18-195">On the **Build** menu, click **Rebuild Solution**.</span></span> <span data-ttu-id="f7d18-196">生成完成后，使用 Windows 资源管理器导航到`<Samples Path>\Admin\OperationsOM\OperationSamples\bin\Debug,`，然后双击**OperationsSamples.exe**。</span><span class="sxs-lookup"><span data-stu-id="f7d18-196">When the build is complete, use Windows Explorer to navigate to `<Samples Path>\Admin\OperationsOM\OperationSamples\bin\Debug,` and then double-click **OperationsSamples.exe**.</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="f7d18-197">类或方法在此示例中使用</span><span class="sxs-lookup"><span data-stu-id="f7d18-197">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="f7d18-198">[Microsoft.BizTalk.Operations.BizTalkOperations](http://msdn.microsoft.com/library/microsoft.biztalk.operations.biztalkoperations.aspx) &#124; [Microsoft.BizTalk.Operations.MessageFlow](http://msdn.microsoft.com/library/microsoft.biztalk.operations.messageflow.aspx) &#124; [Microsoft.BizTalk.Operations.SendPortInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.sendportinstance.aspx)&#124; [Microsoft.BizTalk.Operations.RoutingFailureInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.routingfailureinstance.aspx) &#124; [Microsoft.BizTalk.Operations.OrchestrationInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.orchestrationinstance.aspx) &#124; [Microsoft.BizTalk.Operations.MSMQtInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.msmqtinstance.aspx) &#124; [Microsoft.BizTalk.Operations.TrackedServiceInstance](http://msdn.microsoft.com/library/Microsoft.BizTalk.Operations.TrackedServiceInstance.aspx)</span><span class="sxs-lookup"><span data-stu-id="f7d18-198">[Microsoft.BizTalk.Operations.BizTalkOperations](http://msdn.microsoft.com/library/microsoft.biztalk.operations.biztalkoperations.aspx)&#124; [Microsoft.BizTalk.Operations.MessageFlow](http://msdn.microsoft.com/library/microsoft.biztalk.operations.messageflow.aspx)&#124; [Microsoft.BizTalk.Operations.SendPortInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.sendportinstance.aspx)&#124; [Microsoft.BizTalk.Operations.RoutingFailureInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.routingfailureinstance.aspx)&#124; [Microsoft.BizTalk.Operations.OrchestrationInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.orchestrationinstance.aspx)&#124; [Microsoft.BizTalk.Operations.MSMQtInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.msmqtinstance.aspx)&#124; [Microsoft.BizTalk.Operations.TrackedServiceInstance](http://msdn.microsoft.com/library/Microsoft.BizTalk.Operations.TrackedServiceInstance.aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7d18-199">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7d18-199">See Also</span></span>  
 [<span data-ttu-id="f7d18-200">Admin-OperationsOM（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="f7d18-200">Admin-OperationsOM (BizTalk Server Samples Folder)</span></span>](../core/admin-operationsom-biztalk-server-samples-folder.md)