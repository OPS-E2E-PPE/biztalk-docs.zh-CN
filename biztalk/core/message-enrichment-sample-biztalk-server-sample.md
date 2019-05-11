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
ms.openlocfilehash: d987164eeb855bfc991e9b4f1b0c8b444b99407b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325120"
---
# <a name="message-enrichment-sample-biztalk-server-sample"></a><span data-ttu-id="7d0c2-102">消息充实示例 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="7d0c2-102">Message Enrichment Sample (BizTalk Server Sample)</span></span>
<span data-ttu-id="7d0c2-103">消息收集示例演示如何将交换标头附加到事务集消息的 X12 和 EDIFACT 文档。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-103">The Message Enrichment sample demonstrates how to append interchange headers to transaction-set messages for X12 and EDIFACT documents.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="7d0c2-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="7d0c2-104">What This Sample Does</span></span>  
 <span data-ttu-id="7d0c2-105">此示例演示如何将对于 EDIFACT，UNA、 UNB 和 UNG 标头和对于 X12，ISA 标头附加到事务集。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-105">This sample demonstrates how to append UNA, UNB, and UNG headers for EDIFACT, and ISA headers for X12, to transaction sets.</span></span> <span data-ttu-id="7d0c2-106">具体而言，此示例执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="7d0c2-106">Specifically, this sample does the following:</span></span>  
  
1.  <span data-ttu-id="7d0c2-107">将测试消息放到 enrichment\in 文件夹时，接收端口获取、 处理它，并将其放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-107">When you drop the test message to the \Message Enrichment\In folder, the receive port picks it up, processes it, and drops it in the MessageBox.</span></span>  
  
2.  <span data-ttu-id="7d0c2-108">MessageEnrichmentOrchestration 选取测试消息从 MessageBox，因为其订阅的消息根据其接收形状上设置筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-108">The MessageEnrichmentOrchestration picks the test message up from the MessageBox, because it subscribes to messages based on a filter expression set on its receive shape.</span></span>  
  
3.  <span data-ttu-id="7d0c2-109">业务流程从消息上下文属性中读取交换标头。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-109">The orchestration reads the interchange headers from the context properties of the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7d0c2-110">UNA 和 UNG 标头是消息的可选的 EDIFACT 消息，因此可能会丢失上下文属性中。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-110">UNA and UNG headers are optional in an EDIFACT message, so can be missing in the context properties of a message.</span></span>  
  
4.  <span data-ttu-id="7d0c2-111">业务流程将交换标头和消息正文写入到一条新消息。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-111">The orchestration writes both the interchange headers and the message body into a single new message.</span></span>  
  
5.  <span data-ttu-id="7d0c2-112">业务流程将在 ReceivePortNameCorrelationType 相关类型到消息上设置其他属性。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-112">The orchestration promotes additional properties that are set in the ReceivePortNameCorrelationType correlation type onto the message.</span></span> <span data-ttu-id="7d0c2-113">这些行为允许业务流程的用户选择所需订阅的属性的列表。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-113">These allow users of the orchestration to select a list of the properties they need for their subscription.</span></span> <span data-ttu-id="7d0c2-114">这些属性是在构造消息形状中编写的。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-114">These properties are written in a construct message shape.</span></span> <span data-ttu-id="7d0c2-115">并非所有已写入到原始消息的上下文属性写入到新消息。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-115">Not all context properties that were written to the original message are written to the new message.</span></span>  
  
6.  <span data-ttu-id="7d0c2-116">业务流程将新消息放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-116">The orchestration drops the new message into the MessageBox.</span></span>  
  
