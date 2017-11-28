---
title: "管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines
- deploying, pipelines
- receive pipelines, about receive pipelines
- pipelines, deploying
- send pipelines, about send pipelines
- receive pipelines
- pipelines, about pipelines
- send pipelines, stages
- send pipelines
- pipelines, receive pipelines
- pipelines, send pipelines
- receive pipelines, stages
ms.assetid: 76947dd8-728a-4fa3-bd33-7a708ae82cac
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5fec49dcc9ba21c5d117188f280f7e9b65fe2b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="pipelines"></a><span data-ttu-id="40249-102">管道</span><span class="sxs-lookup"><span data-stu-id="40249-102">Pipelines</span></span>
<span data-ttu-id="40249-103">管道是 Microsoft BizTalk Server 的组件，用于提供管道和筛选器集成模式的实现方式。</span><span class="sxs-lookup"><span data-stu-id="40249-103">Pipelines are a component of Microsoft BizTalk Server that provides an implementation of the Pipes and Filters integration pattern.</span></span> <span data-ttu-id="40249-104">在接收和发送消息的过程中，由于业务原因，需要对消息执行转换，以便为其进入或离开 BizTalk Server 做准备。</span><span class="sxs-lookup"><span data-stu-id="40249-104">During the receiving and sending of messages, there are business reasons to perform transformations on messages to prepare them to enter or leave BizTalk Server.</span></span>  
  
 <span data-ttu-id="40249-105">一个常见示例就是您可能需要将一个以逗号分隔的平面文件转换成一个 XML 文件，以便利用 BizTalk Server 中的某些功能（例如映射）；平面文件拆装器组件实现的就是这样的功能。</span><span class="sxs-lookup"><span data-stu-id="40249-105">A common example is that you may need to transform a comma-delimited flat file into an XML file in order to take advantage of certain features in BizTalk Server such as maps; the flat file disassembler component does just that.</span></span> <span data-ttu-id="40249-106">在集成方案中，常需要在接收或发送消息之前对消息执行几种类型的转换；管道就是用于满足这种需求的。</span><span class="sxs-lookup"><span data-stu-id="40249-106">It is common in integration scenarios to have a need to perform several types of transformations to a message before receiving or sending it; pipelines are used to meet this requirement.</span></span> <span data-ttu-id="40249-107">使用管道，开发人员可以定义在接收或发送消息时对消息执行的一系列转换。</span><span class="sxs-lookup"><span data-stu-id="40249-107">Pipelines enable the developer to define a series of transformations that will be performed on a message as it is being received or sent.</span></span>  
  
 <span data-ttu-id="40249-108">有两种类型的管道：发送管道和接收管道，这两种管道都与相应的端口（在其中执行管道）匹配。</span><span class="sxs-lookup"><span data-stu-id="40249-108">There are two types of pipelines, send and receive, and these match the ports in which they execute.</span></span> <span data-ttu-id="40249-109">*发送管道*在发送端口执行，在一个请求/响应的响应部分接收端口，而*接收管道*执行中接收位置和一个请求/响应的响应部分中发送端口。</span><span class="sxs-lookup"><span data-stu-id="40249-109">*Send pipelines* are executed in send ports and in the response portion of a request/response receive port, while *receive pipelines* are executed in receive locations, and in the response portion of a solicit/response send port.</span></span> <span data-ttu-id="40249-110">实际上，接收管道可用于转换发布到 MessageBox 数据库的消息，而发送管道则用于已被订阅并且发送出 BizTalk Server 的消息。</span><span class="sxs-lookup"><span data-stu-id="40249-110">Essentially, receive pipelines are intended to be used to transform messages that are being published to the MessageBox database, while send pipelines are intended to be used on messages which have been subscribed to and are being sent out of BizTalk Server.</span></span>  
  
 <span data-ttu-id="40249-111">每个管道都有一组阶段，执行管道时按顺序执行这些阶段。</span><span class="sxs-lookup"><span data-stu-id="40249-111">Each pipeline has a set of stages that are executed in order when the pipeline is executed.</span></span> <span data-ttu-id="40249-112">每个阶段可以包含零个或多个组件。</span><span class="sxs-lookup"><span data-stu-id="40249-112">Each stage can contain zero or more components.</span></span> <span data-ttu-id="40249-113">最大组件数取决于具体的阶段。</span><span class="sxs-lookup"><span data-stu-id="40249-113">The maximum number of components depends on the stage.</span></span>  
  
## <a name="receive-pipeline-stages"></a><span data-ttu-id="40249-114">接收管道阶段</span><span class="sxs-lookup"><span data-stu-id="40249-114">Receive Pipeline Stages</span></span>  
 <span data-ttu-id="40249-115">![接收管道阶段](../core/media/arch-pipe-receive.gif "arch_pipe_receive")</span><span class="sxs-lookup"><span data-stu-id="40249-115">![Receive pipeline stages](../core/media/arch-pipe-receive.gif "arch_pipe_receive")</span></span>  
  
