---
title: 管道工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5d9a2aeff4b73eebb95b8be8a76b92fb9c7848d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395758"
---
# <a name="pipeline-tools"></a><span data-ttu-id="a95cf-102">管道工具</span><span class="sxs-lookup"><span data-stu-id="a95cf-102">Pipeline Tools</span></span>
<span data-ttu-id="a95cf-103">使用 Microsoft 提供的管道工具[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]软件开发工具包 (SDK) 使您可以验证管道工作正常，而无需配置 BizTalk Server 环境，如发送/接收端口。</span><span class="sxs-lookup"><span data-stu-id="a95cf-103">The pipeline tools supplied with the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Software Development Kit (SDK) enable you to verify that a pipeline is functioning correctly without having to configure the BizTalk Server environment, such as send/receive ports.</span></span> <span data-ttu-id="a95cf-104">此外可以使用管道工具：</span><span class="sxs-lookup"><span data-stu-id="a95cf-104">You can also use the pipeline tools to:</span></span>  

-   <span data-ttu-id="a95cf-105">调试服务器环境外的第三方管道组件。</span><span class="sxs-lookup"><span data-stu-id="a95cf-105">Debug third-party pipeline components outside of the server environment.</span></span>  

-   <span data-ttu-id="a95cf-106">诊断解析引擎错误消息。</span><span class="sxs-lookup"><span data-stu-id="a95cf-106">Diagnose parsing engine error messages.</span></span>  

-   <span data-ttu-id="a95cf-107">尝试使用不同的架构，而无需编译、 部署、 取消部署和重新编译的负担。</span><span class="sxs-lookup"><span data-stu-id="a95cf-107">Experiment with different schemas without the burden of compiling, deploying, undeploying, and recompiling.</span></span>  

-   <span data-ttu-id="a95cf-108">浏览平面文件和 XML 组装器/拆装器行为。</span><span class="sxs-lookup"><span data-stu-id="a95cf-108">Explore flat file and XML assembler/disassembler behavior.</span></span>  

-   <span data-ttu-id="a95cf-109">查看拆装器输出和发现哪些消息上下文属性将升级以及它们的值。</span><span class="sxs-lookup"><span data-stu-id="a95cf-109">View disassembler output and discover which message context properties are promoted and their values.</span></span>  

-   <span data-ttu-id="a95cf-110">运行没有拆装器和组装器组件发送/接收管道 （例如，可以查看 S/MIME 解码器的输出）。</span><span class="sxs-lookup"><span data-stu-id="a95cf-110">Run send/receive pipelines without disassembler and assembler components (for example, you can view the output of the S/MIME decoder).</span></span>  

-   <span data-ttu-id="a95cf-111">使管道的细粒度的性能度量值本身 （而不是整个消息传送子系统）。</span><span class="sxs-lookup"><span data-stu-id="a95cf-111">Make fine-grained performance measurements of the pipeline alone (rather than the entire messaging subsystem).</span></span>  

## <a name="location-in-sdk"></a><span data-ttu-id="a95cf-112">在 SDK 中的位置</span><span class="sxs-lookup"><span data-stu-id="a95cf-112">Location in SDK</span></span>  
 <span data-ttu-id="a95cf-113">\<*Installation Path*\>\SDK\Utilities\PipelineTools</span><span class="sxs-lookup"><span data-stu-id="a95cf-113">\<*Installation Path*\>\SDK\Utilities\PipelineTools</span></span>  

 <span data-ttu-id="a95cf-114">将管道工具用于执行、 调试和分析管道和管道组件 （即，平面文件和 XML 组装器/拆装器组件）。</span><span class="sxs-lookup"><span data-stu-id="a95cf-114">You use pipeline tools for executing, debugging, and profiling pipelines, and pipeline components (that is, flat file and XML assembler/disassembler components).</span></span>  

## <a name="file-inventory"></a><span data-ttu-id="a95cf-115">文件清单</span><span class="sxs-lookup"><span data-stu-id="a95cf-115">File Inventory</span></span>  
 <span data-ttu-id="a95cf-116">下表列出了管道工具文件，并描述其用途。</span><span class="sxs-lookup"><span data-stu-id="a95cf-116">The following table lists the pipeline tools files and describes their purpose.</span></span>  


