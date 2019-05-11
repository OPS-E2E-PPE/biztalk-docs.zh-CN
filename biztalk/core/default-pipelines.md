---
title: 默认管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, PassThruTransmit
- pipelines, PassThruReceive
- pipelines, XMLTransmit
- pipelines, StsReceive
- pipelines, StsSend
- pipelines, StsFileReceive
- Microsoft.BizTalk.KwTpm.StsDefaultPipelines.EnvSchema XML envelope
- pipelines, XMLReceive
- pipelines, backward compatibility
- Microsoft.BizTalk.DefaultPipelines assembly
- pipelines, default
ms.assetid: 7d82bb2c-c7f1-44a1-9e1b-89b0bb806845
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a49e806bf8d38c7b2018f583e443589065be71a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389709"
---
# <a name="default-pipelines"></a><span data-ttu-id="cca5d-102">默认管道</span><span class="sxs-lookup"><span data-stu-id="cca5d-102">Default Pipelines</span></span>
<span data-ttu-id="cca5d-103">当您创建新的应用程序，默认管道创建和部署默认情况下，显示在中每个 BizTalk 项目的 \References 文件夹下的 Microsoft.BizTalk.DefaultPipelines 程序集。</span><span class="sxs-lookup"><span data-stu-id="cca5d-103">When you create a new application, the default pipelines are created and deployed by default and appear in the Microsoft.BizTalk.DefaultPipelines assembly in the \References folder for every BizTalk project.</span></span> <span data-ttu-id="cca5d-104">不能在管道设计器中修改默认管道。</span><span class="sxs-lookup"><span data-stu-id="cca5d-104">The default pipelines cannot be modified in Pipeline Designer.</span></span> <span data-ttu-id="cca5d-105">这些管道配置的发送端口时，可以选择，或接收位置在 BizTalk 浏览器。</span><span class="sxs-lookup"><span data-stu-id="cca5d-105">These pipelines can be selected when configuring a send port or receive location in BizTalk Explorer.</span></span> <span data-ttu-id="cca5d-106">本主题介绍默认管道以及何时使用它们。</span><span class="sxs-lookup"><span data-stu-id="cca5d-106">This topic describes the default pipelines and when to use them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cca5d-107">XML 接收管道和 XML 发送管道不支持大于 4gb 的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="cca5d-107">The XML receive and XML send pipelines do not support XML documents larger than 4 gigabytes.</span></span>  
  
## <a name="passthrureceive-pipeline"></a><span data-ttu-id="cca5d-108">PassThruReceive 管道</span><span class="sxs-lookup"><span data-stu-id="cca5d-108">PassThruReceive pipeline</span></span>  
 <span data-ttu-id="cca5d-109">直通接收管道不包含任何组件。</span><span class="sxs-lookup"><span data-stu-id="cca5d-109">The pass-through receive pipeline has no components.</span></span> <span data-ttu-id="cca5d-110">需要处理任何消息负载时，它用于简单直通方案。</span><span class="sxs-lookup"><span data-stu-id="cca5d-110">It is used for simple pass-through scenarios when no message payload processing is necessary.</span></span> <span data-ttu-id="cca5d-111">当源和目标的消息已知的并且需要对消息进行任何验证，编码或拆装时，通常使用此管道。</span><span class="sxs-lookup"><span data-stu-id="cca5d-111">This pipeline is generally used when the source and the destination of the message are known, and the message requires no validation, encoding, or disassembling.</span></span> <span data-ttu-id="cca5d-112">此管道通常与直通发送管道结合使用。</span><span class="sxs-lookup"><span data-stu-id="cca5d-112">This pipeline is commonly used in conjunction with the pass-through send pipeline.</span></span>  
  
 <span data-ttu-id="cca5d-113">因为它不包含拆装器，则无法将消息路由到业务流程使用直通接收管道。</span><span class="sxs-lookup"><span data-stu-id="cca5d-113">Because it does not contain a disassembler, the pass-through receive pipeline cannot be used to route messages to orchestrations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cca5d-114">直通接收管道不支持属性升级。</span><span class="sxs-lookup"><span data-stu-id="cca5d-114">The pass-through receive pipeline does not support property promotion.</span></span>  
  
## <a name="passthrutransmit-pipeline"></a><span data-ttu-id="cca5d-115">PassThruTransmit 管道</span><span class="sxs-lookup"><span data-stu-id="cca5d-115">PassThruTransmit pipeline</span></span>  
 <span data-ttu-id="cca5d-116">传递发送管道不包含任何组件。</span><span class="sxs-lookup"><span data-stu-id="cca5d-116">The pass-through-send pipeline has no components.</span></span> <span data-ttu-id="cca5d-117">将消息发送到目标之前需要处理任何文档时，通常使用此管道。</span><span class="sxs-lookup"><span data-stu-id="cca5d-117">This pipeline is generally used when no document processing is necessary before sending the message to a destination.</span></span>  
  
