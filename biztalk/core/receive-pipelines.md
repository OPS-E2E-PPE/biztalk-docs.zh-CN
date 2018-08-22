---
title: 接收管道 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive pipelines, about receive pipelines
- receive pipelines, message flow
- receive pipelines
- messages, receive pipelines
- messages, message flow
- pipelines, receive pipelines
- receive pipelines, stages
ms.assetid: ee75c1d4-00b7-4177-bca3-1447a39d2238
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0a248c69cb96603e9c4883e5d21caa39165da13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268861"
---
# <a name="receive-pipelines"></a><span data-ttu-id="ffa46-102">接收管道</span><span class="sxs-lookup"><span data-stu-id="ffa46-102">Receive Pipelines</span></span>
<span data-ttu-id="ffa46-103">下图显示消息处理工作流，其中突出显示了接收管道：</span><span class="sxs-lookup"><span data-stu-id="ffa46-103">The following figure shows the message processing workflow, highlighting the receive pipeline.</span></span>  
  
 <span data-ttu-id="ffa46-104">![消息处理工作流的图示。](../core/media/ebiz-dev-busprcsb.gif "ebiz_dev_busprcsb")</span><span class="sxs-lookup"><span data-stu-id="ffa46-104">![Diagram of the message processing workflow.](../core/media/ebiz-dev-busprcsb.gif "ebiz_dev_busprcsb")</span></span>  
<span data-ttu-id="ffa46-105">消息处理工作流示意图</span><span class="sxs-lookup"><span data-stu-id="ffa46-105">Depicts the message processing workflow.</span></span>  
  
 <span data-ttu-id="ffa46-106">接收适配器收到消息后，接收管道将对该消息进行处理。</span><span class="sxs-lookup"><span data-stu-id="ffa46-106">A receive pipeline operates on a message after it is received by the receive adapter.</span></span> <span data-ttu-id="ffa46-107">接收管道将获取初始消息，执行一些转换，并将原始数据拆为零条、一条或多条消息。</span><span class="sxs-lookup"><span data-stu-id="ffa46-107">The receive pipeline takes the initial message, performs some transformations, and disassembles the raw data into zero, one, or multiple messages.</span></span> <span data-ttu-id="ffa46-108">然后，BizTalk Server 即可对各条消息进行处理。</span><span class="sxs-lookup"><span data-stu-id="ffa46-108">These individual messages can then be processed by BizTalk Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ffa46-109">如果向接收管道添加了使用组件，则该管道不会生成消息。</span><span class="sxs-lookup"><span data-stu-id="ffa46-109">A receive pipeline can produce zero messages if a consuming component is added to the pipeline.</span></span> <span data-ttu-id="ffa46-110">在这种情况下，管道组件将使用消息，但不生成任何输出消息。</span><span class="sxs-lookup"><span data-stu-id="ffa46-110">In this case, the pipeline component consumes the message and does not produce any output messages.</span></span> <span data-ttu-id="ffa46-111">如果使用组件置于拆装组件之后，则在使用第一个消息后将停止管道执行，并且不会从拆装组件中检索任何后续消息。</span><span class="sxs-lookup"><span data-stu-id="ffa46-111">If a consuming component is placed after a disassembling component, pipeline execution stops after the first message is consumed and no subsequent messages are retrieved from the disassembling component.</span></span>  
  
 <span data-ttu-id="ffa46-112">在创建时的业务流程，你可以创建新的接收管道或可以使用两个默认之一接收 BizTalk Server 中包含的管道-传递接收管道或 XML 接收管道。</span><span class="sxs-lookup"><span data-stu-id="ffa46-112">When creating a business process, you can create a new receive pipeline or you can use one of the two default receive pipelines included in BizTalk Server—the pass-through receive pipeline or the XML receive pipeline.</span></span> <span data-ttu-id="ffa46-113">有关这些默认管道的详细信息，请参阅[默认管道](../core/default-pipelines.md)。</span><span class="sxs-lookup"><span data-stu-id="ffa46-113">For more information about these default pipelines, see [Default Pipelines](../core/default-pipelines.md).</span></span>  
  
 <span data-ttu-id="ffa46-114">接收管道包括四个阶段：解码、拆装、验证和解析参与方。</span><span class="sxs-lookup"><span data-stu-id="ffa46-114">The receive pipeline consists of four stages: Decode, Disassemble, Validate, and ResolveParty.</span></span> <span data-ttu-id="ffa46-115">本主题包含了有关填充这些阶段的设计注意事项。</span><span class="sxs-lookup"><span data-stu-id="ffa46-115">This topic contains design considerations for populating these stages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ffa46-116">在此版本中，不支持更改这些阶段在管道中的顺序或存在状态。</span><span class="sxs-lookup"><span data-stu-id="ffa46-116">In this release, changing the order or presence of these stages in a pipeline is not supported.</span></span>  
  
