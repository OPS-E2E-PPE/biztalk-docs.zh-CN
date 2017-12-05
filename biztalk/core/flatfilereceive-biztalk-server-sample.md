---
title: "FlatFileReceive （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90bd9e8d-6ed9-49c4-8437-c0c8b2a9a78d
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db996437cce8cb6f89fb00b589fcbc95429e72f2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="flatfilereceive-biztalk-server-sample"></a><span data-ttu-id="1d6f7-102">FlatFileReceive （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="1d6f7-102">FlatFileReceive (BizTalk Server Sample)</span></span>
<span data-ttu-id="1d6f7-103">FlatFileReceive 示例演示如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将平面文件处理成等效的 .xml 文件。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-103">The FlatFileReceive sample demonstrates how you can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to process a flat file into the equivalent .xml file.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="1d6f7-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="1d6f7-104">What This Sample Does</span></span>  
 <span data-ttu-id="1d6f7-105">本示例将 FFInput 文件夹配置为接收位置。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-105">This sample configures the folder FFInput as a receive location.</span></span> <span data-ttu-id="1d6f7-106">在将文件（如示例文件 FlatFileReceive_in.txt）放入此文件夹后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将按照以下一系列步骤处理该文件内的消息：</span><span class="sxs-lookup"><span data-stu-id="1d6f7-106">When you place a file, such as the sample file FlatFileReceive_in.txt, into this folder, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes the message in this file using the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="1d6f7-107">读取接收位置文件夹 FFInput 下的输入文件中的消息。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-107">Reads the message from the input file in the receive location folder FFInput.</span></span>  
  
2.  <span data-ttu-id="1d6f7-108">在接收管道中，平面文件拆装器组件将平面文件格式的消息转换为等效的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-108">In the receive pipeline, the Flat File Disassembler component converts the message from flat file format to the equivalent XML message.</span></span>  
  
3.  <span data-ttu-id="1d6f7-109">在 MessageBox 数据库中，消息会路由至 FILE 发送端口，该端口将 XML 消息写入到发送适配器文件夹 FFOutput 中的某一文件中。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-109">In the MessageBox database, the message is routed to a FILE send port that writes the XML message to a file in the send adapter folder FFOutput.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="1d6f7-110">本示例旨在如何以及为何</span><span class="sxs-lookup"><span data-stu-id="1d6f7-110">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="1d6f7-111">示例消息反映了本示例的诸多基本设计特征。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-111">The sample message dictates much of the basic design in this sample.</span></span> <span data-ttu-id="1d6f7-112">平面文件消息必须使用自定义接收管道内的平面文件拆装器和平面文件架构进行拆装。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-112">Flat file messages must be disassembled using the Flat File Disassembler and a flat file schema within a custom receive pipeline.</span></span> <span data-ttu-id="1d6f7-113">下表对以上设计元素和其他设计元素进行了总结。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-113">These and other design elements are summarized in the following table.</span></span>  
  
