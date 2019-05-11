---
title: 架构解析器组件 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Flat File Disassembler [pipeline component], examples
- examples, schemas
- schemas, examples
- examples, Flat File Disassembler [pipeline component]
ms.assetid: 9ef68988-c4ee-42d5-83b5-a5c978b2007d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d34ef9109c95ae853c9d3b8319961a7c22d73628
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396914"
---
# <a name="schema-resolver-component-biztalk-server-sample"></a><span data-ttu-id="9c3f0-102">架构解析器组件 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="9c3f0-102">Schema Resolver Component (BizTalk Server Sample)</span></span>
<span data-ttu-id="9c3f0-103">架构解析器组件示例演示如何扩展的功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]平面文件拆装器组件。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-103">The Schema Resolver Component sample demonstrates how to extend the functionality of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] flat file disassembler component.</span></span>  
  
 <span data-ttu-id="9c3f0-104">平面文件拆装器组件通常要求您在设计时定义分析架构。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-104">The flat file disassembler component normally requires you to define a parsing schema at design time.</span></span> <span data-ttu-id="9c3f0-105">因此如果您希望收到相同的接收位置上的不同的平面文件文档，则通常在接收管道，一个用于每个架构中包含多个平面文件拆装器。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-105">So if you expect to receive different flat file documents on the same receive location, you typically include several flat file disassemblers in the receive pipeline, one for each schema.</span></span> <span data-ttu-id="9c3f0-106">在运行时，使用管道探测机制选择正确的拆装器组件。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-106">At run time, the correct disassembler component is selected using a pipeline probing mechanism.</span></span> <span data-ttu-id="9c3f0-107">但是，这种方法是如果你有多个平面文件架构，因为探测每个对应的拆装器组件会降低管道性能开销。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-107">However, this approach is expensive if you have many flat file schemas because probing for every corresponding disassembler component degrades pipeline performance.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="9c3f0-108">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="9c3f0-108">What This Sample Does</span></span>  
 <span data-ttu-id="9c3f0-109">架构解析器组件演示为平面文件拆装器中选择架构的一种替代方法。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-109">The Schema Resolver component demonstrates an alternative method of selecting the schema for a flat file disassembler.</span></span> <span data-ttu-id="9c3f0-110">在此示例中，定义四个架构，并且每个架构的消息的前两个字符是唯一的。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-110">In this sample, four schemas are defined and the first two characters of a message for each schema are unique.</span></span> <span data-ttu-id="9c3f0-111">唯一的前两个字符和相应的架构之间定义了一个映射。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-111">A mapping is defined between the unique first two characters and the corresponding schema.</span></span> <span data-ttu-id="9c3f0-112">当输入的消息发送到架构解析器组件时，它读取前两个字符，确定要用于对应的文档的架构、 将架构信息保存在消息上下文，，然后调用成标准的平面文件拆装器组件。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-112">When the input message is given to the Schema Resolver component, it reads the first two characters, determines which schema to use for the corresponding document, saves the schema information on the message context, and then calls into the standard flat file disassembler component.</span></span> <span data-ttu-id="9c3f0-113">标准平面文件拆装器组件从消息上下文读取架构信息，并使用该架构分析文档。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-113">The standard flat file disassembler component reads the schema information from the message context and uses that schema to parse the document.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="9c3f0-114">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="9c3f0-114">Where to Find This Sample</span></span>  
 <span data-ttu-id="9c3f0-115">*\<Samples Path\>* \Pipelines\SchemaResolverComponent\\</span><span class="sxs-lookup"><span data-stu-id="9c3f0-115">*\<Samples Path\>* \Pipelines\SchemaResolverComponent\\</span></span>  
  
 <span data-ttu-id="9c3f0-116">下表显示了此示例中使用的文件，并说明其用途。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-116">The following table shows the files used in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="9c3f0-117">文件</span><span class="sxs-lookup"><span data-stu-id="9c3f0-117">File(s)</span></span>|<span data-ttu-id="9c3f0-118">Description</span><span class="sxs-lookup"><span data-stu-id="9c3f0-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9c3f0-119">SchemaResolverSample.sln</span><span class="sxs-lookup"><span data-stu-id="9c3f0-119">SchemaResolverSample.sln</span></span>|<span data-ttu-id="9c3f0-120">运用自定义管道组件的 BizTalk 项目的解决方案。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-120">Solution for the BizTalk project that exercises the custom pipeline component.</span></span>|  