## <a name="decode-stage"></a><span data-ttu-id="ffa46-117">解码阶段</span><span class="sxs-lookup"><span data-stu-id="ffa46-117">Decode stage</span></span>  
  
-   <span data-ttu-id="ffa46-118">此阶段用于对消息进行解码或解密的组件。</span><span class="sxs-lookup"><span data-stu-id="ffa46-118">This stage is used for components that decode or decrypt the message.</span></span>  
  
    -   <span data-ttu-id="ffa46-119">如果需要将传入消息从一种格式解码为另一种格式，则需要在此阶段中放置 MIME/SMIME 解码器管道组件或自定义解码组件。</span><span class="sxs-lookup"><span data-stu-id="ffa46-119">The MIME/SMIME Decoder pipeline component or a custom decoding component should be placed in this stage if the incoming messages need to be decoded from one format to another.</span></span>  
  
-   <span data-ttu-id="ffa46-120">只要此阶段获取一条消息，就生成一条消息。</span><span class="sxs-lookup"><span data-stu-id="ffa46-120">This stage takes one message and produces one message.</span></span>  
  
-   <span data-ttu-id="ffa46-121">此阶段可包含 0 到 255 个组件。</span><span class="sxs-lookup"><span data-stu-id="ffa46-121">This stage can contain between zero and 255 components.</span></span>  
  
-   <span data-ttu-id="ffa46-122">此阶段中的所有组件均将运行。</span><span class="sxs-lookup"><span data-stu-id="ffa46-122">All components in this stage are run.</span></span>  
  
## <a name="disassemble-stage"></a><span data-ttu-id="ffa46-123">拆装阶段</span><span class="sxs-lookup"><span data-stu-id="ffa46-123">Disassemble stage</span></span>  
  
-   <span data-ttu-id="ffa46-124">此阶段用于对消息进行解析或拆装的组件。</span><span class="sxs-lookup"><span data-stu-id="ffa46-124">This stage is used for components that parse or disassemble the message.</span></span>  
  
    -   <span data-ttu-id="ffa46-125">此阶段内的组件可探测消息以查看是否可识别消息的格式。</span><span class="sxs-lookup"><span data-stu-id="ffa46-125">The components within this stage probe the message to see if the format of the message is recognized.</span></span> <span data-ttu-id="ffa46-126">其中一个组件将根据格式的识别情况拆装消息。</span><span class="sxs-lookup"><span data-stu-id="ffa46-126">Based on the recognition of the format, one of the components disassembles the message.</span></span>  
  
    -   <span data-ttu-id="ffa46-127">如果此阶段包含多个组件，则只运行第一个识别消息格式的组件。</span><span class="sxs-lookup"><span data-stu-id="ffa46-127">If this stage contains more than one component, only the first component that recognizes the message format is run.</span></span> <span data-ttu-id="ffa46-128">如果此阶段内的所有组件均无法识别消息格式，则消息处理将失败。</span><span class="sxs-lookup"><span data-stu-id="ffa46-128">If none of the components within the stage recognize the message format, the message processing fails.</span></span>  
  
    -   <span data-ttu-id="ffa46-129">此阶段应包含可实施特殊行为以拆装消息内容的所有自定义组件。</span><span class="sxs-lookup"><span data-stu-id="ffa46-129">This stage should include any custom components that implement special behavior to disassemble the message contents.</span></span>  
  
    -   <span data-ttu-id="ffa46-130">此阶段可包含 0 到 255 个组件。</span><span class="sxs-lookup"><span data-stu-id="ffa46-130">This stage can contain between zero and 255 components.</span></span> <span data-ttu-id="ffa46-131">如果此阶段不包含任何组件，则会以直通方式传递消息。</span><span class="sxs-lookup"><span data-stu-id="ffa46-131">If there are no components in the stage, the message is passed through.</span></span>  
  
## <a name="validate-stage"></a><span data-ttu-id="ffa46-132">验证阶段</span><span class="sxs-lookup"><span data-stu-id="ffa46-132">Validate stage</span></span>  
  