|<span data-ttu-id="1d6f7-114">设计元素</span><span class="sxs-lookup"><span data-stu-id="1d6f7-114">Design element</span></span>|<span data-ttu-id="1d6f7-115">选择的原因</span><span class="sxs-lookup"><span data-stu-id="1d6f7-115">Reason(s) selected</span></span>|  
|--------------------|--------------------------|  
|<span data-ttu-id="1d6f7-116">自定义接收管道</span><span class="sxs-lookup"><span data-stu-id="1d6f7-116">Custom receive pipeline</span></span>|<span data-ttu-id="1d6f7-117">-自定义管道使用平面文件拆装器和平面文件架构转换入站采购订单消息。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-117">-   The custom pipeline uses the Flat File Disassembler and a flat file schema to translate inbound purchase order messages.</span></span> <span data-ttu-id="1d6f7-118">平面文件拆装器自身不是管道，因此在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中配置接收管道时不能使用平面文件拆装器。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-118">The Flat File Disassembler is not itself a pipeline and cannot be used when configuring a receive pipeline in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management console.</span></span>|  
|<span data-ttu-id="1d6f7-119">平面文件架构</span><span class="sxs-lookup"><span data-stu-id="1d6f7-119">Flat file schema</span></span>|<span data-ttu-id="1d6f7-120">-定义的所有相同的记录和字段特性 （包括结构） 作为 XML 架构，并提供用于定义所有所需将平面文件实例消息转换为等效的 XML 实例的平面文件特征的机制消息 （或相反）。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-120">-   Define all of the same record and field characteristics (including structure) as an XML schema and provide a mechanism for defining all of the flat file characteristics that are required to translate a flat file instance message into an equivalent XML instance message (or vice versa).</span></span>|  
|<span data-ttu-id="1d6f7-121">订阅筛选器</span><span class="sxs-lookup"><span data-stu-id="1d6f7-121">Subscription filter</span></span>|<span data-ttu-id="1d6f7-122">-订阅筛选器执行实际的路由通过捕获满足基于属性的字段的一个或多个条件的消息。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-122">-   The subscription filter performs the actual routing by capturing messages that meet one or more criteria based on property fields.</span></span>|  
|<span data-ttu-id="1d6f7-123">XMLTransmit</span><span class="sxs-lookup"><span data-stu-id="1d6f7-123">XMLTransmit</span></span>|<span data-ttu-id="1d6f7-124">-执行基本的程序集的传出 XML 消息在需要时。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-124">-   Performs basic assembly of outgoing XML messages where needed.</span></span> <span data-ttu-id="1d6f7-125">PassThruTransmit 管道不提供其他支持。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-125">The PassThruTransmit pipeline provides no additional support.</span></span>|  
  
 <span data-ttu-id="1d6f7-126">通过结合这些元素，产生了一个可从接收位置接受平面文件格式的采购订单消息并将生成的 XML 表示形式写出到发送位置的解决方案。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-126">These elements are combined to produce a solution that accepts purchase order messages in flat file format from the receive location and writes out the resulting XML representation to the send location.</span></span>  
  
 <span data-ttu-id="1d6f7-127">下列注意事项适用于此示例的设计：</span><span class="sxs-lookup"><span data-stu-id="1d6f7-127">The following considerations apply to the design of this sample:</span></span>  
  
-   <span data-ttu-id="1d6f7-128">平面文件架构 (PO.xsd) 包含描述采购订单平面文件的结构的扩展标注。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-128">The flat file schema (PO.xsd) contains extended annotations describing the structure of the purchase order flat file.</span></span> <span data-ttu-id="1d6f7-129">可手动创建这些文件，但大多数文件都可以使用平面文件向导生成。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-129">These files can be created by hand, but many can be generated by using the Flat File Wizard.</span></span>  
  
-   <span data-ttu-id="1d6f7-130">平面文件架构使用 elementFormDefault 的 Unqualified 值。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-130">The flat file schema uses an elementFormDefault value of Unqualified.</span></span> <span data-ttu-id="1d6f7-131">这会生成正确结果，但该结果带有其他意外 XML 命名空间 (xmlns) 限定。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-131">This produces correct results but with additional and unexpected XML namespace (xmlns) qualifications.</span></span> <span data-ttu-id="1d6f7-132">使用 elementFormDefault 的 Qualified 值可避免此问题。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-132">Use an elementFormDefault of Qualified to avoid this issue.</span></span>  
  
-   <span data-ttu-id="1d6f7-133">XmlTransmit 用作发送管道。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-133">XmlTransmit is used as the send pipeline.</span></span> <span data-ttu-id="1d6f7-134">当发送管道中不需要属性降级或其他消息处理时，请使用 PassThruTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-134">Use the PassThruTransmit pipeline when property demotion or other messaging processing is not required in the send port.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="1d6f7-135">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="1d6f7-135">Where to Find This Sample</span></span>  
 <span data-ttu-id="1d6f7-136">*\<示例路径\>*\Pipelines\AssemblerDisassembler\FlatFileReceive\\</span><span class="sxs-lookup"><span data-stu-id="1d6f7-136">*\<Samples Path\>*\Pipelines\AssemblerDisassembler\FlatFileReceive\\</span></span>  
  
 <span data-ttu-id="1d6f7-137">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="1d6f7-137">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="1d6f7-138">文件</span><span class="sxs-lookup"><span data-stu-id="1d6f7-138">File(s)</span></span>|<span data-ttu-id="1d6f7-139">Description</span><span class="sxs-lookup"><span data-stu-id="1d6f7-139">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1d6f7-140">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="1d6f7-140">Cleanup.bat</span></span>|<span data-ttu-id="1d6f7-141">用于取消部署程序集并从全局程序集缓存中删除这些程序集。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-141">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="1d6f7-142">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-142">Removes send and receive ports.</span></span> <span data-ttu-id="1d6f7-143">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-143">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="1d6f7-144">FFReceivePipeline.btp</span><span class="sxs-lookup"><span data-stu-id="1d6f7-144">FFReceivePipeline.btp</span></span>|<span data-ttu-id="1d6f7-145">带平面文件拆装器组件的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收管道文件。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-145">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive pipeline file with the Flat File Disassembler component.</span></span>|  
