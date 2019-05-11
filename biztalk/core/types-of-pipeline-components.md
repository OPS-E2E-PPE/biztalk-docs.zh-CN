---
title: 类型的管道组件 |Microsoft Docs
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
ms.openlocfilehash: c6b8ad31d2e135aec1283b5057e6b39de45ad422
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379925"
---
# <a name="types-of-pipeline-components"></a><span data-ttu-id="728b2-102">类型的管道组件</span><span class="sxs-lookup"><span data-stu-id="728b2-102">Types of Pipeline Components</span></span>
<span data-ttu-id="728b2-103">三种类型的管道组件所含[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]： 常规、 组装和拆装。</span><span class="sxs-lookup"><span data-stu-id="728b2-103">Three types of pipeline components are included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]: general, assembling, and disassembling.</span></span> <span data-ttu-id="728b2-104">这三种类型的任何可实现探测功能。</span><span class="sxs-lookup"><span data-stu-id="728b2-104">Any of these three types can also implement probing functionality.</span></span> <span data-ttu-id="728b2-105">本主题介绍每种类型的组件，并在其中每个组件通常使用的阶段。</span><span class="sxs-lookup"><span data-stu-id="728b2-105">This topic describes each type of component and the stages in which each component is generally used.</span></span>  
  
## <a name="general"></a><span data-ttu-id="728b2-106">常规</span><span class="sxs-lookup"><span data-stu-id="728b2-106">General</span></span>  
 <span data-ttu-id="728b2-107">常规组件接收一个消息、 处理消息，并生成零个或一个消息。</span><span class="sxs-lookup"><span data-stu-id="728b2-107">General components take one message, process the message, and produce zero or one message.</span></span>  
  
 <span data-ttu-id="728b2-108">常规组件包括的 MIME/SMIME 解码器、 MIME/SMIME 编码器、 参与方解析和验证程序组件。</span><span class="sxs-lookup"><span data-stu-id="728b2-108">The MIME/SMIME Decoder, MIME/SMIME Encoder, Party Resolution, and Validator components are the included general components.</span></span> <span data-ttu-id="728b2-109">您可能需要创建自定义常规组件在发送前，压缩的消息大小，或等待其他信息以对其进行处理时使用一条消息。</span><span class="sxs-lookup"><span data-stu-id="728b2-109">You may need to create custom general components to compress the size of a message before sending, or to consume a message while waiting for additional information to process it.</span></span>  
  
 <span data-ttu-id="728b2-110">常规组件应置于解码、 编码、 预组装、 解析参与方，或验证阶段。</span><span class="sxs-lookup"><span data-stu-id="728b2-110">General components should be placed in the Decode, Encode, Pre-assemble, ResolveParty, or Validate stages.</span></span>  
  
 <span data-ttu-id="728b2-111">有关开发常规管道组件的信息，请参阅[开发常规管道组件](../core/developing-a-general-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="728b2-111">For information about developing general pipeline components, see [Developing a General Pipeline Component](../core/developing-a-general-pipeline-component.md).</span></span>  
  
## <a name="assembling"></a><span data-ttu-id="728b2-112">组合</span><span class="sxs-lookup"><span data-stu-id="728b2-112">Assembling</span></span>  
 <span data-ttu-id="728b2-113">组装组件具有方面的许多工作来准备要发送的消息。</span><span class="sxs-lookup"><span data-stu-id="728b2-113">Assembling components have numerous responsibilities to prepare the message to be sent.</span></span> <span data-ttu-id="728b2-114">首先，该组件将 XML 消息转换为消息，根据组装器和架构中设置属性的类型的相应 XML 或非 XML 本机格式。</span><span class="sxs-lookup"><span data-stu-id="728b2-114">First, the component converts the XML message to the appropriate XML or non-XML native format of the message, based on the type of assembler and properties set in the schema.</span></span> <span data-ttu-id="728b2-115">此外，组装组件组装和将消息包装到信封中，或添加一个标头或尾部 （或两者） 消息。</span><span class="sxs-lookup"><span data-stu-id="728b2-115">In addition, assembling components assemble and wrap the message in an envelope, or add a header or trailer (or both) to the message.</span></span> <span data-ttu-id="728b2-116">在组装期间，某些属性将移动消息上下文中的文档的正文或信封。</span><span class="sxs-lookup"><span data-stu-id="728b2-116">During assembly, some properties are moved from the message context to the body of the document or to the envelope.</span></span>  
  
 <span data-ttu-id="728b2-117">BizTalk 框架组装器、 平面文件组装器和 XML 组装器组件是默认的组装组件。</span><span class="sxs-lookup"><span data-stu-id="728b2-117">The BizTalk Framework Assembler, Flat File Assembler, and XML Assembler components are the default assembling components.</span></span>  
  
 <span data-ttu-id="728b2-118">组装组件应置于发送管道的组装阶段中。</span><span class="sxs-lookup"><span data-stu-id="728b2-118">Assembling components should be placed in the Assemble stage of send pipelines.</span></span>  
  
 <span data-ttu-id="728b2-119">有关开发组装管道组件的信息，请参阅[开发组装管道组件](../core/developing-an-assembling-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="728b2-119">For information about developing assembling pipeline components, see [Developing an Assembling Pipeline Component](../core/developing-an-assembling-pipeline-component.md).</span></span>  
  
## <a name="disassembling"></a><span data-ttu-id="728b2-120">反汇编</span><span class="sxs-lookup"><span data-stu-id="728b2-120">Disassembling</span></span>  
 <span data-ttu-id="728b2-121">拆装组件完成许多任务来准备要拆分为单独的文档，根据信封的消息，BizTalk Server 中使用的文档架构。</span><span class="sxs-lookup"><span data-stu-id="728b2-121">Disassembling components complete many tasks to prepare the message to be split up into individual documents according to envelope and document schemas for use within BizTalk Server.</span></span> <span data-ttu-id="728b2-122">首先，拆装组件可能会将非 XML 消息转换为其 XML 表示形式，这是处理所需的 BizTalk server。</span><span class="sxs-lookup"><span data-stu-id="728b2-122">First, the disassembling component may convert non-XML messages into their XML representation, which is required for processing by BizTalk Server.</span></span> <span data-ttu-id="728b2-123">接下来，该消息被拆装成可以发送给不同业务流程的单个消息。</span><span class="sxs-lookup"><span data-stu-id="728b2-123">Next, the message is disassembled into singular messages that can be sent to separate orchestrations.</span></span> <span data-ttu-id="728b2-124">该消息被拆装通过移除信封，将消息拆分成单个文档根据信封和消息架构，然后将属性从信封移到单独的消息上下文。</span><span class="sxs-lookup"><span data-stu-id="728b2-124">The message is disassembled by removing the envelope, splitting the message up into individual documents according to envelope and message schemas, and then moving properties from the envelope to the individual message contexts.</span></span> <span data-ttu-id="728b2-125">此外，某些属性可以升级从消息的正文为标头。</span><span class="sxs-lookup"><span data-stu-id="728b2-125">Additionally, some properties may be promoted from the body of the message to the header.</span></span> <span data-ttu-id="728b2-126">由架构确定升级的属性。</span><span class="sxs-lookup"><span data-stu-id="728b2-126">The promoted properties are determined by the schema.</span></span>  
  
 <span data-ttu-id="728b2-127">拆装组件还必须设置恰当地使用消息路由的消息的消息类型属性。</span><span class="sxs-lookup"><span data-stu-id="728b2-127">The disassembling component must also set the message type property, which is used for routing messages appropriately.</span></span> <span data-ttu-id="728b2-128">消息类型属性是消息正文的 Namespace #RootElement。</span><span class="sxs-lookup"><span data-stu-id="728b2-128">The message type property is the Namespace#RootElement of the message body.</span></span> <span data-ttu-id="728b2-129">其他属性，如内容类型和字符集设置为上下文属性的一部分。</span><span class="sxs-lookup"><span data-stu-id="728b2-129">Other properties, such as the content type and character set are set as part of the context property.</span></span>  
  
 <span data-ttu-id="728b2-130">BizTalk 框架拆装器、 平面文件拆装器和 XML 拆装器组件是默认拆装组件包含在 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="728b2-130">The BizTalk Framework Disassembler, Flat File Disassembler, and XML Disassembler components are the default disassembling components included with BizTalk Server.</span></span>  
  
 <span data-ttu-id="728b2-131">接收管道的拆装阶段中，应使用拆装组件。</span><span class="sxs-lookup"><span data-stu-id="728b2-131">Disassembling components should be used in the Disassemble stage of receive pipelines.</span></span>  
  
 <span data-ttu-id="728b2-132">有关开发拆装管道组件的信息，请参阅[开发拆装管道组件](../core/developing-a-disassembling-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="728b2-132">For information about developing disassembling pipeline components, see [Developing a Disassembling Pipeline Component](../core/developing-a-disassembling-pipeline-component.md).</span></span>  
  
## <a name="probing"></a><span data-ttu-id="728b2-133">探测</span><span class="sxs-lookup"><span data-stu-id="728b2-133">Probing</span></span>  
 <span data-ttu-id="728b2-134">探测组件可以检查该消息来查看其是否在该组件理解的格式中的第一个部分。</span><span class="sxs-lookup"><span data-stu-id="728b2-134">A probing component checks the first portion of the message to see if it is in a format that the component understands.</span></span> <span data-ttu-id="728b2-135">如果格式已知的则会将整个消息交给此组件进行处理。</span><span class="sxs-lookup"><span data-stu-id="728b2-135">If the format is known, the whole message is given to this component for processing.</span></span>  
  
 <span data-ttu-id="728b2-136">有关开发探测管道组件，请参阅[开发探测管道组件](../core/developing-a-probing-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="728b2-136">For information about developing probing pipeline components, see [Developing a Probing Pipeline Component](../core/developing-a-probing-pipeline-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="728b2-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="728b2-137">See Also</span></span>  
 <span data-ttu-id="728b2-138">[类型的管道](../core/types-of-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="728b2-138">[Types of Pipelines](../core/types-of-pipelines.md) </span></span>  
 <span data-ttu-id="728b2-139">[默认管道](../core/default-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="728b2-139">[Default Pipelines](../core/default-pipelines.md) </span></span>  
 <span data-ttu-id="728b2-140">[管道模板](../core/pipeline-templates.md) </span><span class="sxs-lookup"><span data-stu-id="728b2-140">[Pipeline Templates](../core/pipeline-templates.md) </span></span>  
 <span data-ttu-id="728b2-141">[管道组件](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="728b2-141">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 [<span data-ttu-id="728b2-142">关于管道、阶段和组件</span><span class="sxs-lookup"><span data-stu-id="728b2-142">About Pipelines, Stages, and Components</span></span>](../core/about-pipelines-stages-and-components.md)