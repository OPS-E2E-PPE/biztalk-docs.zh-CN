---
title: 公用流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public processes, orchestrations
- business processes, public processes
- public processes, trading partners
- BTARN, public processes
- orchestrations, public-process orchestrations
- public processes
- trading partners, public processes
- public processes, about public processes
ms.assetid: 5ccc7449-5741-4d49-beb6-567bcd93f679
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 426884dd700ad5b7862b5c191339b8ca49388232
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282608"
---
# <a name="public-processes"></a><span data-ttu-id="b025e-102">公用流程</span><span class="sxs-lookup"><span data-stu-id="b025e-102">Public Processes</span></span>
<span data-ttu-id="b025e-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]涉及与贸易合作伙伴作为公用过程集成的业务流程来实现。</span><span class="sxs-lookup"><span data-stu-id="b025e-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] implements business processes that involve integration with trading partners as public processes.</span></span> <span data-ttu-id="b025e-104">它实现作为专用流程将组织内部的业务流程。</span><span class="sxs-lookup"><span data-stu-id="b025e-104">It implements business processes that are internal to an organization as private processes.</span></span> <span data-ttu-id="b025e-105">使用公共和专用流程将服务内容处理及后端集成 （在专用流程中） 与隔离开来 RosettaNet 实现框架 (RNIF) 处理 （在公用流程）。</span><span class="sxs-lookup"><span data-stu-id="b025e-105">Using public and private processes isolates RosettaNet Implementation Framework (RNIF) handling (in the public process) from the service content processing and back-end integration (in the private process).</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="b025e-106">公用流程作为长期 BizTalk 业务流程来实现。</span><span class="sxs-lookup"><span data-stu-id="b025e-106">implements public processes as long-running BizTalk orchestrations.</span></span> <span data-ttu-id="b025e-107">一个公用业务流程在发起方和响应方各上运行。</span><span class="sxs-lookup"><span data-stu-id="b025e-107">One public-process orchestration runs on the initiator side and one on the responder side.</span></span> <span data-ttu-id="b025e-108">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序提供了版本的发起方和响应方公用业务流程的 RNIF 1.1 和 RNIF 2.01。</span><span class="sxs-lookup"><span data-stu-id="b025e-108">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program provides versions of the initiator and responder public-process orchestrations for both RNIF 1.1 and RNIF 2.01.</span></span>  
  
 <span data-ttu-id="b025e-109">这些公用业务流程实现所有的 RNIF 流程。</span><span class="sxs-lookup"><span data-stu-id="b025e-109">These public-process orchestrations implement all RNIF processes.</span></span> <span data-ttu-id="b025e-110">公用流程使 RNIF 从其他组件的复杂性。</span><span class="sxs-lookup"><span data-stu-id="b025e-110">Public processes hide the complexity of RNIF from the rest of the components.</span></span> <span data-ttu-id="b025e-111">除了强制实施符合 RNIF 消息流，则公用流程还确定默认跟踪设置，并提供在运行时进程状态信息。</span><span class="sxs-lookup"><span data-stu-id="b025e-111">Besides enforcing the RNIF-compliant message flow, the public process also determines default-tracking settings and provides process state information at run time.</span></span> <span data-ttu-id="b025e-112">它不会处理一条消息的服务内容。</span><span class="sxs-lookup"><span data-stu-id="b025e-112">It does not process the service content of a message.</span></span> <span data-ttu-id="b025e-113">专用流程执行此操作。</span><span class="sxs-lookup"><span data-stu-id="b025e-113">The private process does this.</span></span>  
  
 <span data-ttu-id="b025e-114">每个贸易合作伙伴协议引用单个公用流程，以便发起或响应合作伙伴接口流程 (PIP) 操作。</span><span class="sxs-lookup"><span data-stu-id="b025e-114">Each trading partner agreement references a single public process to initiate or respond to Partner Interface Process (PIP) actions.</span></span> <span data-ttu-id="b025e-115">但是，公用流程是 PIP 不可知。</span><span class="sxs-lookup"><span data-stu-id="b025e-115">However, the public processes are PIP-agnostic.</span></span>  
  
 <span data-ttu-id="b025e-116">RosettaNet 规范对公用流程的设计进行了规定。</span><span class="sxs-lookup"><span data-stu-id="b025e-116">The RosettaNet specifications dictate the design of the public process.</span></span> <span data-ttu-id="b025e-117">建议您不要修改公用流程。</span><span class="sxs-lookup"><span data-stu-id="b025e-117">It is recommended that you do not modify a public process.</span></span> <span data-ttu-id="b025e-118">公用业务流程是版本控制和签名。</span><span class="sxs-lookup"><span data-stu-id="b025e-118">The public-process orchestration is versioned and signed.</span></span> <span data-ttu-id="b025e-119">如果您修改公用流程，它将不再符合 RNIF 的。</span><span class="sxs-lookup"><span data-stu-id="b025e-119">If you modify a public process, it will no longer be RNIF-compliant.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b025e-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="b025e-120">In This Section</span></span>  
  
-   [<span data-ttu-id="b025e-121">发起方公用流程</span><span class="sxs-lookup"><span data-stu-id="b025e-121">Initiator Public Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md)  
  
-   [<span data-ttu-id="b025e-122">响应方公用流程</span><span class="sxs-lookup"><span data-stu-id="b025e-122">Responder Public Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/responder-public-process.md)