|<span data-ttu-id="9c3f0-121">SchemaResolverSample.btproj</span><span class="sxs-lookup"><span data-stu-id="9c3f0-121">SchemaResolverSample.btproj</span></span>|<span data-ttu-id="9c3f0-122">运用自定义管道组件的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-122">BizTalk project that exercises the custom pipeline component.</span></span>|  
|<span data-ttu-id="9c3f0-123">SchemaResolverRP.btp</span><span class="sxs-lookup"><span data-stu-id="9c3f0-123">SchemaResolverRP.btp</span></span>|<span data-ttu-id="9c3f0-124">接收包含自定义组件的管道。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-124">Receive pipeline that contains the custom component.</span></span>|  
|<span data-ttu-id="9c3f0-125">PurchaseOrder.xsd, PurchaseRequest.xsd, SalesOrder.xsd, SalesRequest.xsd</span><span class="sxs-lookup"><span data-stu-id="9c3f0-125">PurchaseOrder.xsd, PurchaseRequest.xsd, SalesOrder.xsd, SalesRequest.xsd</span></span>|<span data-ttu-id="9c3f0-126">平面文件架构。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-126">Flat file schemas.</span></span>|  
|<span data-ttu-id="9c3f0-127">POInstance.txt、 PRInstance.txt、 SOInstance.txt、 SRInstance.txt</span><span class="sxs-lookup"><span data-stu-id="9c3f0-127">POInstance.txt, PRInstance.txt, SOInstance.txt, SRInstance.txt</span></span>|<span data-ttu-id="9c3f0-128">相应的平面文件文档实例。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-128">Corresponding flat file document instances.</span></span>|  
|<span data-ttu-id="9c3f0-129">SchemaResolverFlatFileDasm.sln</span><span class="sxs-lookup"><span data-stu-id="9c3f0-129">SchemaResolverFlatFileDasm.sln</span></span>|<span data-ttu-id="9c3f0-130">实现管道组件的解决方案。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-130">Solution for the implementation of the pipeline component.</span></span>|  
|<span data-ttu-id="9c3f0-131">SchemaResolverFlatFileDasm.csproj</span><span class="sxs-lookup"><span data-stu-id="9c3f0-131">SchemaResolverFlatFileDasm.csproj</span></span>|<span data-ttu-id="9c3f0-132">C#实现管道组件的项目。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-132">C# project for the implementation of the pipeline component.</span></span>|  
|<span data-ttu-id="9c3f0-133">SchemaResolverFlatFileDasmComp.cs</span><span class="sxs-lookup"><span data-stu-id="9c3f0-133">SchemaResolverFlatFileDasmComp.cs</span></span>|<span data-ttu-id="9c3f0-134">管道组件的实现。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-134">Implementation of the pipeline component.</span></span>|  
|<span data-ttu-id="9c3f0-135">SeekableReadOnlyStream.cs</span><span class="sxs-lookup"><span data-stu-id="9c3f0-135">SeekableReadOnlyStream.cs</span></span>|<span data-ttu-id="9c3f0-136">实现组件使用的可查找只读流。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-136">Implementation of the seekable read-only stream used by component.</span></span>|  
|<span data-ttu-id="9c3f0-137">VirtualStream.cs</span><span class="sxs-lookup"><span data-stu-id="9c3f0-137">VirtualStream.cs</span></span>|<span data-ttu-id="9c3f0-138">实现管道组件使用的虚拟流。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-138">Implementation of the virtual stream used by pipeline component.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="9c3f0-139">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="9c3f0-139">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="9c3f0-140">使用以下过程生成并初始化架构解析器组件示例。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-140">Use the following procedure to build and initialize the Schema Resolver Component sample.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="9c3f0-141">若要生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="9c3f0-141">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="9c3f0-142">在命令窗口中，将目录 (cd) 更改到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="9c3f0-142">In a command window, change directory (cd) to the following folder:</span></span>  
  
     <span data-ttu-id="9c3f0-143">*\<Samples Path\>* \Pipelines\SchemaResolverComponent</span><span class="sxs-lookup"><span data-stu-id="9c3f0-143">*\<Samples Path\>* \Pipelines\SchemaResolverComponent</span></span>  
  
2.  <span data-ttu-id="9c3f0-144">运行文件 Setup.bat，以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9c3f0-144">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="9c3f0-145">生成组件。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-145">Builds the component.</span></span>  
  
    -   <span data-ttu-id="9c3f0-146">将组件程序集复制到 BizTalk \Pipeline components 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-146">Copies the component assembly into the BizTalk \Pipeline components folder.</span></span>  
  
    -   <span data-ttu-id="9c3f0-147">生成和部署示例 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-147">Builds and deploys the sample BizTalk project.</span></span>  
  
    -   <span data-ttu-id="9c3f0-148">配置接收位置和发送端口，并启动它们。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-148">Configures the receive location and send port, and starts them.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c3f0-149">在尝试运行本示例前，你应确认在生成和初始化过程中未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-149">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="9c3f0-150">运行本示例</span><span class="sxs-lookup"><span data-stu-id="9c3f0-150">Running This Sample</span></span>  
 <span data-ttu-id="9c3f0-151">使用以下过程运行架构解析器组件示例。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-151">Use the following procedure to run the Schema Resolver Component sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="9c3f0-152">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="9c3f0-152">To run this sample</span></span>  
  
1.  <span data-ttu-id="9c3f0-153">POInstance.txt、 PRInstance.txt、 SOInstance.txt 和 SRInstance.txt 文件放入接收位置\<*安装路径*\>\SDK\Samples\Pipelines\SchemaResolverComponent\In</span><span class="sxs-lookup"><span data-stu-id="9c3f0-153">Drop the POInstance.txt, PRInstance.txt, SOInstance.txt, and SRInstance.txt files into the receive location \<*Installation Path*\>\SDK\Samples\Pipelines\SchemaResolverComponent\In</span></span>  
  
2.  <span data-ttu-id="9c3f0-154">查看写入到的四个.xml 文件\<Installdir\>\SDK\Samples\Pipelines\SchemaResolverComponent\Out 文件夹。</span><span class="sxs-lookup"><span data-stu-id="9c3f0-154">Observe the four .xml files written to the \<Installdir\>\SDK\Samples\Pipelines\SchemaResolverComponent\Out folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c3f0-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c3f0-155">See Also</span></span>  
 [<span data-ttu-id="9c3f0-156">管道 （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="9c3f0-156">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)