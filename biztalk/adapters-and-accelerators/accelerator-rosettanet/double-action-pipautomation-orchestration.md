---
title: 双操作 PIPAutomation 业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9159f7b1-cb83-41f1-8637-39c5ddcc63ae
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f04b04d20189307c3d42e60c43c2c4c9254ffb7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008422"
---
# <a name="double-action-pipautomation-orchestration"></a><span data-ttu-id="5c35f-102">双操作 PIPAutomation 业务流程</span><span class="sxs-lookup"><span data-stu-id="5c35f-102">Double Action PIPAutomation Orchestration</span></span>
<span data-ttu-id="5c35f-103">此 DoubleAction.odx 示例演示如何实现为双操作合作伙伴接口流程 (PIP) 0C2、0C4、3A2 和 3A4 自动生成响应的业务流程。</span><span class="sxs-lookup"><span data-stu-id="5c35f-103">The DoubleAction.odx sample illustrates how to implement an orchestration to automatically generate responses for the double-action Partner Interface Processes (PIPs) 0C2, 0C4, 3A2, and 3A4.</span></span> <span data-ttu-id="5c35f-104">你可将此示例项目扩展为支持其他双操作 PIP。</span><span class="sxs-lookup"><span data-stu-id="5c35f-104">You can extend this sample project to support additional double-action PIPs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c35f-105">该示例文件夹中提供的映射为示例映射。</span><span class="sxs-lookup"><span data-stu-id="5c35f-105">The maps provided in the sample folder are samples.</span></span> <span data-ttu-id="5c35f-106">若要使用这些映射，必须根据你的具体要求来更改它们。</span><span class="sxs-lookup"><span data-stu-id="5c35f-106">To use them, you must change them based on your specific requirements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c35f-107">在扩展此示例项目时，只能扩展为支持其他双操作 PIP，而不能扩展为支持单操作 PIP。</span><span class="sxs-lookup"><span data-stu-id="5c35f-107">You should extend this sample project to support double-action PIPs only, not single-action PIPs.</span></span> <span data-ttu-id="5c35f-108">如果将此业务流程扩展为处理单操作 PIP，则它将返回一个错误。</span><span class="sxs-lookup"><span data-stu-id="5c35f-108">This orchestration will return an error if you extend it to process a single-action PIP.</span></span> <span data-ttu-id="5c35f-109">若要确保此业务流程不处理单操作 PIP，请参阅下面的“筛选单操作消息”部分。</span><span class="sxs-lookup"><span data-stu-id="5c35f-109">To ensure that this orchestration will not process single-action PIPs, see the Filtering Out Single-Action Messages section below.</span></span>  
  
 <span data-ttu-id="5c35f-110">默认情况下，Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]安装程序将安装在此示例\<*驱动器*\>: \Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction。</span><span class="sxs-lookup"><span data-stu-id="5c35f-110">By default, the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Setup program installs this sample in \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction.</span></span>  
  
 <span data-ttu-id="5c35f-111">此示例项目包含以下内容：</span><span class="sxs-lookup"><span data-stu-id="5c35f-111">This sample project includes:</span></span>  
  
