---
title: 使用管道设计器创建管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, processing messages
- pipelines, Pipeline Designer
- Pipeline Designer, about Pipeline Designer
ms.assetid: 858302d8-a912-4199-95e5-4322db789b4e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62e182440522e82f7ae6eaeaf52234161bee7483
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998606"
---
# <a name="creating-pipelines-using-pipeline-designer"></a><span data-ttu-id="600d7-102">使用管道设计器创建管道</span><span class="sxs-lookup"><span data-stu-id="600d7-102">Creating Pipelines Using Pipeline Designer</span></span>
<span data-ttu-id="600d7-103">Microsoft BizTalk Server 主要处理 XML 文档格式。</span><span class="sxs-lookup"><span data-stu-id="600d7-103">Microsoft BizTalk Server works mainly with the XML document format.</span></span> <span data-ttu-id="600d7-104">通常，消息必须从本身格式转换为其 XML 表示形式，才能充分利用 BizTalk Server 的处理功能。</span><span class="sxs-lookup"><span data-stu-id="600d7-104">For a message to take full advantage of BizTalk Server processing, it must often be transformed from its native format into its XML representation.</span></span> <span data-ttu-id="600d7-105">BizTalk Server 管道可对传入消息和传出消息执行这种转换，并执行其他特定于数据的操作（例如数据加密或解密、属性升级等）。</span><span class="sxs-lookup"><span data-stu-id="600d7-105">BizTalk Server pipelines perform this transformation, as well as other data-specific actions (such as data encryption or decryption, property promotion, and so on) on incoming and outgoing messages.</span></span> <span data-ttu-id="600d7-106">本部分提供有关管道和管道设计器的概念信息和任务特定信息。</span><span class="sxs-lookup"><span data-stu-id="600d7-106">This section provides conceptual and task-specific information about pipelines and Pipeline Designer.</span></span>  
  
 <span data-ttu-id="600d7-107">管道的作用是在适配器接收消息后对消息进行准备以便服务器处理，或在服务器处理消息后对消息进行准备以便发送。</span><span class="sxs-lookup"><span data-stu-id="600d7-107">The purpose of a pipeline is to prepare a message for processing by the server after being received by an adapter or to prepare a message for sending after being processed by the server.</span></span>  
  
 <span data-ttu-id="600d7-108">管道通常执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="600d7-108">Pipelines commonly perform:</span></span>  
  
- <span data-ttu-id="600d7-109">从不同格式到 XML 格式的数据规范化。</span><span class="sxs-lookup"><span data-stu-id="600d7-109">Data normalization from various formats to XML.</span></span>  
  
- <span data-ttu-id="600d7-110">从 XML 格式到不同格式的数据转换。</span><span class="sxs-lookup"><span data-stu-id="600d7-110">Data transformation from XML to various formats.</span></span>  
  
- <span data-ttu-id="600d7-111">属性升级和降级。</span><span class="sxs-lookup"><span data-stu-id="600d7-111">Property promotion and demotion.</span></span>  
  
- <span data-ttu-id="600d7-112">文档拆装和组装。</span><span class="sxs-lookup"><span data-stu-id="600d7-112">Document disassembly and assembly.</span></span>  
  
- <span data-ttu-id="600d7-113">文档解码和编码。</span><span class="sxs-lookup"><span data-stu-id="600d7-113">Document decoding and encoding.</span></span>  
  
- <span data-ttu-id="600d7-114">文档解密和加密。</span><span class="sxs-lookup"><span data-stu-id="600d7-114">Document decryption and encryption.</span></span>  
  
- <span data-ttu-id="600d7-115">文档签名和数字签名验证。</span><span class="sxs-lookup"><span data-stu-id="600d7-115">Document signing and digital signature verification.</span></span>  
  
  <span data-ttu-id="600d7-116">下图显示了在使用管道处理消息过程中涉及的工作流：</span><span class="sxs-lookup"><span data-stu-id="600d7-116">The following figure shows the workflow involved in processing a message by using pipelines.</span></span>  
  
  <span data-ttu-id="600d7-117">![用于处理消息的工作流的图表。](../core/media/ebiz-dev-busprcsadptc.gif "ebiz_dev_busprcsadptc")</span><span class="sxs-lookup"><span data-stu-id="600d7-117">![Diagram of workflow for processing a message.](../core/media/ebiz-dev-busprcsadptc.gif "ebiz_dev_busprcsadptc")</span></span>  
  <span data-ttu-id="600d7-118">消息处理工作流示意图</span><span class="sxs-lookup"><span data-stu-id="600d7-118">Depicts the message processing workflow.</span></span>  
  
  <span data-ttu-id="600d7-119">如图所示，消息将从适配器传递到接收管道，在管道中消息将转换为 XML。</span><span class="sxs-lookup"><span data-stu-id="600d7-119">As shown in the figure, the message is passed from the adapter to the receive pipeline where it is transformed to XML.</span></span> <span data-ttu-id="600d7-120">然后，消息可由业务流程使用，或传递给发送管道，然后传递给发送适配器。</span><span class="sxs-lookup"><span data-stu-id="600d7-120">The message can then be used by orchestrations, or passed to a send pipeline, and then to a send adapter.</span></span>  
  
  <span data-ttu-id="600d7-121">有关使用键盘快捷键的管道设计器的信息，请参阅[管道设计器键盘快捷方式](../core/pipeline-designer-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="600d7-121">For information about using the keyboard shortcuts for Pipeline Designer, see [Pipeline Designer Keyboard Shortcuts](../core/pipeline-designer-keyboard-shortcuts.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="600d7-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="600d7-122">In This Section</span></span>  
  
-   [<span data-ttu-id="600d7-123">关于管道、阶段和组件</span><span class="sxs-lookup"><span data-stu-id="600d7-123">About Pipelines, Stages, and Components</span></span>](../core/about-pipelines-stages-and-components.md)  
  
-   [<span data-ttu-id="600d7-124">使用管道设计器</span><span class="sxs-lookup"><span data-stu-id="600d7-124">Using Pipeline Designer</span></span>](../core/using-pipeline-designer.md)  
  
-   [<span data-ttu-id="600d7-125">使用管道设计器创建管道</span><span class="sxs-lookup"><span data-stu-id="600d7-125">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)  
  
-   [<span data-ttu-id="600d7-126">配置本地管道组件</span><span class="sxs-lookup"><span data-stu-id="600d7-126">Configuring Native Pipeline Components</span></span>](../core/configuring-native-pipeline-components.md)  
  
-   [<span data-ttu-id="600d7-127">如何部署管道</span><span class="sxs-lookup"><span data-stu-id="600d7-127">How to Deploy Pipelines</span></span>](../core/how-to-deploy-pipelines.md)  
  
-   [<span data-ttu-id="600d7-128">如何确保管道安全</span><span class="sxs-lookup"><span data-stu-id="600d7-128">How to Secure Pipelines</span></span>](../core/how-to-secure-pipelines.md)