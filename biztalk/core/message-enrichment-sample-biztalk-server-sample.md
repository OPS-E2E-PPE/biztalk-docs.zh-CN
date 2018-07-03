---
title: 消息充实示例 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41ed707-dbdb-46b7-97a6-86fdbc8ad285
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01fa66b344548654a4d2e2e2f2b8700b604ec0e7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998502"
---
# <a name="message-enrichment-sample-biztalk-server-sample"></a><span data-ttu-id="22ec7-102">消息收集示例（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="22ec7-102">Message Enrichment Sample (BizTalk Server Sample)</span></span>
<span data-ttu-id="22ec7-103">消息收集示例演示如何将 X12 文档和 EDIFACT 文档的交换标头附加到事务集消息中。</span><span class="sxs-lookup"><span data-stu-id="22ec7-103">The Message Enrichment sample demonstrates how to append interchange headers to transaction-set messages for X12 and EDIFACT documents.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="22ec7-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="22ec7-104">What This Sample Does</span></span>  
 <span data-ttu-id="22ec7-105">本示例演示如何将针对 EDIFACT 的 UNA、UNB 和 UNG 标头及针对 X12 的 ISA 标头附加到事务集。</span><span class="sxs-lookup"><span data-stu-id="22ec7-105">This sample demonstrates how to append UNA, UNB, and UNG headers for EDIFACT, and ISA headers for X12, to transaction sets.</span></span> <span data-ttu-id="22ec7-106">具体而言，本示例执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="22ec7-106">Specifically, this sample does the following:</span></span>  
  
1.  <span data-ttu-id="22ec7-107">将测试消息放入 \Message Enrichment\In 文件夹时，接收端口将提取和处理该消息，然后将其放入 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="22ec7-107">When you drop the test message to the \Message Enrichment\In folder, the receive port picks it up, processes it, and drops it in the MessageBox.</span></span>  
  
2.  <span data-ttu-id="22ec7-108">MessageEnrichmentOrchestration 将从 MessageBox 中提取该测试消息，因为该业务流程基于在其接收形状上设置的筛选器表达式订阅消息。</span><span class="sxs-lookup"><span data-stu-id="22ec7-108">The MessageEnrichmentOrchestration picks the test message up from the MessageBox, because it subscribes to messages based on a filter expression set on its receive shape.</span></span>  
  
3.  <span data-ttu-id="22ec7-109">业务流程从消息的上下文属性中读取交换标头。</span><span class="sxs-lookup"><span data-stu-id="22ec7-109">The orchestration reads the interchange headers from the context properties of the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="22ec7-110">因为 UNA 和 UNG 标头在 EDIFACT 消息中不是必需部分，所以在消息的上下文属性中可能会缺失此类标头。</span><span class="sxs-lookup"><span data-stu-id="22ec7-110">UNA and UNG headers are optional in an EDIFACT message, so can be missing in the context properties of a message.</span></span>  
  
4.  <span data-ttu-id="22ec7-111">业务流程将交换标头和消息正文写入单个新消息中。</span><span class="sxs-lookup"><span data-stu-id="22ec7-111">The orchestration writes both the interchange headers and the message body into a single new message.</span></span>  
  
5.  <span data-ttu-id="22ec7-112">业务流程将在 ReceivePortNameCorrelationType 相关类型中设置的其他属性升级到该消息中。</span><span class="sxs-lookup"><span data-stu-id="22ec7-112">The orchestration promotes additional properties that are set in the ReceivePortNameCorrelationType correlation type onto the message.</span></span> <span data-ttu-id="22ec7-113">利用这些属性，业务流程的用户可以选择订阅时所需属性的列表。</span><span class="sxs-lookup"><span data-stu-id="22ec7-113">These allow users of the orchestration to select a list of the properties they need for their subscription.</span></span> <span data-ttu-id="22ec7-114">这些属性是在构造消息形状中编写的。</span><span class="sxs-lookup"><span data-stu-id="22ec7-114">These properties are written in a construct message shape.</span></span> <span data-ttu-id="22ec7-115">并非所有写入原始消息的上下文属性都将写入新消息。</span><span class="sxs-lookup"><span data-stu-id="22ec7-115">Not all context properties that were written to the original message are written to the new message.</span></span>  
  
