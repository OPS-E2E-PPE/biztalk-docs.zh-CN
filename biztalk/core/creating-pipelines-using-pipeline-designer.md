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
ms.openlocfilehash: ead846de3a731a73ee1c0908801485d67ff68a79
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353624"
---
# <a name="creating-pipelines-using-pipeline-designer"></a><span data-ttu-id="3a143-102">使用管道设计器创建管道</span><span class="sxs-lookup"><span data-stu-id="3a143-102">Creating Pipelines Using Pipeline Designer</span></span>
<span data-ttu-id="3a143-103">Microsoft BizTalk Server 程序主要处理 XML 文档格式。</span><span class="sxs-lookup"><span data-stu-id="3a143-103">Microsoft BizTalk Server works mainly with the XML document format.</span></span> <span data-ttu-id="3a143-104">若要充分利用 BizTalk Server 处理的消息，必须经常将它转换从其本机格式转换为 XML 表示形式。</span><span class="sxs-lookup"><span data-stu-id="3a143-104">For a message to take full advantage of BizTalk Server processing, it must often be transformed from its native format into its XML representation.</span></span> <span data-ttu-id="3a143-105">BizTalk Server 管道对传入和传出消息执行此转换，以及其他特定于数据的操作 （例如数据加密或解密、 属性升级等）。</span><span class="sxs-lookup"><span data-stu-id="3a143-105">BizTalk Server pipelines perform this transformation, as well as other data-specific actions (such as data encryption or decryption, property promotion, and so on) on incoming and outgoing messages.</span></span> <span data-ttu-id="3a143-106">本部分提供有关管道和管道设计器的概念和特定于任务的信息。</span><span class="sxs-lookup"><span data-stu-id="3a143-106">This section provides conceptual and task-specific information about pipelines and Pipeline Designer.</span></span>  
  
 <span data-ttu-id="3a143-107">若要准备的消息进行处理服务器在适配器接收后或准备服务器处理后发送一条消息，管道的作用。</span><span class="sxs-lookup"><span data-stu-id="3a143-107">The purpose of a pipeline is to prepare a message for processing by the server after being received by an adapter or to prepare a message for sending after being processed by the server.</span></span>  
  
 <span data-ttu-id="3a143-108">管道通常执行：</span><span class="sxs-lookup"><span data-stu-id="3a143-108">Pipelines commonly perform:</span></span>  
  
- <span data-ttu-id="3a143-109">数据规范化为各种格式为 XML。</span><span class="sxs-lookup"><span data-stu-id="3a143-109">Data normalization from various formats to XML.</span></span>  
  
- <span data-ttu-id="3a143-110">数据转换为 XML 为各种格式。</span><span class="sxs-lookup"><span data-stu-id="3a143-110">Data transformation from XML to various formats.</span></span>  
  
- <span data-ttu-id="3a143-111">属性升级和降级。</span><span class="sxs-lookup"><span data-stu-id="3a143-111">Property promotion and demotion.</span></span>  
  
- <span data-ttu-id="3a143-112">文档拆装和组装。</span><span class="sxs-lookup"><span data-stu-id="3a143-112">Document disassembly and assembly.</span></span>  
  
- <span data-ttu-id="3a143-113">文档解码和编码。</span><span class="sxs-lookup"><span data-stu-id="3a143-113">Document decoding and encoding.</span></span>  
  
- <span data-ttu-id="3a143-114">文档解密和加密。</span><span class="sxs-lookup"><span data-stu-id="3a143-114">Document decryption and encryption.</span></span>  
  
- <span data-ttu-id="3a143-115">文档签名和数字签名验证。</span><span class="sxs-lookup"><span data-stu-id="3a143-115">Document signing and digital signature verification.</span></span>  
  
  <span data-ttu-id="3a143-116">下图显示工作流所涉及到使用管道来处理一条消息。</span><span class="sxs-lookup"><span data-stu-id="3a143-116">The following figure shows the workflow involved in processing a message by using pipelines.</span></span>  
  
  <span data-ttu-id="3a143-117">![消息的处理的工作流的图示。](../core/media/ebiz-dev-busprcsadptc.gif "ebiz_dev_busprcsadptc")</span><span class="sxs-lookup"><span data-stu-id="3a143-117">![Diagram of workflow for processing a message.](../core/media/ebiz-dev-busprcsadptc.gif "ebiz_dev_busprcsadptc")</span></span>  
  <span data-ttu-id="3a143-118">消息处理工作流示意图</span><span class="sxs-lookup"><span data-stu-id="3a143-118">Depicts the message processing workflow.</span></span>  
  
  <span data-ttu-id="3a143-119">如图所示，该消息是从适配器传递到接收管道它将转换为 XML。</span><span class="sxs-lookup"><span data-stu-id="3a143-119">As shown in the figure, the message is passed from the adapter to the receive pipeline where it is transformed to XML.</span></span> <span data-ttu-id="3a143-120">然后可以使用的业务流程，或传递到发送管道，再到发送适配器消息。</span><span class="sxs-lookup"><span data-stu-id="3a143-120">The message can then be used by orchestrations, or passed to a send pipeline, and then to a send adapter.</span></span>  
  
  <span data-ttu-id="3a143-121">有关使用键盘快捷键的管道设计器的信息，请参阅[管道设计器键盘快捷方式](../core/pipeline-designer-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="3a143-121">For information about using the keyboard shortcuts for Pipeline Designer, see [Pipeline Designer Keyboard Shortcuts](../core/pipeline-designer-keyboard-shortcuts.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3a143-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="3a143-122">In This Section</span></span>  
  
-   [<span data-ttu-id="3a143-123">关于管道、阶段和组件</span><span class="sxs-lookup"><span data-stu-id="3a143-123">About Pipelines, Stages, and Components</span></span>](../core/about-pipelines-stages-and-components.md)  
  
-   [<span data-ttu-id="3a143-124">使用管道设计器</span><span class="sxs-lookup"><span data-stu-id="3a143-124">Using Pipeline Designer</span></span>](../core/using-pipeline-designer.md)  
  
-   [<span data-ttu-id="3a143-125">使用管道设计器创建管道</span><span class="sxs-lookup"><span data-stu-id="3a143-125">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)  
  
-   [<span data-ttu-id="3a143-126">配置本地管道组件</span><span class="sxs-lookup"><span data-stu-id="3a143-126">Configuring Native Pipeline Components</span></span>](../core/configuring-native-pipeline-components.md)  
  
-   [<span data-ttu-id="3a143-127">如何部署管道</span><span class="sxs-lookup"><span data-stu-id="3a143-127">How to Deploy Pipelines</span></span>](../core/how-to-deploy-pipelines.md)  
  
-   [<span data-ttu-id="3a143-128">如何确保管道安全</span><span class="sxs-lookup"><span data-stu-id="3a143-128">How to Secure Pipelines</span></span>](../core/how-to-secure-pipelines.md)