7.  <span data-ttu-id="7d0c2-117">发送端口提取新消息并将其通过文件适配器发送至 \message enrichment\out 文件夹。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-117">The send port picks up the new message and sends it via the FILE adapter to the \Message Enrichment\Out folder.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="7d0c2-118">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="7d0c2-118">Where to Find This Sample</span></span>  
 <span data-ttu-id="7d0c2-119">此示例位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装文件夹：[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\Message Enrichment。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-119">This sample is located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\Message Enrichment.</span></span>  
  
 <span data-ttu-id="7d0c2-120">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="7d0c2-120">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="7d0c2-121">文件</span><span class="sxs-lookup"><span data-stu-id="7d0c2-121">File(s)</span></span>|<span data-ttu-id="7d0c2-122">Description</span><span class="sxs-lookup"><span data-stu-id="7d0c2-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7d0c2-123">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="7d0c2-123">Cleanup.bat</span></span>|<span data-ttu-id="7d0c2-124">取消部署示例方案。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-124">Undeploys the example scenario.</span></span> <span data-ttu-id="7d0c2-125">为了使它成功必须是业务流程没有活动实例。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-125">In order for it to succeed there must be no active instances of the orchestration.</span></span> <span data-ttu-id="7d0c2-126">否则，它将失败。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-126">Otherwise, it will fail.</span></span>|  
|<span data-ttu-id="7d0c2-127">MessageEnrichment.sln</span><span class="sxs-lookup"><span data-stu-id="7d0c2-127">MessageEnrichment.sln</span></span>|<span data-ttu-id="7d0c2-128">包含 MessageEnrichment 和 MessageEnrichmentLibrary 项目。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-128">Contains the MessageEnrichment and MessageEnrichmentLibrary projects.</span></span>|  
|<span data-ttu-id="7d0c2-129">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="7d0c2-129">Setup.bat</span></span>|<span data-ttu-id="7d0c2-130">将部署包含接收端口、 发送端口和业务流程的示例方案。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-130">Deploys an example scenario that consists of a receive port, send port, and orchestration.</span></span>|  
|<span data-ttu-id="7d0c2-131">EDIFACT_example.edi</span><span class="sxs-lookup"><span data-stu-id="7d0c2-131">EDIFACT_example.edi</span></span>|<span data-ttu-id="7d0c2-132">输入的 EDIFACT 消息。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-132">An input EDIFACT message.</span></span>|  
|<span data-ttu-id="7d0c2-133">X12_example.edi</span><span class="sxs-lookup"><span data-stu-id="7d0c2-133">X12_example.edi</span></span>|<span data-ttu-id="7d0c2-134">输入 X12 消息。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-134">An input X12 message.</span></span>|  
|<span data-ttu-id="7d0c2-135">MessageEnrichment.btproj</span><span class="sxs-lookup"><span data-stu-id="7d0c2-135">MessageEnrichment.btproj</span></span>|<span data-ttu-id="7d0c2-136">包含 MessageEnrichment 业务流程和架构的项目。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-136">The project containing the MessageEnrichment orchestrations and schemas.</span></span>|  
|<span data-ttu-id="7d0c2-137">MessageEnrichmentBindings.xml</span><span class="sxs-lookup"><span data-stu-id="7d0c2-137">MessageEnrichmentBindings.xml</span></span>|<span data-ttu-id="7d0c2-138">包含该业务流程、 端口和参与方绑定的文件。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-138">The file containing bindings for the orchestration, the ports, and the parties.</span></span>|  
|<span data-ttu-id="7d0c2-139">MessageEnrichmentOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="7d0c2-139">MessageEnrichmentOrchestration.odx</span></span>|<span data-ttu-id="7d0c2-140">将标头附加到消息的业务流程。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-140">The orchestration that appends the headers to the message.</span></span>|  
|<span data-ttu-id="7d0c2-141">MessageEnrichmentOrchestration.odx.cs</span><span class="sxs-lookup"><span data-stu-id="7d0c2-141">MessageEnrichmentOrchestration.odx.cs</span></span>|<span data-ttu-id="7d0c2-142">将标头附加到消息的业务流程代码。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-142">The orchestration code that appends the headers to the message.</span></span>|  
|<span data-ttu-id="7d0c2-143">EFACT_D98B_APERAK.xsd</span><span class="sxs-lookup"><span data-stu-id="7d0c2-143">EFACT_D98B_APERAK.xsd</span></span>|<span data-ttu-id="7d0c2-144">输入消息的 EDIFACT 架构。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-144">The EDIFACT schema for the input message.</span></span>|  
|<span data-ttu-id="7d0c2-145">Enriched_EFACT_D98B_APERAK.xsd</span><span class="sxs-lookup"><span data-stu-id="7d0c2-145">Enriched_EFACT_D98B_APERAK.xsd</span></span>|<span data-ttu-id="7d0c2-146">输出消息的 EDIFACT 架构。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-146">The EDIFACT schema for the output message.</span></span>|  
|<span data-ttu-id="7d0c2-147">X12_00401_864.xsd</span><span class="sxs-lookup"><span data-stu-id="7d0c2-147">X12_00401_864.xsd</span></span>|<span data-ttu-id="7d0c2-148">X12 输入消息的架构。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-148">The X12 schema for the input message.</span></span>|  
|<span data-ttu-id="7d0c2-149">Enriched_X12_00401_864.xsd</span><span class="sxs-lookup"><span data-stu-id="7d0c2-149">Enriched_X12_00401_864.xsd</span></span>|<span data-ttu-id="7d0c2-150">X12 输出消息的架构。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-150">The X12 schema for the output message.</span></span>|  
|<span data-ttu-id="7d0c2-151">Headers.xsd</span><span class="sxs-lookup"><span data-stu-id="7d0c2-151">Headers.xsd</span></span>|<span data-ttu-id="7d0c2-152">添加到输入消息的标头的架构。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-152">The schemas for the headers added to the input messages.</span></span>|  
|<span data-ttu-id="7d0c2-153">MessageEnrichmentLibrary.csproj</span><span class="sxs-lookup"><span data-stu-id="7d0c2-153">MessageEnrichmentLibrary.csproj</span></span>|<span data-ttu-id="7d0c2-154">包含 Headers.cs、 OrchestrationUtilities.cs 和 ParseHeaders.cs 文件的项目。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-154">The project containing the Headers.cs, OrchestrationUtilities.cs, and ParseHeaders.cs files.</span></span>|  
|<span data-ttu-id="7d0c2-155">Headers.cs</span><span class="sxs-lookup"><span data-stu-id="7d0c2-155">Headers.cs</span></span>|<span data-ttu-id="7d0c2-156">包括表示标头数据的类。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-156">Includes classes representing headers data.</span></span>|  
|<span data-ttu-id="7d0c2-157">OrchestrationUtilities.cs</span><span class="sxs-lookup"><span data-stu-id="7d0c2-157">OrchestrationUtilities.cs</span></span>|<span data-ttu-id="7d0c2-158">包括使用业务流程的实用工具方法。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-158">Includes utility methods used by orchestration.</span></span>|  
|<span data-ttu-id="7d0c2-159">ParseHeaders.cs</span><span class="sxs-lookup"><span data-stu-id="7d0c2-159">ParseHeaders.cs</span></span>|<span data-ttu-id="7d0c2-160">包括新的消息中使用的 UNA 默认值。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-160">Includes the default values for UNA that are used in the new messages.</span></span> <span data-ttu-id="7d0c2-161">这些值取自 ParseHeaders.cs 中的 SerializeEDIFACTHeaders 方法。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-161">These values are taken from the SerializeEDIFACTHeaders method in ParseHeaders.cs.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="7d0c2-162">如何使用此示例</span><span class="sxs-lookup"><span data-stu-id="7d0c2-162">How to Use This Sample</span></span>  
 <span data-ttu-id="7d0c2-163">本示例用作将交换标头附加到 EDI 事务集消息所必需的操作的可运行示例。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-163">Use this sample as a working example of the actions required to append interchange headers to EDI transaction-set messages.</span></span>  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="7d0c2-164">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="7d0c2-164">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="7d0c2-165">生成并初始化消息收集示例，您需要生成和部署本示例中，在 BizTalk 项目配置接收端口和位置，并配置两个不同的发送端口。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-165">To build and initialize the Message Enrichment sample, you need to build and deploy the BizTalk project for this sample, configure the receive port and location, and configure two different send ports.</span></span>  
  
#### <a name="to-build-and-deploy-the-biztalk-project-for-this-sample"></a><span data-ttu-id="7d0c2-166">若要生成和部署此示例的 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="7d0c2-166">To build and deploy the BizTalk project for this sample</span></span>  
  
1. <span data-ttu-id="7d0c2-167">使用 Notepad.Exe，打开[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\MessageEnrichment\\</span><span class="sxs-lookup"><span data-stu-id="7d0c2-167">Using Notepad.Exe, open [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\MessageEnrichment\\</span></span>  
   <span data-ttu-id="7d0c2-168">MessageEnrichment\properties\AssemblyInfo.cs 并在文件底部添加以下行：</span><span class="sxs-lookup"><span data-stu-id="7d0c2-168">MessageEnrichment\properties\AssemblyInfo.cs and add the following line at the bottom of the file:</span></span>  
  
   ```  
   [assembly: Microsoft.XLANGs.BaseTypes.BizTalkAssembly(typeof(Microsoft.BizTalk.XLANGs.BTXEngine.BTXService))]  
   ```  
  
2. <span data-ttu-id="7d0c2-169">保存修改的 AssemblyInfo.cs 文件，然后退出记事本。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-169">Save the modified AssemblyInfo.cs file and then exit Notepad.</span></span>  
  
3. <span data-ttu-id="7d0c2-170">在命令窗口中，转至以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="7d0c2-170">In a command window, move to the following folder:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="7d0c2-171">SDK\Samples\EDI\Message Enrichment</span><span class="sxs-lookup"><span data-stu-id="7d0c2-171">SDK\Samples\EDI\Message Enrichment</span></span>  
  
4. <span data-ttu-id="7d0c2-172">运行**Setup.bat**，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7d0c2-172">Run **Setup.bat**, which performs the following actions:</span></span>  
  
   -   <span data-ttu-id="7d0c2-173">创建接收 (**中**) 和发送 (**出**) \MessageEnrichment 文件夹中的以下示例的文件夹。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-173">Creates the receive (**in**) and send (**out**) folders for this sample in the \MessageEnrichment folder.</span></span>  
  
   -   <span data-ttu-id="7d0c2-174">密钥对写入 messageenrichmentlibrary\testkey.snk。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-174">Writes a key pair to MessageEnrichmentLibrary\testkey.snk</span></span>  
  
   -   <span data-ttu-id="7d0c2-175">生成并部署 MessageEnrichmentLibrary.btproj 项目。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-175">Builds and deploys the MessageEnrichmentLibrary.btproj project.</span></span>  
  
   -   <span data-ttu-id="7d0c2-176">生成并部署 MessageEnrichment.btproj 项目。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-176">Builds and deploys the MessageEnrichment.btproj project.</span></span>  
  
   -   <span data-ttu-id="7d0c2-177">读取 MessageEnrichmentBindings.xml 中的绑定信息。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-177">Reads binding information in MessageEnrichmentBindings.xml.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="7d0c2-178">此项目的绑定需要的 BizTalk 主机标记为受信任的身份验证。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-178">The binding for this project requires that the BizTalk host is marked as Authentication Trusted.</span></span>  <span data-ttu-id="7d0c2-179">若要使用这与不受信任的主机，修改 MessageEnrichmentBindings.xml 并更改 HostTrusted ="true"条目为 HostTrusted ="false"。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-179">In order to use this with a host that is not trusted, modify the MessageEnrichmentBindings.xml and change the HostTrusted=”true” entries to HostTrusted=”false”.</span></span>  
  
   -   <span data-ttu-id="7d0c2-180">更新业务流程绑定。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-180">Updates orchestration bindings.</span></span>  
  
   -   <span data-ttu-id="7d0c2-181">更新发送端口、 发送端口组和接收端口。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-181">Updates send ports, send port groups, and receive ports.</span></span>  
  
   -   <span data-ttu-id="7d0c2-182">更新参与方和登记。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-182">Updates parties and enlistments.</span></span>  
  
   -   <span data-ttu-id="7d0c2-183">启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-183">Starts the send port.</span></span>  
  
   -   <span data-ttu-id="7d0c2-184">启用接收位置。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-184">Enables the receive location.</span></span>  
  
   -   <span data-ttu-id="7d0c2-185">登记并启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-185">Enlists and starts the orchestration.</span></span>  
  
   <span data-ttu-id="7d0c2-186">现在便可使用本示例 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-186">BizTalk Server is ready now to work with this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="7d0c2-187">运行本示例</span><span class="sxs-lookup"><span data-stu-id="7d0c2-187">Running This Sample</span></span>  
 <span data-ttu-id="7d0c2-188">使用以下过程运行消息收集示例。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-188">Use the following procedure to run the Message Enrichment sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="7d0c2-189">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="7d0c2-189">To run this sample</span></span>  
  
1.  <span data-ttu-id="7d0c2-190">将 \MessageEnrichment\Instances 文件夹中的 EDIFACT_examples.edi 文件复制到 \MessageEnrichment\In 文件夹。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-190">Copy the EDIFACT_examples.edi file from the \MessageEnrichment\Instances folder into the \MessageEnrichment\In folder.</span></span>  
  
2.  <span data-ttu-id="7d0c2-191">验证 EDIFACT_examples.edi 文件将从 \MessageEnrichment\In 文件夹中消失，并且会显示在 \MessageEnrichment\Out 文件夹。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-191">Verify that the EDIFACT_examples.edi files disappears from the \MessageEnrichment\In folder, and appears in the \MessageEnrichment\Out folder.</span></span>  
  
3.  <span data-ttu-id="7d0c2-192">打开 \MessageEnrichment\Out 文件夹中的文件。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-192">Open the file in the \MessageEnrichment\Out folder.</span></span> <span data-ttu-id="7d0c2-193">验证它的 XML 表示形式 EDIFACT_examples.edi 文件在 \MessageEnrichment\Instances 文件夹中，并且是与输出文件包含 EDIFACT UNA、 UNB 和 UNG 标头的 EDIFACT_examples.edi 文件具有相同的内容。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-193">Verify that it is an XML representation of the EDIFACT_examples.edi file in the \MessageEnrichment\Instances folder, and that is has the same contents as the EDIFACT_examples.edi file, with the exception that the output file has EDIFACT UNA, UNB, and UNG headers.</span></span>  
  
4.  <span data-ttu-id="7d0c2-194">针对 \MessageEnrichment\Instances 文件夹中的 X12_examples.edi 文件重复步骤 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-194">Repeat steps 1 and 2 with the X12_examples.edi file from the \MessageEnrichment\Instances folder.</span></span>  
  
5.  <span data-ttu-id="7d0c2-195">打开 \MessageEnrichment\Out 文件夹中的新文件。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-195">Open the new file in the \MessageEnrichment\Out folder.</span></span> <span data-ttu-id="7d0c2-196">验证它是否的 XML 表示形式 X12_examples.edi 文件在 \MessageEnrichment\Instances 文件夹中，并且是与输出文件包含 X12 的 X12_examples.edi 文件具有相同内容 ISA 标头。</span><span class="sxs-lookup"><span data-stu-id="7d0c2-196">Verify that it is an XML representation of the X12_examples.edi file in the \MessageEnrichment\Instances folder, and that is has the same contents as the X12_examples.edi file, with the exception that the output file has X12 ISA headers.</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="7d0c2-197">类或方法在此示例中使用</span><span class="sxs-lookup"><span data-stu-id="7d0c2-197">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="7d0c2-198">None</span><span class="sxs-lookup"><span data-stu-id="7d0c2-198">None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d0c2-199">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d0c2-199">See Also</span></span>  
 [<span data-ttu-id="7d0c2-200">EDI 和 AS2（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="7d0c2-200">EDI and AS2 (BizTalk Server Samples Folder)</span></span>](../core/edi-and-as2-biztalk-server-samples-folder.md)