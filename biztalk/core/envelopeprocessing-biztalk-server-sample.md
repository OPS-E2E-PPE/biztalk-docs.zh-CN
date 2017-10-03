---
title: "EnvelopeProcessing （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, envelopes
- flat files, processing
- examples, flat files
- examples, messages
- examples, envelopes
- envelopes, messages
- flat files, examples
- envelopes, examples
ms.assetid: b4cd979b-c7b4-446c-be29-c9f3169afa1f
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aee15dc6fffefd550a5b12c662d4df76ca09c1fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="envelopeprocessing-biztalk-server-sample"></a><span data-ttu-id="f3ce5-102">EnvelopeProcessing （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="f3ce5-102">EnvelopeProcessing (BizTalk Server Sample)</span></span>
<span data-ttu-id="f3ce5-103">EnvelopeProcessing 示例演示如何在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管道中处理消息和消息信封。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-103">The EnvelopeProcessing sample demonstrates how to process messages and message envelopes in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipelines.</span></span> <span data-ttu-id="f3ce5-104">此外，它还显示如何将平面文件消息处理成 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-104">Further, it shows how to process flat file messages into XML messages.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="f3ce5-105">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="f3ce5-105">What This Sample Does</span></span>  
 <span data-ttu-id="f3ce5-106">本示例将 EnvInput 文件夹配置为接收位置。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-106">This sample configures the folder EnvInput as a receive location.</span></span> <span data-ttu-id="f3ce5-107">在将文件（如示例文件 EnvelopeProcessing_in.txt）放入此文件夹后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将按照以下步骤处理该文件内的消息：</span><span class="sxs-lookup"><span data-stu-id="f3ce5-107">When you place a file, such as the sample file EnvelopeProcessing_in.txt, in this folder, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes the messages in this file using the following steps:</span></span>  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f3ce5-108"> 从接收位置文件夹 EnvInput 检索消息文件。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-108"> retrieves the message file from the receive location folder EnvInput.</span></span>  
  
2.  <span data-ttu-id="f3ce5-109">在接收管道中，平面文件拆装器管道组件将从平面文件消息中删除标头和尾部，并将其分析成各个消息。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-109">In the receive pipeline, the Flat File Disassembler pipeline component removes the header and trailer from the flat file messages, and parses them into individual messages.</span></span>  
  
3.  <span data-ttu-id="f3ce5-110">在 MessageBox 数据库中，使用订阅筛选器将消息路由到发送端口。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-110">In the MessageBox database, the messages are routed to the send port using subscription filters.</span></span>  
  
4.  <span data-ttu-id="f3ce5-111">在发送端口的发送管道中，XML 组装器管道组件将消息包装在 XML 信封中，然后将其放入发送适配器文件夹 EnvOutput 中。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-111">In the send pipeline of the send port, XML Assembler pipeline component wraps the messages in XML envelopes and then places them into the send adapter folder EnvOutput.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="f3ce5-112">本示例旨在如何以及为何</span><span class="sxs-lookup"><span data-stu-id="f3ce5-112">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="f3ce5-113">本示例的设计必须适合两个基本要求：</span><span class="sxs-lookup"><span data-stu-id="f3ce5-113">The design of this sample had to accommodate two basic requirements:</span></span>  
  
-   <span data-ttu-id="f3ce5-114">接收和处理包含一个或多个采购订单的平面文件消息。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-114">Receive and process a flat file message containing one or more purchase orders.</span></span>  
  
-   <span data-ttu-id="f3ce5-115">将一个包含一个采购订单和发件人信息的 XML 消息发送到一个目录，以便由后端处理系统提取。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-115">Send one XML message containing one purchase order and sender information to a directory for pickup by a back-end processing system.</span></span>  
  
 <span data-ttu-id="f3ce5-116">为满足这些要求，结合使用了平面文件/XML 架构和自定义管道。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-116">To meet these requirements, a combination of flat file/XML schemas and custom pipelines were used.</span></span> <span data-ttu-id="f3ce5-117">下表对以上设计元素和其他设计元素进行了总结。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-117">These and other design elements are summarized in the following table.</span></span>  
  
