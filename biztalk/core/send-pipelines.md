---
title: "发送管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send pipelines, message flow
- send pipelines, about send pipelines
- messages, message flow
- send pipelines, stages
- pipelines, send pipelines
- messages, send pipelines
ms.assetid: c963b2d8-3b2b-4575-8105-c750deae8189
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef08909dbc47e11f5c9fecae6f65e01dbe79441b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="send-pipelines"></a><span data-ttu-id="eb4a7-102">发送管道</span><span class="sxs-lookup"><span data-stu-id="eb4a7-102">Send Pipelines</span></span>
<span data-ttu-id="eb4a7-103">下图显示消息处理工作流，其中突出显示了发送管道：</span><span class="sxs-lookup"><span data-stu-id="eb4a7-103">The following figure shows the message processing workflow, highlighting the send pipeline.</span></span>  
  
 <span data-ttu-id="eb4a7-104">![消息的处理的工作流的图示。] (../core/media/ebiz-dev-busprcsadptc.gif "ebiz_dev_busprcsadptc")</span><span class="sxs-lookup"><span data-stu-id="eb4a7-104">![Diagram of workflow for processing a message.](../core/media/ebiz-dev-busprcsadptc.gif "ebiz_dev_busprcsadptc")</span></span>  
<span data-ttu-id="eb4a7-105">消息处理工作流示意图</span><span class="sxs-lookup"><span data-stu-id="eb4a7-105">Depicts the message processing workflow.</span></span>  
  
 <span data-ttu-id="eb4a7-106">发送管道负责在将文档发送到最终目标之前对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="eb4a7-106">A send pipeline is responsible for processing documents before sending them to their final destinations.</span></span> <span data-ttu-id="eb4a7-107">发送管道获取一条消息，并生成一条要发送的消息。</span><span class="sxs-lookup"><span data-stu-id="eb4a7-107">The send pipeline takes one message and produces one message to send.</span></span>  
  
 <span data-ttu-id="eb4a7-108">你可以创建新的发送管道或可以使用 BizTalk Server 中包含两个默认发送管道之一-传递发送管道和 XML 发送管道。</span><span class="sxs-lookup"><span data-stu-id="eb4a7-108">You can create a new send pipeline or you can use one of the two default send pipelines included in BizTalk Server—the pass-through send pipeline and the XML send pipeline.</span></span>  
  
 <span data-ttu-id="eb4a7-109">默认情况下，发送管道由三个空阶段组成：预组装、组装和编码。</span><span class="sxs-lookup"><span data-stu-id="eb4a7-109">By default, the send pipeline consists of three empty stages: Pre-assemble, Assemble and Encode.</span></span> <span data-ttu-id="eb4a7-110">本主题包含了有关填充这些阶段的设计注意事项。</span><span class="sxs-lookup"><span data-stu-id="eb4a7-110">This topic contains design considerations for populating these stages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb4a7-111">如果向发送管道添加了使用组件，则该管道不会生成消息。</span><span class="sxs-lookup"><span data-stu-id="eb4a7-111">A send pipeline can produce zero messages when a consuming component is added to the pipeline.</span></span>  
  
## <a name="pre-assemble-stage"></a><span data-ttu-id="eb4a7-112">预组装阶段</span><span class="sxs-lookup"><span data-stu-id="eb4a7-112">Pre-assemble stage</span></span>  
  
-   <span data-ttu-id="eb4a7-113">此阶段是自定义组件的占位符，这些自定义组件将在对消息进行序列化之前对该消息执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="eb4a7-113">This stage is a placeholder for custom components that should perform some action on the message before the message is serialized.</span></span>  
  
-   <span data-ttu-id="eb4a7-114">此阶段对每条消息运行一次。</span><span class="sxs-lookup"><span data-stu-id="eb4a7-114">This stage is run once per message.</span></span>  
  
-   <span data-ttu-id="eb4a7-115">此阶段可包含 0 到 255 个组件。</span><span class="sxs-lookup"><span data-stu-id="eb4a7-115">This stage can contain between zero and 255 components.</span></span>  
  