|<span data-ttu-id="40249-116">阶段</span><span class="sxs-lookup"><span data-stu-id="40249-116">Stage</span></span>|<span data-ttu-id="40249-117">用途</span><span class="sxs-lookup"><span data-stu-id="40249-117">Purpose</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="40249-118">**解码**</span><span class="sxs-lookup"><span data-stu-id="40249-118">**Decode**</span></span>|<span data-ttu-id="40249-119">对消息数据进行解密或解码</span><span class="sxs-lookup"><span data-stu-id="40249-119">Decrypts or decodes the message data</span></span>|  
|<span data-ttu-id="40249-120">**反汇编**</span><span class="sxs-lookup"><span data-stu-id="40249-120">**Disassemble**</span></span>|<span data-ttu-id="40249-121">将交换拆装成更小的消息并解析消息内容</span><span class="sxs-lookup"><span data-stu-id="40249-121">Disassembles an interchange into smaller messages and parses message contents</span></span>|  
|<span data-ttu-id="40249-122">**验证**</span><span class="sxs-lookup"><span data-stu-id="40249-122">**Validate**</span></span>|<span data-ttu-id="40249-123">验证消息数据，通常根据某个架构验证</span><span class="sxs-lookup"><span data-stu-id="40249-123">Validates the message data, generally against a schema</span></span>|  
|<span data-ttu-id="40249-124">**解析参与方**</span><span class="sxs-lookup"><span data-stu-id="40249-124">**Resolve Party**</span></span>|<span data-ttu-id="40249-125">标识消息或消息上下文中与某些安全令牌相关联的 BizTalk Server 参与方</span><span class="sxs-lookup"><span data-stu-id="40249-125">Identifies the BizTalk Server party associated with some security token in the message or message context</span></span>|  
  
## <a name="send-pipeline-stages"></a><span data-ttu-id="40249-126">发送管道阶段</span><span class="sxs-lookup"><span data-stu-id="40249-126">Send Pipeline Stages</span></span>  
 <span data-ttu-id="40249-127">![发送管道阶段](../core/media/arch-pipe-send.gif "arch_pipe_send")</span><span class="sxs-lookup"><span data-stu-id="40249-127">![Send pipeline stages](../core/media/arch-pipe-send.gif "arch_pipe_send")</span></span>  
  
