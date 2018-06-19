---
title: FlatFileSend （BizTalk Server 示例） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52dd0018-e272-40db-a26a-509d444d7106
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a9e967a8127a07b561e950b084bf799b0e2a4ee
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969691"
---
# <a name="flatfilesend-biztalk-server-sample"></a><span data-ttu-id="c755d-102">FlatFileSend（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="c755d-102">FlatFileSend (BizTalk Server Sample)</span></span>
<span data-ttu-id="c755d-103">FlatFileSend 示例演示如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将 XML 文件处理成等效的平面文件。</span><span class="sxs-lookup"><span data-stu-id="c755d-103">The FlatFileSend sample demonstrates how you can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to process an XML file into the equivalent flat file.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="c755d-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="c755d-104">What This Sample Does</span></span>  
 <span data-ttu-id="c755d-105">本示例将 FFInput 文件夹配置为接收位置。</span><span class="sxs-lookup"><span data-stu-id="c755d-105">This sample configures the folder FFInput as a receive location.</span></span> <span data-ttu-id="c755d-106">在将文件（如示例文件 FlatFileSend_in.xml）放入此文件夹后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将按照以下步骤处理该文件内的消息：</span><span class="sxs-lookup"><span data-stu-id="c755d-106">When you place a file, such as the sample file FlatFileSend_in.xml, into this folder, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes the message in this file using the following steps:</span></span>  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c755d-107"> 读取接收位置文件夹 FFInput 下的输入文件中的消息。</span><span class="sxs-lookup"><span data-stu-id="c755d-107"> reads the message from the input file in the receive location folder FFInput.</span></span>  
  
2.  <span data-ttu-id="c755d-108">相应消息通过 XML 接收管道传递。</span><span class="sxs-lookup"><span data-stu-id="c755d-108">The message is passed through an XML receive pipeline.</span></span>  
  
3.  <span data-ttu-id="c755d-109">在 MessageBox 数据库中，消息会路由至 FILE 发送端口，该端口具有一个配置有平面文件组装器组件的发送管道。</span><span class="sxs-lookup"><span data-stu-id="c755d-109">In the MessageBox database, the message is routed to a FILE send port that has a send pipeline configured with a Flat File Assembler component.</span></span> <span data-ttu-id="c755d-110">平面文件组装器组件使用平面文件架构将 XML 消息转换为等效的平面文件表示形式。</span><span class="sxs-lookup"><span data-stu-id="c755d-110">The Flat File Assembler component converts the XML message to an equivalent flat file representation using a flat file schema.</span></span>  
  
4.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c755d-111"> 将转换后的消息写入发送适配器文件夹 FFOutput 下的文本文件。</span><span class="sxs-lookup"><span data-stu-id="c755d-111"> writes the converted message to a text file in the send adapter folder FFOutput.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="c755d-112">本示例旨在如何以及为何</span><span class="sxs-lookup"><span data-stu-id="c755d-112">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="c755d-113">示例消息反映了本示例的诸多基本设计特征。</span><span class="sxs-lookup"><span data-stu-id="c755d-113">The sample message dictates much of the basic design in this sample.</span></span> <span data-ttu-id="c755d-114">平面文件消息必须使用自定义发送管道内的平面文件组装器和平面文件架构进行组装。</span><span class="sxs-lookup"><span data-stu-id="c755d-114">Flat file messages must be assembled using the Flat File Assembler and a flat file schema within a custom send pipeline.</span></span> <span data-ttu-id="c755d-115">下表对以上设计元素和其他设计元素进行了总结。</span><span class="sxs-lookup"><span data-stu-id="c755d-115">These and other design elements are summarized in the following table.</span></span>  
  
