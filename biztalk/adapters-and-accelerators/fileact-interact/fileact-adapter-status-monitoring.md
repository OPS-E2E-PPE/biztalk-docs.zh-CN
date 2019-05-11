---
title: FileAct 适配器状态监视 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 15833004-4276-4975-a0e7-8fff3c82576b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1701e68b592e7f6eab012d14b1a14d6143c09da9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367158"
---
# <a name="fileact-adapter-status-monitoring"></a><span data-ttu-id="424b3-102">FileAct 适配器状态监视</span><span class="sxs-lookup"><span data-stu-id="424b3-102">FileAct Adapter Status Monitoring</span></span>
<span data-ttu-id="424b3-103">下图显示了文件传输和这些状态之间的转换的可能状态。</span><span class="sxs-lookup"><span data-stu-id="424b3-103">The possible states of a file transfer and the transitions between those states are illustrated in the following figure.</span></span>  
  
 <span data-ttu-id="424b3-104">![FileAct 适配器文件传输状态](../../adapters-and-accelerators/fileact-interact/media/2e01feaa-6b68-49a2-a47d-6359be1f4034.gif "2e01feaa-6b68-49a2-a47d-6359be1f4034")</span><span class="sxs-lookup"><span data-stu-id="424b3-104">![FileAct adapter file transfer states](../../adapters-and-accelerators/fileact-interact/media/2e01feaa-6b68-49a2-a47d-6359be1f4034.gif "2e01feaa-6b68-49a2-a47d-6359be1f4034")</span></span>  
  
 <span data-ttu-id="424b3-105">文件传输状态如下：</span><span class="sxs-lookup"><span data-stu-id="424b3-105">The file transfer states are:</span></span>  
  
-   <span data-ttu-id="424b3-106">**启动**– 客户端已协商信息发送到服务器，但未收到响应。</span><span class="sxs-lookup"><span data-stu-id="424b3-106">**Initiated** – The client has sent the negotiation message to the server, but has not yet received the response.</span></span> <span data-ttu-id="424b3-107">服务器已收到协商请求，但不是发送响应。</span><span class="sxs-lookup"><span data-stu-id="424b3-107">The server has received the negotiation request, but has not yet sent the response.</span></span>  
  
-   <span data-ttu-id="424b3-108">**接受**– 服务器已接受请求和响应消息中发送 TransferAnswer，传输是仍在进行中。</span><span class="sxs-lookup"><span data-stu-id="424b3-108">**Accepted** – The server has accepted the request and has sent the TransferAnswer in the response message, and the transfer is still in progress.</span></span>  
  
-   <span data-ttu-id="424b3-109">**拒绝**– 服务器已拒绝的请求和响应消息中具有 TransferAnswer，已终止传输。</span><span class="sxs-lookup"><span data-stu-id="424b3-109">**Rejected** – The server has rejected the request and has the TransferAnswer in the response message, and has terminated the transfer.</span></span>  
  
-   <span data-ttu-id="424b3-110">**正在进行**– 传输正在进行中并且将继续执行 （与上面定期续订）。</span><span class="sxs-lookup"><span data-stu-id="424b3-110">**Ongoing** – The transfer is in progress and is proceeding (renewed periodically as above).</span></span>  
  
-   <span data-ttu-id="424b3-111">**完成**-文件传输已成功完成，就而言这方面的传输，包括的摘要值进行比较。</span><span class="sxs-lookup"><span data-stu-id="424b3-111">**Completed** – The file transfer has completed successfully as far as that side of the transfer is concerned, including the comparison of the digest value.</span></span>  
  
-   <span data-ttu-id="424b3-112">**失败**-文件传输失败，因为数据访问处理、 通信或超时异常。</span><span class="sxs-lookup"><span data-stu-id="424b3-112">**Failed** – The file transfer has failed because of a data access, processing, communications or timeout exception.</span></span> <span data-ttu-id="424b3-113">(注意：SWIFTNet 链接会强制实施超时和的值由 SWIFT）。</span><span class="sxs-lookup"><span data-stu-id="424b3-113">(Note: Timeout is enforced by SWIFTNet Link, and the value is determined by SWIFT).</span></span>  
  
-   <span data-ttu-id="424b3-114">**中止**-文件传输已中止 （任一端中止我的问题）。</span><span class="sxs-lookup"><span data-stu-id="424b3-114">**Aborted** – The file transfer has been aborted (either side my issue the abort).</span></span>  
  
-   <span data-ttu-id="424b3-115">**未知和重复**– 只是由于计时，出现此状态。</span><span class="sxs-lookup"><span data-stu-id="424b3-115">**Unknown and Duplicated** – This state occurs only because of timing.</span></span> <span data-ttu-id="424b3-116">对于发送程序，该文件应重新发送标记为可能是重复 (PDIndicator)。</span><span class="sxs-lookup"><span data-stu-id="424b3-116">In the case of a sender, the file should be re-sent marked as possibly duplicated (PDIndicator).</span></span> <span data-ttu-id="424b3-117">对于接收方，当 PDIndicator 意味着，该文件可能已发送，FileAct 适配器将检查重复项，并且如果找到，则将返回 TransferAnswer 的重复，这将终止当前尝试。</span><span class="sxs-lookup"><span data-stu-id="424b3-117">In the case of a receiver, when the PDIndicator implies that the file might have already been sent, the FileAct Adapter will check for the duplication, and if found, will return a TransferAnswer of Duplicated, which will terminate the current attempt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="424b3-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="424b3-118">See Also</span></span>  
 <span data-ttu-id="424b3-119">[FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="424b3-119">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="424b3-120">[FileAct 适配器实时端到端基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="424b3-120">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="424b3-121">[FileAct 适配器实时本地基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="424b3-121">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="424b3-122">[FileAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="424b3-122">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="424b3-123">[FileAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="424b3-123">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="424b3-124">[FileAct 适配器文件和传输标识](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="424b3-124">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="424b3-125">[FileAct 适配器支持信息传输](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="424b3-125">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 [<span data-ttu-id="424b3-126">FileAct 适配器送达通知</span><span class="sxs-lookup"><span data-stu-id="424b3-126">FileAct Adapter Delivery Notification</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)