## <a name="xmlreceive-pipeline"></a><span data-ttu-id="cca5d-118">XMLReceive 管道</span><span class="sxs-lookup"><span data-stu-id="cca5d-118">XMLReceive pipeline</span></span>  
 <span data-ttu-id="cca5d-119">XML 接收管道包括以下阶段：</span><span class="sxs-lookup"><span data-stu-id="cca5d-119">The XML receive pipeline consists of the following stages:</span></span>  
  
-   <span data-ttu-id="cca5d-120">**解码。**</span><span class="sxs-lookup"><span data-stu-id="cca5d-120">**Decode.**</span></span> <span data-ttu-id="cca5d-121">Empty</span><span class="sxs-lookup"><span data-stu-id="cca5d-121">Empty</span></span>  
  
-   <span data-ttu-id="cca5d-122">**反汇编。**</span><span class="sxs-lookup"><span data-stu-id="cca5d-122">**Disassemble.**</span></span> <span data-ttu-id="cca5d-123">包含 XML 拆装器组件</span><span class="sxs-lookup"><span data-stu-id="cca5d-123">Contains the XML Disassembler component</span></span>  
  
-   <span data-ttu-id="cca5d-124">**验证。**</span><span class="sxs-lookup"><span data-stu-id="cca5d-124">**Validate.**</span></span> <span data-ttu-id="cca5d-125">Empty</span><span class="sxs-lookup"><span data-stu-id="cca5d-125">Empty</span></span>  
  
-   <span data-ttu-id="cca5d-126">**解析参与方。**</span><span class="sxs-lookup"><span data-stu-id="cca5d-126">**ResolveParty.**</span></span> <span data-ttu-id="cca5d-127">运行参与方解析组件，证书使用者或源安全 ID 解析为参与方 id。</span><span class="sxs-lookup"><span data-stu-id="cca5d-127">Runs the Party Resolution component, which resolves the certificate subject or the source security ID to the party ID.</span></span>  
  
## <a name="xmltransmit-pipeline"></a><span data-ttu-id="cca5d-128">XMLTransmit 管道</span><span class="sxs-lookup"><span data-stu-id="cca5d-128">XMLTransmit pipeline</span></span>  
 <span data-ttu-id="cca5d-129">XML 发送管道包括以下阶段：</span><span class="sxs-lookup"><span data-stu-id="cca5d-129">The XML send pipeline consists of the following stages:</span></span>  
  
-   <span data-ttu-id="cca5d-130">**预组装。**</span><span class="sxs-lookup"><span data-stu-id="cca5d-130">**Pre-assemble.**</span></span> <span data-ttu-id="cca5d-131">Empty</span><span class="sxs-lookup"><span data-stu-id="cca5d-131">Empty</span></span>  
  
-   <span data-ttu-id="cca5d-132">**组装。**</span><span class="sxs-lookup"><span data-stu-id="cca5d-132">**Assemble.**</span></span> <span data-ttu-id="cca5d-133">包含 XML 组装器组件</span><span class="sxs-lookup"><span data-stu-id="cca5d-133">Contains the XML Assembler component</span></span>  
  
-   <span data-ttu-id="cca5d-134">**对进行编码。**</span><span class="sxs-lookup"><span data-stu-id="cca5d-134">**Encode.**</span></span> <span data-ttu-id="cca5d-135">Empty</span><span class="sxs-lookup"><span data-stu-id="cca5d-135">Empty</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cca5d-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="cca5d-136">See Also</span></span>  
 <span data-ttu-id="cca5d-137">[类型的管道](../core/types-of-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="cca5d-137">[Types of Pipelines](../core/types-of-pipelines.md) </span></span>  
 <span data-ttu-id="cca5d-138">[类型的管道组件](../core/types-of-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="cca5d-138">[Types of Pipeline Components](../core/types-of-pipeline-components.md) </span></span>  
 <span data-ttu-id="cca5d-139">[管道模板](../core/pipeline-templates.md) </span><span class="sxs-lookup"><span data-stu-id="cca5d-139">[Pipeline Templates](../core/pipeline-templates.md) </span></span>  
 <span data-ttu-id="cca5d-140">[管道组件](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="cca5d-140">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 [<span data-ttu-id="cca5d-141">关于管道、阶段和组件</span><span class="sxs-lookup"><span data-stu-id="cca5d-141">About Pipelines, Stages, and Components</span></span>](../core/about-pipelines-stages-and-components.md)