|<span data-ttu-id="c755d-116">设计元素</span><span class="sxs-lookup"><span data-stu-id="c755d-116">Design element</span></span>|<span data-ttu-id="c755d-117">选择的原因</span><span class="sxs-lookup"><span data-stu-id="c755d-117">Reason(s) selected</span></span>|  
|--------------------|--------------------------|  
|<span data-ttu-id="c755d-118">自定义发送管道</span><span class="sxs-lookup"><span data-stu-id="c755d-118">Custom send pipeline</span></span>|<span data-ttu-id="c755d-119">-自定义管道使用平面文件汇编器和平面文件架构来将实例消息转换为平面文件格式;平面文件汇编器本身不是管道，并且不能在配置中的发送管道[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="c755d-119">-   The custom pipeline uses the Flat File Assembler and a flat file schema to translate the instance messages into flat file format; the Flat File Assembler is not itself a pipeline and cannot be used when configuring a send pipeline in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management console.</span></span>|  
|<span data-ttu-id="c755d-120">平面文件架构</span><span class="sxs-lookup"><span data-stu-id="c755d-120">Flat file schema</span></span>|<span data-ttu-id="c755d-121">-定义的所有相同的记录和字段特性 （包括结构） 为 XML 架构，并提供了用于定义所有所需转换为平面文件消息 （或相反） 的 XML 实例消息的平面文件特征的机制。</span><span class="sxs-lookup"><span data-stu-id="c755d-121">-   Define all of the same record and field characteristics (including structure) as an XML schema and provides a mechanism for defining all of the flat file characteristics that are required to translate an XML instance message into a flat file message (or vice versa).</span></span>|  
|<span data-ttu-id="c755d-122">订阅筛选器</span><span class="sxs-lookup"><span data-stu-id="c755d-122">Subscription filter</span></span>|<span data-ttu-id="c755d-123">-订阅筛选器执行实际的路由通过捕获满足基于属性的字段的一个或多个条件的消息。</span><span class="sxs-lookup"><span data-stu-id="c755d-123">-   The subscription filter performs the actual routing by capturing messages that meet one or more criteria based on property fields.</span></span>|  
|<span data-ttu-id="c755d-124">XMLReceive</span><span class="sxs-lookup"><span data-stu-id="c755d-124">XMLReceive</span></span>|<span data-ttu-id="c755d-125">-执行 XML 的入站消息的处理。</span><span class="sxs-lookup"><span data-stu-id="c755d-125">-   Performs processing of inbound XML messages.</span></span> <span data-ttu-id="c755d-126">在本示例中，用作源消息的是采购订单的 XML 表示形式。</span><span class="sxs-lookup"><span data-stu-id="c755d-126">For this example an XML representation of a purchase order is used as the source message.</span></span>|  
  
 <span data-ttu-id="c755d-127">通过结合这些元素，产生了一个可从接收位置接受 XML 格式的采购订单消息并将平面文件格式的采购订单写出到发送位置的解决方案。</span><span class="sxs-lookup"><span data-stu-id="c755d-127">These elements are combined to produce a solution that accepts purchase order messages in XML format from the receive location and writes out a flat file purchase order to the send location.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="c755d-128">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="c755d-128">Where to Find This Sample</span></span>  
 <span data-ttu-id="c755d-129">*\<示例路径\>* \Pipelines\AssemblerDisassembler\FlatFileSend</span><span class="sxs-lookup"><span data-stu-id="c755d-129">*\<Samples Path\>* \Pipelines\AssemblerDisassembler\FlatFileSend</span></span>  
  
 <span data-ttu-id="c755d-130">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="c755d-130">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="c755d-131">文件</span><span class="sxs-lookup"><span data-stu-id="c755d-131">File(s)</span></span>|<span data-ttu-id="c755d-132">Description</span><span class="sxs-lookup"><span data-stu-id="c755d-132">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c755d-133">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="c755d-133">Cleanup.bat</span></span>|<span data-ttu-id="c755d-134">用于取消部署程序集并从全局程序集缓存中删除这些程序集。</span><span class="sxs-lookup"><span data-stu-id="c755d-134">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="c755d-135">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="c755d-135">Removes send and receive ports.</span></span> <span data-ttu-id="c755d-136">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="c755d-136">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="c755d-137">FlatFileSend.btproj、FlatFileSend.sln</span><span class="sxs-lookup"><span data-stu-id="c755d-137">FlatFileSend.btproj, FlatFileSend.sln</span></span>|<span data-ttu-id="c755d-138">本示例的项目文件和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="c755d-138">Project and solution files for this sample.</span></span>|  
|<span data-ttu-id="c755d-139">FlatFileSendBinding.xml</span><span class="sxs-lookup"><span data-stu-id="c755d-139">FlatFileSendBinding.xml</span></span>|<span data-ttu-id="c755d-140">用于如端口绑定之类的自动化设置。</span><span class="sxs-lookup"><span data-stu-id="c755d-140">Used for automated setup such as port binding.</span></span>|  
|<span data-ttu-id="c755d-141">FlatFileSend_in.xml</span><span class="sxs-lookup"><span data-stu-id="c755d-141">FlatFileSend_in.xml</span></span>|<span data-ttu-id="c755d-142">示例输入文件。</span><span class="sxs-lookup"><span data-stu-id="c755d-142">Sample input file.</span></span>|  
|<span data-ttu-id="c755d-143">PO.xsd</span><span class="sxs-lookup"><span data-stu-id="c755d-143">PO.xsd</span></span>|<span data-ttu-id="c755d-144">出站平面文件的架构。</span><span class="sxs-lookup"><span data-stu-id="c755d-144">Schema for outbound flat file.</span></span>|  
|<span data-ttu-id="c755d-145">SendPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="c755d-145">SendPipeline.btp</span></span>|<span data-ttu-id="c755d-146">带平面文件组装器组件的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送管道文件。</span><span class="sxs-lookup"><span data-stu-id="c755d-146">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send pipeline file with the Flat File Assembler component.</span></span>|  
|<span data-ttu-id="c755d-147">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="c755d-147">Setup.bat</span></span>|<span data-ttu-id="c755d-148">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="c755d-148">Used to build and initialize this sample.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="c755d-149">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="c755d-149">How to Use This Sample</span></span>  
 <span data-ttu-id="c755d-150">可将本示例用作您自己的平面文件处理解决方案的基础，</span><span class="sxs-lookup"><span data-stu-id="c755d-150">Use this sample as the basis for your own flat file processing solution.</span></span> <span data-ttu-id="c755d-151">并可根据自己的需要扩展本示例中用到的诸多设计元素。</span><span class="sxs-lookup"><span data-stu-id="c755d-151">You can extend many of the design elements used in this sample to fit your own requirements.</span></span>  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="c755d-152">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="c755d-152">Building and Initializing This Sample</span></span>  
  
1.  <span data-ttu-id="c755d-153">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="c755d-153">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="c755d-154">*\<示例路径\>* \Pipelines\AssemblerDisassembler\FlatFileSend</span><span class="sxs-lookup"><span data-stu-id="c755d-154">*\<Samples Path\>* \Pipelines\AssemblerDisassembler\FlatFileSend</span></span>  
  
2.  <span data-ttu-id="c755d-155">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c755d-155">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="c755d-156">在下面的文件夹中，为本示例创建输入 (FFInput) 和输出 (FFOutput) 文件夹：</span><span class="sxs-lookup"><span data-stu-id="c755d-156">Creates the input (FFInput) and output (FFOutput) folders for this sample in the folder:</span></span>  
  
         <span data-ttu-id="c755d-157">*\<示例路径\>* \Pipelines\AssemblerDisassembler\FlatFileSend</span><span class="sxs-lookup"><span data-stu-id="c755d-157">*\<Samples Path\>* \Pipelines\AssemblerDisassembler\FlatFileSend</span></span>  
  
    -   <span data-ttu-id="c755d-158">编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]此示例项目。</span><span class="sxs-lookup"><span data-stu-id="c755d-158">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for this sample.</span></span>  
  
    -   <span data-ttu-id="c755d-159">创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置、发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="c755d-159">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c755d-160">此示例显示以下警告时创建和绑定的端口：`Warning: Receive handler not specified for receive location "FlatFileSend_RL"; updating with first receive handler with matching transport type. Warning: Host not specified for orchestration "FlatFileSend"; updating with first available host.`可以放心地忽略这些警告。</span><span class="sxs-lookup"><span data-stu-id="c755d-160">This sample displays the following warnings when creating and binding the ports: `Warning: Receive handler not specified for receive location "FlatFileSend_RL"; updating with first receive handler with matching transport type. Warning: Host not specified for orchestration "FlatFileSend"; updating with first available host.` You can safely ignore these warnings.</span></span> <span data-ttu-id="c755d-161">（考虑可能命名在用户安装中，主机名的差异和接收处理程序省略了从绑定文件。）</span><span class="sxs-lookup"><span data-stu-id="c755d-161">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  
  
    -   <span data-ttu-id="c755d-162">启用接收位置并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="c755d-162">Enables the receive location, and starts the send port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c755d-163">在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="c755d-163">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c755d-164">如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat，必须首先创建强名称密钥对使用.NET Framework 强名称工具 (sn.exe)。</span><span class="sxs-lookup"><span data-stu-id="c755d-164">If you choose to open and build the project in this sample without running Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="c755d-165">使用此密钥对生成的程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="c755d-165">Use this key pair to sign the resulting assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c755d-166">若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="c755d-166">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="c755d-167">在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。</span><span class="sxs-lookup"><span data-stu-id="c755d-167">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="c755d-168">运行本示例</span><span class="sxs-lookup"><span data-stu-id="c755d-168">Running This Sample</span></span>  
  