|   <span data-ttu-id="a95cf-117">文件</span><span class="sxs-lookup"><span data-stu-id="a95cf-117">File(s)</span></span>    |                                                                                                                                                                                                                                <span data-ttu-id="a95cf-118">Description</span><span class="sxs-lookup"><span data-stu-id="a95cf-118">Description</span></span>                                                                                                                                                                                                                                 |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a95cf-119">DSDump.exe</span><span class="sxs-lookup"><span data-stu-id="a95cf-119">DSDump.exe</span></span>  |                                                <span data-ttu-id="a95cf-120">允许您转储文档架构结构，它是内存中轻量表示形式的一个或多个 XSD 架构，有或没有平面文件批注。</span><span class="sxs-lookup"><span data-stu-id="a95cf-120">Enables you to dump the document schema structure, which is an in-memory lightweight representation of the one or more XSD schemas, with or without flat file annotations.</span></span> <span data-ttu-id="a95cf-121">获取解析引擎错误时，此工具很有帮助如 $Root 0 美元 $ 3 个 2 美元，并且需要对其进行解码。</span><span class="sxs-lookup"><span data-stu-id="a95cf-121">This tool can be helpful when you get parsing engine errors such as $Root$0$3$2 and you need to decode them.</span></span> <span data-ttu-id="a95cf-122">$ 后的数字表示基于 0 的索引或记录的文档架构中的显示方式。</span><span class="sxs-lookup"><span data-stu-id="a95cf-122">Numbers after $ mean 0-based index or records as they appear in the document schema.</span></span>                                                |
|  <span data-ttu-id="a95cf-123">FFAsm.exe</span><span class="sxs-lookup"><span data-stu-id="a95cf-123">FFAsm.exe</span></span>   |                                                                                                                                     <span data-ttu-id="a95cf-124">运行平面文件组装器组件，通过模拟发送管道，使您可以查看如何序列化或用户的 XML 文档组装到平面文件文档直接调用它。</span><span class="sxs-lookup"><span data-stu-id="a95cf-124">Runs the flat file assembler component, directly invoking it by emulating a send pipeline to enable you to see how it serializes or assembles a user's XML document(s) into a flat file document.</span></span>                                                                                                                                      |
|  <span data-ttu-id="a95cf-125">FFDasm.exe</span><span class="sxs-lookup"><span data-stu-id="a95cf-125">FFDasm.exe</span></span>  |                                                                                                                               <span data-ttu-id="a95cf-126">运行平面文件拆装器组件，通过模拟接收管道，使您可以查看如何解析或拆装到一个或多个 XML 文档的用户的平面文件文档直接调用它。</span><span class="sxs-lookup"><span data-stu-id="a95cf-126">Runs the flat file disassembler component, directly invoking it by emulating a receive pipeline to enable you to see how it parses or disassembles a user's flat file document into one or more XML documents.</span></span>                                                                                                                               |
| <span data-ttu-id="a95cf-127">Pipeline.exe</span><span class="sxs-lookup"><span data-stu-id="a95cf-127">Pipeline.exe</span></span> | <span data-ttu-id="a95cf-128">运行发送或接收管道;接受一个或多个输入的文档及其部分、 XSD 架构和相关的信息;并生成输出文档后管道运行。</span><span class="sxs-lookup"><span data-stu-id="a95cf-128">Runs a send or receive pipeline; accepts one or more input documents and their parts, XSD schemas and related information; and produces an output document after the pipeline runs.</span></span> <span data-ttu-id="a95cf-129">因此，访问包含 BizTalk 框架组装器和拆装器组件的管道，Pipeline.exe 不访问 BizTalk Server 数据库，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可能不支持在执行过程的数据库。</span><span class="sxs-lookup"><span data-stu-id="a95cf-129">Pipeline.exe does not access BizTalk Server databases, so pipelines containing BizTalk Framework assembler and disassembler components that access [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases during execution may not be supported.</span></span> |
|  <span data-ttu-id="a95cf-130">XMLAsm.exe</span><span class="sxs-lookup"><span data-stu-id="a95cf-130">XMLAsm.exe</span></span>  |                                                                                                                                 <span data-ttu-id="a95cf-131">运行 XML 组装器组件，直接调用它，通过模拟发送管道来，可以查看如何序列化、 组装或信封用户的 XML 文档转换为输出 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="a95cf-131">Runs the XML assembler component, directly invoking it by emulating a send pipeline to enable you to see how it serializes, assembles, or envelopes a user's XML document(s) into an output XML document.</span></span>                                                                                                                                  |
| <span data-ttu-id="a95cf-132">XMLDasm.exe</span><span class="sxs-lookup"><span data-stu-id="a95cf-132">XMLDasm.exe</span></span>  |                                                                                                                             <span data-ttu-id="a95cf-133">运行 XML 拆装器组件，直接调用它，通过模拟接收管道来，可以查看如何分析拆装或解用户的 XML 文档到一个或多个 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="a95cf-133">Runs the XML disassembler component, directly invoking it by emulating a receive pipeline to enable you to see how it parses, disassembles, or un-envelopes a user's XML document into one or more XML documents.</span></span>                                                                                                                              |

## <a name="usage"></a><span data-ttu-id="a95cf-134">用法</span><span class="sxs-lookup"><span data-stu-id="a95cf-134">Usage</span></span>  
 <span data-ttu-id="a95cf-135">以下各节提供了每个文件的更详细的说明。</span><span class="sxs-lookup"><span data-stu-id="a95cf-135">A more detailed description of each file is provided in the sections that follow.</span></span>  

### <a name="dsdumpexe"></a><span data-ttu-id="a95cf-136">DSDump.exe</span><span class="sxs-lookup"><span data-stu-id="a95cf-136">DSDump.exe</span></span>  
 <span data-ttu-id="a95cf-137">DSDump.exe 允许您转储文档架构结构，它是一个或多个 XSD 架构、 有或没有平面文件批注的内存中轻量表示形式。</span><span class="sxs-lookup"><span data-stu-id="a95cf-137">DSDump.exe enables you to dump the document schema structure, which is an in-memory lightweight representation of one or more XSD schemas, with or without flat file annotations.</span></span>  

 <span data-ttu-id="a95cf-138">DSDump.exe （文档架构转储工具） 支持以下命令行参数：</span><span class="sxs-lookup"><span data-stu-id="a95cf-138">DSDump.exe (document schema dump tool) supports the following command-line parameter:</span></span>  

```  
DSDump.exe schemaFileName  
```  

 <span data-ttu-id="a95cf-139">如果成功，DSDump 打印到控制台的文档架构。</span><span class="sxs-lookup"><span data-stu-id="a95cf-139">In case of success, DSDump prints the document schema to the console.</span></span>  

### <a name="ffasmexe"></a><span data-ttu-id="a95cf-140">FFAsm.exe</span><span class="sxs-lookup"><span data-stu-id="a95cf-140">FFAsm.exe</span></span>  
 <span data-ttu-id="a95cf-141">FFAsm.exe （平面文件组装器） 支持以下命令行参数：</span><span class="sxs-lookup"><span data-stu-id="a95cf-141">FFAsm.exe (flat file assembler) supports the following command-line parameters:</span></span>  

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

 <span data-ttu-id="a95cf-142">例如，如果你想要将三个输入的 XML 文档组装到一个具有标头和属性降级的单个平面文件文档，使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="a95cf-142">For example, if you want to assemble three input XML documents into a single flat file document with a header and property demotion, use the following command:</span></span>  

```  
FFAsm.exe file_in1.xml file_in2.xml file_in3.xml –hs myHeaderSchema.xsd –bs myBodySchema.xsd -d  
```  

### <a name="ffdasmexe"></a><span data-ttu-id="a95cf-143">FFDasm.exe</span><span class="sxs-lookup"><span data-stu-id="a95cf-143">FFDasm.exe</span></span>  
 <span data-ttu-id="a95cf-144">FFDasm.exe （平面文件反汇编程序） 支持以下命令行参数：</span><span class="sxs-lookup"><span data-stu-id="a95cf-144">FFDasm.exe (flat file disassembler) supports the following command-line parameters:</span></span>  

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

 <span data-ttu-id="a95cf-145">例如，如果你想要拆装平面文件文档包含头部、 正文和尾部，并将结果显示到控制台，使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="a95cf-145">For example, if you want to disassemble a flat file document that has a header, body, and trailer, and display the results to the console, use the following command:</span></span>  

```  
FFDasm.exe file_in.txt –hs myHeaderSchema.xsd –bs myBodySchema.xsd –ts myTrailerSchema.xsd –c  
```  

### <a name="pipelineexe"></a><span data-ttu-id="a95cf-146">Pipeline.exe</span><span class="sxs-lookup"><span data-stu-id="a95cf-146">Pipeline.exe</span></span>  
 <span data-ttu-id="a95cf-147">Pipeline.exe （管道工具） 支持以下命令行参数：</span><span class="sxs-lookup"><span data-stu-id="a95cf-147">Pipeline.exe (the Pipeline tool) supports the following command-line parameters:</span></span>  

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

 <span data-ttu-id="a95cf-148">例如，如果你想要从 receivepipeline.btp (具有 XML 拆装器和 XML 验证器组件） 运行接收管道使用 mySchema.xsd 和显示到控制台，结果，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="a95cf-148">For example, if you want to run a receive pipeline from the file ReceivePipeline.btp (which has XML disassembler and XML validator components) using mySchema.xsd and display the results to the console, use the following command:</span></span>  

```  
Pipeline.exe ReceivePipeline.btp –d file_in.xml –s MySchema.xsd:MyProject.MySchema -c  

```  

 <span data-ttu-id="a95cf-149">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="a95cf-149">\- Or -</span></span>  

```  
Pipeline.exe ReceivePipeline.btp –d file_in.xml –s MySchema.xsd –proj MyProject.btproj -c  

```  

 <span data-ttu-id="a95cf-150">在第一个示例中，限定的类型名称 (**MyProject.MySchema**) 架构是包含作为命令行参数。</span><span class="sxs-lookup"><span data-stu-id="a95cf-150">In the first example, a qualified type name (**MyProject.MySchema**) for the schema is included as a command-line argument.</span></span> <span data-ttu-id="a95cf-151">在第二个示例中，从指定的 BizTalk 项目文件中获取该架构。</span><span class="sxs-lookup"><span data-stu-id="a95cf-151">In the second example, the schema is obtained from the specified BizTalk project file.</span></span>  

 <span data-ttu-id="a95cf-152">此外可以从编译运行管道[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目文件，如下面的示例 （管道由其程序集限定类型名称引用） 中所示：</span><span class="sxs-lookup"><span data-stu-id="a95cf-152">You can also run pipelines from the compiled [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project files, as in the following example (the pipeline is referenced by its assembly-qualified type name):</span></span>  

```  
Pipeline.exe -pt "TestBtsProject.ReceivePipeline, TestBtsProject, Version=1.0.0.0, Culture=neutral, PublicKeyToken=e03965cb5971ad66" -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c  
```  

 <span data-ttu-id="a95cf-153">在以下示例中，管道引用由其类型名称和程序集文件名分别：</span><span class="sxs-lookup"><span data-stu-id="a95cf-153">In the following example, a pipeline is referenced by its type name and assembly file name separately:</span></span>  

```  
Pipeline.exe -pt TestBtsProject.ReceivePipeline –an TestBtsProject.dll -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c   
```  

 <span data-ttu-id="a95cf-154">下面的示例演示其程序集名称所引用的管道：</span><span class="sxs-lookup"><span data-stu-id="a95cf-154">The following example shows a pipeline referenced by its assembly name:</span></span>  

```  
Pipeline.exe -pt TestBtsProject.ReceivePipeline –an "TestBtsProject, Version=1.0.0.0, Culture=neutral, PublicKeyToken=e03965cb5971ad66" -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c  
```  

 <span data-ttu-id="a95cf-155">Pipeline.exe 运行时使用你用于启动其任何凭据。</span><span class="sxs-lookup"><span data-stu-id="a95cf-155">Pipeline.exe runs with whatever credentials you have used to launch it.</span></span> <span data-ttu-id="a95cf-156">它不使用的普通帐户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机实例下运行，您可能不能运行包含需要数据库访问权限组件的管道。</span><span class="sxs-lookup"><span data-stu-id="a95cf-156">It does not use the account that normal [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host instances run under, so you may not be able to run pipelines that contain components that require database access.</span></span> <span data-ttu-id="a95cf-157">请确保具有所需的所有权限的帐户下运行 Pipeline.exe。</span><span class="sxs-lookup"><span data-stu-id="a95cf-157">Make sure you run Pipeline.exe under an account that has all the required privileges.</span></span>  

 <span data-ttu-id="a95cf-158">仅应使用 Pipeline.exe 来验证没有第三方自定义组件的自定义管道。</span><span class="sxs-lookup"><span data-stu-id="a95cf-158">You should only use Pipeline.exe to verify custom pipelines without third-party custom components.</span></span> <span data-ttu-id="a95cf-159">如果使用 pipeline.exe 来验证与第三方自定义组件的自定义管道，Pipeline.exe 将生成所需的输出。</span><span class="sxs-lookup"><span data-stu-id="a95cf-159">If you use pipeline.exe to verify a custom pipeline with third-party custom components, Pipeline.exe will produce the desired output.</span></span> <span data-ttu-id="a95cf-160">但是，如果在部署具有第三方自定义组件的相同自定义管道使用管道在接收或发送端口，然后使用 Pipeline.exe 将消息提交到管道，管道将失败，BizTalk Server 将返回错误。</span><span class="sxs-lookup"><span data-stu-id="a95cf-160">However, if you deploy the same custom pipeline with third-party custom components, use the pipeline in a receive or send port, and then use Pipeline.exe to submit a message to the pipeline, the pipeline will fail and BizTalk Server will return an error.</span></span>  

### <a name="xmlasmexe"></a><span data-ttu-id="a95cf-161">XMLAsm.exe</span><span class="sxs-lookup"><span data-stu-id="a95cf-161">XMLAsm.exe</span></span>  
 <span data-ttu-id="a95cf-162">XMLAsm.exe （XML 组装器工具） 支持以下命令行参数：</span><span class="sxs-lookup"><span data-stu-id="a95cf-162">XMLAsm.exe  (XML Assembler tool) supports the following command-line parameters:</span></span>  

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

 <span data-ttu-id="a95cf-163">例如，如果你想要将两个输入的 XML 文档组装到一个具有信封的单个 XML 文档并将结果显示到控制台，使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="a95cf-163">For example, if you want to assemble two input XML documents into a single XML document with an envelope and display the results to the console, use the following command:</span></span>  

```  
FFAsm.exe file_in1.xml file_in2.xml–es myEnvelopeSchema.xsd –ds myBodySchema.xsd –c  
```  

### <a name="xmldasmexe"></a><span data-ttu-id="a95cf-164">XMLDasm.exe</span><span class="sxs-lookup"><span data-stu-id="a95cf-164">XMLDasm.exe</span></span>  
 <span data-ttu-id="a95cf-165">XMLDasm.exe 支持以下命令行参数：</span><span class="sxs-lookup"><span data-stu-id="a95cf-165">XMLDasm.exe supports the following command-line parameters:</span></span>  

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

 <span data-ttu-id="a95cf-166">例如，如果您希望拆装具有两个嵌套信封的 XML 文档并将结果显示到控制台，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="a95cf-166">For example, if you want to disassemble an XML document with two nested envelopes and display the results to the console, use the following command:</span></span>  

```  
XmlDasm.exe file_in.txt –ds myDocumentSchema.xsd –es myEnvelopeSchema1.xsd –es myEnvelopeSchema2.xsd –c  
```  

## <a name="see-also"></a><span data-ttu-id="a95cf-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="a95cf-167">See Also</span></span>  
 [<span data-ttu-id="a95cf-168">SDK 中的实用工具</span><span class="sxs-lookup"><span data-stu-id="a95cf-168">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)