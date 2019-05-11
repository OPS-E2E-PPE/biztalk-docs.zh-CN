---
title: 管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8ef3fab99e8356d00da859a29548064fc4af086
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395746"
---
# <a name="pipelines"></a><span data-ttu-id="646c5-102">管道</span><span class="sxs-lookup"><span data-stu-id="646c5-102">Pipelines</span></span>
<span data-ttu-id="646c5-103">管道是 Microsoft BizTalk Server 提供的管道和筛选器的集成模式的实现的一个组件。</span><span class="sxs-lookup"><span data-stu-id="646c5-103">Pipelines are a component of Microsoft BizTalk Server that provides an implementation of the Pipes and Filters integration pattern.</span></span> <span data-ttu-id="646c5-104">在接收和发送的消息，有业务原因对消息，以使其进入或离开 BizTalk Server 准备好执行转换。</span><span class="sxs-lookup"><span data-stu-id="646c5-104">During the receiving and sending of messages, there are business reasons to perform transformations on messages to prepare them to enter or leave BizTalk Server.</span></span>  
  
 <span data-ttu-id="646c5-105">常见示例是，您可能需要将以逗号分隔的平面文件转换为 XML 文件，以便利用 BizTalk Server 中的某些功能映射; 例如平面文件拆装器组件实现这一。</span><span class="sxs-lookup"><span data-stu-id="646c5-105">A common example is that you may need to transform a comma-delimited flat file into an XML file in order to take advantage of certain features in BizTalk Server such as maps; the flat file disassembler component does just that.</span></span> <span data-ttu-id="646c5-106">通常需要执行几种类型的转换到一条消息之前接收或发送; 集成方案中使用管道为满足此要求。</span><span class="sxs-lookup"><span data-stu-id="646c5-106">It is common in integration scenarios to have a need to perform several types of transformations to a message before receiving or sending it; pipelines are used to meet this requirement.</span></span> <span data-ttu-id="646c5-107">管道可让开发人员定义的一系列将一条消息时对其执行的转换已接收或发送。</span><span class="sxs-lookup"><span data-stu-id="646c5-107">Pipelines enable the developer to define a series of transformations that will be performed on a message as it is being received or sent.</span></span>  
  
 <span data-ttu-id="646c5-108">有两种类型的管道，发送和接收，以及这些与在其中执行的端口匹配。</span><span class="sxs-lookup"><span data-stu-id="646c5-108">There are two types of pipelines, send and receive, and these match the ports in which they execute.</span></span> <span data-ttu-id="646c5-109">*发送管道*执行的发送端口和请求/响应的响应部分在接收端口，而*接收管道*执行在接收位置，和要求/响应的响应部分发送端口。</span><span class="sxs-lookup"><span data-stu-id="646c5-109">*Send pipelines* are executed in send ports and in the response portion of a request/response receive port, while *receive pipelines* are executed in receive locations, and in the response portion of a solicit/response send port.</span></span> <span data-ttu-id="646c5-110">实际上，接收管道都应使用转换而旨在使用已被订阅并且 BizTalk server 发送的消息的发送管道发布到 MessageBox 数据库的消息。</span><span class="sxs-lookup"><span data-stu-id="646c5-110">Essentially, receive pipelines are intended to be used to transform messages that are being published to the MessageBox database, while send pipelines are intended to be used on messages which have been subscribed to and are being sent out of BizTalk Server.</span></span>  
  
 <span data-ttu-id="646c5-111">每个管道包含一组执行管道时按顺序执行的阶段。</span><span class="sxs-lookup"><span data-stu-id="646c5-111">Each pipeline has a set of stages that are executed in order when the pipeline is executed.</span></span> <span data-ttu-id="646c5-112">每个阶段可以包含零个或多个组件。</span><span class="sxs-lookup"><span data-stu-id="646c5-112">Each stage can contain zero or more components.</span></span> <span data-ttu-id="646c5-113">最大组件数取决于该阶段。</span><span class="sxs-lookup"><span data-stu-id="646c5-113">The maximum number of components depends on the stage.</span></span>  
  
## <a name="receive-pipeline-stages"></a><span data-ttu-id="646c5-114">接收管道阶段</span><span class="sxs-lookup"><span data-stu-id="646c5-114">Receive Pipeline Stages</span></span>  
 <span data-ttu-id="646c5-115">![接收管道阶段](../core/media/arch-pipe-receive.gif "arch_pipe_receive")</span><span class="sxs-lookup"><span data-stu-id="646c5-115">![Receive pipeline stages](../core/media/arch-pipe-receive.gif "arch_pipe_receive")</span></span>  
  