1.  <span data-ttu-id="c755d-169">将 FlatFileSend_in.xml 文件的副本放到 FFInput 文件夹下。</span><span class="sxs-lookup"><span data-stu-id="c755d-169">Put a copy of the file FlatFileSend_in.xml into the folder FFInput.</span></span>  
  
2.  <span data-ttu-id="c755d-170">查看在 FFOutput 文件夹中创建的文本文件。</span><span class="sxs-lookup"><span data-stu-id="c755d-170">Observe the text file created in the folder FFOutput.</span></span> <span data-ttu-id="c755d-171">文本文件的名称取决于消息 ID GUID。</span><span class="sxs-lookup"><span data-stu-id="c755d-171">The name of the text file is based on the message ID GUID.</span></span> <span data-ttu-id="c755d-172">此文件包含与 XML 输入文件 FlatFileSend_in.xml 等效的平面文件。</span><span class="sxs-lookup"><span data-stu-id="c755d-172">This file contains the flat file equivalent of the XML input file FlatFileSend_in.xml.</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="c755d-173">本示例中使用的类或方法</span><span class="sxs-lookup"><span data-stu-id="c755d-173">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="c755d-174">配置脚本 Setup.bat 和 Cleanup.bat 依赖于以下 Windows 管理规范 (WMI) 管理脚本：</span><span class="sxs-lookup"><span data-stu-id="c755d-174">The configuration scripts Setup.bat and Cleanup.bat rely on the following administrative Windows Management Instrumentation (WMI) scripts:</span></span>  
  
