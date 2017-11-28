---
title: "管道工具 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline tools, XMLAsm.exe
- pipeline tools, FFDasm.exe
- Pipeline.exe
- FFDasm.exe
- pipeline tools, XMLDasm.exe
- pipeline tools
- XMLAsm.exe
- pipeline tools, DSDump.exe
- FFAsm.exe
- pipeline tools, FFAsm.exe
- pipeline tools, how to
- pipeline tools, about pipeline tools
- pipeline tools, Pipeline.exe
- utilities, pipeline tools
- XMLDasm.exe
ms.assetid: ca4d053a-1473-4d40-8cd0-1ed3a3af988a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c64b61c1c96b0ad6f9185ccd511d00f6dae2251
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="pipeline-tools"></a><span data-ttu-id="1481c-102">管道工具</span><span class="sxs-lookup"><span data-stu-id="1481c-102">Pipeline Tools</span></span>
<span data-ttu-id="1481c-103">使用随 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 软件开发工具包 (SDK) 提供的管道工具可以验证管道在正常工作，而不必配置 BizTalk Server 环境，如发送/接收端口。</span><span class="sxs-lookup"><span data-stu-id="1481c-103">The pipeline tools supplied with the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Software Development Kit (SDK) enable you to verify that a pipeline is functioning correctly without having to configure the BizTalk Server environment, such as send/receive ports.</span></span> <span data-ttu-id="1481c-104">管道工具还具有以下用途：</span><span class="sxs-lookup"><span data-stu-id="1481c-104">You can also use the pipeline tools to:</span></span>  
  
-   <span data-ttu-id="1481c-105">调试服务器环境外的第三方管道组件。</span><span class="sxs-lookup"><span data-stu-id="1481c-105">Debug third-party pipeline components outside of the server environment.</span></span>  
  
-   <span data-ttu-id="1481c-106">诊断解析引擎错误消息。</span><span class="sxs-lookup"><span data-stu-id="1481c-106">Diagnose parsing engine error messages.</span></span>  
  
-   <span data-ttu-id="1481c-107">试验不同的架构，但不必编译、部署、取消部署和重新编译。</span><span class="sxs-lookup"><span data-stu-id="1481c-107">Experiment with different schemas without the burden of compiling, deploying, undeploying, and recompiling.</span></span>  
  
-   <span data-ttu-id="1481c-108">浏览平面文件和 XML 程序集/拆装器行为。</span><span class="sxs-lookup"><span data-stu-id="1481c-108">Explore flat file and XML assembler/disassembler behavior.</span></span>  
  
-   <span data-ttu-id="1481c-109">查看拆装器输出，发现哪些消息上下文属性已升级及属性值。</span><span class="sxs-lookup"><span data-stu-id="1481c-109">View disassembler output and discover which message context properties are promoted and their values.</span></span>  
  
-   <span data-ttu-id="1481c-110">运行没有拆装器和组装器组件的发送/接收管道（例如，您可以查看 S/MIME 解码器的输出）。</span><span class="sxs-lookup"><span data-stu-id="1481c-110">Run send/receive pipelines without disassembler and assembler components (for example, you can view the output of the S/MIME decoder).</span></span>  
  
-   <span data-ttu-id="1481c-111">单独对管道（而不是整个消息传送子系统）进行精细的性能测量。</span><span class="sxs-lookup"><span data-stu-id="1481c-111">Make fine-grained performance measurements of the pipeline alone (rather than the entire messaging subsystem).</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="1481c-112">在 SDK 中的位置</span><span class="sxs-lookup"><span data-stu-id="1481c-112">Location in SDK</span></span>  
 <span data-ttu-id="1481c-113">\<*安装路径*> \SDK\Utilities\PipelineTools</span><span class="sxs-lookup"><span data-stu-id="1481c-113">\<*Installation Path*>\SDK\Utilities\PipelineTools</span></span>  
  
 <span data-ttu-id="1481c-114">将管道工具用于执行、调试和分析管道和管道组件（即平面文件和 XML 组装器/拆装器组件）。</span><span class="sxs-lookup"><span data-stu-id="1481c-114">You use pipeline tools for executing, debugging, and profiling pipelines, and pipeline components (that is, flat file and XML assembler/disassembler components).</span></span>  
  
