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
ms.openlocfilehash: 2f9d0288defa0705c7e12f102011edbf9ee7e90d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984718"
---
# <a name="public-processes"></a><span data-ttu-id="7abe2-102">公用流程</span><span class="sxs-lookup"><span data-stu-id="7abe2-102">Public Processes</span></span>
<span data-ttu-id="7abe2-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]涉及与贸易合作伙伴作为公用过程集成的业务流程来实现。</span><span class="sxs-lookup"><span data-stu-id="7abe2-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] implements business processes that involve integration with trading partners as public processes.</span></span> <span data-ttu-id="7abe2-104">而将组织内部的业务流程作为专用流程来实现。</span><span class="sxs-lookup"><span data-stu-id="7abe2-104">It implements business processes that are internal to an organization as private processes.</span></span> <span data-ttu-id="7abe2-105">使用专用流程和公用流程可将 RosettaNet 实现框架 (RNIF) 处理（在公用流程中）与服务内容处理及后端集成（在专用流程中）分隔开来。</span><span class="sxs-lookup"><span data-stu-id="7abe2-105">Using public and private processes isolates RosettaNet Implementation Framework (RNIF) handling (in the public process) from the service content processing and back-end integration (in the private process).</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="7abe2-106"> 公用流程作为长期 BizTalk 业务流程来实现。</span><span class="sxs-lookup"><span data-stu-id="7abe2-106"> implements public processes as long-running BizTalk orchestrations.</span></span> <span data-ttu-id="7abe2-107">在发起方和响应方各会运行一个公用业务流程。</span><span class="sxs-lookup"><span data-stu-id="7abe2-107">One public-process orchestration runs on the initiator side and one on the responder side.</span></span> <span data-ttu-id="7abe2-108">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序提供了版本的发起方和响应方公用业务流程的 RNIF 1.1 和 RNIF 2.01。</span><span class="sxs-lookup"><span data-stu-id="7abe2-108">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program provides versions of the initiator and responder public-process orchestrations for both RNIF 1.1 and RNIF 2.01.</span></span>  
  
 <span data-ttu-id="7abe2-109">这些公用业务流程实现了所有的 RNIF 流程。</span><span class="sxs-lookup"><span data-stu-id="7abe2-109">These public-process orchestrations implement all RNIF processes.</span></span> <span data-ttu-id="7abe2-110">公用流程使 RNIF 对于其他组件来说变得相对简单了。</span><span class="sxs-lookup"><span data-stu-id="7abe2-110">Public processes hide the complexity of RNIF from the rest of the components.</span></span> <span data-ttu-id="7abe2-111">除了执行与 RNIF 兼容的消息流之外，公用流程还确定默认跟踪设置并在运行时提供流程状态信息。</span><span class="sxs-lookup"><span data-stu-id="7abe2-111">Besides enforcing the RNIF-compliant message flow, the public process also determines default-tracking settings and provides process state information at run time.</span></span> <span data-ttu-id="7abe2-112">它并不处理消息的服务内容。</span><span class="sxs-lookup"><span data-stu-id="7abe2-112">It does not process the service content of a message.</span></span> <span data-ttu-id="7abe2-113">这由专用流程来处理。</span><span class="sxs-lookup"><span data-stu-id="7abe2-113">The private process does this.</span></span>  
  
 <span data-ttu-id="7abe2-114">每个贸易合作伙伴协议都引用一个单一的公用流程，以便发起或响应合作伙伴接口流程 (PIP) 操作。</span><span class="sxs-lookup"><span data-stu-id="7abe2-114">Each trading partner agreement references a single public process to initiate or respond to Partner Interface Process (PIP) actions.</span></span> <span data-ttu-id="7abe2-115">然而，公用流程是 PIP 不可知的。</span><span class="sxs-lookup"><span data-stu-id="7abe2-115">However, the public processes are PIP-agnostic.</span></span>  
  
 <span data-ttu-id="7abe2-116">RosettaNet 规范对公用流程的设计进行了规定。</span><span class="sxs-lookup"><span data-stu-id="7abe2-116">The RosettaNet specifications dictate the design of the public process.</span></span> <span data-ttu-id="7abe2-117">建议您不要修改公用流程。</span><span class="sxs-lookup"><span data-stu-id="7abe2-117">It is recommended that you do not modify a public process.</span></span> <span data-ttu-id="7abe2-118">公用业务流程是版本化的，且经过签名。</span><span class="sxs-lookup"><span data-stu-id="7abe2-118">The public-process orchestration is versioned and signed.</span></span> <span data-ttu-id="7abe2-119">如果您修改了公用流程，它将不再兼容 RNIF。</span><span class="sxs-lookup"><span data-stu-id="7abe2-119">If you modify a public process, it will no longer be RNIF-compliant.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7abe2-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="7abe2-120">In This Section</span></span>  
  
-   [<span data-ttu-id="7abe2-121">发起方公用流程</span><span class="sxs-lookup"><span data-stu-id="7abe2-121">Initiator Public Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md)  
  
-   [<span data-ttu-id="7abe2-122">响应方公用流程</span><span class="sxs-lookup"><span data-stu-id="7abe2-122">Responder Public Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/responder-public-process.md)