-   <span data-ttu-id="c755d-175">启动发送端口\StartSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="c755d-175">Start Send Port\StartSendPort.vbs</span></span>  
  
-   <span data-ttu-id="c755d-176">启用接收位置\EnableRecLoc</span><span class="sxs-lookup"><span data-stu-id="c755d-176">Enable Receive Location\EnableRecLoc</span></span>  
  
-   <span data-ttu-id="c755d-177">删除发送端口\RemoveSendPort</span><span class="sxs-lookup"><span data-stu-id="c755d-177">Remove Send Port\RemoveSendPort</span></span>  
  
 <span data-ttu-id="c755d-178">安装和清除批处理文件使用以下 BTSTask：</span><span class="sxs-lookup"><span data-stu-id="c755d-178">The setup and cleanup batch files use BTSTask as follows:</span></span>  
  
-   <span data-ttu-id="c755d-179">**BTSTask ImportBindings**应用绑定文件并创建应用程序、 端口和绑定</span><span class="sxs-lookup"><span data-stu-id="c755d-179">**BTSTask ImportBindings** to apply the binding file and create the application, ports, and bindings</span></span>  
  
-   <span data-ttu-id="c755d-180">**BTSTask RemoveApp**删除 FlatFileSendApplication</span><span class="sxs-lookup"><span data-stu-id="c755d-180">**BTSTask RemoveApp** to remove the FlatFileSendApplication</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c755d-181">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c755d-181">See Also</span></span>  
-  [<span data-ttu-id="c755d-182">平面文件架构</span><span class="sxs-lookup"><span data-stu-id="c755d-182">Flat File Schemas</span></span>](../core/flat-file-schemas.md)   
-  [<span data-ttu-id="c755d-183">默认管道</span><span class="sxs-lookup"><span data-stu-id="c755d-183">Default Pipelines</span></span>](../core/default-pipelines.md)   
-  [<span data-ttu-id="c755d-184">Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="c755d-184">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
-  <span data-ttu-id="c755d-185">**WMI 脚本示例**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="c755d-185">**WMI Script Samples** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
-  [<span data-ttu-id="c755d-186">BTSTask 命令行参考</span><span class="sxs-lookup"><span data-stu-id="c755d-186">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)   
-  [<span data-ttu-id="c755d-187">FlatFileReceive（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="c755d-187">FlatFileReceive (BizTalk Server Sample)</span></span>](../core/flatfilereceive-biztalk-server-sample.md)