|<span data-ttu-id="f3ce5-118">设计元素</span><span class="sxs-lookup"><span data-stu-id="f3ce5-118">Design element</span></span>|<span data-ttu-id="f3ce5-119">选择的原因</span><span class="sxs-lookup"><span data-stu-id="f3ce5-119">Reason(s) selected</span></span>|  
|--------------------|--------------------------|  
|<span data-ttu-id="f3ce5-120">自定义接收管道</span><span class="sxs-lookup"><span data-stu-id="f3ce5-120">Custom receive pipeline</span></span>|<span data-ttu-id="f3ce5-121">-使用平面文件拆装器和平面文件架构将传入的采购订单消息。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-121">-   Uses the Flat File Disassembler and flat file schemas to translate inbound purchase order messages.</span></span>|  
|<span data-ttu-id="f3ce5-122">消息标头、正文和尾部的平面文件架构</span><span class="sxs-lookup"><span data-stu-id="f3ce5-122">Flat file schemas for message header, body, and trailer</span></span>|<span data-ttu-id="f3ce5-123">-定义的所有相同的记录和字段特性 （包括结构） 作为 XML 架构并提供一种机制，用于定义所有所需将平面文件实例消息转换为等效的 XML 实例的平面文件特征消息 （或相反）。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-123">-   Defines all of the same record and field characteristics (including structure) as XML schemas and provide a mechanism for defining all of the flat file characteristics that are required to translate a flat file instance message into an equivalent XML instance message (or vice versa).</span></span><br /><span data-ttu-id="f3ce5-124">标头、 正文和预告片架构用于拆分为离散区块处理的正文。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-124">-   Header, body, and trailer schemas are used to split the body into discrete chunks for processing.</span></span>|  
|<span data-ttu-id="f3ce5-125">信封架构</span><span class="sxs-lookup"><span data-stu-id="f3ce5-125">Envelope schema</span></span>|<span data-ttu-id="f3ce5-126">-用于包装具有从标头信息的单个采购订单。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-126">-   Used to wrap individual purchase orders with information from the header.</span></span>|  
|<span data-ttu-id="f3ce5-127">订阅筛选器</span><span class="sxs-lookup"><span data-stu-id="f3ce5-127">Subscription filter</span></span>|<span data-ttu-id="f3ce5-128">-订阅筛选器执行实际的路由通过捕获满足基于属性的字段的一个或多个条件的消息。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-128">-   The subscription filter performs the actual routing by capturing messages that meet one or more criteria based on property fields.</span></span>|  
|<span data-ttu-id="f3ce5-129">自定义发送管道</span><span class="sxs-lookup"><span data-stu-id="f3ce5-129">Custom send pipeline</span></span>|<span data-ttu-id="f3ce5-130">-使用 XML 汇编程序和信封和正文的架构的组合来将实例消息转换为 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-130">-   Uses the XML Assembler and a combination of envelope and body schemas to translate the instance messages into XML format.</span></span>|  
  
 <span data-ttu-id="f3ce5-131">以下注意事项适用于设计本示例：</span><span class="sxs-lookup"><span data-stu-id="f3ce5-131">The following considerations apply to the design of this sample.</span></span>  
  
-   <span data-ttu-id="f3ce5-132">平面文件架构 (PO.xsd) 包含描述采购订单平面文件的结构的扩展标注。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-132">The flat file schema (PO.xsd) contains extended annotations describing the structure of the purchase order flat file.</span></span> <span data-ttu-id="f3ce5-133">可手动创建这些文件，但大多数文件都可以使用平面文件向导生成。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-133">These files can be created by hand, but many can be generated by using the Flat File Wizard.</span></span>  
  
-   <span data-ttu-id="f3ce5-134">采购订单 (PO.xsd) 平面文件架构使用 elementFormDefault 值 Unqualified。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-134">The purchase order (PO.xsd) flat file schema uses an elementFormDefault value of Unqualified.</span></span> <span data-ttu-id="f3ce5-135">这会生成正确结果，但该结果带有其他意外 xmlns 限定。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-135">This produces correct results but with additional and unexpected xmlns qualifications.</span></span> <span data-ttu-id="f3ce5-136">使用 elementFormDefault 的 Qualified 值可避免此问题。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-136">Use an elementFormDefault of Qualified to avoid this issue.</span></span>  
  
-   <span data-ttu-id="f3ce5-137">使用标头和尾部平面文件架构从消息中分离出标题和尾部数据。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-137">Header and trailer flat file schemas are used to separate heading and trailing data from the message.</span></span> <span data-ttu-id="f3ce5-138">平面文件拆装器的标头、文档和尾部架构属性被分别设置为标头、采购订单和尾部架构。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-138">The Flat File Disassembler header, document, and trailer schema properties were set to the header, purchase order, and trailer schema respectively.</span></span>  
  