6.  <span data-ttu-id="22ec7-116">业务流程将新消息放入 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="22ec7-116">The orchestration drops the new message into the MessageBox.</span></span>  
  
7.  <span data-ttu-id="22ec7-117">发送端口提取新消息，并通过 FILE 适配器将其发送至 \Message Enrichment\Out 文件夹。</span><span class="sxs-lookup"><span data-stu-id="22ec7-117">The send port picks up the new message and sends it via the FILE adapter to the \Message Enrichment\Out folder.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="22ec7-118">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="22ec7-118">Where to Find This Sample</span></span>  
 <span data-ttu-id="22ec7-119">此示例位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装文件夹： [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\Message Enrichment。</span><span class="sxs-lookup"><span data-stu-id="22ec7-119">This sample is located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\Message Enrichment.</span></span>  
  
 <span data-ttu-id="22ec7-120">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="22ec7-120">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="22ec7-121">文件</span><span class="sxs-lookup"><span data-stu-id="22ec7-121">File(s)</span></span>|<span data-ttu-id="22ec7-122">Description</span><span class="sxs-lookup"><span data-stu-id="22ec7-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="22ec7-123">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="22ec7-123">Cleanup.bat</span></span>|<span data-ttu-id="22ec7-124">取消部署示例方案。</span><span class="sxs-lookup"><span data-stu-id="22ec7-124">Undeploys the example scenario.</span></span> <span data-ttu-id="22ec7-125">为了成功完成此操作，绝对不能存在活动的业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="22ec7-125">In order for it to succeed there must be no active instances of the orchestration.</span></span> <span data-ttu-id="22ec7-126">否则，操作将失败。</span><span class="sxs-lookup"><span data-stu-id="22ec7-126">Otherwise, it will fail.</span></span>|  
|<span data-ttu-id="22ec7-127">MessageEnrichment.sln</span><span class="sxs-lookup"><span data-stu-id="22ec7-127">MessageEnrichment.sln</span></span>|<span data-ttu-id="22ec7-128">包含 MessageEnrichment 和 MessageEnrichmentLibrary 项目。</span><span class="sxs-lookup"><span data-stu-id="22ec7-128">Contains the MessageEnrichment and MessageEnrichmentLibrary projects.</span></span>|  
|<span data-ttu-id="22ec7-129">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="22ec7-129">Setup.bat</span></span>|<span data-ttu-id="22ec7-130">部署包含接收端口、发送端口和业务流程的示例方案。</span><span class="sxs-lookup"><span data-stu-id="22ec7-130">Deploys an example scenario that consists of a receive port, send port, and orchestration.</span></span>|  
|<span data-ttu-id="22ec7-131">EDIFACT_example.edi</span><span class="sxs-lookup"><span data-stu-id="22ec7-131">EDIFACT_example.edi</span></span>|<span data-ttu-id="22ec7-132">一条 EDIFACT 输入消息。</span><span class="sxs-lookup"><span data-stu-id="22ec7-132">An input EDIFACT message.</span></span>|  
|<span data-ttu-id="22ec7-133">X12_example.edi</span><span class="sxs-lookup"><span data-stu-id="22ec7-133">X12_example.edi</span></span>|<span data-ttu-id="22ec7-134">一条 X12 输入消息。</span><span class="sxs-lookup"><span data-stu-id="22ec7-134">An input X12 message.</span></span>|  
|<span data-ttu-id="22ec7-135">MessageEnrichment.btproj</span><span class="sxs-lookup"><span data-stu-id="22ec7-135">MessageEnrichment.btproj</span></span>|<span data-ttu-id="22ec7-136">包含 MessageEnrichment 业务流程和架构的项目。</span><span class="sxs-lookup"><span data-stu-id="22ec7-136">The project containing the MessageEnrichment orchestrations and schemas.</span></span>|  
|<span data-ttu-id="22ec7-137">MessageEnrichmentBindings.xml</span><span class="sxs-lookup"><span data-stu-id="22ec7-137">MessageEnrichmentBindings.xml</span></span>|<span data-ttu-id="22ec7-138">包含业务流程、端口和参与方的绑定的文件。</span><span class="sxs-lookup"><span data-stu-id="22ec7-138">The file containing bindings for the orchestration, the ports, and the parties.</span></span>|  
|<span data-ttu-id="22ec7-139">MessageEnrichmentOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="22ec7-139">MessageEnrichmentOrchestration.odx</span></span>|<span data-ttu-id="22ec7-140">将标头附加到消息的业务流程。</span><span class="sxs-lookup"><span data-stu-id="22ec7-140">The orchestration that appends the headers to the message.</span></span>|  
|<span data-ttu-id="22ec7-141">MessageEnrichmentOrchestration.odx.cs</span><span class="sxs-lookup"><span data-stu-id="22ec7-141">MessageEnrichmentOrchestration.odx.cs</span></span>|<span data-ttu-id="22ec7-142">将标头附加到消息的业务流程代码。</span><span class="sxs-lookup"><span data-stu-id="22ec7-142">The orchestration code that appends the headers to the message.</span></span>|  
|<span data-ttu-id="22ec7-143">EFACT_D98B_APERAK.xsd</span><span class="sxs-lookup"><span data-stu-id="22ec7-143">EFACT_D98B_APERAK.xsd</span></span>|<span data-ttu-id="22ec7-144">输入消息的 EDIFACT 架构。</span><span class="sxs-lookup"><span data-stu-id="22ec7-144">The EDIFACT schema for the input message.</span></span>|  
|<span data-ttu-id="22ec7-145">Enriched_EFACT_D98B_APERAK.xsd</span><span class="sxs-lookup"><span data-stu-id="22ec7-145">Enriched_EFACT_D98B_APERAK.xsd</span></span>|<span data-ttu-id="22ec7-146">输出消息的 EDIFACT 架构。</span><span class="sxs-lookup"><span data-stu-id="22ec7-146">The EDIFACT schema for the output message.</span></span>|  
|<span data-ttu-id="22ec7-147">X12_00401_864.xsd</span><span class="sxs-lookup"><span data-stu-id="22ec7-147">X12_00401_864.xsd</span></span>|<span data-ttu-id="22ec7-148">输入消息的 X12 架构。</span><span class="sxs-lookup"><span data-stu-id="22ec7-148">The X12 schema for the input message.</span></span>|  
|<span data-ttu-id="22ec7-149">Enriched_X12_00401_864.xsd</span><span class="sxs-lookup"><span data-stu-id="22ec7-149">Enriched_X12_00401_864.xsd</span></span>|<span data-ttu-id="22ec7-150">输出消息的 X12 架构。</span><span class="sxs-lookup"><span data-stu-id="22ec7-150">The X12 schema for the output message.</span></span>|  
|<span data-ttu-id="22ec7-151">Headers.xsd</span><span class="sxs-lookup"><span data-stu-id="22ec7-151">Headers.xsd</span></span>|<span data-ttu-id="22ec7-152">要添加到输入消息的标头的架构。</span><span class="sxs-lookup"><span data-stu-id="22ec7-152">The schemas for the headers added to the input messages.</span></span>|  
|<span data-ttu-id="22ec7-153">MessageEnrichmentLibrary.csproj</span><span class="sxs-lookup"><span data-stu-id="22ec7-153">MessageEnrichmentLibrary.csproj</span></span>|<span data-ttu-id="22ec7-154">包含 Headers.cs、OrchestrationUtilities.cs 和 ParseHeaders.cs 文件的项目。</span><span class="sxs-lookup"><span data-stu-id="22ec7-154">The project containing the Headers.cs, OrchestrationUtilities.cs, and ParseHeaders.cs files.</span></span>|  
|<span data-ttu-id="22ec7-155">Headers.cs</span><span class="sxs-lookup"><span data-stu-id="22ec7-155">Headers.cs</span></span>|<span data-ttu-id="22ec7-156">包括表示标头数据的类。</span><span class="sxs-lookup"><span data-stu-id="22ec7-156">Includes classes representing headers data.</span></span>|  
|<span data-ttu-id="22ec7-157">OrchestrationUtilities.cs</span><span class="sxs-lookup"><span data-stu-id="22ec7-157">OrchestrationUtilities.cs</span></span>|<span data-ttu-id="22ec7-158">包含业务流程使用的实用工具方法。</span><span class="sxs-lookup"><span data-stu-id="22ec7-158">Includes utility methods used by orchestration.</span></span>|  
|<span data-ttu-id="22ec7-159">ParseHeaders.cs</span><span class="sxs-lookup"><span data-stu-id="22ec7-159">ParseHeaders.cs</span></span>|<span data-ttu-id="22ec7-160">包含新消息中使用的 UNA 默认值。</span><span class="sxs-lookup"><span data-stu-id="22ec7-160">Includes the default values for UNA that are used in the new messages.</span></span> <span data-ttu-id="22ec7-161">这些值取自 ParseHeaders.cs 中的 SerializeEDIFACTHeaders 方法。</span><span class="sxs-lookup"><span data-stu-id="22ec7-161">These values are taken from the SerializeEDIFACTHeaders method in ParseHeaders.cs.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="22ec7-162">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="22ec7-162">How to Use This Sample</span></span>  
 <span data-ttu-id="22ec7-163">可将本示例作为演示将交换标头附加到 EDI 事务集消息所需操作的可运行示例。</span><span class="sxs-lookup"><span data-stu-id="22ec7-163">Use this sample as a working example of the actions required to append interchange headers to EDI transaction-set messages.</span></span>  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="22ec7-164">生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="22ec7-164">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="22ec7-165">若要生成并初始化消息收集示例，您需要为本示例生成并部署 BizTalk 项目、配置接收端口和位置，并配置两个不同的发送端口。</span><span class="sxs-lookup"><span data-stu-id="22ec7-165">To build and initialize the Message Enrichment sample, you need to build and deploy the BizTalk project for this sample, configure the receive port and location, and configure two different send ports.</span></span>  
  
#### <a name="to-build-and-deploy-the-biztalk-project-for-this-sample"></a><span data-ttu-id="22ec7-166">为本示例生成并部署 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="22ec7-166">To build and deploy the BizTalk project for this sample</span></span>  
  
1. <span data-ttu-id="22ec7-167">使用 Notepad.Exe，打开[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\MessageEnrichment\\</span><span class="sxs-lookup"><span data-stu-id="22ec7-167">Using Notepad.Exe, open [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\MessageEnrichment\\</span></span>  
   <span data-ttu-id="22ec7-168">MessageEnrichment\properties\AssemblyInfo.cs 并在文件底部添加以下行：</span><span class="sxs-lookup"><span data-stu-id="22ec7-168">MessageEnrichment\properties\AssemblyInfo.cs and add the following line at the bottom of the file:</span></span>  
  
   ```  
   [assembly: Microsoft.XLANGs.BaseTypes.BizTalkAssembly(typeof(Microsoft.BizTalk.XLANGs.BTXEngine.BTXService))]  
   ```  
  
2. <span data-ttu-id="22ec7-169">保存修改的 AssemblyInfo.cs 文件，然后退出记事本。</span><span class="sxs-lookup"><span data-stu-id="22ec7-169">Save the modified AssemblyInfo.cs file and then exit Notepad.</span></span>  
  
3. <span data-ttu-id="22ec7-170">在命令窗口中，转至以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="22ec7-170">In a command window, move to the following folder:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="22ec7-171">SDK\Samples\EDI\Message Enrichment</span><span class="sxs-lookup"><span data-stu-id="22ec7-171">SDK\Samples\EDI\Message Enrichment</span></span>  
  
4. <span data-ttu-id="22ec7-172">运行**Setup.bat**，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="22ec7-172">Run **Setup.bat**, which performs the following actions:</span></span>  
  
   -   <span data-ttu-id="22ec7-173">创建接收 (**中**) 和发送 (**出**) \MessageEnrichment 文件夹中的以下示例的文件夹。</span><span class="sxs-lookup"><span data-stu-id="22ec7-173">Creates the receive (**in**) and send (**out**) folders for this sample in the \MessageEnrichment folder.</span></span>  
  
   -   <span data-ttu-id="22ec7-174">将密钥对写入 MessageEnrichmentLibrary\testkey.snk。</span><span class="sxs-lookup"><span data-stu-id="22ec7-174">Writes a key pair to MessageEnrichmentLibrary\testkey.snk</span></span>  
  
   -   <span data-ttu-id="22ec7-175">生成并部署 MessageEnrichmentLibrary.btproj 项目。</span><span class="sxs-lookup"><span data-stu-id="22ec7-175">Builds and deploys the MessageEnrichmentLibrary.btproj project.</span></span>  
  
   -   <span data-ttu-id="22ec7-176">生成并部署 MessageEnrichment.btproj 项目。</span><span class="sxs-lookup"><span data-stu-id="22ec7-176">Builds and deploys the MessageEnrichment.btproj project.</span></span>  
  
   -   <span data-ttu-id="22ec7-177">读取 MessageEnrichmentBindings.xml 中的绑定信息。</span><span class="sxs-lookup"><span data-stu-id="22ec7-177">Reads binding information in MessageEnrichmentBindings.xml.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="22ec7-178">此项目的绑定需要将 BizTalk 主机标记为受信任的身份验证。</span><span class="sxs-lookup"><span data-stu-id="22ec7-178">The binding for this project requires that the BizTalk host is marked as Authentication Trusted.</span></span>  <span data-ttu-id="22ec7-179">为了将此绑定与不受信任的主机一起使用，请修改 MessageEnrichmentBindings.xml 并将 HostTrusted=”true” 条目更改为 HostTrusted=”false”。</span><span class="sxs-lookup"><span data-stu-id="22ec7-179">In order to use this with a host that is not trusted, modify the MessageEnrichmentBindings.xml and change the HostTrusted=”true” entries to HostTrusted=”false”.</span></span>  
  
   -   <span data-ttu-id="22ec7-180">更新业务流程绑定。</span><span class="sxs-lookup"><span data-stu-id="22ec7-180">Updates orchestration bindings.</span></span>  
  
   -   <span data-ttu-id="22ec7-181">更新发送端口、发送端口组和接收端口。</span><span class="sxs-lookup"><span data-stu-id="22ec7-181">Updates send ports, send port groups, and receive ports.</span></span>  
  
   -   <span data-ttu-id="22ec7-182">更新参与方和登记。</span><span class="sxs-lookup"><span data-stu-id="22ec7-182">Updates parties and enlistments.</span></span>  
  
   -   <span data-ttu-id="22ec7-183">启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="22ec7-183">Starts the send port.</span></span>  
  
   -   <span data-ttu-id="22ec7-184">启用接收位置。</span><span class="sxs-lookup"><span data-stu-id="22ec7-184">Enables the receive location.</span></span>  
  
   -   <span data-ttu-id="22ec7-185">登记并启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="22ec7-185">Enlists and starts the orchestration.</span></span>  
  
   <span data-ttu-id="22ec7-186">BizTalk Server 现在便可使用本示例。</span><span class="sxs-lookup"><span data-stu-id="22ec7-186">BizTalk Server is ready now to work with this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="22ec7-187">运行本示例</span><span class="sxs-lookup"><span data-stu-id="22ec7-187">Running This Sample</span></span>  
 <span data-ttu-id="22ec7-188">使用以下过程运行消息收集示例。</span><span class="sxs-lookup"><span data-stu-id="22ec7-188">Use the following procedure to run the Message Enrichment sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="22ec7-189">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="22ec7-189">To run this sample</span></span>  
  
1.  <span data-ttu-id="22ec7-190">将 \MessageEnrichment\Instances 文件夹中的 EDIFACT_examples.edi 文件复制到 \MessageEnrichment\In 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="22ec7-190">Copy the EDIFACT_examples.edi file from the \MessageEnrichment\Instances folder into the \MessageEnrichment\In folder.</span></span>  
  
2.  <span data-ttu-id="22ec7-191">验证 EDIFACT_examples.edi 文件是否已从 \MessageEnrichment\In 文件夹中消失，并显示在 \MessageEnrichment\Out 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="22ec7-191">Verify that the EDIFACT_examples.edi files disappears from the \MessageEnrichment\In folder, and appears in the \MessageEnrichment\Out folder.</span></span>  
  
3.  <span data-ttu-id="22ec7-192">打开 \MessageEnrichment\Out 文件夹中的文件。</span><span class="sxs-lookup"><span data-stu-id="22ec7-192">Open the file in the \MessageEnrichment\Out folder.</span></span> <span data-ttu-id="22ec7-193">验证该文件是否为 \MessageEnrichment\Instances 文件夹中的 EDIFACT_examples.edi 文件的 XML 表示形式，并且包含与 EDIFACT_examples.edi 文件相同的内容。不过与之不同的是，该输出文件包含 EDIFACT UNA、UNB 和 UNG 标头。</span><span class="sxs-lookup"><span data-stu-id="22ec7-193">Verify that it is an XML representation of the EDIFACT_examples.edi file in the \MessageEnrichment\Instances folder, and that is has the same contents as the EDIFACT_examples.edi file, with the exception that the output file has EDIFACT UNA, UNB, and UNG headers.</span></span>  
  
4.  <span data-ttu-id="22ec7-194">针对 \MessageEnrichment\Instances 文件夹中的 X12_examples.edi 文件，请重复步骤 1 至 2。</span><span class="sxs-lookup"><span data-stu-id="22ec7-194">Repeat steps 1 and 2 with the X12_examples.edi file from the \MessageEnrichment\Instances folder.</span></span>  
  
5.  <span data-ttu-id="22ec7-195">打开 \MessageEnrichment\Out 文件夹中的新文件。</span><span class="sxs-lookup"><span data-stu-id="22ec7-195">Open the new file in the \MessageEnrichment\Out folder.</span></span> <span data-ttu-id="22ec7-196">验证该文件是否为 \MessageEnrichment\Instances 文件夹中的 X12_examples.edi 文件的 XML 表示形式，并且包含与 X12_examples.edi 文件相同的内容。不过与之不同的是，该输出文件包含 X12 ISA 标头。</span><span class="sxs-lookup"><span data-stu-id="22ec7-196">Verify that it is an XML representation of the X12_examples.edi file in the \MessageEnrichment\Instances folder, and that is has the same contents as the X12_examples.edi file, with the exception that the output file has X12 ISA headers.</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="22ec7-197">本示例中使用的类或方法</span><span class="sxs-lookup"><span data-stu-id="22ec7-197">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="22ec7-198">InclusionThresholdSetting</span><span class="sxs-lookup"><span data-stu-id="22ec7-198">None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22ec7-199">请参阅</span><span class="sxs-lookup"><span data-stu-id="22ec7-199">See Also</span></span>  
 [<span data-ttu-id="22ec7-200">EDI 和 AS2（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="22ec7-200">EDI and AS2 (BizTalk Server Samples Folder)</span></span>](../core/edi-and-as2-biztalk-server-samples-folder.md)