|<span data-ttu-id="40249-128">阶段</span><span class="sxs-lookup"><span data-stu-id="40249-128">Stage</span></span>|<span data-ttu-id="40249-129">用途</span><span class="sxs-lookup"><span data-stu-id="40249-129">Purpose</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="40249-130">**预先组合**</span><span class="sxs-lookup"><span data-stu-id="40249-130">**Pre-assemble**</span></span>|<span data-ttu-id="40249-131">在组装消息之前执行任何必要的消息处理</span><span class="sxs-lookup"><span data-stu-id="40249-131">Performs any message processing necessary before assembling the message</span></span>|  
|<span data-ttu-id="40249-132">**将组合**</span><span class="sxs-lookup"><span data-stu-id="40249-132">**Assemble**</span></span>|<span data-ttu-id="40249-133">通过添加信封、将 XML 转换为平面文件，或是执行其他一些接收管道中拆装阶段的补充任务等步骤，组装消息并为其传输做准备。</span><span class="sxs-lookup"><span data-stu-id="40249-133">Assembles the message and prepares it to be transmitted by taking steps such as adding envelopes, converting XML to flat files, or other tasks complementary to the disassemble stage in a receive pipeline</span></span>|  
|<span data-ttu-id="40249-134">**编码**</span><span class="sxs-lookup"><span data-stu-id="40249-134">**Encode**</span></span>|<span data-ttu-id="40249-135">在传送前对消息进行编码或加密</span><span class="sxs-lookup"><span data-stu-id="40249-135">Encodes or encrypts the message before delivery</span></span>|  
  
 <span data-ttu-id="40249-136">在管道中的阶段都具有*执行模式*的任一 All 或第一个匹配项，它控制如果多个组件添加到某一阶段获取执行的组件。</span><span class="sxs-lookup"><span data-stu-id="40249-136">A stage in a pipeline has an *execution mode* of either All or First Match, which controls the components that get executed if more than one component is added to a stage.</span></span> <span data-ttu-id="40249-137">对于使用“全部”模式的阶段，按照每个组件在阶段中的配置顺序来调用组件处理消息。</span><span class="sxs-lookup"><span data-stu-id="40249-137">For stages with a mode of All, each component is called to process the message in the order in which they are configured in the stage.</span></span> <span data-ttu-id="40249-138">如果模式为“第一个匹配”，将轮询每个组件以指示其是否为正确的组件，直到找到一个匹配项，此时将执行匹配的组件，而不执行其余的组件。</span><span class="sxs-lookup"><span data-stu-id="40249-138">When the mode is First Match, each component is polled to indicate that it is the right component until a match is found, at which point the component that matches is executed, while the remaining components do not get executed.</span></span>  
  
 <span data-ttu-id="40249-139">作为执行模式的一个示例，接收管道的拆装阶段为“第一个匹配”阶段，因此将调用阶段中的每个组件以了解其是否能够识别和处理消息。</span><span class="sxs-lookup"><span data-stu-id="40249-139">As an example of execution modes, the Disassemble stage of a receive pipeline is a First Match stage, thus each component in the stage is called to see if it recognizes the message and can process it.</span></span> <span data-ttu-id="40249-140">如果组件发出肯定的响应，则不会再查询该阶段中的其他组件是否也能够处理消息。</span><span class="sxs-lookup"><span data-stu-id="40249-140">If the component responds in the affirmative, then no other components in that stage are queried to see if they can also handle the message.</span></span> <span data-ttu-id="40249-141">但是，接收管道的解码阶段具有“全部”执行模式，这意味着系统将按照组件的配置顺序调用此阶段中的每个组件来处理消息。</span><span class="sxs-lookup"><span data-stu-id="40249-141">However, the Decode stage of a receive pipeline has an execution mode of All, meaning that each component in this stage is called to process the message in the order in which they were configured.</span></span> <span data-ttu-id="40249-142">第一个解码器可能是用于解密消息，而第二个则可能用于从某种压缩格式中对消息进行解压缩。</span><span class="sxs-lookup"><span data-stu-id="40249-142">The first decoder might be to decrypt the message, while the second might be to decompress the message from a zipped format.</span></span>  
  
 <span data-ttu-id="40249-143">当开发人员希望在一个接收管道中使用多个拆装器时，在管道处理过程中会出现执行模式的一种常见结果。</span><span class="sxs-lookup"><span data-stu-id="40249-143">One common consequence of execution mode in pipeline processing occurs when a developer wants to use multiple disassemblers in a single receive pipeline.</span></span> <span data-ttu-id="40249-144">通常拆装组件之间仅有轻微的不同，例如配置有相似但不同架构的两个平面文件拆装器。</span><span class="sxs-lookup"><span data-stu-id="40249-144">Often the disassembling components differ only slightly, for example two flat file disassemblers with similar but different schemas configured.</span></span> <span data-ttu-id="40249-145">在这种情况下，尽管消息可能与第二个拆装器中定义的架构匹配，但是第一个拆装器可能通过其探测确定它能够处理该消息。</span><span class="sxs-lookup"><span data-stu-id="40249-145">In this case, while the message might actually match the schema defined in the second disassembler, the first disassembler might determine through its probing that it can process the message.</span></span> <span data-ttu-id="40249-146">只有在处理消息之后才能发现错误而消息被挂起。</span><span class="sxs-lookup"><span data-stu-id="40249-146">It is only after processing the message that the error is discovered and the message suspended.</span></span> <span data-ttu-id="40249-147">在这些情况下，您可以新建一个具有更多特定探测逻辑的拆装器，或者创建两个不同的管道并在不同的接收位置接收不同的消息。</span><span class="sxs-lookup"><span data-stu-id="40249-147">In these cases, you can either create a new disassembler which has more specific probing logic in it, or create two different pipelines and receive the different messages in different receive locations.</span></span>  
  
## <a name="pipeline-deployment"></a><span data-ttu-id="40249-148">管道部署</span><span class="sxs-lookup"><span data-stu-id="40249-148">Pipeline Deployment</span></span>  
 <span data-ttu-id="40249-149">在部署包含管道的程序集时，管理数据库将保存该管道。</span><span class="sxs-lookup"><span data-stu-id="40249-149">When you deploy an assembly that contains a pipeline, the Management database saves the pipeline.</span></span> <span data-ttu-id="40249-150">管道与特定版本的程序集相关联的结果如下：</span><span class="sxs-lookup"><span data-stu-id="40249-150">The pipeline is associated with the specific version of the assembly with the following results:</span></span>  
  
-   <span data-ttu-id="40249-151">如果部署使用相同管道的多个程序集，则管理数据库将为每个程序集的管道创建一个条目。</span><span class="sxs-lookup"><span data-stu-id="40249-151">If you deploy multiple assemblies that use the same pipeline, the Management database creates one entry for the pipeline for each assembly.</span></span>  
  
-   <span data-ttu-id="40249-152">删除包含管道的程序集时，管理数据库将删除与该程序集相关联的管道。</span><span class="sxs-lookup"><span data-stu-id="40249-152">When you remove an assembly that contains a pipeline, the Management database removes the pipeline that is associated with the assembly.</span></span> <span data-ttu-id="40249-153">由于每个相关联的程序集在管理数据库中都有一个管道副本，因此删除一个程序集并不会影响其他程序集。</span><span class="sxs-lookup"><span data-stu-id="40249-153">Because there is a copy of the pipeline for each associated assembly in the Management database, removing one assembly does not affect the others.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40249-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40249-154">See Also</span></span>  
 [<span data-ttu-id="40249-155">项目</span><span class="sxs-lookup"><span data-stu-id="40249-155">Artifacts</span></span>](../core/artifacts.md)