- <span data-ttu-id="5c35f-112">存储的过程 (`PipAutomationGetAction)`检索新操作消息 Pip 0c2、 0c4、 3A2 和 3A4。</span><span class="sxs-lookup"><span data-stu-id="5c35f-112">A stored procedure (`PipAutomationGetAction)` to retrieve new action messages for the PIPs 0C2, 0C4, 3A2, and 3A4.</span></span>  
  
- <span data-ttu-id="5c35f-113">一个绑定到 SQL 存储过程的接收位置 (MessagesToLOB_Receive_Location)。</span><span class="sxs-lookup"><span data-stu-id="5c35f-113">A receive location (MessagesToLOB_Receive_Location) bound to the SQL stored procedure.</span></span>  
  
- <span data-ttu-id="5c35f-114">一个业务流程 (DoubleAction.odx)，用于处理每个 PIP，根据映射生成每个 PIP 的相应响应，以及将响应保存到 BTARNDATA 数据库的 MessagesFromLOB 表中。</span><span class="sxs-lookup"><span data-stu-id="5c35f-114">An orchestration (DoubleAction.odx) that processes each PIP, generates the appropriate response based on a map for each PIP, and saves the response in the MessagesFromLOB table of the BTARNDATA database.</span></span> <span data-ttu-id="5c35f-115">该业务流程使用 Microsoft.Solutions.BTARN.Shared.dll 中的 `RNIFSubmit` 方法来提交消息。</span><span class="sxs-lookup"><span data-stu-id="5c35f-115">The orchestration uses the `RNIFSubmit` method from Microsoft.Solutions.BTARN.Shared.dll to submit the message.</span></span>  
  
- <span data-ttu-id="5c35f-116">一个绑定文件 (DoubleActionBinding.xml)，文件 Setup.bat 使用该绑定文件创建用于 DoubleAction 业务流程的 MessagesToLOB_Receive_Port。</span><span class="sxs-lookup"><span data-stu-id="5c35f-116">A binding file (DoubleActionBinding.xml) that the file Setup.bat uses to create the MessagesToLOB_Receive_Port for use with the DoubleAction orchestration.</span></span>  
  
- <span data-ttu-id="5c35f-117">一个生成和初始化该示例的安装文件。</span><span class="sxs-lookup"><span data-stu-id="5c35f-117">A setup file to build and initialize the sample.</span></span> <span data-ttu-id="5c35f-118">如果 BizTalk Server 正在运行的 32 位计算机上，在运行文件 setup.bat\<驱动器\>: \Program Files\Microsoft BizTalk Accelerator for RosettaNet \SDK\PIPAutomation\DoubleAction 文件夹。</span><span class="sxs-lookup"><span data-stu-id="5c35f-118">If BizTalk Server is running on a 32-bit computer, run the file setup.bat in the \<drive\>:\Program Files\Microsoft BizTalk Accelerator for RosettaNet \SDK\PIPAutomation\DoubleAction folder.</span></span> <span data-ttu-id="5c35f-119">如果 BizTalk Server 正在运行的 64 位计算机上，运行同一文件夹中的 setupx64.bat。</span><span class="sxs-lookup"><span data-stu-id="5c35f-119">If BizTalk Server is running on a 64-bit computer, run setupx64.bat in the same folder.</span></span>  
  
  <span data-ttu-id="5c35f-120">该业务流程使用 BTARNData 数据库中的 PipAutomationGetAction 存储过程（源文件为 DoubleAction 目录中的 DoubleAction.sql）来接收消息。</span><span class="sxs-lookup"><span data-stu-id="5c35f-120">The orchestration receives messages using the PipAutomationGetAction stored procedure in the BTARNData database (the source file is DoubleAction.sql in the DoubleAction directory).</span></span> <span data-ttu-id="5c35f-121">此存储过程从 MessagesToLOB 表中检索消息。</span><span class="sxs-lookup"><span data-stu-id="5c35f-121">This stored procedure retrieves the messages from the MessagesToLOB table.</span></span>  
  
  <span data-ttu-id="5c35f-122">若要扩展此示例项目以支持其他双操作 PIP，可在该双操作 PIP 的业务流程中添加路径。</span><span class="sxs-lookup"><span data-stu-id="5c35f-122">To extend this sample project to support additional double-action PIPs, add a path in the orchestration for the double-action PIP.</span></span> <span data-ttu-id="5c35f-123">此路径应包含一个映射，将响应消息构造为请求消息。</span><span class="sxs-lookup"><span data-stu-id="5c35f-123">This path will include a map that will construct a respond message to a request message.</span></span> <span data-ttu-id="5c35f-124">有关示例映射，请参阅[3A2 请求到 3A2 响应映射示例](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)并[3A4 请求到 3A4 响应映射示例&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="5c35f-124">For example maps, see the [3A2 Request to 3A2 Response Map Sample](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md) and the [3A4 Request to 3A4 Response Map Sample &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md).</span></span>  
  
### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="5c35f-125">构建和初始化此示例</span><span class="sxs-lookup"><span data-stu-id="5c35f-125">To build and initialize this sample</span></span>  
  
1. <span data-ttu-id="5c35f-126">在命令提示符处，找到*\<驱动器\>*: \Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction 文件夹。</span><span class="sxs-lookup"><span data-stu-id="5c35f-126">At a command prompt, locate the *\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction folder.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5c35f-127">在运行安装程序之前，用记事本打开 DoubleAction.sql 文件（在上面所述的文件夹中）。</span><span class="sxs-lookup"><span data-stu-id="5c35f-127">Before running the Setup program, open the file DoubleAction.sql (in the above folder) in Notepad.</span></span> <span data-ttu-id="5c35f-128">上**文件**菜单上，单击**另存为**。</span><span class="sxs-lookup"><span data-stu-id="5c35f-128">On the **File** menu, click **Save As**.</span></span> <span data-ttu-id="5c35f-129">在中**编码**列表中，选择**ANSI**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="5c35f-129">In the **Encoding** list, select **ANSI**, and then click **Save**.</span></span> <span data-ttu-id="5c35f-130">单击**是**以覆盖现有文件。</span><span class="sxs-lookup"><span data-stu-id="5c35f-130">Click **Yes** to overwrite the existing file.</span></span>  
  
2. <span data-ttu-id="5c35f-131">如果您的 BizTalk Server 正在运行的 32 位计算机上，在运行文件 setup.bat\<驱动器\>: \Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction 文件夹。</span><span class="sxs-lookup"><span data-stu-id="5c35f-131">If your BizTalk Server is running on a 32-bit computer, run the file setup.bat in the \<drive\>:\Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction folder.</span></span> <span data-ttu-id="5c35f-132">如果您的 BizTalk Server 安装在 64 位计算机上运行，请在同一文件夹中运行 setupx64.bat。</span><span class="sxs-lookup"><span data-stu-id="5c35f-132">If your BizTalk Server installation is running on a 64-bit computer, run setupx64.bat in the same folder.</span></span> <span data-ttu-id="5c35f-133">该批处理文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5c35f-133">The batch file will perform the following actions:</span></span>  
  
   - <span data-ttu-id="5c35f-134">在 BTARNDATA 数据库中创建一个 SQL 存储过程 (`PipAutomationGetAction`)，用于从 MessagesToLOB 表中检索操作消息。</span><span class="sxs-lookup"><span data-stu-id="5c35f-134">Creates a SQL stored procedure (`PipAutomationGetAction`) in the BTARNDATA database to retrieve the action message from the MessagesToLOB table.</span></span> <span data-ttu-id="5c35f-135">这还可以确保不会重复读取检索到的记录。</span><span class="sxs-lookup"><span data-stu-id="5c35f-135">This also ensures that the retrieved records will not be read again.</span></span>  
  
   - <span data-ttu-id="5c35f-136">编译 HeaderHelper [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] 项目，并在全局程序集缓存中注册此程序集。</span><span class="sxs-lookup"><span data-stu-id="5c35f-136">Compiles the HeaderHelper [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] project and registers the assembly in the global assembly cache.</span></span>  
  
   - <span data-ttu-id="5c35f-137">创建并绑定 BizTalk Server SQL 接收端口 (MessagesToLOB_Receive_Port)。</span><span class="sxs-lookup"><span data-stu-id="5c35f-137">Creates and binds the BizTalk Server SQL receive port (MessagesToLOB_Receive_Port).</span></span>  
  
   - <span data-ttu-id="5c35f-138">启用接收位置 (MessagesToLOB_Receive_Location)。</span><span class="sxs-lookup"><span data-stu-id="5c35f-138">Enables the receive location (MessagesToLOB_Receive_Location).</span></span>  
  
   - <span data-ttu-id="5c35f-139">编译并部署双操作 PIPAutomation 业务流程 (DoubleAction.odx)。</span><span class="sxs-lookup"><span data-stu-id="5c35f-139">Compiles and deploys the Double-Action PIPAutomation Orchestration (DoubleAction.odx).</span></span>  
  
   - <span data-ttu-id="5c35f-140">绑定并启动 BizTalk Server 业务流程。</span><span class="sxs-lookup"><span data-stu-id="5c35f-140">Binds and starts the BizTalk Server orchestration.</span></span>  
  
     > [!NOTE]
     >  <span data-ttu-id="5c35f-141">编译时示例将显示一些警告。</span><span class="sxs-lookup"><span data-stu-id="5c35f-141">The sample displays some warnings while compiling.</span></span> <span data-ttu-id="5c35f-142">你可以忽略这些警告。</span><span class="sxs-lookup"><span data-stu-id="5c35f-142">You can ignore these warnings.</span></span>  
  
     > [!NOTE]
     >  <span data-ttu-id="5c35f-143">此示例使用默认主机名**BizTalkServerApplication**部署项目时。</span><span class="sxs-lookup"><span data-stu-id="5c35f-143">The sample uses the default host name **BizTalkServerApplication** when deploying the project.</span></span> <span data-ttu-id="5c35f-144">如果你想要运行该示例不同的主机，你将需要编辑下的 DoubleActionBinding.xml 中找到的默认主机名\<SDK\>\PIPAutomation\DoubleAction 文件夹。</span><span class="sxs-lookup"><span data-stu-id="5c35f-144">If you would like to run the sample under a different host, you will need to edit the default host names found in DoubleActionBinding.xml under \<SDK\>\PIPAutomation\DoubleAction folder.</span></span>  
  
### <a name="to-run-the-double-action-pipautomation-sample"></a><span data-ttu-id="5c35f-145">运行双操作 PIPAutomation 示例</span><span class="sxs-lookup"><span data-stu-id="5c35f-145">To run the Double-Action PIPAutomation sample</span></span>  
  
1. <span data-ttu-id="5c35f-146">创建本组织角色为发起方的 3A4 协议。</span><span class="sxs-lookup"><span data-stu-id="5c35f-146">Create a 3A4 agreement where the home role is an initiator.</span></span> <span data-ttu-id="5c35f-147">将本组织的 GBI 设置为 123456789，将合作伙伴的 GBI 设置为 987654321。</span><span class="sxs-lookup"><span data-stu-id="5c35f-147">Set the GBI for the home organization to 123456789, and set the GBI for the partner to 987654321.</span></span> <span data-ttu-id="5c35f-148">这允许您使用 SampleInstances 文件夹中的示例，该文件夹位于 SDK 中的 LOBApplication 文件夹下。</span><span class="sxs-lookup"><span data-stu-id="5c35f-148">This lets you use the samples provided in the SampleInstances folder under the LOBApplication folder in the SDK.</span></span>  
  
2. <span data-ttu-id="5c35f-149">使用 Loopback 协议镜像实用工具，为在步骤 1 中创建的 3A4 PIP 创建镜像。</span><span class="sxs-lookup"><span data-stu-id="5c35f-149">Using the Loopback agreement-mirroring utility, create a mirror for the 3A4 PIP created in step 1.</span></span>  
  
3. <span data-ttu-id="5c35f-150">使用 LOBApplication.exe SDK 实用工具提交 3A4 PIP 请求消息。</span><span class="sxs-lookup"><span data-stu-id="5c35f-150">Using the LOBApplication.exe SDK utility, submit a 3A4 PIP Request message.</span></span> <span data-ttu-id="5c35f-151">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 文件夹中包含一个输入的示例\<*安装目录*\>\SDK\LOBApplication\SampleInstances\3A4_Request.xml。</span><span class="sxs-lookup"><span data-stu-id="5c35f-151">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes an input sample in the folder \<*Installation Directory*\>\SDK\LOBApplication\SampleInstances\3A4_Request.xml.</span></span>  
  
4. <span data-ttu-id="5c35f-152">在 BTARNDATA 数据库运行以下查询：</span><span class="sxs-lookup"><span data-stu-id="5c35f-152">Run the following query on the BTARNDATA database:</span></span>  
  
   ```  
   Select * from MessagesToLOB  
   ```  
  
5. <span data-ttu-id="5c35f-153">几秒钟后，会有四个新消息出现在此表中。</span><span class="sxs-lookup"><span data-stu-id="5c35f-153">After several seconds, four new messages appear in this table.</span></span> <span data-ttu-id="5c35f-154">其中两个消息是确认信号。</span><span class="sxs-lookup"><span data-stu-id="5c35f-154">Two of them are acknowledgment signals.</span></span> <span data-ttu-id="5c35f-155">一个信号是 Async 3A4 请求消息。</span><span class="sxs-lookup"><span data-stu-id="5c35f-155">One signal is the Async 3A4 Request Message.</span></span> <span data-ttu-id="5c35f-156">另一个信号是 Async 3A4 响应消息。</span><span class="sxs-lookup"><span data-stu-id="5c35f-156">One signal is the Async 3A4 Response Message.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5c35f-157">若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="5c35f-157">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="5c35f-158">再次运行 Setup.bat 前，必须先运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="5c35f-158">You must run Cleanup.bat before running Setup.bat again.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c35f-159">Remarks</span><span class="sxs-lookup"><span data-stu-id="5c35f-159">Remarks</span></span>  
 <span data-ttu-id="5c35f-160">公用业务流程自动生成确认消息（ACK 和 NACK 信号消息）。</span><span class="sxs-lookup"><span data-stu-id="5c35f-160">The public orchestration automatically generates acknowledgments (ACK and NACK signal messages).</span></span> <span data-ttu-id="5c35f-161">业务线 (LOB) 应用程序不需要生成它们。</span><span class="sxs-lookup"><span data-stu-id="5c35f-161">The line-of-business (LOB) application does not need to generate them.</span></span>  
  
 <span data-ttu-id="5c35f-162">路由到 MessagesFromLOB 表的消息的格式称为 LOBMessage。</span><span class="sxs-lookup"><span data-stu-id="5c35f-162">The format of the message that is routed to the MessagesFromLOB table is called LOBMessage.</span></span> <span data-ttu-id="5c35f-163">架构是 C:\Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\RNIFSchemas\GlobalSchemas\LOBMessage.xsd 中可用。</span><span class="sxs-lookup"><span data-stu-id="5c35f-163">The schema is available in C:\Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\RNIFSchemas\GlobalSchemas\LOBMessage.xsd.</span></span> <span data-ttu-id="5c35f-164">如果使用 `RNIFSubmit` 方法，则不必处理消息格式。</span><span class="sxs-lookup"><span data-stu-id="5c35f-164">If you use the `RNIFSubmit` method, you do not have to work with the message format.</span></span> <span data-ttu-id="5c35f-165">只需提交的附加信息的 ServiceContent。</span><span class="sxs-lookup"><span data-stu-id="5c35f-165">You only need to submit the ServiceContent with the additional information.</span></span> <span data-ttu-id="5c35f-166">`RNIFSubmit` 填充 MessagesFromLOB 表中的记录。</span><span class="sxs-lookup"><span data-stu-id="5c35f-166">`RNIFSubmit` populates the record in the MessagesFromLOB table.</span></span>  
  
## <a name="filtering-out-single-action-messages"></a><span data-ttu-id="5c35f-167">筛选单操作消息</span><span class="sxs-lookup"><span data-stu-id="5c35f-167">Filtering Out Single-Action Messages</span></span>  
 <span data-ttu-id="5c35f-168">此业务流程应只接收双操作消息。</span><span class="sxs-lookup"><span data-stu-id="5c35f-168">This orchestration should receive only double-action messages.</span></span> <span data-ttu-id="5c35f-169">你不应将此示例项目扩展为支持单操作 PIP。</span><span class="sxs-lookup"><span data-stu-id="5c35f-169">You should not extend this sample project to support single-action PIPs.</span></span> <span data-ttu-id="5c35f-170">如果使用此业务流程来处理单操作消息，BTARN 将出现错误。</span><span class="sxs-lookup"><span data-stu-id="5c35f-170">BTARN will post errors if you use this orchestration to process single-action messages.</span></span> <span data-ttu-id="5c35f-171">为了防止该业务流程接收单操作消息，请更改 PIPAutomationGetAction 存储过程中的以下行：</span><span class="sxs-lookup"><span data-stu-id="5c35f-171">In order to prevent the orchestration from receiving a single-action message, change the following line in the PIPAutomationGetAction stored procedure:</span></span>  
  
```  
SELECT PIPInstanceID,DestinationPartyName,SourcePartyName,PIPCode,PIPVersion,ServiceContent FROM MessagesToLOB  
```  
  
 <span data-ttu-id="5c35f-172">在上面的行中添加用于筛选单操作消息的 WHERE 子句。</span><span class="sxs-lookup"><span data-stu-id="5c35f-172">To the above line, add a WHERE clause that will filter out single-action messages.</span></span> <span data-ttu-id="5c35f-173">该 WHERE 子句中包含将要处理的所有单操作消息。</span><span class="sxs-lookup"><span data-stu-id="5c35f-173">Include in the WHERE clause all the single-action messages that you will be processing.</span></span> <span data-ttu-id="5c35f-174">代码行应如以下所示：</span><span class="sxs-lookup"><span data-stu-id="5c35f-174">The line should be as follows:</span></span>  
  
```  
SELECT PIPInstanceID,DestinationPartyName,SourcePartyName,PIPCode,PIPVersion,ServiceContent FROM MessagesToLOB WHERE PIPCode NOT IN ( '0A1', '3B2', '3C3', '0C1', '0C3' )  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c35f-175">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c35f-175">See Also</span></span>  
 <span data-ttu-id="5c35f-176">[3A2 请求到 3A2 响应映射示例](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md) </span><span class="sxs-lookup"><span data-stu-id="5c35f-176">[3A2 Request to 3A2 Response Map Sample](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md) </span></span>  
 <span data-ttu-id="5c35f-177">[3A4 请求到 3A4 响应映射示例](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md) </span><span class="sxs-lookup"><span data-stu-id="5c35f-177">[3A4 Request to 3A4 Response Map Sample](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md) </span></span>  
 [<span data-ttu-id="5c35f-178">业务流程示例</span><span class="sxs-lookup"><span data-stu-id="5c35f-178">Orchestration Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)