---
title: FileAct 适配器存储和转发 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50110bf0-75c2-426c-9833-65c3117224b2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6971d1b65f32018b15bf8ae022ca6d64d23701da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367166"
---
# <a name="fileact-adapter-store-and-forward"></a><span data-ttu-id="2a953-102">FileAct 适配器存储和转发</span><span class="sxs-lookup"><span data-stu-id="2a953-102">FileAct Adapter Store and Forward</span></span>
<span data-ttu-id="2a953-103">中存储和转发 (SnF) 模式下，文件被发送给在发送时，进行排队并在目标队列中的检索。</span><span class="sxs-lookup"><span data-stu-id="2a953-103">In Store and Forward (SnF) mode, files are delivered to queue at send time, and are retrieved from the queue by the destination.</span></span> <span data-ttu-id="2a953-104">中间响应将返回通过 SWIFTNet 到发件人，直到该文件安全地传递到目标。</span><span class="sxs-lookup"><span data-stu-id="2a953-104">Intermediate responses are returned by SWIFTNet to the sender until the file is safely delivered to the destination.</span></span>  
  
## <a name="sending-using-snf"></a><span data-ttu-id="2a953-105">发送使用 SnF</span><span class="sxs-lookup"><span data-stu-id="2a953-105">Sending Using SnF</span></span>  
 <span data-ttu-id="2a953-106">如果您创建一个单向发送端口，适配器将在 SnF 模式下工作，并将消息发送到队列。</span><span class="sxs-lookup"><span data-stu-id="2a953-106">If you create a one-way send port, the adapter works in SnF mode and sends messages to the queue.</span></span>  
  
## <a name="receiving-using-snf"></a><span data-ttu-id="2a953-107">接收使用 SnF</span><span class="sxs-lookup"><span data-stu-id="2a953-107">Receiving Using SnF</span></span>  
 <span data-ttu-id="2a953-108">SnF FileAct 在推送模式下运行。</span><span class="sxs-lookup"><span data-stu-id="2a953-108">SnF FileAct operates in Push mode.</span></span> <span data-ttu-id="2a953-109">这是运行时选项。</span><span class="sxs-lookup"><span data-stu-id="2a953-109">This is a run-time option.</span></span>  
  
 <span data-ttu-id="2a953-110">能够从队列检索消息前, SWIFTNet SnF 应收到获取队列的请求。</span><span class="sxs-lookup"><span data-stu-id="2a953-110">Before being able to retrieve messages from a queue, SWIFTNet SnF should receive a request to acquire the queue.</span></span> <span data-ttu-id="2a953-111">这是通过调用的进程外 COM + 组件接收适配器实现的。</span><span class="sxs-lookup"><span data-stu-id="2a953-111">This is accomplished by the receive adapter invoking the out-of-proc COM+ component.</span></span> <span data-ttu-id="2a953-112">成功的采集之后, 创建一个会话。</span><span class="sxs-lookup"><span data-stu-id="2a953-112">After a successful acquire, a session is created.</span></span> <span data-ttu-id="2a953-113">然后将请求中指定的模式中打开队列。</span><span class="sxs-lookup"><span data-stu-id="2a953-113">The queue will then be opened in the mode specified in the Request.</span></span> <span data-ttu-id="2a953-114">所有消息将都返回到的物理节点发出的请求。</span><span class="sxs-lookup"><span data-stu-id="2a953-114">All messages will be returned to the physical node which issued the request.</span></span>  
  
 <span data-ttu-id="2a953-115">消息传递中指定的顺序 （请注意，可以交织在一起，并按优先级排列 InterAct 和 FileAct 传输。）序列化的消息，但是，是依赖于就好像它们存储的时间。</span><span class="sxs-lookup"><span data-stu-id="2a953-115">Messages are delivered in the order specified (note that InterAct and FileAct transmissions can be interspersed, and arranged by priority.) The sequencing of messages, however, is dependent on the time that they were stored.</span></span> <span data-ttu-id="2a953-116">对于 FileAct，这是完成文件存储，不在启动时的时间。</span><span class="sxs-lookup"><span data-stu-id="2a953-116">In the case of FileAct, this is the time that the file storage is completed, not when it started.</span></span>  
  
### <a name="push-a-file-from-the-queue"></a><span data-ttu-id="2a953-117">将文件从队列推送</span><span class="sxs-lookup"><span data-stu-id="2a953-117">Push a File From the Queue</span></span>  
 <span data-ttu-id="2a953-118">FileAct 适配器 （服务器） 接收 HandleFileRequest 来自 SWIFTNet，其中包含的队列名称、 会话和序列的信息。</span><span class="sxs-lookup"><span data-stu-id="2a953-118">The FileAct adapter (server) receives a HandleFileRequest from SWIFTNet, containing the queue, session and sequence information.</span></span> <span data-ttu-id="2a953-119">服务器使用 HandleFileResponse 做出响应。</span><span class="sxs-lookup"><span data-stu-id="2a953-119">The server responds with a HandleFileResponse.</span></span>  
  
 <span data-ttu-id="2a953-120">然后，服务器会颁发 FetchFileRequest 和文件传送到服务器。</span><span class="sxs-lookup"><span data-stu-id="2a953-120">The server then issues FetchFileRequest and the file is delivered to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a953-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a953-121">See Also</span></span>  
 <span data-ttu-id="2a953-122">[FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="2a953-122">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="2a953-123">[FileAct 适配器实时端到端基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="2a953-123">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="2a953-124">[FileAct 适配器实时本地基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="2a953-124">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="2a953-125">[FileAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="2a953-125">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="2a953-126">[FileAct 适配器文件和传输标识](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="2a953-126">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="2a953-127">[FileAct 适配器支持信息传输](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="2a953-127">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 <span data-ttu-id="2a953-128">[FileAct 适配器送达通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="2a953-128">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="2a953-129">FileAct 适配器状态监视</span><span class="sxs-lookup"><span data-stu-id="2a953-129">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)