-   <span data-ttu-id="ffa46-133">此阶段用于对消息格式进行验证的组件。</span><span class="sxs-lookup"><span data-stu-id="ffa46-133">This stage is used for components that validate the message format.</span></span>  
  
    -   <span data-ttu-id="ffa46-134">管道组件只能处理与该组件中指定的架构相符的消息。</span><span class="sxs-lookup"><span data-stu-id="ffa46-134">A pipeline component processes only messages that conform to the schemas specified in that component.</span></span> <span data-ttu-id="ffa46-135">如果管道所收到消息的架构与管道中的任何组件均不关联，则不会处理该消息。</span><span class="sxs-lookup"><span data-stu-id="ffa46-135">If a pipeline receives a message whose schema is not associated with any component in the pipeline, that message is not processed.</span></span> <span data-ttu-id="ffa46-136">此时，将根据提交该消息的适配器挂起该消息或向发件人发送错误消息。</span><span class="sxs-lookup"><span data-stu-id="ffa46-136">Depending on the adapter that submits the message, the message is either suspended or an error is issued to the sender.</span></span>  
  
    -   <span data-ttu-id="ffa46-137">此阶段中的组件用于验证拆装阶段生成的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="ffa46-137">Components in this stage are used to validate the XML messages produced by the Disassemble stage.</span></span> <span data-ttu-id="ffa46-138">此阶段中的组件将指定用于执行 XML 验证的架构。</span><span class="sxs-lookup"><span data-stu-id="ffa46-138">Components in this stage specify schemas to perform the XML validation.</span></span>  
  
-   <span data-ttu-id="ffa46-139">此阶段可包含 0 到 255 个组件。</span><span class="sxs-lookup"><span data-stu-id="ffa46-139">This stage can contain between zero and 255 components.</span></span>  
  
-   <span data-ttu-id="ffa46-140">此阶段中的所有组件均将运行。</span><span class="sxs-lookup"><span data-stu-id="ffa46-140">All components in this stage are run.</span></span>  
  
    -   <span data-ttu-id="ffa46-141">此阶段可能会运行多次。</span><span class="sxs-lookup"><span data-stu-id="ffa46-141">This stage may be run more than once.</span></span> <span data-ttu-id="ffa46-142">拆装阶段每创建一条消息，此阶段就会运行一次。</span><span class="sxs-lookup"><span data-stu-id="ffa46-142">It runs once per message created by the Disassemble stage.</span></span>  
  
## <a name="resolveparty-stage"></a><span data-ttu-id="ffa46-143">解析参与方阶段</span><span class="sxs-lookup"><span data-stu-id="ffa46-143">ResolveParty stage</span></span>  
  
-   <span data-ttu-id="ffa46-144">此阶段是一个占位符，供[方解析管道组件](../core/party-resolution-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="ffa46-144">This stage is a placeholder for the [Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md).</span></span>  
  
-   <span data-ttu-id="ffa46-145">此阶段可能会运行多次。</span><span class="sxs-lookup"><span data-stu-id="ffa46-145">This stage may be run more than once.</span></span> <span data-ttu-id="ffa46-146">拆装阶段每创建一条消息，此阶段就会运行一次。</span><span class="sxs-lookup"><span data-stu-id="ffa46-146">It runs once per message created by the Disassemble stage.</span></span>  
  
-   <span data-ttu-id="ffa46-147">此阶段可包含 0 到 255 个组件。</span><span class="sxs-lookup"><span data-stu-id="ffa46-147">This stage can contain between zero and 255 components.</span></span>  
  
-   <span data-ttu-id="ffa46-148">此阶段中的所有组件均将运行。</span><span class="sxs-lookup"><span data-stu-id="ffa46-148">All components in this stage are run.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffa46-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ffa46-149">See Also</span></span>  
 <span data-ttu-id="ffa46-150">[发送管道](../core/send-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="ffa46-150">[Send Pipelines](../core/send-pipelines.md) </span></span>  
 <span data-ttu-id="ffa46-151">[有关管道、 阶段和组件](../core/about-pipelines-stages-and-components.md) </span><span class="sxs-lookup"><span data-stu-id="ffa46-151">[About Pipelines, Stages, and Components](../core/about-pipelines-stages-and-components.md) </span></span>  
 <span data-ttu-id="ffa46-152">[类型的管道组件](../core/types-of-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="ffa46-152">[Types of Pipeline Components](../core/types-of-pipeline-components.md) </span></span>  
 <span data-ttu-id="ffa46-153">[默认管道](../core/default-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="ffa46-153">[Default Pipelines](../core/default-pipelines.md) </span></span>  
 <span data-ttu-id="ffa46-154">[管道模板](../core/pipeline-templates.md) </span><span class="sxs-lookup"><span data-stu-id="ffa46-154">[Pipeline Templates](../core/pipeline-templates.md) </span></span>  
 <span data-ttu-id="ffa46-155">[管道组件](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="ffa46-155">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 [<span data-ttu-id="ffa46-156">类型的管道</span><span class="sxs-lookup"><span data-stu-id="ffa46-156">Types of Pipelines</span></span>](../core/types-of-pipelines.md)