---
title: 自定义参与方解析 （BizTalk Server 示例） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, parties
- pipeline components [custom], examples
- pipeline components [custom], parties
- examples, pipeline components [custom]
- parties, pipeline components [custom]
- parties, custom
ms.assetid: 1f88450f-5fe9-486d-bfb8-fd11181c78b4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 066d551cc2d802778673492de5de352fbcd48fa9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353354"
---
# <a name="custom-party-resolution-biztalk-server-sample"></a><span data-ttu-id="30c49-102">自定义参与方解析（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="30c49-102">Custom Party Resolution (BizTalk Server Sample)</span></span>
<span data-ttu-id="30c49-103">自定义参与方解析示例演示如何编写自定义管道组件以解析自定义参与方。</span><span class="sxs-lookup"><span data-stu-id="30c49-103">The Custom Party Resolution sample demonstrates how to write a custom pipeline component to resolve a custom party.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="30c49-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="30c49-104">What This Sample Does</span></span>  
 <span data-ttu-id="30c49-105">自定义参与方解析示例使用以下一系列步骤完成其任务：</span><span class="sxs-lookup"><span data-stu-id="30c49-105">The Custom Party Resolution sample accomplishes its task using the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="30c49-106">从文件夹检索 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="30c49-106">An XML document is retrieved from a folder.</span></span>  
  
2.  <span data-ttu-id="30c49-107">管道解析参与方。</span><span class="sxs-lookup"><span data-stu-id="30c49-107">The pipeline resolves the party.</span></span>  
  
3.  <span data-ttu-id="30c49-108">将 XML 消息写入文件夹。</span><span class="sxs-lookup"><span data-stu-id="30c49-108">The XML message is written to a folder.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="30c49-109">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="30c49-109">Where to Find This Sample</span></span>  
 <span data-ttu-id="30c49-110">*\<示例路径 >* \Pipelines\CustomPartyResolution\\</span><span class="sxs-lookup"><span data-stu-id="30c49-110">*\<Samples Path>* \Pipelines\CustomPartyResolution\\</span></span>  
  
 <span data-ttu-id="30c49-111">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="30c49-111">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="30c49-112">文件</span><span class="sxs-lookup"><span data-stu-id="30c49-112">File(s)</span></span>|<span data-ttu-id="30c49-113">Description</span><span class="sxs-lookup"><span data-stu-id="30c49-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="30c49-114">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="30c49-114">AssemblyInfo.cs</span></span>|<span data-ttu-id="30c49-115">程序集信息 C# 源文件。</span><span class="sxs-lookup"><span data-stu-id="30c49-115">Assembly information C# source file.</span></span>|  
|<span data-ttu-id="30c49-116">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="30c49-116">Cleanup.bat</span></span>|<span data-ttu-id="30c49-117">清除批处理文件。</span><span class="sxs-lookup"><span data-stu-id="30c49-117">Cleanup batch file.</span></span>|  
|<span data-ttu-id="30c49-118">CustomPartyResolution.sln</span><span class="sxs-lookup"><span data-stu-id="30c49-118">CustomPartyResolution.sln</span></span>|<span data-ttu-id="30c49-119">解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="30c49-119">Solution file.</span></span>|  
|<span data-ttu-id="30c49-120">CustomPartyResolutionBinding.xml</span><span class="sxs-lookup"><span data-stu-id="30c49-120">CustomPartyResolutionBinding.xml</span></span>|<span data-ttu-id="30c49-121">绑定文件。</span><span class="sxs-lookup"><span data-stu-id="30c49-121">Binding file.</span></span>|  
|<span data-ttu-id="30c49-122">CustomPartyResolutionPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="30c49-122">CustomPartyResolutionPipeline.btp</span></span>|<span data-ttu-id="30c49-123">管道文件。</span><span class="sxs-lookup"><span data-stu-id="30c49-123">Pipeline file.</span></span>|  
|<span data-ttu-id="30c49-124">CustomPartyResolutionPipeline.btproj</span><span class="sxs-lookup"><span data-stu-id="30c49-124">CustomPartyResolutionPipeline.btproj</span></span>|<span data-ttu-id="30c49-125">管道项目文件。</span><span class="sxs-lookup"><span data-stu-id="30c49-125">Pipeline project file.</span></span>|  
|<span data-ttu-id="30c49-126">CustomPartyResolutionPipelineComponent.cs</span><span class="sxs-lookup"><span data-stu-id="30c49-126">CustomPartyResolutionPipelineComponent.cs</span></span>|<span data-ttu-id="30c49-127">管道组件 C# 源代码。</span><span class="sxs-lookup"><span data-stu-id="30c49-127">Pipeline component C# source code.</span></span>|  
|<span data-ttu-id="30c49-128">CustomPartyResolutionPipelineComponent.csproj</span><span class="sxs-lookup"><span data-stu-id="30c49-128">CustomPartyResolutionPipelineComponent.csproj</span></span>|<span data-ttu-id="30c49-129">管道组件 Visual Studio 项目文件。</span><span class="sxs-lookup"><span data-stu-id="30c49-129">Pipeline component Visual Studio project file.</span></span>|  
|<span data-ttu-id="30c49-130">InboundDocumentSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="30c49-130">InboundDocumentSchema.xsd</span></span>|<span data-ttu-id="30c49-131">入站文档架构。</span><span class="sxs-lookup"><span data-stu-id="30c49-131">Inbound document schema.</span></span>|  
|<span data-ttu-id="30c49-132">PartyResolutionStream.cs</span><span class="sxs-lookup"><span data-stu-id="30c49-132">PartyResolutionStream.cs</span></span>|<span data-ttu-id="30c49-133">参与方解析流 C# 源代码。</span><span class="sxs-lookup"><span data-stu-id="30c49-133">Party resolution stream C# source code.</span></span>|  
|<span data-ttu-id="30c49-134">RoutingPropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="30c49-134">RoutingPropertySchema.xsd</span></span>|<span data-ttu-id="30c49-135">路由属性架构文件。</span><span class="sxs-lookup"><span data-stu-id="30c49-135">Routing property schema file.</span></span>|  
|<span data-ttu-id="30c49-136">SampleInboundDocumentSchema.xml</span><span class="sxs-lookup"><span data-stu-id="30c49-136">SampleInboundDocumentSchema.xml</span></span>|<span data-ttu-id="30c49-137">入站文档架构文件。</span><span class="sxs-lookup"><span data-stu-id="30c49-137">Inbound document schema file.</span></span>|  
|<span data-ttu-id="30c49-138">SampleInboundDocumentSchema_Party1.xml</span><span class="sxs-lookup"><span data-stu-id="30c49-138">SampleInboundDocumentSchema_Party1.xml</span></span>|<span data-ttu-id="30c49-139">示例数据实例。</span><span class="sxs-lookup"><span data-stu-id="30c49-139">Sample data instance.</span></span>|  
|<span data-ttu-id="30c49-140">SampleInboundDocumentSchema_Party2.xml</span><span class="sxs-lookup"><span data-stu-id="30c49-140">SampleInboundDocumentSchema_Party2.xml</span></span>|<span data-ttu-id="30c49-141">示例数据实例。</span><span class="sxs-lookup"><span data-stu-id="30c49-141">Sample data instance.</span></span>|  
|<span data-ttu-id="30c49-142">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="30c49-142">Setup.bat</span></span>|<span data-ttu-id="30c49-143">生成和安装示例管道组件批处理文件。</span><span class="sxs-lookup"><span data-stu-id="30c49-143">Build and setup sample pipeline component batch file.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="30c49-144">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="30c49-144">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-custom-party-resolution-sample"></a><span data-ttu-id="30c49-145">生成并初始化自定义参与方解析示例</span><span class="sxs-lookup"><span data-stu-id="30c49-145">To build and initialize the Custom Party Resolution sample</span></span>  
  