-   <span data-ttu-id="eb4a7-116">此阶段中的所有组件均将运行。</span><span class="sxs-lookup"><span data-stu-id="eb4a7-116">All components in this stage are run.</span></span>  
  
## <a name="assemble-stage"></a><span data-ttu-id="eb4a7-117">组装阶段</span><span class="sxs-lookup"><span data-stu-id="eb4a7-117">Assemble stage</span></span>  
  
-   <span data-ttu-id="eb4a7-118">此阶段中的组件负责组装或序列化消息，并将该消息转换为 XML 或从 XML 进行转换。</span><span class="sxs-lookup"><span data-stu-id="eb4a7-118">Components in this stage are responsible for assembling or serializing the message and converting it to or from XML.</span></span>  
  
-   <span data-ttu-id="eb4a7-119">此阶段可以不包含任何组件，也可以包含一个组件。</span><span class="sxs-lookup"><span data-stu-id="eb4a7-119">This stage accepts zero components or one component.</span></span>  
  
-   <span data-ttu-id="eb4a7-120">此阶段中的所有组件均将运行。</span><span class="sxs-lookup"><span data-stu-id="eb4a7-120">All components in this stage are run.</span></span>  
  
## <a name="encode-stage"></a><span data-ttu-id="eb4a7-121">编码阶段</span><span class="sxs-lookup"><span data-stu-id="eb4a7-121">Encode stage</span></span>  
  
-   <span data-ttu-id="eb4a7-122">此阶段用于对消息进行编码或加密的组件。</span><span class="sxs-lookup"><span data-stu-id="eb4a7-122">This stage is used for components that encode or encrypt the message.</span></span>  
  
    -   <span data-ttu-id="eb4a7-123">如果需要对消息进行签名，请将 MIME/SMIME 编码器组件或自定义编码组件置于此阶段。</span><span class="sxs-lookup"><span data-stu-id="eb4a7-123">Place the MIME/SMIME Encoder component or a custom encoding component in this stage if message signing is required.</span></span>  
  
-   <span data-ttu-id="eb4a7-124">此阶段对每条消息运行一次。</span><span class="sxs-lookup"><span data-stu-id="eb4a7-124">This stage is run once per message.</span></span>  
  
-   <span data-ttu-id="eb4a7-125">此阶段可包含 0 到 255 个组件。</span><span class="sxs-lookup"><span data-stu-id="eb4a7-125">This stage can contain between zero and 255 components.</span></span>  
  
-   <span data-ttu-id="eb4a7-126">此阶段中的所有组件均将执行。</span><span class="sxs-lookup"><span data-stu-id="eb4a7-126">All components in this stage are executed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb4a7-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb4a7-127">See Also</span></span>  
 <span data-ttu-id="eb4a7-128">[接收管道](../core/receive-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="eb4a7-128">[Receive Pipelines](../core/receive-pipelines.md) </span></span>  
 <span data-ttu-id="eb4a7-129">[有关管道、 阶段和组件](../core/about-pipelines-stages-and-components.md) </span><span class="sxs-lookup"><span data-stu-id="eb4a7-129">[About Pipelines, Stages, and Components](../core/about-pipelines-stages-and-components.md) </span></span>  
 <span data-ttu-id="eb4a7-130">[类型的管道](../core/types-of-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="eb4a7-130">[Types of Pipelines](../core/types-of-pipelines.md) </span></span>  
 <span data-ttu-id="eb4a7-131">[默认管道](../core/default-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="eb4a7-131">[Default Pipelines](../core/default-pipelines.md) </span></span>  
 <span data-ttu-id="eb4a7-132">[管道模板](../core/pipeline-templates.md) </span><span class="sxs-lookup"><span data-stu-id="eb4a7-132">[Pipeline Templates](../core/pipeline-templates.md) </span></span>  
 <span data-ttu-id="eb4a7-133">[管道组件](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="eb4a7-133">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 [<span data-ttu-id="eb4a7-134">类型的管道组件</span><span class="sxs-lookup"><span data-stu-id="eb4a7-134">Types of Pipeline Components</span></span>](../core/types-of-pipeline-components.md)