-   <span data-ttu-id="f3ce5-139">XML 信封架构结合标头和采购订单中的元素生成单个 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-139">The XML envelope schema combines elements from the header and purchase order to produce a single XML message.</span></span> <span data-ttu-id="f3ce5-140">标头架构提升到 SourceParty 字段源字段**BTS.bts_system_properties**命名空间; 信封架构提升此相同的值，从而可以降级到出站消息。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-140">The header schema promotes the Source field into the SourceParty field in the **BTS.bts_system_properties** namespace; the envelope schema promotes this same value, causing it to be demoted into the outbound message.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="f3ce5-141">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="f3ce5-141">Where to Find This Sample</span></span>  
 <span data-ttu-id="f3ce5-142">`<Samples Path>`\Pipelines\AssemblerDisassembler\EnvelopeProcessing\\</span><span class="sxs-lookup"><span data-stu-id="f3ce5-142">`<Samples Path>`\Pipelines\AssemblerDisassembler\EnvelopeProcessing\\</span></span>  
  
 <span data-ttu-id="f3ce5-143">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="f3ce5-143">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="f3ce5-144">文件</span><span class="sxs-lookup"><span data-stu-id="f3ce5-144">File(s)</span></span>|<span data-ttu-id="f3ce5-145">Description</span><span class="sxs-lookup"><span data-stu-id="f3ce5-145">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f3ce5-146">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="f3ce5-146">Cleanup.bat</span></span>|<span data-ttu-id="f3ce5-147">用于取消部署程序集并从全局程序集缓存中删除这些程序集。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-147">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="f3ce5-148">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-148">Removes send and receive ports.</span></span> <span data-ttu-id="f3ce5-149">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-149">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="f3ce5-150">EnvelopeProcessing.btproj、EnvelopeProcessing.sln</span><span class="sxs-lookup"><span data-stu-id="f3ce5-150">EnvelopeProcessing.btproj, EnvelopeProcessing.sln</span></span>|<span data-ttu-id="f3ce5-151">本示例的项目文件和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-151">Project and solution files for this sample.</span></span>|  
|<span data-ttu-id="f3ce5-152">EnvelopeProcessing_in.txt</span><span class="sxs-lookup"><span data-stu-id="f3ce5-152">EnvelopeProcessing_in.txt</span></span>|<span data-ttu-id="f3ce5-153">示例输入文件。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-153">Sample input file.</span></span>|  
|<span data-ttu-id="f3ce5-154">Header.xsd, PO.xsd、Trailer.xsd</span><span class="sxs-lookup"><span data-stu-id="f3ce5-154">Header.xsd, PO.xsd, Trailer.xsd</span></span>|<span data-ttu-id="f3ce5-155">分别为平面文件标头、正文和尾部的架构。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-155">Schema for flat file header, body, and trailer, respectively.</span></span>|  
|<span data-ttu-id="f3ce5-156">XmlEnvelope.xsd</span><span class="sxs-lookup"><span data-stu-id="f3ce5-156">XmlEnvelope.xsd</span></span>|<span data-ttu-id="f3ce5-157">出站 XML 信封的架构。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-157">Schema for outbound XML envelope.</span></span>|  
|<span data-ttu-id="f3ce5-158">EnvReceivePipeline.btp、EnvSendPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="f3ce5-158">EnvReceivePipeline.btp, EnvSendPipeline.btp</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f3ce5-159"> 分别使用平面文件拆装器和 XML 组装器管道组件接收和发送管道文件。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-159"> receive and send pipeline files with the Flat File Disassembler and XML Assembler pipeline components, respectively.</span></span>|  
|<span data-ttu-id="f3ce5-160">EnvelopeProcessingBinding.xml</span><span class="sxs-lookup"><span data-stu-id="f3ce5-160">EnvelopeProcessingBinding.xml</span></span>|<span data-ttu-id="f3ce5-161">用于如端口绑定之类的自动化设置。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-161">Used for automated setup such as port binding.</span></span>|  
|<span data-ttu-id="f3ce5-162">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="f3ce5-162">Setup.bat</span></span>|<span data-ttu-id="f3ce5-163">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-163">Used to build and initialize this sample.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="f3ce5-164">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="f3ce5-164">How to Use This Sample</span></span>  
 <span data-ttu-id="f3ce5-165">可将本示例用作您自己的平面文件处理解决方案的基础，</span><span class="sxs-lookup"><span data-stu-id="f3ce5-165">Use this sample as the basis for your own flat file processing solution.</span></span> <span data-ttu-id="f3ce5-166">并可根据自己的需要扩展本示例中用到的诸多设计元素。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-166">You can extend many of the design elements used in this sample to fit your own requirements.</span></span> <span data-ttu-id="f3ce5-167">以下是一些示例：</span><span class="sxs-lookup"><span data-stu-id="f3ce5-167">Some examples are as follows:</span></span>  
  