1.  <span data-ttu-id="30c49-146">在命令窗口中，将目录更改 (**cd**) 的以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="30c49-146">In a command window, change directory (**cd**) to the following folder:</span></span>  
  
     <span data-ttu-id="30c49-147">*\<示例路径 >* \Pipelines\CustomPartyResolution\\</span><span class="sxs-lookup"><span data-stu-id="30c49-147">*\<Samples Path>* \Pipelines\CustomPartyResolution\\</span></span>  
  
2.  <span data-ttu-id="30c49-148">运行 Setup.bat 文件，这将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="30c49-148">Run the file Setup.bat, which will perform the following actions:</span></span>  
  
    -   <span data-ttu-id="30c49-149">创建示例中使用的输入和输出目录。</span><span class="sxs-lookup"><span data-stu-id="30c49-149">Creates the input and output directories used in the sample.</span></span>  
  
    -   <span data-ttu-id="30c49-150">生成新的密钥文件。</span><span class="sxs-lookup"><span data-stu-id="30c49-150">Generates a new key file.</span></span>  
  
    -   <span data-ttu-id="30c49-151">生成和部署自定义参与方解析管道组件。</span><span class="sxs-lookup"><span data-stu-id="30c49-151">Builds and deploys the Custom Party Resolution pipeline component.</span></span>  
  
    -   <span data-ttu-id="30c49-152">将复制到生成的管道组件*\<安装路径 >* \Pipeline 组件的目录。</span><span class="sxs-lookup"><span data-stu-id="30c49-152">Copies the built pipeline component to the *\<Installation Path>* \Pipeline Components directory.</span></span>  
  
    -   <span data-ttu-id="30c49-153">创建发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="30c49-153">Creates the send and receive ports.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30c49-154">在尝试运行本示例前，你应确认在生成和初始化过程中未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="30c49-154">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="30c49-155">运行本示例</span><span class="sxs-lookup"><span data-stu-id="30c49-155">Running This Sample</span></span>  
  
#### <a name="to-run-the-custom-party-resolution-sample"></a><span data-ttu-id="30c49-156">运行自定义参与方解析示例</span><span class="sxs-lookup"><span data-stu-id="30c49-156">To run the Custom Party Resolution sample</span></span>  
  
1.  <span data-ttu-id="30c49-157">将文件 SampleInboundDocumentSchema_Party1.xml 或 SampleInboundDocumentSchema_Party2.xml 复制到 \In 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="30c49-157">Copy to file SampleInboundDocumentSchema_Party1.xml or SampleInboundDocumentSchema_Party2.xml to the \In folder.</span></span>  
  
2.  <span data-ttu-id="30c49-158">结果将显示在 \Out 文件夹以 filename *guid*.xml。</span><span class="sxs-lookup"><span data-stu-id="30c49-158">The results will appear in the \Out folder with the filename *guid*.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30c49-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30c49-159">See Also</span></span>  
 [<span data-ttu-id="30c49-160">管道 （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="30c49-160">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)