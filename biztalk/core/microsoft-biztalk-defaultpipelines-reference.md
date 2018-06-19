---
title: Microsoft.BizTalk.DefaultPipelines 引用 |Microsoft 文档
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
- pipelines
- PassThruTransmit pipelines
- XMLReceive pipelines
- pipelines, XMLTransmit
- Pipeline Designer
- pipelines, XMLReceive
- pipelines, about pipelines
- PassThruReceive pipelines
- XMLTransmit pipelines
- namespaces, Microsoft.BizTalk.DefaultPipelines namespace
- Microsoft.BizTalk.DefaultPipelines namespace
ms.assetid: a54f8813-9c6f-4afe-8c76-2db3fa478947
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ad7cad78e3e8606371a5fa49673297cf590ddbe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263405"
---
# <a name="microsoftbiztalkdefaultpipelines-reference"></a><span data-ttu-id="88236-102">Microsoft.BizTalk.DefaultPipelines 引用</span><span class="sxs-lookup"><span data-stu-id="88236-102">Microsoft.BizTalk.DefaultPipelines Reference</span></span>
<span data-ttu-id="88236-103">**Microsoft.BizTalk.DefaultPipelines**命名空间包含以下管道：</span><span class="sxs-lookup"><span data-stu-id="88236-103">The **Microsoft.BizTalk.DefaultPipelines** namespace contains the following pipelines:</span></span>  
  
-   <span data-ttu-id="88236-104">XMLReceive</span><span class="sxs-lookup"><span data-stu-id="88236-104">XMLReceive</span></span>  
  
-   <span data-ttu-id="88236-105">PassThruReceive</span><span class="sxs-lookup"><span data-stu-id="88236-105">PassThruReceive</span></span>  
  
-   <span data-ttu-id="88236-106">XMLTransmit</span><span class="sxs-lookup"><span data-stu-id="88236-106">XMLTransmit</span></span>  
  
-   <span data-ttu-id="88236-107">PassThruTransmit</span><span class="sxs-lookup"><span data-stu-id="88236-107">PassThruTransmit</span></span>  
  
 <span data-ttu-id="88236-108">管道是一个软件组件，用于定义并链接一个或多个阶段，处理消息接收或发送[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="88236-108">A pipeline is a software component that defines and links one or more stages for processing messages received or sent by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="88236-109">这些阶段包括诸如编码或解码、拆装或组装、解密或加密这类功能。</span><span class="sxs-lookup"><span data-stu-id="88236-109">The stages include functions such as encoding or decoding, disassembling or assembling, and decrypting or encrypting.</span></span> <span data-ttu-id="88236-110">这些功能是按特定顺序实现的。</span><span class="sxs-lookup"><span data-stu-id="88236-110">These functions are implemented in a specific order.</span></span> <span data-ttu-id="88236-111">可以使用管道设计器来创建接收管道和发送管道。</span><span class="sxs-lookup"><span data-stu-id="88236-111">You can use Pipeline Designer to create receive and send pipelines.</span></span>  
  
 <span data-ttu-id="88236-112">包含在 BizTalk 项目的默认管道引用可以处理所有类型的文档使用**PassThruReceive**和**PassThruTransmit**管道。</span><span class="sxs-lookup"><span data-stu-id="88236-112">The default pipeline references included in a BizTalk project can process all types of documents using the **PassThruReceive** and **PassThruTransmit** pipelines.</span></span>  
  
 <span data-ttu-id="88236-113">下面分别列出了各默认管道中的默认组件。</span><span class="sxs-lookup"><span data-stu-id="88236-113">The following lists show the default components in the default pipelines.</span></span> <span data-ttu-id="88236-114">其中还指示了每个管道中组件的默认顺序。</span><span class="sxs-lookup"><span data-stu-id="88236-114">These lists also indicate the default order of the components in each pipeline.</span></span> <span data-ttu-id="88236-115">如有必要，可以添加和删除组件。</span><span class="sxs-lookup"><span data-stu-id="88236-115">You can add and delete components if necessary.</span></span>  
  
 <span data-ttu-id="88236-116">默认 XMLReceive 管道中的默认组件包括：</span><span class="sxs-lookup"><span data-stu-id="88236-116">The default components in the default XMLReceive pipeline are:</span></span>  
  
-   <span data-ttu-id="88236-117">解密器</span><span class="sxs-lookup"><span data-stu-id="88236-117">Decrypter</span></span>  
  
-   <span data-ttu-id="88236-118">解码器</span><span class="sxs-lookup"><span data-stu-id="88236-118">Decoder</span></span>  
  
-   <span data-ttu-id="88236-119">拆装器</span><span class="sxs-lookup"><span data-stu-id="88236-119">Disassembler</span></span>  
  
-   <span data-ttu-id="88236-120">验证程序</span><span class="sxs-lookup"><span data-stu-id="88236-120">Validator</span></span>  
  
-   <span data-ttu-id="88236-121">参与方解析</span><span class="sxs-lookup"><span data-stu-id="88236-121">Party Resolution</span></span>  
  
 <span data-ttu-id="88236-122">默认 XMLTransmit 管道中的默认组件包括：</span><span class="sxs-lookup"><span data-stu-id="88236-122">The default components in the default XMLTransmit pipeline are:</span></span>  
  
-   <span data-ttu-id="88236-123">组装器</span><span class="sxs-lookup"><span data-stu-id="88236-123">Assembler</span></span>  
  
-   <span data-ttu-id="88236-124">编码器</span><span class="sxs-lookup"><span data-stu-id="88236-124">Encoder</span></span>  
  
-   <span data-ttu-id="88236-125">加密器</span><span class="sxs-lookup"><span data-stu-id="88236-125">Encrypter</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88236-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88236-126">See Also</span></span>  
 <span data-ttu-id="88236-127">[创建管道使用管道设计器](../core/creating-pipelines-using-pipeline-designer.md) </span><span class="sxs-lookup"><span data-stu-id="88236-127">[Creating Pipelines Using Pipeline Designer](../core/creating-pipelines-using-pipeline-designer.md) </span></span>  
 [<span data-ttu-id="88236-128">有关 BizTalk 项目中包含的 BizTalk Namespace 引用</span><span class="sxs-lookup"><span data-stu-id="88236-128">About BizTalk Namespace References Included in BizTalk Projects</span></span>](../core/about-biztalk-namespace-references-included-in-biztalk-projects.md)