## <a name="file-inventory"></a><span data-ttu-id="1481c-115">文件库存</span><span class="sxs-lookup"><span data-stu-id="1481c-115">File Inventory</span></span>  
 <span data-ttu-id="1481c-116">下表列出了管道工具文件并说明其用途。</span><span class="sxs-lookup"><span data-stu-id="1481c-116">The following table lists the pipeline tools files and describes their purpose.</span></span>  
  
|<span data-ttu-id="1481c-117">文件</span><span class="sxs-lookup"><span data-stu-id="1481c-117">File(s)</span></span>|<span data-ttu-id="1481c-118">Description</span><span class="sxs-lookup"><span data-stu-id="1481c-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1481c-119">DSDump.exe</span><span class="sxs-lookup"><span data-stu-id="1481c-119">DSDump.exe</span></span>|<span data-ttu-id="1481c-120">允许您转储文档架构结构，它是一个或多个 XSD 架构的内存中轻量表示形式，有或没有平面文件批注。</span><span class="sxs-lookup"><span data-stu-id="1481c-120">Enables you to dump the document schema structure, which is an in-memory lightweight representation of the one or more XSD schemas, with or without flat file annotations.</span></span> <span data-ttu-id="1481c-121">此工具在您获取诸如 $Root$0$3$2 这样的解析引擎错误并且需要对其进行解码时很有帮助。</span><span class="sxs-lookup"><span data-stu-id="1481c-121">This tool can be helpful when you get parsing engine errors such as $Root$0$3$2 and you need to decode them.</span></span> <span data-ttu-id="1481c-122">$ 后的数字表示基于 0 的索引或记录，这些索引或记录显示在文档架构中。</span><span class="sxs-lookup"><span data-stu-id="1481c-122">Numbers after $ mean 0-based index or records as they appear in the document schema.</span></span>|  
|<span data-ttu-id="1481c-123">FFAsm.exe</span><span class="sxs-lookup"><span data-stu-id="1481c-123">FFAsm.exe</span></span>|<span data-ttu-id="1481c-124">运行平面文件组装器组件，通过模拟发送管道来直接调用它，从而允许您看到它如何将用户的 XML 文档序列化或组装到平面文件文档中。</span><span class="sxs-lookup"><span data-stu-id="1481c-124">Runs the flat file assembler component, directly invoking it by emulating a send pipeline to enable you to see how it serializes or assembles a user's XML document(s) into a flat file document.</span></span>|  
|<span data-ttu-id="1481c-125">FFDasm.exe</span><span class="sxs-lookup"><span data-stu-id="1481c-125">FFDasm.exe</span></span>|<span data-ttu-id="1481c-126">运行平面文件拆装器组件，通过模拟接收管道来直接调用它，从而允许您看到它如何将用户的平面文件文档解析或拆装到一个或多个 XML 文档中。</span><span class="sxs-lookup"><span data-stu-id="1481c-126">Runs the flat file disassembler component, directly invoking it by emulating a receive pipeline to enable you to see how it parses or disassembles a user's flat file document into one or more XML documents.</span></span>|  
|<span data-ttu-id="1481c-127">Pipeline.exe</span><span class="sxs-lookup"><span data-stu-id="1481c-127">Pipeline.exe</span></span>|<span data-ttu-id="1481c-128">运行发送或接收管道；接受一个或多个输入文档及其部分、XSD 架构和相关信息；并且在管道运行后生成输出文档。</span><span class="sxs-lookup"><span data-stu-id="1481c-128">Runs a send or receive pipeline; accepts one or more input documents and their parts, XSD schemas and related information; and produces an output document after the pipeline runs.</span></span> <span data-ttu-id="1481c-129">Pipeline.exe 不会访问 BizTalk Server 数据库，因此包含 BizTalk Framework 汇编程序和反汇编程序组件的管道的访问[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]期间执行数据库可能不受支持。</span><span class="sxs-lookup"><span data-stu-id="1481c-129">Pipeline.exe does not access BizTalk Server databases, so pipelines containing BizTalk Framework assembler and disassembler components that access [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases during execution may not be supported.</span></span>|  
|<span data-ttu-id="1481c-130">XMLAsm.exe</span><span class="sxs-lookup"><span data-stu-id="1481c-130">XMLAsm.exe</span></span>|<span data-ttu-id="1481c-131">运行 XML 组装器组件，通过模拟发送管道来直接调用它，从而允许您看到它如何将用户的 XML 文档序列化、组装或封装到输出 XML 文档中。</span><span class="sxs-lookup"><span data-stu-id="1481c-131">Runs the XML assembler component, directly invoking it by emulating a send pipeline to enable you to see how it serializes, assembles, or envelopes a user's XML document(s) into an output XML document.</span></span>|  
|<span data-ttu-id="1481c-132">XMLDasm.exe</span><span class="sxs-lookup"><span data-stu-id="1481c-132">XMLDasm.exe</span></span>|<span data-ttu-id="1481c-133">运行 XML 拆装器组件，通过模拟接收管道来直接调用它，从而允许您看到它如何将用户的 XML 文档解析、拆装或解封装到一个或多个 XML 文档中。</span><span class="sxs-lookup"><span data-stu-id="1481c-133">Runs the XML disassembler component, directly invoking it by emulating a receive pipeline to enable you to see how it parses, disassembles, or un-envelopes a user's XML document into one or more XML documents.</span></span>|  
  
## <a name="usage"></a><span data-ttu-id="1481c-134">用法</span><span class="sxs-lookup"><span data-stu-id="1481c-134">Usage</span></span>  
 <span data-ttu-id="1481c-135">后面的部分针对每个文件提供了更详细的说明。</span><span class="sxs-lookup"><span data-stu-id="1481c-135">A more detailed description of each file is provided in the sections that follow.</span></span>  
  
### <a name="dsdumpexe"></a><span data-ttu-id="1481c-136">DSDump.exe</span><span class="sxs-lookup"><span data-stu-id="1481c-136">DSDump.exe</span></span>  
 <span data-ttu-id="1481c-137">DSDump.exe 允许您转储文档架构结构，它是一个或多个 XSD 架构的内存中轻量表示形式，有或没有平面文件批注。</span><span class="sxs-lookup"><span data-stu-id="1481c-137">DSDump.exe enables you to dump the document schema structure, which is an in-memory lightweight representation of one or more XSD schemas, with or without flat file annotations.</span></span>  
  
 <span data-ttu-id="1481c-138">DSDump.exe（文档架构转储工具）支持以下命令行参数：</span><span class="sxs-lookup"><span data-stu-id="1481c-138">DSDump.exe (document schema dump tool) supports the following command-line parameter:</span></span>  
  
```  
DSDump.exe schemaFileName  
```  
  
 <span data-ttu-id="1481c-139">如果成功，DSDump 则将文档架构显示到控制台。</span><span class="sxs-lookup"><span data-stu-id="1481c-139">In case of success, DSDump prints the document schema to the console.</span></span>  
  
### <a name="ffasmexe"></a><span data-ttu-id="1481c-140">FFAsm.exe</span><span class="sxs-lookup"><span data-stu-id="1481c-140">FFAsm.exe</span></span>  
 <span data-ttu-id="1481c-141">FFAsm.exe（平面文件组装器）支持以下命令行参数：</span><span class="sxs-lookup"><span data-stu-id="1481c-141">FFAsm.exe (flat file assembler) supports the following command-line parameters:</span></span>  
  
```  
usage: ffasm document... [-dm documentMask...]-bs bodySchema [ -hs headerSchema ] [ -ts trailerSchema ] [ -c ] [ -d ] [ -sb ] [ -m filenamemask ] [ -en encoding ] [ -v ]  
  
where:  
  document           XML document(s)  
  documentMask       XML document(s) file mask, e.g., c:\\documents\\*.xml  
  bodySchema         Flat File body schema  
  headerSchema       Flat File header schema  
  trailerSchema      Flat File trailer schema  
  -c                 Display assembled FF message on the console  
  -d                 Demote properties  
  -sb                Set body schema(s) as design-time property  
  -m                 Output file name mask (default is %MessageID%)  
  encoding           Output message encoding name (e.g. windows-1252) or   
                         code page (e.g. 936)  
  -v                 Verbose mode  
  
file name macros:  
  %MessageID%        FF message identifier (Guid)  
  %MessagePartID%    FF message part identifier (Guid)  
  
```  
  
 <span data-ttu-id="1481c-142">例如，如果您希望将三个输入 XML 文档组装到一个具有头部和属性降级的平面文件文档，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="1481c-142">For example, if you want to assemble three input XML documents into a single flat file document with a header and property demotion, use the following command:</span></span>  
  
```  
FFAsm.exe file_in1.xml file_in2.xml file_in3.xml –hs myHeaderSchema.xsd –bs myBodySchema.xsd -d  
```  
  
### <a name="ffdasmexe"></a><span data-ttu-id="1481c-143">FFDasm.exe</span><span class="sxs-lookup"><span data-stu-id="1481c-143">FFDasm.exe</span></span>  
 <span data-ttu-id="1481c-144">FFDasm.exe（平面文件拆装器）支持以下命令行参数：</span><span class="sxs-lookup"><span data-stu-id="1481c-144">FFDasm.exe (flat file disassembler) supports the following command-line parameters:</span></span>  
  
```  
usage: ffdasm document -bs bodySchema [ -hs headerSchema ] [ -ts trailerSchema ] [ -s ] [ -c ] [ -p ] [ -m filenamemask ] [ -en encoding ] [ -v ]  
  
where:  
  document           Flat File document  
  bodySchema         Flat File body schema  
  headerSchema       Flat File header schema  
  trailerSchema      Flat File trailer schema  
  -s                 Validate document structure  
  -c                 Display disassembled XML message on the console  
  -p                 Display promoted properties on the console  
  encoding           Input message body part encoding name (e.g. windows-1252) or code page (e.g., 396)  
  -m                 Output file name mask (default is %MessageID%)  
  -v                 Verbous mode  
  
file name macros:  
  %MessageID%        XML message identifier (Guid)  
  %MessagePartID%    XML message part identifier (Guid)  
  
```  
  
 <span data-ttu-id="1481c-145">例如，如果您希望拆装一个具有头部、正文和尾部的平面文件文档，并将结果显示到控制台，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="1481c-145">For example, if you want to disassemble a flat file document that has a header, body, and trailer, and display the results to the console, use the following command:</span></span>  
  
```  
FFDasm.exe file_in.txt –hs myHeaderSchema.xsd –bs myBodySchema.xsd –ts myTrailerSchema.xsd –c  
```  
  
### <a name="pipelineexe"></a><span data-ttu-id="1481c-146">Pipeline.exe</span><span class="sxs-lookup"><span data-stu-id="1481c-146">Pipeline.exe</span></span>  
 <span data-ttu-id="1481c-147">Pipeline.exe（管道工具）支持以下命令行参数：</span><span class="sxs-lookup"><span data-stu-id="1481c-147">Pipeline.exe (the Pipeline tool) supports the following command-line parameters:</span></span>  
  
```  
usage: pipeline ( pipeline[.btp] | -pt pipelineTypeName [ -an assemblyName ] ) -d document... [ -part part... ] [ -s schema[.xsd][:namespace.type]... ] [ -proj project[.btproj] ] [ -p ] [ -c ] [ -t ] [ -m filenamemask ] [ -pm partfilenamemask ] [ -en encoding ] [ -v ]  
  
where:  
  pipeline                Pipeline file name  
  pipelineTypeName     Compiled pipeline assembly qualified type name (e.g.   
"MyPipelines.ReceivePipeline, MyPipelines,   
Version=1.0.0.0, Culture=neutral,   
PublicKeyToken=e03965cb5971ad66" or full name (e.g.   
"MyPipelines.ReceivePipeline") if assembly name is   
specified  
  assemblyName         Compiled pipeline assembly file name (e.g.   
MyPipelines.dll) or name (e.g. "MyPipelines,   
Version=1.0.0.0, Culture=neutral,   
PublicKeyToken=e03965cb5971ad66")  
  document             Input document(s)  
  part                 Input document's part  
  schema               Schema file name  
  namespace            Schema namespace (as in BizTalk project system)  
  type                 Schema type (as in BizTalk project system)  
  project              BizTalk project file  
  -p                   Display promoted context properties for receive and   
send pipelines, and promote context properties for   
send pipelines  
  -c                      Display output document on the console  
  -t                      Display elapsed time of components execution  
  filenamemask         Output message file name mask (default is   
Message_%MessageID%.out)  
  partfilenamemask     Output part file name mask (default is   
Part_%MessagePartID%.out)  
  encoding             Output message encoding name (e.g. windows-1252)   
or code page (e.g. 936)  
  -v                   Verbous mode  
  
note:  
You can specify namespace and type for schemas either using namespace.type notation in schema file reference or by using BizTalk project file.  
  
file name macros:  
  %MessageID%           Message identifier (Guid)  
  %MessagePartID%       Message part identifier (Guid)  
  %MessageNumber%       Message number  
  
```  
  
 <span data-ttu-id="1481c-148">例如，如果要使用 mySchema.xsd 从 ReceivePipeline.btp（具有 XML 拆装器和 XML 验证器组件）运行接收管道，并将结果显示到控制台，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="1481c-148">For example, if you want to run a receive pipeline from the file ReceivePipeline.btp (which has XML disassembler and XML validator components) using mySchema.xsd and display the results to the console, use the following command:</span></span>  
  
```  
Pipeline.exe ReceivePipeline.btp –d file_in.xml –s MySchema.xsd:MyProject.MySchema -c  
  
```  
  
 <span data-ttu-id="1481c-149">\-或者-</span><span class="sxs-lookup"><span data-stu-id="1481c-149">\- Or -</span></span>  
  
```  
Pipeline.exe ReceivePipeline.btp –d file_in.xml –s MySchema.xsd –proj MyProject.btproj -c  
  
```  
  
 <span data-ttu-id="1481c-150">在第一个示例中，限定的类型名称 (**MyProject.MySchema**) 作为命令行自变量包含架构为。</span><span class="sxs-lookup"><span data-stu-id="1481c-150">In the first example, a qualified type name (**MyProject.MySchema**) for the schema is included as a command-line argument.</span></span> <span data-ttu-id="1481c-151">在第二个示例中，从指定的 BizTalk 项目文件获取架构。</span><span class="sxs-lookup"><span data-stu-id="1481c-151">In the second example, the schema is obtained from the specified BizTalk project file.</span></span>  
  
 <span data-ttu-id="1481c-152">你还可以从编译运行管道[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目文件，如下面的示例 （由其程序集限定类型名称引用管道） 所示：</span><span class="sxs-lookup"><span data-stu-id="1481c-152">You can also run pipelines from the compiled [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project files, as in the following example (the pipeline is referenced by its assembly-qualified type name):</span></span>  
  
```  
Pipeline.exe -pt "TestBtsProject.ReceivePipeline, TestBtsProject, Version=1.0.0.0, Culture=neutral, PublicKeyToken=e03965cb5971ad66" -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c  
```  
  
 <span data-ttu-id="1481c-153">在以下示例中，管道由其类型名和程序集文件名分别引用：</span><span class="sxs-lookup"><span data-stu-id="1481c-153">In the following example, a pipeline is referenced by its type name and assembly file name separately:</span></span>  
  
```  
Pipeline.exe -pt TestBtsProject.ReceivePipeline –an TestBtsProject.dll -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c   
```  
  
 <span data-ttu-id="1481c-154">以下示例显示了由其程序集名称引用的管道：</span><span class="sxs-lookup"><span data-stu-id="1481c-154">The following example shows a pipeline referenced by its assembly name:</span></span>  
  
```  
Pipeline.exe -pt TestBtsProject.ReceivePipeline –an "TestBtsProject, Version=1.0.0.0, Culture=neutral, PublicKeyToken=e03965cb5971ad66" -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c  
```  
  
 <span data-ttu-id="1481c-155">Pipeline.exe 运行时，使用您用于启动它的任意凭据。</span><span class="sxs-lookup"><span data-stu-id="1481c-155">Pipeline.exe runs with whatever credentials you have used to launch it.</span></span> <span data-ttu-id="1481c-156">它不使用的帐户，它正常[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机实例下运行，你可能不能运行包含要求数据库访问权限的组件的管道。</span><span class="sxs-lookup"><span data-stu-id="1481c-156">It does not use the account that normal [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host instances run under, so you may not be able to run pipelines that contain components that require database access.</span></span> <span data-ttu-id="1481c-157">请确保在具有所有必需权限的帐户下运行 Pipeline.exe。</span><span class="sxs-lookup"><span data-stu-id="1481c-157">Make sure you run Pipeline.exe under an account that has all the required privileges.</span></span>  
  
 <span data-ttu-id="1481c-158">您应该只使用 Pipeline.exe 来验证没有第三方自定义组件的自定义管道。</span><span class="sxs-lookup"><span data-stu-id="1481c-158">You should only use Pipeline.exe to verify custom pipelines without third-party custom components.</span></span> <span data-ttu-id="1481c-159">如果使用 pipeline.exe 来验证有第三方自定义组件的自定义管道，Pipeline.exe 将生成所需的输出。</span><span class="sxs-lookup"><span data-stu-id="1481c-159">If you use pipeline.exe to verify a custom pipeline with third-party custom components, Pipeline.exe will produce the desired output.</span></span> <span data-ttu-id="1481c-160">不过，如果部署同一个具有第三方自定义组件的自定义管道，在接收或发送端口中使用管道，然后使用 Pipeline.exe 将消息提交到管道，该管道将失败，BizTalk Server 将返回错误。</span><span class="sxs-lookup"><span data-stu-id="1481c-160">However, if you deploy the same custom pipeline with third-party custom components, use the pipeline in a receive or send port, and then use Pipeline.exe to submit a message to the pipeline, the pipeline will fail and BizTalk Server will return an error.</span></span>  
  
### <a name="xmlasmexe"></a><span data-ttu-id="1481c-161">XMLAsm.exe</span><span class="sxs-lookup"><span data-stu-id="1481c-161">XMLAsm.exe</span></span>  
 <span data-ttu-id="1481c-162">XMLAsm.exe（XML 组装器工具）支持以下命令行参数：</span><span class="sxs-lookup"><span data-stu-id="1481c-162">XMLAsm.exe  (XML Assembler tool) supports the following command-line parameters:</span></span>  
  
```  
usage: xmlasm document...[-dm documentmask...] -ds documentSchema... [ -es envelopeSchema... ] [ -c ] [ -d ] [ -sd ] [ -m filenamemask ] [ -v ]  
  
where:  
  document           XML document(s)  
  documentMask       XML document(s) file mask, e.g., c:\\documents\\*.xml  
  documentSchema     XML document schema(s)  
  envelopeSchema     XML envelope schema(s)  
  -c                 Display assembled XML message on the console  
  -d                 Demote properties  
  -sd                Set document schema(s) as design-time property  
  -d                 Demote properties  
  -m                 Output file name mask (default is %MessageID%)  
  -v                 Verbous mode  
  
file name macros:  
  %MessageID%        XML message identifier (Guid)  
  %MessagePartID%    XML message part identifier (Guid)  
  
```  
  
 <span data-ttu-id="1481c-163">例如，如果您希望将两个输入 XML 文档组装到一个具有信封的 XML 文档，并将结果显示到控制台，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="1481c-163">For example, if you want to assemble two input XML documents into a single XML document with an envelope and display the results to the console, use the following command:</span></span>  
  
```  
FFAsm.exe file_in1.xml file_in2.xml–es myEnvelopeSchema.xsd –ds myBodySchema.xsd –c  
```  
  
### <a name="xmldasmexe"></a><span data-ttu-id="1481c-164">XMLDasm.exe</span><span class="sxs-lookup"><span data-stu-id="1481c-164">XMLDasm.exe</span></span>  
 <span data-ttu-id="1481c-165">XMLDasm.exe 支持以下命令行参数：</span><span class="sxs-lookup"><span data-stu-id="1481c-165">XMLDasm.exe supports the following command-line parameters:</span></span>  
  
```  
usage: xmldasm document -ds documentSchema... [ -es envelopeSchema... ] [ -s ] [ -c ] [ -p ] [ -sd ] [ -se ] [ -m filenamemask ] [ -en encoding ] [ -v ]  
  
where:  
  document           XML document  
  documentSchema     XML document schema(s)  
  envelopeSchema     XML envelope schema(s)  
  -s                 Validate document structure  
  -c                 Display disassembled XML message on the console  
  -p                 Display promoted properties on the console  
  -sd                Set document schema(s) as design-time property  
  -se                Set envelope schema(s) as design-time property  
  -m                 Output file name mask (default is %MessageID%)  
  encoding           Input message body part encoding name (e.g., windows-1252) or code page (e.g., 936)  
  -v                 Verbous mode  
  
file name macros:  
  %MessageID%        XML message identifier (Guid)  
  %MessagePartID%    XML message part identifier (Guid)  
  %MessageNumber%    XML message number  
  
```  
  
 <span data-ttu-id="1481c-166">例如，如果您希望拆装具有两个嵌套信封的 XML 文档，并将结果显示到控制台，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="1481c-166">For example, if you want to disassemble an XML document with two nested envelopes and display the results to the console, use the following command:</span></span>  
  
```  
XmlDasm.exe file_in.txt –ds myDocumentSchema.xsd –es myEnvelopeSchema1.xsd –es myEnvelopeSchema2.xsd –c  
```  
  
## <a name="see-also"></a><span data-ttu-id="1481c-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1481c-167">See Also</span></span>  
 [<span data-ttu-id="1481c-168">SDK 中的实用程序</span><span class="sxs-lookup"><span data-stu-id="1481c-168">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)