|<span data-ttu-id="1d6f7-146">FlatFileReceive.btproj、FlatFileReceive.sln</span><span class="sxs-lookup"><span data-stu-id="1d6f7-146">FlatFileReceive.btproj, FlatFileReceive.sln</span></span>|<span data-ttu-id="1d6f7-147">本示例的项目文件和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-147">Project and solution files for this sample.</span></span>|  
|<span data-ttu-id="1d6f7-148">FlatFileReceive_in.txt</span><span class="sxs-lookup"><span data-stu-id="1d6f7-148">FlatFileReceive_in.txt</span></span>|<span data-ttu-id="1d6f7-149">示例输入文件。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-149">Sample input file.</span></span>|  
|<span data-ttu-id="1d6f7-150">FlatFileReceiveBinding.xml</span><span class="sxs-lookup"><span data-stu-id="1d6f7-150">FlatFileReceiveBinding.xml</span></span>|<span data-ttu-id="1d6f7-151">用于如端口绑定之类的自动化设置。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-151">Used for automated setup such as port binding.</span></span>|  
|<span data-ttu-id="1d6f7-152">PO.xsd</span><span class="sxs-lookup"><span data-stu-id="1d6f7-152">PO.xsd</span></span>|<span data-ttu-id="1d6f7-153">入站平面文件的架构。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-153">Schema for the inbound flat file.</span></span>|  
|<span data-ttu-id="1d6f7-154">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="1d6f7-154">Setup.bat</span></span>|<span data-ttu-id="1d6f7-155">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-155">Used to build and initialize this sample.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="1d6f7-156">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="1d6f7-156">How to Use This Sample</span></span>  
 <span data-ttu-id="1d6f7-157">可将本示例用作您自己的平面文件处理解决方案的基础，</span><span class="sxs-lookup"><span data-stu-id="1d6f7-157">Use this sample as the basis for your own flat file processing solution.</span></span> <span data-ttu-id="1d6f7-158">并可根据自己的需要扩展本示例中用到的诸多设计元素。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-158">You can extend many of the design elements used in this sample to fit your own requirements.</span></span>  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="1d6f7-159">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="1d6f7-159">Building and Initializing This Sample</span></span>  
  
1.  <span data-ttu-id="1d6f7-160">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="1d6f7-160">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="1d6f7-161">*\<示例路径\>*\Pipelines\AssemblerDisassembler\FlatFileReceive</span><span class="sxs-lookup"><span data-stu-id="1d6f7-161">*\<Samples Path\>*\Pipelines\AssemblerDisassembler\FlatFileReceive</span></span>  
  
2.  <span data-ttu-id="1d6f7-162">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1d6f7-162">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="1d6f7-163">在下面的文件夹中，为本示例创建输入 (FFInput) 和输出 (FFOutput) 文件夹：</span><span class="sxs-lookup"><span data-stu-id="1d6f7-163">Creates the input (FFInput) and output (FFOutput) folders for this sample in the folder:</span></span>  
  
         <span data-ttu-id="1d6f7-164">*\<示例路径\>*\Pipelines\AssemblerDisassembler\FlatFileReceive</span><span class="sxs-lookup"><span data-stu-id="1d6f7-164">*\<Samples Path\>*\Pipelines\AssemblerDisassembler\FlatFileReceive</span></span>  
  
    -   <span data-ttu-id="1d6f7-165">为本示例编译并部署 Visual Studio 项目。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-165">Compiles and deploys the Visual Studio project for this sample.</span></span>  
  
    -   <span data-ttu-id="1d6f7-166">创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置、发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-166">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="1d6f7-167">此示例显示以下警告时创建和绑定端口：`Warning: Receive handler not specified for receive location "FlatFileReceive_RL"; updating with first receive handler with matching transport type.`可以放心地忽略这些警告。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-167">This sample displays the following warning when creating and binding ports: `Warning: Receive handler not specified for receive location "FlatFileReceive_RL"; updating with first receive handler with matching transport type.` You can safely ignore these warnings.</span></span> <span data-ttu-id="1d6f7-168">（考虑可能命名在用户安装中，主机名的差异和接收处理程序省略了从绑定文件。）</span><span class="sxs-lookup"><span data-stu-id="1d6f7-168">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  
  
    -   <span data-ttu-id="1d6f7-169">启用接收位置并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-169">Enables the receive location, and starts the send port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d6f7-170">在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-170">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d6f7-171">如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat，必须首先创建强名称密钥对使用.NET Framework 强名称工具 (sn.exe)。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-171">If you choose to open and build the project in this sample without running Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="1d6f7-172">使用此密钥对生成的程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-172">Use this key pair to sign the resulting assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d6f7-173">若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-173">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="1d6f7-174">在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-174">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="1d6f7-175">运行本示例</span><span class="sxs-lookup"><span data-stu-id="1d6f7-175">Running This Sample</span></span>  
  
