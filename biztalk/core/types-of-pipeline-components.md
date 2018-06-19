---
title: 类型的管道组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, components
ms.assetid: 9b493758-6b0f-4223-94bb-8f077ee735a9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9ba18aed137380f6b3d491ad52cfcee94bf111a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286773"
---
# <a name="types-of-pipeline-components"></a><span data-ttu-id="fdb4d-102">类型的管道组件</span><span class="sxs-lookup"><span data-stu-id="fdb4d-102">Types of Pipeline Components</span></span>
<span data-ttu-id="fdb4d-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供了三种管道组件类型：常规、组装和拆装。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-103">Three types of pipeline components are included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]: general, assembling, and disassembling.</span></span> <span data-ttu-id="fdb4d-104">这三种类型均可实现探测功能。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-104">Any of these three types can also implement probing functionality.</span></span> <span data-ttu-id="fdb4d-105">本主题介绍每种组件类型及其通常所用的阶段。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-105">This topic describes each type of component and the stages in which each component is generally used.</span></span>  
  
## <a name="general"></a><span data-ttu-id="fdb4d-106">常规</span><span class="sxs-lookup"><span data-stu-id="fdb4d-106">General</span></span>  
 <span data-ttu-id="fdb4d-107">常规组件在接收一个消息后对其进行处理，然后生成一个消息，或不生成任何消息。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-107">General components take one message, process the message, and produce zero or one message.</span></span>  
  
 <span data-ttu-id="fdb4d-108">提供的常规组件包括 MIME/SMIME 解码器、MIME/SMIME 编码器、参与方解析和验证器组件。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-108">The MIME/SMIME Decoder, MIME/SMIME Encoder, Party Resolution, and Validator components are the included general components.</span></span> <span data-ttu-id="fdb4d-109">您可能需要创建自定义常规组件，以便在发送消息前压缩消息的大小，或在等待用于处理消息的其他信息时使用该消息。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-109">You may need to create custom general components to compress the size of a message before sending, or to consume a message while waiting for additional information to process it.</span></span>  
  
 <span data-ttu-id="fdb4d-110">常规组件应置于解码、编码、预组装、解析参与方或验证阶段中。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-110">General components should be placed in the Decode, Encode, Pre-assemble, ResolveParty, or Validate stages.</span></span>  
  
 <span data-ttu-id="fdb4d-111">有关开发常规管道组件的信息，请参阅[开发的常规管道组件](../core/developing-a-general-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-111">For information about developing general pipeline components, see [Developing a General Pipeline Component](../core/developing-a-general-pipeline-component.md).</span></span>  
  
## <a name="assembling"></a><span data-ttu-id="fdb4d-112">组合</span><span class="sxs-lookup"><span data-stu-id="fdb4d-112">Assembling</span></span>  
 <span data-ttu-id="fdb4d-113">组装组件用于执行准备待发送消息方面的许多工作。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-113">Assembling components have numerous responsibilities to prepare the message to be sent.</span></span> <span data-ttu-id="fdb4d-114">首先，该组件会根据组装器的类型和架构中设置的属性，将 XML 消息转换为相应的 XML 或非 XML 本地格式。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-114">First, the component converts the XML message to the appropriate XML or non-XML native format of the message, based on the type of assembler and properties set in the schema.</span></span> <span data-ttu-id="fdb4d-115">此外，组装组件还会将消息组装并包装到信封中，或向消息添加头部或尾部（或同时添加这二者）。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-115">In addition, assembling components assemble and wrap the message in an envelope, or add a header or trailer (or both) to the message.</span></span> <span data-ttu-id="fdb4d-116">在组装期间，某些属性将从消息上下文移至文档的正文，或移至信封。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-116">During assembly, some properties are moved from the message context to the body of the document or to the envelope.</span></span>  
  
 <span data-ttu-id="fdb4d-117">BizTalk 框架组装器、平面文件组装器和 XML 组装器组件是默认的组装组件。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-117">The BizTalk Framework Assembler, Flat File Assembler, and XML Assembler components are the default assembling components.</span></span>  
  
 <span data-ttu-id="fdb4d-118">组装组件应置于发送管道的组装阶段。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-118">Assembling components should be placed in the Assemble stage of send pipelines.</span></span>  
  
 <span data-ttu-id="fdb4d-119">有关开发组装管道组件的信息，请参阅[开发组合管道组件](../core/developing-an-assembling-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-119">For information about developing assembling pipeline components, see [Developing an Assembling Pipeline Component](../core/developing-an-assembling-pipeline-component.md).</span></span>  
  
## <a name="disassembling"></a><span data-ttu-id="fdb4d-120">反汇编</span><span class="sxs-lookup"><span data-stu-id="fdb4d-120">Disassembling</span></span>  
 <span data-ttu-id="fdb4d-121">拆装组件对消息进行许多准备，以根据 BizTalk Server 中使用的信封和文档架构将消息拆分成若干个单独文档。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-121">Disassembling components complete many tasks to prepare the message to be split up into individual documents according to envelope and document schemas for use within BizTalk Server.</span></span> <span data-ttu-id="fdb4d-122">首先，拆装组件会将非 XML 消息转换成其 XML 表示形式，这对于 BizTalk Server 处理消息来说是必需的。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-122">First, the disassembling component may convert non-XML messages into their XML representation, which is required for processing by BizTalk Server.</span></span> <span data-ttu-id="fdb4d-123">然后，该消息被拆装成可以发送给不同业务流程的单个消息。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-123">Next, the message is disassembled into singular messages that can be sent to separate orchestrations.</span></span> <span data-ttu-id="fdb4d-124">拆装消息时需要执行以下步骤：移除信封，根据信封和消息架构将消息拆分成单个文档，然后将属性从信封移至各消息上下文中。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-124">The message is disassembled by removing the envelope, splitting the message up into individual documents according to envelope and message schemas, and then moving properties from the envelope to the individual message contexts.</span></span> <span data-ttu-id="fdb4d-125">另外，某些属性可能从消息的正文升级到头部。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-125">Additionally, some properties may be promoted from the body of the message to the header.</span></span> <span data-ttu-id="fdb4d-126">要升级的属性是由架构确定的。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-126">The promoted properties are determined by the schema.</span></span>  
  
 <span data-ttu-id="fdb4d-127">拆装组件还必须设置消息类型属性，以用于正确地路由消息。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-127">The disassembling component must also set the message type property, which is used for routing messages appropriately.</span></span> <span data-ttu-id="fdb4d-128">消息类型属性是消息正文的 Namespace#RootElement。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-128">The message type property is the Namespace#RootElement of the message body.</span></span> <span data-ttu-id="fdb4d-129">诸如内容类型和字符集之类的其他属性则被设置为上下文属性的一部分。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-129">Other properties, such as the content type and character set are set as part of the context property.</span></span>  
  
 <span data-ttu-id="fdb4d-130">BizTalk 框架拆装器、平面文件拆装器和 XML 拆装器组件是 BizTalk Server 提供的默认拆装组件。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-130">The BizTalk Framework Disassembler, Flat File Disassembler, and XML Disassembler components are the default disassembling components included with BizTalk Server.</span></span>  
  
 <span data-ttu-id="fdb4d-131">拆装组件应用于接收管道的拆装阶段。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-131">Disassembling components should be used in the Disassemble stage of receive pipelines.</span></span>  
  
 <span data-ttu-id="fdb4d-132">有关开发分解管道组件的信息，请参阅[开发反汇编管道组件](../core/developing-a-disassembling-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-132">For information about developing disassembling pipeline components, see [Developing a Disassembling Pipeline Component](../core/developing-a-disassembling-pipeline-component.md).</span></span>  
  
## <a name="probing"></a><span data-ttu-id="fdb4d-133">探测</span><span class="sxs-lookup"><span data-stu-id="fdb4d-133">Probing</span></span>  
 <span data-ttu-id="fdb4d-134">探测组件可以检查消息的第一部分，以确定组件是否可以识别此消息的格式。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-134">A probing component checks the first portion of the message to see if it is in a format that the component understands.</span></span> <span data-ttu-id="fdb4d-135">如果格式是已知的，则会将整个消息交给此组件进行处理。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-135">If the format is known, the whole message is given to this component for processing.</span></span>  
  
 <span data-ttu-id="fdb4d-136">有关开发探测的信息管道组件，请参阅[开发探测管道组件](../core/developing-a-probing-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="fdb4d-136">For information about developing probing pipeline components, see [Developing a Probing Pipeline Component](../core/developing-a-probing-pipeline-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdb4d-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fdb4d-137">See Also</span></span>  
 <span data-ttu-id="fdb4d-138">[类型的管道](../core/types-of-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="fdb4d-138">[Types of Pipelines](../core/types-of-pipelines.md) </span></span>  
 <span data-ttu-id="fdb4d-139">[默认管道](../core/default-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="fdb4d-139">[Default Pipelines](../core/default-pipelines.md) </span></span>  
 <span data-ttu-id="fdb4d-140">[管道模板](../core/pipeline-templates.md) </span><span class="sxs-lookup"><span data-stu-id="fdb4d-140">[Pipeline Templates](../core/pipeline-templates.md) </span></span>  
 <span data-ttu-id="fdb4d-141">[管道组件](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="fdb4d-141">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 [<span data-ttu-id="fdb4d-142">有关管道、 阶段和组件</span><span class="sxs-lookup"><span data-stu-id="fdb4d-142">About Pipelines, Stages, and Components</span></span>](../core/about-pipelines-stages-and-components.md)