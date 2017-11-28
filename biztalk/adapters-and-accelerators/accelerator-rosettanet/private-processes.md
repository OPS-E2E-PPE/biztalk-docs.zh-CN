---
title: "私有进程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private processes, trading partners
- private processes, about private processes
- private processes, orchestrations
- private processes
- orchestrations, private-process orchestrations
- trading partners, private processes
- BTARN, private processes
- business processes, private processes
ms.assetid: 0c5895eb-22c1-431f-a769-ae6ca05d1e45
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b28bf49af1305220d96f129080b274b5391495eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="private-processes"></a><span data-ttu-id="e2157-102">私有进程</span><span class="sxs-lookup"><span data-stu-id="e2157-102">Private Processes</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="e2157-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]实现都是作为私有进程组织内部的业务流程。</span><span class="sxs-lookup"><span data-stu-id="e2157-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] implements business processes that are internal to an organization as private processes.</span></span> <span data-ttu-id="e2157-104">公共进程处理涉及与贸易合作伙伴集成的业务流程。</span><span class="sxs-lookup"><span data-stu-id="e2157-104">Public processes handle business processes that involve integration with trading partners.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="e2157-105">隔离服务内容处理中的和后端集成 （专用的过程中） 从 RosettaNet 实现框架 (RNIF) （公共在进程中） 处理。</span><span class="sxs-lookup"><span data-stu-id="e2157-105"> isolates service-content processing and back-end integration (in the private process) from RosettaNet Implementation Framework (RNIF) handling (in the public process).</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="e2157-106">实现私有进程作为长时间运行 BizTalk 业务流程。</span><span class="sxs-lookup"><span data-stu-id="e2157-106"> implements private processes as long-running BizTalk orchestrations.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="e2157-107">在发起方端，另一个在响应方端使用一个私有进程业务流程。</span><span class="sxs-lookup"><span data-stu-id="e2157-107"> uses one private-process orchestration on the initiator side and one on the responder side.</span></span> <span data-ttu-id="e2157-108">每个专用流程解释并处理服务内容的消息部分，包括传入消息和传出消息。</span><span class="sxs-lookup"><span data-stu-id="e2157-108">Each private process interprets and processes the service-content message part, either incoming or outgoing.</span></span> <span data-ttu-id="e2157-109">专用流程将服务内容发送给公用流程，或从公用流程接收服务内容。</span><span class="sxs-lookup"><span data-stu-id="e2157-109">The private process sends the service content to, or receives it from, the public process.</span></span> <span data-ttu-id="e2157-110">专用流程不处理头，也不执行 RNIF 处理。</span><span class="sxs-lookup"><span data-stu-id="e2157-110">A private process does not handle headers, and does not perform RNIF processing.</span></span> <span data-ttu-id="e2157-111">这两种处理均由公用流程执行。</span><span class="sxs-lookup"><span data-stu-id="e2157-111">It leaves that to the public process.</span></span>  
  
 <span data-ttu-id="e2157-112">在企业方案中，每个 PIP 消息架构通常只有一个专用流程。</span><span class="sxs-lookup"><span data-stu-id="e2157-112">In an enterprise scenario, there would typically be one private process for each PIP message schema.</span></span> <span data-ttu-id="e2157-113">但是，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包括两个专用业务流程，可以处理任何 PIP 消息。</span><span class="sxs-lookup"><span data-stu-id="e2157-113">However, the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes two private-process orchestrations that can process any PIP message.</span></span> <span data-ttu-id="e2157-114">为发起程序的进程是一个业务流程 (PrivateInitiator.odx，请参阅[PrivateInitiator 示例 &#91;RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)) 和响应方过程有一个是 (PrivateResponder.odx，请参阅[PrivateResponder 示例 &#91;RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)).</span><span class="sxs-lookup"><span data-stu-id="e2157-114">One orchestration is for the initiator process (PrivateInitiator.odx, see [PrivateInitiator Sample &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)) and one is for the responder process (PrivateResponder.odx, see [PrivateResponder Sample &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)).</span></span> <span data-ttu-id="e2157-115">您必须自定义专用流程，使 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 适合您的特定业务流程。</span><span class="sxs-lookup"><span data-stu-id="e2157-115">You will have to customize the private processes to adapt [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] to your specific business processes.</span></span>  
  
 <span data-ttu-id="e2157-116">SDK 还包括实现合并业务规则的 PIP 特定私有响应方进程的进程 (PIP3A4PrivateResponder.odx，请参阅[3A4 私有响应方业务流程使用业务规则](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md))。</span><span class="sxs-lookup"><span data-stu-id="e2157-116">The SDK also includes a process that implements a PIP-specific private responder process incorporating a business rule (PIP3A4PrivateResponder.odx, see [3A4 Private Responder Orchestration Using a Business Rule](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)).</span></span>  
  
 <span data-ttu-id="e2157-117">专用流程将服务内容的格式由后端业务线 (LOB) 格式更改为 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="e2157-117">The private process changes the format of the service content from the back-end line-of-business (LOB) format to XML.</span></span> <span data-ttu-id="e2157-118">一旦服务内容更改为 XML 格式，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 就对其进行处理，而公用流程会将符合 RNIF 的头添加到服务内容中进行传输。</span><span class="sxs-lookup"><span data-stu-id="e2157-118">As soon as it is in XML format, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] processes the service content, and the public process adds RNIF-compliant headers to the service content for transmission.</span></span>  
  
 <span data-ttu-id="e2157-119">专用流程通过 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 数据库中的 MessageToLOB 表和 MessagesFromLOB 表连接到后端业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="e2157-119">The private process connects to the back-end line-of-business applications through the MessageToLOB and MessagesFromLOB tables in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database.</span></span> <span data-ttu-id="e2157-120">此数据库处理 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 和 LOB 应用程序之间的通信。</span><span class="sxs-lookup"><span data-stu-id="e2157-120">This database handles the communication between [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] and the LOB applications.</span></span> <span data-ttu-id="e2157-121">LOB 应用程序使用接口来访问数据库表。</span><span class="sxs-lookup"><span data-stu-id="e2157-121">The LOB application uses an interface to gain access to the database tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e2157-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="e2157-122">In This Section</span></span>  
  
-   [<span data-ttu-id="e2157-123">发起方私有过程</span><span class="sxs-lookup"><span data-stu-id="e2157-123">Initiator Private Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)  
  
-   [<span data-ttu-id="e2157-124">响应方私有过程</span><span class="sxs-lookup"><span data-stu-id="e2157-124">Responder Private Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)