-   <span data-ttu-id="f3ce5-168">增强示例以在 XML 版本之外还编写每个采购订单的平面文件版本。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-168">Enhance the sample to write a flat file version of each purchase order in addition to the XML version.</span></span> <span data-ttu-id="f3ce5-169">这可以通过创建新的自定义发送管道和使用平面文件组装器来实现。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-169">You can do this by creating a new custom send pipeline and using the Flat File Assembler.</span></span> <span data-ttu-id="f3ce5-170">在平面文件组装器中，指定平面文件标头、采购订单和尾部架构。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-170">On the Flat File Assembler, specify the flat file header, purchase order, and trailer schemas.</span></span> <span data-ttu-id="f3ce5-171">当用于发送端口中时，这将生成带有标头/尾部信息的单个采购订单。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-171">When used in a send port, it produces individual purchase orders with header/trailer information.</span></span>  
  
-   <span data-ttu-id="f3ce5-172">使用采购订单中的更多信息增强信封。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-172">Enhance the envelope with more information from the purchase order.</span></span> <span data-ttu-id="f3ce5-173">若要将其他信息写入出站消息，请使用 Quick Promote 升级“发送到”名称或其他字段，将字段添加到信封中，然后将信封字段升级为相同字段。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-173">To write additional information into the outbound message, promote the "ship to" name or other fields using Quick Promote, add fields to the envelope, and then promote the envelope fields to the same field.</span></span> <span data-ttu-id="f3ce5-174">当通过组装器处理消息时，将对升级的属性降级并将其复制到出站消息中。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-174">When the message is processed through the assembler, promoted properties are demoted and copied into the outbound message.</span></span>  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="f3ce5-175">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="f3ce5-175">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-envelopeprocessing-sample"></a><span data-ttu-id="f3ce5-176">生成和初始化 EnvelopeProcessing 示例</span><span class="sxs-lookup"><span data-stu-id="f3ce5-176">To build and initialize the EnvelopeProcessing sample</span></span>  
  
1.  <span data-ttu-id="f3ce5-177">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="f3ce5-177">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="f3ce5-178">*\<示例路径 >*\Pipelines\AssemblerDisassembler\EnvelopeProcessing</span><span class="sxs-lookup"><span data-stu-id="f3ce5-178">*\<Samples Path>*\Pipelines\AssemblerDisassembler\EnvelopeProcessing</span></span>  
  
2.  <span data-ttu-id="f3ce5-179">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f3ce5-179">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="f3ce5-180">在下面的文件夹中，为本示例创建输入 (EnvInput) 和输出 (EnvOutput) 文件夹：</span><span class="sxs-lookup"><span data-stu-id="f3ce5-180">Creates the input (EnvInput) and output (EnvOutput) folders for this sample in the folder:</span></span>  
  
         <span data-ttu-id="f3ce5-181">*\<示例路径 >*\Pipelines\AssemblerDisassembler\EnvelopeProcessing\\</span><span class="sxs-lookup"><span data-stu-id="f3ce5-181">*\<Samples Path>*\Pipelines\AssemblerDisassembler\EnvelopeProcessing\\</span></span>  
  
    -   <span data-ttu-id="f3ce5-182">为本示例编译并部署 Visual Studio 项目。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-182">Compiles and deploys the Visual Studio project for this sample.</span></span>  
  
    -   <span data-ttu-id="f3ce5-183">创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置、发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-183">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  
  
         <span data-ttu-id="f3ce5-184">本示例在创建和绑定端口时将显示以下警告：</span><span class="sxs-lookup"><span data-stu-id="f3ce5-184">This sample displays the following warnings when creating and binding ports:</span></span>  
  
        ```  
        Warning: Receive handler not specified for receive location "EnvelopeProcessing_RL"; updating with first receive handler with matching transport type.  
        Warning: Host not specified for orchestration "EnvelopeProcessing"; updating with first available host.  
        ```  
  
         <span data-ttu-id="f3ce5-185">可以安全地忽略这些警告。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-185">You can safely ignore these warnings.</span></span> <span data-ttu-id="f3ce5-186">（考虑可能命名在用户安装中，主机名的差异和接收处理程序省略了从绑定文件。）</span><span class="sxs-lookup"><span data-stu-id="f3ce5-186">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  
  
    -   <span data-ttu-id="f3ce5-187">启用接收位置并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-187">Enables the receive location, and starts the send port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3ce5-188">在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-188">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3ce5-189">如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat，必须首先创建强名称密钥对使用.NET Framework 强名称工具 (sn.exe)。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-189">If you choose to open and build the project in this sample without running Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="f3ce5-190">使用此密钥对生成的程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-190">Use this key pair to sign the resulting assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3ce5-191">若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-191">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="f3ce5-192">在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-192">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="f3ce5-193">运行本示例</span><span class="sxs-lookup"><span data-stu-id="f3ce5-193">Running This Sample</span></span>  
  
