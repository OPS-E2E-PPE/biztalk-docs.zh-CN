---
title: "默认管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ceb3f06f2e2b57ec37bc4a95a385574de594940
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="default-pipelines"></a><span data-ttu-id="b2161-102">默认管道</span><span class="sxs-lookup"><span data-stu-id="b2161-102">Default Pipelines</span></span>
<span data-ttu-id="b2161-103">默认情况下，在创建新应用程序时将创建和部署默认管道。这些管道将显示在每个 BizTalk 项目的 \References 文件夹下的 Microsoft.BizTalk.DefaultPipelines 程序集中。</span><span class="sxs-lookup"><span data-stu-id="b2161-103">When you create a new application, the default pipelines are created and deployed by default and appear in the Microsoft.BizTalk.DefaultPipelines assembly in the \References folder for every BizTalk project.</span></span> <span data-ttu-id="b2161-104">在管道设计器中不能修改默认管道。</span><span class="sxs-lookup"><span data-stu-id="b2161-104">The default pipelines cannot be modified in Pipeline Designer.</span></span> <span data-ttu-id="b2161-105">在 BizTalk 浏览器中配置发送端口或接收位置时，可以选择这些管道。</span><span class="sxs-lookup"><span data-stu-id="b2161-105">These pipelines can be selected when configuring a send port or receive location in BizTalk Explorer.</span></span> <span data-ttu-id="b2161-106">本主题对这些默认管道以及何时使用这些管道进行了说明。</span><span class="sxs-lookup"><span data-stu-id="b2161-106">This topic describes the default pipelines and when to use them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2161-107">XML 接收管道和 XML 发送管道不支持大于 4GB 的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="b2161-107">The XML receive and XML send pipelines do not support XML documents larger than 4 gigabytes.</span></span>  
  
## <a name="passthrureceive-pipeline"></a><span data-ttu-id="b2161-108">PassThruReceive 管道</span><span class="sxs-lookup"><span data-stu-id="b2161-108">PassThruReceive pipeline</span></span>  
 <span data-ttu-id="b2161-109">直通接收管道不包含任何组件。</span><span class="sxs-lookup"><span data-stu-id="b2161-109">The pass-through receive pipeline has no components.</span></span> <span data-ttu-id="b2161-110">该管道用于不需要处理任何消息负载的简单直通方案。</span><span class="sxs-lookup"><span data-stu-id="b2161-110">It is used for simple pass-through scenarios when no message payload processing is necessary.</span></span> <span data-ttu-id="b2161-111">在消息的源和目标已知，并且不需对消息进行验证、编码或拆装时，通常使用此管道。</span><span class="sxs-lookup"><span data-stu-id="b2161-111">This pipeline is generally used when the source and the destination of the message are known, and the message requires no validation, encoding, or disassembling.</span></span> <span data-ttu-id="b2161-112">此管道通常与直通发送管道一起使用。</span><span class="sxs-lookup"><span data-stu-id="b2161-112">This pipeline is commonly used in conjunction with the pass-through send pipeline.</span></span>  
  
 <span data-ttu-id="b2161-113">由于直通接收管道不包含拆装器，因此不能用于向业务流程路由消息。</span><span class="sxs-lookup"><span data-stu-id="b2161-113">Because it does not contain a disassembler, the pass-through receive pipeline cannot be used to route messages to orchestrations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2161-114">直通接收管道不支持属性升级。</span><span class="sxs-lookup"><span data-stu-id="b2161-114">The pass-through receive pipeline does not support property promotion.</span></span>  
  
## <a name="passthrutransmit-pipeline"></a><span data-ttu-id="b2161-115">PassThruTransmit 管道</span><span class="sxs-lookup"><span data-stu-id="b2161-115">PassThruTransmit pipeline</span></span>  
 <span data-ttu-id="b2161-116">直通发送管道不包含任何组件。</span><span class="sxs-lookup"><span data-stu-id="b2161-116">The pass-through-send pipeline has no components.</span></span> <span data-ttu-id="b2161-117">如果向目标发送消息前不需处理任何文档，则通常使用此管道。</span><span class="sxs-lookup"><span data-stu-id="b2161-117">This pipeline is generally used when no document processing is necessary before sending the message to a destination.</span></span>  
  