1.  <span data-ttu-id="1d6f7-176">将 FlatFileReceive_in.txt 文件的副本放到 FFInput 文件夹下。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-176">Put a copy of the file FlatFileReceive_in.txt into the folder FFInput.</span></span>  
  
2.  <span data-ttu-id="1d6f7-177">查看在 FFOutput 文件夹中创建的 .xml 文件。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-177">Observe the .xml file created in the folder FFOutput.</span></span> <span data-ttu-id="1d6f7-178">此输出文件是根据消息 ID GUID 命名的。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-178">The name of the output file is based on the message ID GUID.</span></span> <span data-ttu-id="1d6f7-179">此文件包含与接收文件夹中放置的平面文件等效的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="1d6f7-179">This file contains XML equivalent of the flat file placed in the receive folder.</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="1d6f7-180">本示例中使用的类或方法</span><span class="sxs-lookup"><span data-stu-id="1d6f7-180">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="1d6f7-181">配置脚本 Setup.bat 和 Cleanup.bat 依赖于以下 Windows 管理规范 (WMI) 管理脚本：</span><span class="sxs-lookup"><span data-stu-id="1d6f7-181">The configuration scripts Setup.bat and Cleanup.bat rely on the following administrative Windows Management Instrumentation (WMI) scripts:</span></span>  
  
-   <span data-ttu-id="1d6f7-182">启动发送端口\StartSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="1d6f7-182">Start Send Port\StartSendPort.vbs</span></span>  
  
-   <span data-ttu-id="1d6f7-183">启用接收位置\EnableRecLoc</span><span class="sxs-lookup"><span data-stu-id="1d6f7-183">Enable Receive Location\EnableRecLoc</span></span>  
  
-   <span data-ttu-id="1d6f7-184">删除发送端口\RemoveSendPort</span><span class="sxs-lookup"><span data-stu-id="1d6f7-184">Remove Send Port\RemoveSendPort</span></span>  
  
 <span data-ttu-id="1d6f7-185">安装和清除批处理文件使用以下 BTSTask：</span><span class="sxs-lookup"><span data-stu-id="1d6f7-185">The setup and cleanup batch files use BTSTask as follows:</span></span>  
  
-   <span data-ttu-id="1d6f7-186">**BTSTask ImportBindings**应用绑定文件并创建应用程序、 端口和绑定</span><span class="sxs-lookup"><span data-stu-id="1d6f7-186">**BTSTask ImportBindings** to apply the binding file and create the application, ports, and bindings</span></span>  
  
-   <span data-ttu-id="1d6f7-187">**BTSTask RemoveApp**删除 FlatFileReceiveApplication</span><span class="sxs-lookup"><span data-stu-id="1d6f7-187">**BTSTask RemoveApp** to remove the FlatFileReceiveApplication</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d6f7-188">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d6f7-188">See Also</span></span>  
-  [<span data-ttu-id="1d6f7-189">Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="1d6f7-189">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
-  [<span data-ttu-id="1d6f7-190">平面文件反汇编程序管道组件</span><span class="sxs-lookup"><span data-stu-id="1d6f7-190">Flat File Disassembler Pipeline Component</span></span>](../core/flat-file-disassembler-pipeline-component.md)   
-  [<span data-ttu-id="1d6f7-191">平面文件架构</span><span class="sxs-lookup"><span data-stu-id="1d6f7-191">Flat File Schemas</span></span>](../core/flat-file-schemas.md)   
-  [<span data-ttu-id="1d6f7-192">默认管道</span><span class="sxs-lookup"><span data-stu-id="1d6f7-192">Default Pipelines</span></span>](../core/default-pipelines.md)   
-  <span data-ttu-id="1d6f7-193">**WMI 脚本示例**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="1d6f7-193">**WMI Script Samples** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>   
-  [<span data-ttu-id="1d6f7-194">BTSTask 命令行参考</span><span class="sxs-lookup"><span data-stu-id="1d6f7-194">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)   
-  [<span data-ttu-id="1d6f7-195">FlatFileSend（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="1d6f7-195">FlatFileSend (BizTalk Server Sample)</span></span>](../core/flatfilesend-biztalk-server-sample.md)