#### <a name="to-run-the-envelopeprocessing-sample"></a><span data-ttu-id="f3ce5-194">运行 EnvelopeProcessing 示例</span><span class="sxs-lookup"><span data-stu-id="f3ce5-194">To run the EnvelopeProcessing sample</span></span>  
  
1.  <span data-ttu-id="f3ce5-195">将 EnvelopeProcessing_in.txt 文件的副本放到 EnvInput 文件夹下。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-195">Put a copy of the file EnvelopeProcessing_in.txt into the folder EnvInput.</span></span>  
  
2.  <span data-ttu-id="f3ce5-196">查看在文件夹 EnvOutput 中创建的三个 .xml 文件。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-196">Observe the three .xml files created in the folder EnvOutput.</span></span> <span data-ttu-id="f3ce5-197">这些 .xml 文件的名称基于其消息 ID GUID。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-197">The names of these .xml files are based on their message ID GUIDs.</span></span> <span data-ttu-id="f3ce5-198">它们包含从输入文件提取和在信封中包装的消息。</span><span class="sxs-lookup"><span data-stu-id="f3ce5-198">They contain the messages extracted from the input file and wrapped in envelopes.</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="f3ce5-199">本示例中使用的类或方法</span><span class="sxs-lookup"><span data-stu-id="f3ce5-199">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="f3ce5-200">配置脚本 Setup.bat 和 Cleanup.bat 依赖于以下 Windows 管理规范 (WMI) 管理脚本：</span><span class="sxs-lookup"><span data-stu-id="f3ce5-200">The configuration scripts Setup.bat and Cleanup.bat rely on the following administrative Windows Management Instrumentation (WMI) scripts:</span></span>  
  
-   <span data-ttu-id="f3ce5-201">启动发送端口\StartSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="f3ce5-201">Start Send Port\StartSendPort.vbs</span></span>  
  
-   <span data-ttu-id="f3ce5-202">启用接收位置\EnableRecLoc</span><span class="sxs-lookup"><span data-stu-id="f3ce5-202">Enable Receive Location\EnableRecLoc</span></span>  
  
-   <span data-ttu-id="f3ce5-203">删除发送端口\RemoveSendPort</span><span class="sxs-lookup"><span data-stu-id="f3ce5-203">Remove Send Port\RemoveSendPort</span></span>  
  
 <span data-ttu-id="f3ce5-204">安装和清除批处理文件使用以下 BTSTask：</span><span class="sxs-lookup"><span data-stu-id="f3ce5-204">The setup and cleanup batch files use BTSTask as follows:</span></span>  
  
-   <span data-ttu-id="f3ce5-205">**BTSTask ImportBindings**应用绑定文件并创建应用程序、 端口和绑定</span><span class="sxs-lookup"><span data-stu-id="f3ce5-205">**BTSTask ImportBindings** to apply the binding file and create the application, ports, and bindings</span></span>  
  
-   <span data-ttu-id="f3ce5-206">**BTSTask RemoveApp**删除 FlatFileReceiveApplication</span><span class="sxs-lookup"><span data-stu-id="f3ce5-206">**BTSTask RemoveApp** to remove the FlatFileReceiveApplication</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3ce5-207">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3ce5-207">See Also</span></span>  
 [<span data-ttu-id="f3ce5-208">管道 AssemblerDisassembler （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="f3ce5-208">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)