---
title: Microsoft.BizTalk.DefaultPipelines 引用 |Microsoft Docs
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
ms.openlocfilehash: a183aa499b5acb56813fcb0433d2fd57258a777d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324843"
---
# <a name="microsoftbiztalkdefaultpipelines-reference"></a><span data-ttu-id="e5e29-102">Microsoft.BizTalk.DefaultPipelines Reference</span><span class="sxs-lookup"><span data-stu-id="e5e29-102">Microsoft.BizTalk.DefaultPipelines Reference</span></span>
<span data-ttu-id="e5e29-103">**Microsoft.BizTalk.DefaultPipelines**命名空间包含以下管道：</span><span class="sxs-lookup"><span data-stu-id="e5e29-103">The **Microsoft.BizTalk.DefaultPipelines** namespace contains the following pipelines:</span></span>  
  
- <span data-ttu-id="e5e29-104">XMLReceive</span><span class="sxs-lookup"><span data-stu-id="e5e29-104">XMLReceive</span></span>  
  
- <span data-ttu-id="e5e29-105">PassThruReceive</span><span class="sxs-lookup"><span data-stu-id="e5e29-105">PassThruReceive</span></span>  
  
- <span data-ttu-id="e5e29-106">XMLTransmit</span><span class="sxs-lookup"><span data-stu-id="e5e29-106">XMLTransmit</span></span>  
  
- <span data-ttu-id="e5e29-107">PassThruTransmit</span><span class="sxs-lookup"><span data-stu-id="e5e29-107">PassThruTransmit</span></span>  
  
  <span data-ttu-id="e5e29-108">管道是一个软件组件，用于定义和链接一个或多个阶段的处理的消息接收或发送的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e5e29-108">A pipeline is a software component that defines and links one or more stages for processing messages received or sent by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="e5e29-109">阶段包括诸如编码或解码、 拆装或组装和解密或加密。</span><span class="sxs-lookup"><span data-stu-id="e5e29-109">The stages include functions such as encoding or decoding, disassembling or assembling, and decrypting or encrypting.</span></span> <span data-ttu-id="e5e29-110">这些函数的实现特定的顺序。</span><span class="sxs-lookup"><span data-stu-id="e5e29-110">These functions are implemented in a specific order.</span></span> <span data-ttu-id="e5e29-111">可以使用管道设计器创建接收和发送管道。</span><span class="sxs-lookup"><span data-stu-id="e5e29-111">You can use Pipeline Designer to create receive and send pipelines.</span></span>  
  
  <span data-ttu-id="e5e29-112">BizTalk 项目中包含的默认管道引用可以处理所有类型的文档使用**PassThruReceive**并**PassThruTransmit**管道。</span><span class="sxs-lookup"><span data-stu-id="e5e29-112">The default pipeline references included in a BizTalk project can process all types of documents using the **PassThruReceive** and **PassThruTransmit** pipelines.</span></span>  
  
  <span data-ttu-id="e5e29-113">以下列表显示了各默认管道中的默认组件。</span><span class="sxs-lookup"><span data-stu-id="e5e29-113">The following lists show the default components in the default pipelines.</span></span> <span data-ttu-id="e5e29-114">其中还指示了每个管道中的组件的默认顺序。</span><span class="sxs-lookup"><span data-stu-id="e5e29-114">These lists also indicate the default order of the components in each pipeline.</span></span> <span data-ttu-id="e5e29-115">可以添加和删除组件，如有必要。</span><span class="sxs-lookup"><span data-stu-id="e5e29-115">You can add and delete components if necessary.</span></span>  
  
  <span data-ttu-id="e5e29-116">默认 XMLReceive 管道中的默认组件包括：</span><span class="sxs-lookup"><span data-stu-id="e5e29-116">The default components in the default XMLReceive pipeline are:</span></span>  
  
- <span data-ttu-id="e5e29-117">解密器</span><span class="sxs-lookup"><span data-stu-id="e5e29-117">Decrypter</span></span>  
  
- <span data-ttu-id="e5e29-118">解码器</span><span class="sxs-lookup"><span data-stu-id="e5e29-118">Decoder</span></span>  
  
- <span data-ttu-id="e5e29-119">拆装器</span><span class="sxs-lookup"><span data-stu-id="e5e29-119">Disassembler</span></span>  
  
- <span data-ttu-id="e5e29-120">验证程序</span><span class="sxs-lookup"><span data-stu-id="e5e29-120">Validator</span></span>  
  
- <span data-ttu-id="e5e29-121">参与方解析</span><span class="sxs-lookup"><span data-stu-id="e5e29-121">Party Resolution</span></span>  
  
  <span data-ttu-id="e5e29-122">默认 XMLTransmit 管道中的默认组件包括：</span><span class="sxs-lookup"><span data-stu-id="e5e29-122">The default components in the default XMLTransmit pipeline are:</span></span>  
  
- <span data-ttu-id="e5e29-123">组装器</span><span class="sxs-lookup"><span data-stu-id="e5e29-123">Assembler</span></span>  
  
- <span data-ttu-id="e5e29-124">编码器</span><span class="sxs-lookup"><span data-stu-id="e5e29-124">Encoder</span></span>  
  
- <span data-ttu-id="e5e29-125">那样</span><span class="sxs-lookup"><span data-stu-id="e5e29-125">Encrypter</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5e29-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5e29-126">See Also</span></span>  
 <span data-ttu-id="e5e29-127">[使用管道设计器创建管道](../core/creating-pipelines-using-pipeline-designer.md) </span><span class="sxs-lookup"><span data-stu-id="e5e29-127">[Creating Pipelines Using Pipeline Designer](../core/creating-pipelines-using-pipeline-designer.md) </span></span>  
 [<span data-ttu-id="e5e29-128">关于 BizTalk 项目中包含的 BizTalk 命名空间引用</span><span class="sxs-lookup"><span data-stu-id="e5e29-128">About BizTalk Namespace References Included in BizTalk Projects</span></span>](../core/about-biztalk-namespace-references-included-in-biztalk-projects.md)