## <a name="xmlreceive-pipeline"></a><span data-ttu-id="b2161-118">XMLReceive 管道</span><span class="sxs-lookup"><span data-stu-id="b2161-118">XMLReceive pipeline</span></span>  
 <span data-ttu-id="b2161-119">XML 接收管道包括以下阶段：</span><span class="sxs-lookup"><span data-stu-id="b2161-119">The XML receive pipeline consists of the following stages:</span></span>  
  
-   <span data-ttu-id="b2161-120">**解码。**</span><span class="sxs-lookup"><span data-stu-id="b2161-120">**Decode.**</span></span> <span data-ttu-id="b2161-121">Empty</span><span class="sxs-lookup"><span data-stu-id="b2161-121">Empty</span></span>  
  
-   <span data-ttu-id="b2161-122">**反汇编。**</span><span class="sxs-lookup"><span data-stu-id="b2161-122">**Disassemble.**</span></span> <span data-ttu-id="b2161-123">包含 XML 拆装器组件</span><span class="sxs-lookup"><span data-stu-id="b2161-123">Contains the XML Disassembler component</span></span>  
  
-   <span data-ttu-id="b2161-124">**验证。**</span><span class="sxs-lookup"><span data-stu-id="b2161-124">**Validate.**</span></span> <span data-ttu-id="b2161-125">Empty</span><span class="sxs-lookup"><span data-stu-id="b2161-125">Empty</span></span>  
  
-   <span data-ttu-id="b2161-126">**ResolveParty。**</span><span class="sxs-lookup"><span data-stu-id="b2161-126">**ResolveParty.**</span></span> <span data-ttu-id="b2161-127">运行参与方解析组件，该组件可以将证书主题或源安全 ID 解析为参与方 ID。</span><span class="sxs-lookup"><span data-stu-id="b2161-127">Runs the Party Resolution component, which resolves the certificate subject or the source security ID to the party ID.</span></span>  
  
## <a name="xmltransmit-pipeline"></a><span data-ttu-id="b2161-128">XMLTransmit 管道</span><span class="sxs-lookup"><span data-stu-id="b2161-128">XMLTransmit pipeline</span></span>  
 <span data-ttu-id="b2161-129">XML 发送管道包括以下阶段：</span><span class="sxs-lookup"><span data-stu-id="b2161-129">The XML send pipeline consists of the following stages:</span></span>  
  
-   <span data-ttu-id="b2161-130">**预先组建。**</span><span class="sxs-lookup"><span data-stu-id="b2161-130">**Pre-assemble.**</span></span> <span data-ttu-id="b2161-131">Empty</span><span class="sxs-lookup"><span data-stu-id="b2161-131">Empty</span></span>  
  
-   <span data-ttu-id="b2161-132">**组建。**</span><span class="sxs-lookup"><span data-stu-id="b2161-132">**Assemble.**</span></span> <span data-ttu-id="b2161-133">包含 XML 组装器组件</span><span class="sxs-lookup"><span data-stu-id="b2161-133">Contains the XML Assembler component</span></span>  
  
-   <span data-ttu-id="b2161-134">**编码。**</span><span class="sxs-lookup"><span data-stu-id="b2161-134">**Encode.**</span></span> <span data-ttu-id="b2161-135">Empty</span><span class="sxs-lookup"><span data-stu-id="b2161-135">Empty</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2161-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2161-136">See Also</span></span>  
 <span data-ttu-id="b2161-137">[类型的管道](../core/types-of-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="b2161-137">[Types of Pipelines](../core/types-of-pipelines.md) </span></span>  
 <span data-ttu-id="b2161-138">[类型的管道组件](../core/types-of-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="b2161-138">[Types of Pipeline Components](../core/types-of-pipeline-components.md) </span></span>  
 <span data-ttu-id="b2161-139">[管道模板](../core/pipeline-templates.md) </span><span class="sxs-lookup"><span data-stu-id="b2161-139">[Pipeline Templates](../core/pipeline-templates.md) </span></span>  
 <span data-ttu-id="b2161-140">[管道组件](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="b2161-140">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 [<span data-ttu-id="b2161-141">有关管道、 阶段和组件</span><span class="sxs-lookup"><span data-stu-id="b2161-141">About Pipelines, Stages, and Components</span></span>](../core/about-pipelines-stages-and-components.md)