|<span data-ttu-id="646c5-116">阶段</span><span class="sxs-lookup"><span data-stu-id="646c5-116">Stage</span></span>|<span data-ttu-id="646c5-117">用途</span><span class="sxs-lookup"><span data-stu-id="646c5-117">Purpose</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="646c5-118">**Decode**</span><span class="sxs-lookup"><span data-stu-id="646c5-118">**Decode**</span></span>|<span data-ttu-id="646c5-119">进行解密或解码的消息数据</span><span class="sxs-lookup"><span data-stu-id="646c5-119">Decrypts or decodes the message data</span></span>|  
|<span data-ttu-id="646c5-120">**反汇编**</span><span class="sxs-lookup"><span data-stu-id="646c5-120">**Disassemble**</span></span>|<span data-ttu-id="646c5-121">将交换拆装成较小的消息并解析消息内容</span><span class="sxs-lookup"><span data-stu-id="646c5-121">Disassembles an interchange into smaller messages and parses message contents</span></span>|  
|<span data-ttu-id="646c5-122">**验证**</span><span class="sxs-lookup"><span data-stu-id="646c5-122">**Validate**</span></span>|<span data-ttu-id="646c5-123">验证消息的数据，通常根据某个架构</span><span class="sxs-lookup"><span data-stu-id="646c5-123">Validates the message data, generally against a schema</span></span>|  
|<span data-ttu-id="646c5-124">**解析参与方**</span><span class="sxs-lookup"><span data-stu-id="646c5-124">**Resolve Party**</span></span>|<span data-ttu-id="646c5-125">标识与消息或消息上下文中某些安全令牌相关联的 BizTalk Server 参与方</span><span class="sxs-lookup"><span data-stu-id="646c5-125">Identifies the BizTalk Server party associated with some security token in the message or message context</span></span>|  
  
## <a name="send-pipeline-stages"></a><span data-ttu-id="646c5-126">发送管道阶段</span><span class="sxs-lookup"><span data-stu-id="646c5-126">Send Pipeline Stages</span></span>  
 <span data-ttu-id="646c5-127">![发送管道阶段](../core/media/arch-pipe-send.gif "arch_pipe_send")</span><span class="sxs-lookup"><span data-stu-id="646c5-127">![Send pipeline stages](../core/media/arch-pipe-send.gif "arch_pipe_send")</span></span>  
  
