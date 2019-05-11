---
title: FlatFileReceive （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 90bd9e8d-6ed9-49c4-8437-c0c8b2a9a78d
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fcae5883f5230b7cd0e97051707133626c87cb4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388059"
---
# <a name="flatfilereceive-biztalk-server-sample"></a><span data-ttu-id="a04f2-102">FlatFileReceive （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="a04f2-102">FlatFileReceive (BizTalk Server Sample)</span></span>
<span data-ttu-id="a04f2-103">FlatFileReceive 示例演示如何使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]平面文件处理成等效的.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="a04f2-103">The FlatFileReceive sample demonstrates how you can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to process a flat file into the equivalent .xml file.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="a04f2-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="a04f2-104">What This Sample Does</span></span>  
 <span data-ttu-id="a04f2-105">此示例将 FFInput 文件夹配置为接收位置。</span><span class="sxs-lookup"><span data-stu-id="a04f2-105">This sample configures the folder FFInput as a receive location.</span></span> <span data-ttu-id="a04f2-106">在一个文件，将此文件夹中，将示例文件 FlatFileReceive_in.txt，如[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理该消息在此文件中使用以下步骤序列：</span><span class="sxs-lookup"><span data-stu-id="a04f2-106">When you place a file, such as the sample file FlatFileReceive_in.txt, into this folder, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes the message in this file using the following sequence of steps:</span></span>  

1.  <span data-ttu-id="a04f2-107">在接收位置文件夹 ffinput 下的输入文件读取的消息。</span><span class="sxs-lookup"><span data-stu-id="a04f2-107">Reads the message from the input file in the receive location folder FFInput.</span></span>  

2.  <span data-ttu-id="a04f2-108">在接收管道中，平面文件拆装器组件消息将从平面文件格式转换为等效的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="a04f2-108">In the receive pipeline, the Flat File Disassembler component converts the message from flat file format to the equivalent XML message.</span></span>  

3.  <span data-ttu-id="a04f2-109">在 MessageBox 数据库中，将消息路由到可以将 XML 消息写入发送适配器文件夹 ffoutput 下的文件发送端口。</span><span class="sxs-lookup"><span data-stu-id="a04f2-109">In the MessageBox database, the message is routed to a FILE send port that writes the XML message to a file in the send adapter folder FFOutput.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="a04f2-110">此示例设计方式和原因</span><span class="sxs-lookup"><span data-stu-id="a04f2-110">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="a04f2-111">示例消息的诸多基本设计在此示例中。</span><span class="sxs-lookup"><span data-stu-id="a04f2-111">The sample message dictates much of the basic design in this sample.</span></span> <span data-ttu-id="a04f2-112">必须使用平面文件拆装器和平面文件架构中自定义接收管道拆装平面文件消息。</span><span class="sxs-lookup"><span data-stu-id="a04f2-112">Flat file messages must be disassembled using the Flat File Disassembler and a flat file schema within a custom receive pipeline.</span></span> <span data-ttu-id="a04f2-113">下表总结了这些和其他设计元素。</span><span class="sxs-lookup"><span data-stu-id="a04f2-113">These and other design elements are summarized in the following table.</span></span>  


|     <span data-ttu-id="a04f2-114">设计元素</span><span class="sxs-lookup"><span data-stu-id="a04f2-114">Design element</span></span>      |                                                                                                                                                                  <span data-ttu-id="a04f2-115">选择的原因</span><span class="sxs-lookup"><span data-stu-id="a04f2-115">Reason(s) selected</span></span>                                                                                                                                                                   |
|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="a04f2-116">自定义接收管道</span><span class="sxs-lookup"><span data-stu-id="a04f2-116">Custom receive pipeline</span></span> | <span data-ttu-id="a04f2-117">-自定义管道使用平面文件拆装器和平面文件架构转换入站采购订单消息。</span><span class="sxs-lookup"><span data-stu-id="a04f2-117">-   The custom pipeline uses the Flat File Disassembler and a flat file schema to translate inbound purchase order messages.</span></span> <span data-ttu-id="a04f2-118">平面文件拆装器自身不是管道，配置中的接收管道时不能使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="a04f2-118">The Flat File Disassembler is not itself a pipeline and cannot be used when configuring a receive pipeline in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management console.</span></span> |
|    <span data-ttu-id="a04f2-119">平面文件架构</span><span class="sxs-lookup"><span data-stu-id="a04f2-119">Flat file schema</span></span>     |                           <span data-ttu-id="a04f2-120">-定义的所有相同的记录和字段特性 （包括结构） 作为 XML 架构，并提供一种机制，用于定义所有平面文件实例消息转换为等效的 XML 实例所需的平面文件特性消息 （或相反）。</span><span class="sxs-lookup"><span data-stu-id="a04f2-120">-   Define all of the same record and field characteristics (including structure) as an XML schema and provide a mechanism for defining all of the flat file characteristics that are required to translate a flat file instance message into an equivalent XML instance message (or vice versa).</span></span>                           |
|   <span data-ttu-id="a04f2-121">订阅筛选器</span><span class="sxs-lookup"><span data-stu-id="a04f2-121">Subscription filter</span></span>   |                                                                                                        <span data-ttu-id="a04f2-122">-订阅筛选器执行实际的路由通过捕获符合基于属性的字段的一个或多个条件的消息。</span><span class="sxs-lookup"><span data-stu-id="a04f2-122">-   The subscription filter performs the actual routing by capturing messages that meet one or more criteria based on property fields.</span></span>                                                                                                         |
|       <span data-ttu-id="a04f2-123">XMLTransmit</span><span class="sxs-lookup"><span data-stu-id="a04f2-123">XMLTransmit</span></span>       |                                                                                                           <span data-ttu-id="a04f2-124">-执行基本组装传出 XML 消息在需要时。</span><span class="sxs-lookup"><span data-stu-id="a04f2-124">-   Performs basic assembly of outgoing XML messages where needed.</span></span> <span data-ttu-id="a04f2-125">PassThruTransmit 管道未提供其他支持。</span><span class="sxs-lookup"><span data-stu-id="a04f2-125">The PassThruTransmit pipeline provides no additional support.</span></span>                                                                                                            |

 <span data-ttu-id="a04f2-126">通过结合这些元素构成一个解决方案，用于接受从接收位置的平面文件格式的采购订单消息并写出到发送位置生成的 XML 表示形式。</span><span class="sxs-lookup"><span data-stu-id="a04f2-126">These elements are combined to produce a solution that accepts purchase order messages in flat file format from the receive location and writes out the resulting XML representation to the send location.</span></span>  

 <span data-ttu-id="a04f2-127">下列注意事项适用于本示例的设计：</span><span class="sxs-lookup"><span data-stu-id="a04f2-127">The following considerations apply to the design of this sample:</span></span>  

-   <span data-ttu-id="a04f2-128">平面文件架构 (PO.xsd) 包含描述采购订单平面文件结构的扩展的标注。</span><span class="sxs-lookup"><span data-stu-id="a04f2-128">The flat file schema (PO.xsd) contains extended annotations describing the structure of the purchase order flat file.</span></span> <span data-ttu-id="a04f2-129">可以进行手动创建这些文件，但可以通过使用平面文件向导生成很多。</span><span class="sxs-lookup"><span data-stu-id="a04f2-129">These files can be created by hand, but many can be generated by using the Flat File Wizard.</span></span>  

-   <span data-ttu-id="a04f2-130">平面文件架构使用 elementFormDefault 值 Unqualified。</span><span class="sxs-lookup"><span data-stu-id="a04f2-130">The flat file schema uses an elementFormDefault value of Unqualified.</span></span> <span data-ttu-id="a04f2-131">这会生成正确的结果，但有多余且意外的 XML 命名空间 (xmlns) 限定。</span><span class="sxs-lookup"><span data-stu-id="a04f2-131">This produces correct results but with additional and unexpected XML namespace (xmlns) qualifications.</span></span> <span data-ttu-id="a04f2-132">使用 elementformdefault 的 Qualified 值可避免此问题。</span><span class="sxs-lookup"><span data-stu-id="a04f2-132">Use an elementFormDefault of Qualified to avoid this issue.</span></span>  

-   <span data-ttu-id="a04f2-133">XmlTransmit 用作发送管道。</span><span class="sxs-lookup"><span data-stu-id="a04f2-133">XmlTransmit is used as the send pipeline.</span></span> <span data-ttu-id="a04f2-134">在发送端口中不需要属性降级或其他消息处理时，请使用 PassThruTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="a04f2-134">Use the PassThruTransmit pipeline when property demotion or other messaging processing is not required in the send port.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="a04f2-135">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="a04f2-135">Where to Find This Sample</span></span>  
 <span data-ttu-id="a04f2-136">*\<Samples Path\>* \Pipelines\AssemblerDisassembler\FlatFileReceive\\</span><span class="sxs-lookup"><span data-stu-id="a04f2-136">*\<Samples Path\>* \Pipelines\AssemblerDisassembler\FlatFileReceive\\</span></span>  

 <span data-ttu-id="a04f2-137">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="a04f2-137">The following table shows the files in this sample and describes their purpose.</span></span>  


|                   <span data-ttu-id="a04f2-138">文件</span><span class="sxs-lookup"><span data-stu-id="a04f2-138">File(s)</span></span>                   |                                                                                           <span data-ttu-id="a04f2-139">Description</span><span class="sxs-lookup"><span data-stu-id="a04f2-139">Description</span></span>                                                                                            |
|---------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                 <span data-ttu-id="a04f2-140">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="a04f2-140">Cleanup.bat</span></span>                 | <span data-ttu-id="a04f2-141">用于取消部署程序集并从全局程序集缓存中删除。</span><span class="sxs-lookup"><span data-stu-id="a04f2-141">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="a04f2-142">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="a04f2-142">Removes send and receive ports.</span></span> <span data-ttu-id="a04f2-143">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="a04f2-143">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span> |
|            <span data-ttu-id="a04f2-144">FFReceivePipeline.btp</span><span class="sxs-lookup"><span data-stu-id="a04f2-144">FFReceivePipeline.btp</span></span>            |                       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a04f2-145">接收管道使用平面文件拆装器组件的文件。</span><span class="sxs-lookup"><span data-stu-id="a04f2-145">receive pipeline file with the Flat File Disassembler component.</span></span>                        |
| <span data-ttu-id="a04f2-146">FlatFileReceive.btproj, FlatFileReceive.sln</span><span class="sxs-lookup"><span data-stu-id="a04f2-146">FlatFileReceive.btproj, FlatFileReceive.sln</span></span> |                                                                           <span data-ttu-id="a04f2-147">本示例的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="a04f2-147">Project and solution files for this sample.</span></span>                                                                            |
|           <span data-ttu-id="a04f2-148">FlatFileReceive_in.txt</span><span class="sxs-lookup"><span data-stu-id="a04f2-148">FlatFileReceive_in.txt</span></span>            |                                                                                        <span data-ttu-id="a04f2-149">示例输入的文件。</span><span class="sxs-lookup"><span data-stu-id="a04f2-149">Sample input file.</span></span>                                                                                        |
|         <span data-ttu-id="a04f2-150">FlatFileReceiveBinding.xml</span><span class="sxs-lookup"><span data-stu-id="a04f2-150">FlatFileReceiveBinding.xml</span></span>          |                                                                          <span data-ttu-id="a04f2-151">用于如端口绑定之类的自动化设置。</span><span class="sxs-lookup"><span data-stu-id="a04f2-151">Used for automated setup such as port binding.</span></span>                                                                          |
|                   <span data-ttu-id="a04f2-152">PO.xsd</span><span class="sxs-lookup"><span data-stu-id="a04f2-152">PO.xsd</span></span>                    |                                                                                <span data-ttu-id="a04f2-153">入站平面文件架构。</span><span class="sxs-lookup"><span data-stu-id="a04f2-153">Schema for the inbound flat file.</span></span>                                                                                 |
|                  <span data-ttu-id="a04f2-154">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="a04f2-154">Setup.bat</span></span>                  |                                                                            <span data-ttu-id="a04f2-155">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="a04f2-155">Used to build and initialize this sample.</span></span>                                                                             |

## <a name="how-to-use-this-sample"></a><span data-ttu-id="a04f2-156">如何使用此示例</span><span class="sxs-lookup"><span data-stu-id="a04f2-156">How to Use This Sample</span></span>  
 <span data-ttu-id="a04f2-157">此示例作为基础用于平面文件处理解决方案。</span><span class="sxs-lookup"><span data-stu-id="a04f2-157">Use this sample as the basis for your own flat file processing solution.</span></span> <span data-ttu-id="a04f2-158">您可以扩展此示例中使用以适合自己需求的设计元素的很多。</span><span class="sxs-lookup"><span data-stu-id="a04f2-158">You can extend many of the design elements used in this sample to fit your own requirements.</span></span>  

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="a04f2-159">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="a04f2-159">Building and Initializing This Sample</span></span>  

1. <span data-ttu-id="a04f2-160">在命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="a04f2-160">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="a04f2-161">*\<Samples Path\>* \Pipelines\AssemblerDisassembler\FlatFileReceive</span><span class="sxs-lookup"><span data-stu-id="a04f2-161">*\<Samples Path\>* \Pipelines\AssemblerDisassembler\FlatFileReceive</span></span>  

2. <span data-ttu-id="a04f2-162">运行文件 Setup.bat，以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a04f2-162">Run the file Setup.bat, which performs the following actions:</span></span>  

   - <span data-ttu-id="a04f2-163">在文件夹中创建的输入 (FFInput) 和为本示例的输出 (FFOutput) 文件夹：</span><span class="sxs-lookup"><span data-stu-id="a04f2-163">Creates the input (FFInput) and output (FFOutput) folders for this sample in the folder:</span></span>  

      <span data-ttu-id="a04f2-164">*\<Samples Path\>* \Pipelines\AssemblerDisassembler\FlatFileReceive</span><span class="sxs-lookup"><span data-stu-id="a04f2-164">*\<Samples Path\>* \Pipelines\AssemblerDisassembler\FlatFileReceive</span></span>  

   - <span data-ttu-id="a04f2-165">编译并部署本示例的 Visual Studio 项目。</span><span class="sxs-lookup"><span data-stu-id="a04f2-165">Compiles and deploys the Visual Studio project for this sample.</span></span>  

   - <span data-ttu-id="a04f2-166">创建并绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置、 发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="a04f2-166">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="a04f2-167">本示例将显示以下警告时创建并绑定端口：`Warning: Receive handler not specified for receive location "FlatFileReceive_RL"; updating with first receive handler with matching transport type.` 您可以放心地忽略这些警告。</span><span class="sxs-lookup"><span data-stu-id="a04f2-167">This sample displays the following warning when creating and binding ports: `Warning: Receive handler not specified for receive location "FlatFileReceive_RL"; updating with first receive handler with matching transport type.` You can safely ignore these warnings.</span></span> <span data-ttu-id="a04f2-168">（若要应对可能的命名差异在用户安装中，主机名和接收处理程序中已省略绑定文件。）</span><span class="sxs-lookup"><span data-stu-id="a04f2-168">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  

   - <span data-ttu-id="a04f2-169">启用该接收位置，并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="a04f2-169">Enables the receive location, and starts the send port.</span></span>  

> [!NOTE]
>  <span data-ttu-id="a04f2-170">您应确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未报告任何错误在生成和初始化过程中尝试运行此示例之前。</span><span class="sxs-lookup"><span data-stu-id="a04f2-170">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="a04f2-171">如果你选择打开并生成本示例中的项目不运行 Setup.bat 的情况下，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。</span><span class="sxs-lookup"><span data-stu-id="a04f2-171">If you choose to open and build the project in this sample without running Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="a04f2-172">使用此密钥对生成程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="a04f2-172">Use this key pair to sign the resulting assembly.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="a04f2-173">若要撤消 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="a04f2-173">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="a04f2-174">必须运行 Setup.bat 前运行 Cleanup.bat 时间。</span><span class="sxs-lookup"><span data-stu-id="a04f2-174">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

## <a name="running-this-sample"></a><span data-ttu-id="a04f2-175">运行本示例</span><span class="sxs-lookup"><span data-stu-id="a04f2-175">Running This Sample</span></span>  

1.  <span data-ttu-id="a04f2-176">将 FlatFileReceive_in.txt 文件的副本放到 FFInput 文件夹下。</span><span class="sxs-lookup"><span data-stu-id="a04f2-176">Put a copy of the file FlatFileReceive_in.txt into the folder FFInput.</span></span>  

2.  <span data-ttu-id="a04f2-177">查看在 FFOutput 文件夹中创建的.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="a04f2-177">Observe the .xml file created in the folder FFOutput.</span></span> <span data-ttu-id="a04f2-178">输出文件的名称根据消息 ID GUID。</span><span class="sxs-lookup"><span data-stu-id="a04f2-178">The name of the output file is based on the message ID GUID.</span></span> <span data-ttu-id="a04f2-179">此文件包含在接收文件夹中放置的平面文件的 XML 等效项。</span><span class="sxs-lookup"><span data-stu-id="a04f2-179">This file contains XML equivalent of the flat file placed in the receive folder.</span></span>  

## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="a04f2-180">类或方法在此示例中使用</span><span class="sxs-lookup"><span data-stu-id="a04f2-180">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="a04f2-181">配置脚本 Setup.bat 和 Cleanup.bat 依赖以下管理的 Windows Management Instrumentation (WMI) 脚本：</span><span class="sxs-lookup"><span data-stu-id="a04f2-181">The configuration scripts Setup.bat and Cleanup.bat rely on the following administrative Windows Management Instrumentation (WMI) scripts:</span></span>  

- <span data-ttu-id="a04f2-182">Start Send Port\StartSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="a04f2-182">Start Send Port\StartSendPort.vbs</span></span>  

- <span data-ttu-id="a04f2-183">Enable Receive Location\EnableRecLoc</span><span class="sxs-lookup"><span data-stu-id="a04f2-183">Enable Receive Location\EnableRecLoc</span></span>  

- <span data-ttu-id="a04f2-184">删除发送端口 \removesendport</span><span class="sxs-lookup"><span data-stu-id="a04f2-184">Remove Send Port\RemoveSendPort</span></span>  

  <span data-ttu-id="a04f2-185">设置和清理批处理文件使用 BTSTask，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a04f2-185">The setup and cleanup batch files use BTSTask as follows:</span></span>  

- <span data-ttu-id="a04f2-186">**BTSTask ImportBindings**应用绑定文件并创建应用程序、 端口和绑定</span><span class="sxs-lookup"><span data-stu-id="a04f2-186">**BTSTask ImportBindings** to apply the binding file and create the application, ports, and bindings</span></span>  

- <span data-ttu-id="a04f2-187">**BTSTask RemoveApp，** 用于删除 FlatFileReceiveApplication</span><span class="sxs-lookup"><span data-stu-id="a04f2-187">**BTSTask RemoveApp** to remove the FlatFileReceiveApplication</span></span>  

## <a name="see-also"></a><span data-ttu-id="a04f2-188">请参阅</span><span class="sxs-lookup"><span data-stu-id="a04f2-188">See Also</span></span>  
- [<span data-ttu-id="a04f2-189">Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="a04f2-189">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
- [<span data-ttu-id="a04f2-190">平面文件反汇编程序管道组件</span><span class="sxs-lookup"><span data-stu-id="a04f2-190">Flat File Disassembler Pipeline Component</span></span>](../core/flat-file-disassembler-pipeline-component.md)   
- [<span data-ttu-id="a04f2-191">平面文件架构</span><span class="sxs-lookup"><span data-stu-id="a04f2-191">Flat File Schemas</span></span>](../core/flat-file-schemas.md)   
- [<span data-ttu-id="a04f2-192">默认管道</span><span class="sxs-lookup"><span data-stu-id="a04f2-192">Default Pipelines</span></span>](../core/default-pipelines.md)   
- <span data-ttu-id="a04f2-193">**WMI 脚本示例** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="a04f2-193">**WMI Script Samples** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>   
- [<span data-ttu-id="a04f2-194">BTSTask 命令行参考</span><span class="sxs-lookup"><span data-stu-id="a04f2-194">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)   
- [<span data-ttu-id="a04f2-195">FlatFileSend（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="a04f2-195">FlatFileSend (BizTalk Server Sample)</span></span>](../core/flatfilesend-biztalk-server-sample.md)