|<span data-ttu-id="646c5-128">阶段</span><span class="sxs-lookup"><span data-stu-id="646c5-128">Stage</span></span>|<span data-ttu-id="646c5-129">用途</span><span class="sxs-lookup"><span data-stu-id="646c5-129">Purpose</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="646c5-130">**Pre-assemble**</span><span class="sxs-lookup"><span data-stu-id="646c5-130">**Pre-assemble**</span></span>|<span data-ttu-id="646c5-131">执行任何必要的消息处理在组装消息之前</span><span class="sxs-lookup"><span data-stu-id="646c5-131">Performs any message processing necessary before assembling the message</span></span>|  
|<span data-ttu-id="646c5-132">**组合**</span><span class="sxs-lookup"><span data-stu-id="646c5-132">**Assemble**</span></span>|<span data-ttu-id="646c5-133">组装消息并使其可以执行如添加信封，将 XML 转换为平面文件或在接收管道的拆装阶段的补充其他任务的步骤来传输做好准备</span><span class="sxs-lookup"><span data-stu-id="646c5-133">Assembles the message and prepares it to be transmitted by taking steps such as adding envelopes, converting XML to flat files, or other tasks complementary to the disassemble stage in a receive pipeline</span></span>|  
|<span data-ttu-id="646c5-134">**Encode**</span><span class="sxs-lookup"><span data-stu-id="646c5-134">**Encode**</span></span>|<span data-ttu-id="646c5-135">进行编码或加密前传递消息</span><span class="sxs-lookup"><span data-stu-id="646c5-135">Encodes or encrypts the message before delivery</span></span>|  
  
 <span data-ttu-id="646c5-136">在管道中的阶段都有*执行模式*要么都的或第一个匹配项，它控制如果多个组件添加到阶段执行的组件。</span><span class="sxs-lookup"><span data-stu-id="646c5-136">A stage in a pipeline has an *execution mode* of either All or First Match, which controls the components that get executed if more than one component is added to a stage.</span></span> <span data-ttu-id="646c5-137">对于模式的所有阶段，调用每个组件来处理该消息中的阶段中配置的顺序。</span><span class="sxs-lookup"><span data-stu-id="646c5-137">For stages with a mode of All, each component is called to process the message in the order in which they are configured in the stage.</span></span> <span data-ttu-id="646c5-138">第一个匹配模式时，每个组件进行轮询，以指示它是正确的组件，直到找到匹配项，此时匹配的组件执行，而不执行其余的组件。</span><span class="sxs-lookup"><span data-stu-id="646c5-138">When the mode is First Match, each component is polled to indicate that it is the right component until a match is found, at which point the component that matches is executed, while the remaining components do not get executed.</span></span>  
  
 <span data-ttu-id="646c5-139">作为执行模式的示例，接收管道的拆装阶段是第一个匹配阶段，因此调用阶段中的每个组件以查看它识别该消息并可以对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="646c5-139">As an example of execution modes, the Disassemble stage of a receive pipeline is a First Match stage, thus each component in the stage is called to see if it recognizes the message and can process it.</span></span> <span data-ttu-id="646c5-140">如果该组件发出肯定的响应，然后不查询该阶段中的任何其他组件以查看如果它们可以处理该消息。</span><span class="sxs-lookup"><span data-stu-id="646c5-140">If the component responds in the affirmative, then no other components in that stage are queried to see if they can also handle the message.</span></span> <span data-ttu-id="646c5-141">但是，接收管道的解码阶段具有执行模式的好处是，这意味着调用在此阶段中的每个组件来处理该消息在其中配置的顺序。</span><span class="sxs-lookup"><span data-stu-id="646c5-141">However, the Decode stage of a receive pipeline has an execution mode of All, meaning that each component in this stage is called to process the message in the order in which they were configured.</span></span> <span data-ttu-id="646c5-142">第一个解码器可能是对消息进行解密，而第二个可能要对从某种压缩格式消息进行解压缩。</span><span class="sxs-lookup"><span data-stu-id="646c5-142">The first decoder might be to decrypt the message, while the second might be to decompress the message from a zipped format.</span></span>  
  
 <span data-ttu-id="646c5-143">当开发人员希望在一个接收管道中使用多个拆装器时，将出现在管道处理过程的执行模式的一种常见结果。</span><span class="sxs-lookup"><span data-stu-id="646c5-143">One common consequence of execution mode in pipeline processing occurs when a developer wants to use multiple disassemblers in a single receive pipeline.</span></span> <span data-ttu-id="646c5-144">通常拆装组件仅略有不同，例如两个相似但不同配置的架构与平面文件拆装器。</span><span class="sxs-lookup"><span data-stu-id="646c5-144">Often the disassembling components differ only slightly, for example two flat file disassemblers with similar but different schemas configured.</span></span> <span data-ttu-id="646c5-145">在这种情况下，虽然消息实际上可能匹配的第二个拆装器中定义的架构，可能会通过它可以处理该消息其探测确定第一个拆装器。</span><span class="sxs-lookup"><span data-stu-id="646c5-145">In this case, while the message might actually match the schema defined in the second disassembler, the first disassembler might determine through its probing that it can process the message.</span></span> <span data-ttu-id="646c5-146">它是仅在处理发现错误的消息和挂起的消息后。</span><span class="sxs-lookup"><span data-stu-id="646c5-146">It is only after processing the message that the error is discovered and the message suspended.</span></span> <span data-ttu-id="646c5-147">在这些情况下，可以创建新的拆装器中，具有更多特定探测逻辑或创建两个不同的管道并接收不同中不同的消息接收位置。</span><span class="sxs-lookup"><span data-stu-id="646c5-147">In these cases, you can either create a new disassembler which has more specific probing logic in it, or create two different pipelines and receive the different messages in different receive locations.</span></span>  
  
## <a name="pipeline-deployment"></a><span data-ttu-id="646c5-148">管道部署</span><span class="sxs-lookup"><span data-stu-id="646c5-148">Pipeline Deployment</span></span>  
 <span data-ttu-id="646c5-149">在部署包含管道的程序集时，管理数据库将保存管道。</span><span class="sxs-lookup"><span data-stu-id="646c5-149">When you deploy an assembly that contains a pipeline, the Management database saves the pipeline.</span></span> <span data-ttu-id="646c5-150">管道是与以下结果与程序集的特定版本相关联：</span><span class="sxs-lookup"><span data-stu-id="646c5-150">The pipeline is associated with the specific version of the assembly with the following results:</span></span>  
  
-   <span data-ttu-id="646c5-151">如果部署使用相同管道的多个程序集时，管理数据库将为每个程序集创建管道的一个条目。</span><span class="sxs-lookup"><span data-stu-id="646c5-151">If you deploy multiple assemblies that use the same pipeline, the Management database creates one entry for the pipeline for each assembly.</span></span>  
  
-   <span data-ttu-id="646c5-152">当您删除包含管道的程序集时，管理数据库中删除与该程序集相关联的管道。</span><span class="sxs-lookup"><span data-stu-id="646c5-152">When you remove an assembly that contains a pipeline, the Management database removes the pipeline that is associated with the assembly.</span></span> <span data-ttu-id="646c5-153">由于没有为管理数据库中每个关联的程序集的管道的副本，因此删除一个程序集不会影响其他。</span><span class="sxs-lookup"><span data-stu-id="646c5-153">Because there is a copy of the pipeline for each associated assembly in the Management database, removing one assembly does not affect the others.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="646c5-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="646c5-154">See Also</span></span>  
 [<span data-ttu-id="646c5-155">项目</span><span class="sxs-lookup"><span data-stu-id="646c5-155">Artifacts</span></span>](../core/artifacts.md)