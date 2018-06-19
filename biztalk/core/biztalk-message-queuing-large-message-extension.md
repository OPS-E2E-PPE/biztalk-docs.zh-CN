---
title: BizTalk 消息队列大型消息扩展 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Message Queuing Large Message Extension
- utilities, BizTalk Message Queuing Large Message Extension
ms.assetid: 5d6892d3-fda8-41a3-8111-d28c11bd71fb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 399c8e02d59a931dbf30bfa31ca28980dfa312be
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006398"
---
# <a name="biztalk-message-queuing-large-message-extension"></a><span data-ttu-id="e3295-102">BizTalk 消息队列大型消息扩展</span><span class="sxs-lookup"><span data-stu-id="e3295-102">BizTalk Message Queuing Large Message Extension</span></span>
<span data-ttu-id="e3295-103">本机消息队列无法处理的消息其正文大于 4megabytes (MB)。</span><span class="sxs-lookup"><span data-stu-id="e3295-103">Native message queuing cannot process a message with a body larger than 4megabytes (MB).</span></span> <span data-ttu-id="e3295-104">但是，Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包含的本地消息队列的加载项可处理大于 4 MB 的消息。</span><span class="sxs-lookup"><span data-stu-id="e3295-104">However, Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes an add-on for native message queuing that permits processing messages larger than 4 MB.</span></span> <span data-ttu-id="e3295-105">此外接程序传递为 Mqrtlarge.dll 文件中，并公开**MQSendLargeMessage**和**MQReceiveLargeMessage**应用程序的编程接口 (Api) 和类似的 COM 模型。</span><span class="sxs-lookup"><span data-stu-id="e3295-105">This add-on is delivered as the Mqrtlarge.dll file, and exposes the **MQSendLargeMessage** and **MQReceiveLargeMessage** application programming interfaces (APIs), and the analogous COM model.</span></span> <span data-ttu-id="e3295-106">这些函数的实现是作为标准的消息队列 Api， **MQSendMessage**和**MQReceiveMessage**分别。</span><span class="sxs-lookup"><span data-stu-id="e3295-106">These functions are implemented as standard message queuing APIs, **MQSendMessage** and **MQReceiveMessage** respectively.</span></span>  
  
 <span data-ttu-id="e3295-107">若要进行大消息交换，消息队列计算机必须已安装了 Mqrtlarge.dll 文件，并且消息队列应用程序应该使用加载项 API。</span><span class="sxs-lookup"><span data-stu-id="e3295-107">To participate in large message exchanges, the message queuing computer must have the Mqrtlarge.dll file installed, and the message queuing application should use the add-on APIs.</span></span> <span data-ttu-id="e3295-108">否则，将分片完成消息。</span><span class="sxs-lookup"><span data-stu-id="e3295-108">Otherwise, complete messages will be fragmented.</span></span>  
  
 <span data-ttu-id="e3295-109">**SDK 中的位置**</span><span class="sxs-lookup"><span data-stu-id="e3295-109">**Location in SDK**</span></span>  
  
 <span data-ttu-id="e3295-110">\<*安装路径*\>\SDK\ Mqrtlarge.dll</span><span class="sxs-lookup"><span data-stu-id="e3295-110">\<*Installation Path*\>\SDK\ Mqrtlarge.dll</span></span>  
  
 <span data-ttu-id="e3295-111">**文件清单**</span><span class="sxs-lookup"><span data-stu-id="e3295-111">**File Inventory**</span></span>  
  
 <span data-ttu-id="e3295-112">下表显示了本实用程序使用的文件及其用途。</span><span class="sxs-lookup"><span data-stu-id="e3295-112">The following table shows the file this utility uses and describes its purpose.</span></span>  
  
|<span data-ttu-id="e3295-113">文件</span><span class="sxs-lookup"><span data-stu-id="e3295-113">File(s)</span></span>|<span data-ttu-id="e3295-114">Description</span><span class="sxs-lookup"><span data-stu-id="e3295-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e3295-115">Mqrtlarge.dll</span><span class="sxs-lookup"><span data-stu-id="e3295-115">Mqrtlarge.dll</span></span>|<span data-ttu-id="e3295-116">公开的 Win32 动态链接库**MQSendLargeMessage**和**MQReceiveLargeMessage**。</span><span class="sxs-lookup"><span data-stu-id="e3295-116">A Win32 dynamic-link library that exposes **MQSendLargeMessage** and **MQReceiveLargeMessage**.</span></span><br /><br /> <span data-ttu-id="e3295-117">标头文件位于*\<安装路径\>* \SDK\Include 目录。</span><span class="sxs-lookup"><span data-stu-id="e3295-117">The header files are located in the *\<Installation Path\>* \SDK\Include directory.</span></span> <span data-ttu-id="e3295-118">**注意：** 必须安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到才能访问 Mqrtlarge.dll 的 64 位版本的 Windows 的 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="e3295-118">**Note:**  You must install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] onto a 64 bit version of Windows in order to access the 64 bit version of Mqrtlarge.dll.</span></span>|  
  
 <span data-ttu-id="e3295-119">**使用此实用工具**</span><span class="sxs-lookup"><span data-stu-id="e3295-119">**Using This Utility**</span></span>  
  
 <span data-ttu-id="e3295-120">通过以下过程运行 Mqrtlarge.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="e3295-120">Use the following procedure to run the Mqrtlarge.dll file.</span></span>  
  
### <a name="to-use-the-mqrtlargedll-file"></a><span data-ttu-id="e3295-121">使用 Mqrtlarge.dll 文件</span><span class="sxs-lookup"><span data-stu-id="e3295-121">To use the Mqrtlarge.dll file</span></span>  
  
1.  > [!NOTE]
    >  <span data-ttu-id="e3295-122">对于不带 BizTalk Server MSMQ 解决方案，MQRTLarge.dll 可能仍正常工作。</span><span class="sxs-lookup"><span data-stu-id="e3295-122">For an MSMQ solution without BizTalk Server, the MQRTLarge.dll may still function correctly.</span></span> <span data-ttu-id="e3295-123">但是，这不是建议的配置，Microsoft 支持，并且如果在 BizTalk Server 环境之外使用，可能会出现意外的结果。</span><span class="sxs-lookup"><span data-stu-id="e3295-123">However, this is not a recommended configuration that Microsoft supports, and unexpected results may occur if used outside of the BizTalk Server environment.</span></span>  
  
     <span data-ttu-id="e3295-124">将文件 Mqrtlarge.dll 添加到未安装 BizTalk Server 的计算机中。</span><span class="sxs-lookup"><span data-stu-id="e3295-124">Add the file Mqrtlarge.dll to the computer that does not contain an installation of BizTalk Server.</span></span> <span data-ttu-id="e3295-125">消息队列使用 Mqrtlarge.dll 向 BizTalk Server 发送消息，或从 BizTalk Server 接收消息。</span><span class="sxs-lookup"><span data-stu-id="e3295-125">Message Queuing uses Mqrtlarge.dll to send or receive messages to or from BizTalk Server.</span></span>  
  
2.  <span data-ttu-id="e3295-126">若要访问 Mqrtlarge.dll 文件中的 API，可在适当应用程序中添加一个对 Mqrtlarge.dll 文件的引用，该应用程序是在其他计算机与 BizTalk 消息队列终结点之间发送或接收消息的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e3295-126">To access the APIs in the Mqrtlarge.dll file, add a reference to the Mqrtlarge.dll file in the applications that send or receive messages to or from other computers to the BizTalk Message Queuing endpoint.</span></span>  
  
 <span data-ttu-id="e3295-127">**备注**</span><span class="sxs-lookup"><span data-stu-id="e3295-127">**Remarks**</span></span>  
  
 <span data-ttu-id="e3295-128">大消息被发送到标准消息队列（也叫作 MSMQ）。</span><span class="sxs-lookup"><span data-stu-id="e3295-128">Large messages are sent to standard Message Queuing (also known as MSMQ) queues.</span></span> <span data-ttu-id="e3295-129">在这类队列中只应使用大消息 API，尽管这不是强制性的。</span><span class="sxs-lookup"><span data-stu-id="e3295-129">You should use only the large message APIs on such queues, although this is not enforced.</span></span>  
  
 <span data-ttu-id="e3295-130">你仍然可以使用**MQSendMessage**将消息发送到大消息发送到队列。</span><span class="sxs-lookup"><span data-stu-id="e3295-130">You can still use **MQSendMessage** to send messages to a queue to which you sent large messages.</span></span> <span data-ttu-id="e3295-131">同样，你可以使用**MQReceiveMessage**从此类队列接收消息，但不建议因为它可能会影响性能**MQReceiveLargeMessage** API。</span><span class="sxs-lookup"><span data-stu-id="e3295-131">Likewise, you can use **MQReceiveMessage** to receive messages from such queues, although it is not recommended because it may impact the performance of the **MQReceiveLargeMessage** API.</span></span>  
  
 <span data-ttu-id="e3295-132">为了进行恢复，建议你使用**DEAD_LETTER**日记记录。</span><span class="sxs-lookup"><span data-stu-id="e3295-132">For recovery purposes, it is recommended that you use **DEAD_LETTER** journaling.</span></span>  
  
 <span data-ttu-id="e3295-133">**碎片**</span><span class="sxs-lookup"><span data-stu-id="e3295-133">**Fragmentation**</span></span>  
  
 <span data-ttu-id="e3295-134">通常情况下，大消息会分段为多个消息，每个消息都小于 4 MB。</span><span class="sxs-lookup"><span data-stu-id="e3295-134">In general, a large message will be fragmented into numerous messages, each smaller than 4 MB.</span></span> <span data-ttu-id="e3295-135">只会将正文分段，了解这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="e3295-135">It is important to understand that only the body is fragmented.</span></span> <span data-ttu-id="e3295-136">其他属性随每个片断一起发送。</span><span class="sxs-lookup"><span data-stu-id="e3295-136">The rest of the properties are sent with each fragment.</span></span>  
  
 <span data-ttu-id="e3295-137">分段的数量由消息的大小和片断的大小确定。</span><span class="sxs-lookup"><span data-stu-id="e3295-137">The number of fragments is defined by the size of the message and the size of the fragments.</span></span> <span data-ttu-id="e3295-138">片断大小可以由文件 Mqrtlarge.dll 或 BizTalk 消息队列的相应部分自动确定。</span><span class="sxs-lookup"><span data-stu-id="e3295-138">The fragment size may be automatically determined by the file Mqrtlarge.dll or the appropriate part of BizTalk Message Queuing.</span></span> <span data-ttu-id="e3295-139">应用程序还可以显式指定片断大小。</span><span class="sxs-lookup"><span data-stu-id="e3295-139">Applications can also explicitly specify the fragment size.</span></span>  
  
 <span data-ttu-id="e3295-140">请注意，大消息扩展要求通过添加固定大小的其他内部数据来扩展消息。</span><span class="sxs-lookup"><span data-stu-id="e3295-140">Note that the large message extension requires extending the message by adding additional internal data of a constant size.</span></span>  
  
 <span data-ttu-id="e3295-141">**PROPID_M_EXTENSION**</span><span class="sxs-lookup"><span data-stu-id="e3295-141">**PROPID_M_EXTENSION**</span></span>  
  
 <span data-ttu-id="e3295-142">你可以使用**PROPID_M_EXTENSION/PROPID_M_EXTENSION_LEN**属性，以对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="e3295-142">You can use the **PROPID_M_EXTENSION/PROPID_M_EXTENSION_LEN** properties to sign the message.</span></span> <span data-ttu-id="e3295-143">签名由 40 个字节 (B) 组成 。</span><span class="sxs-lookup"><span data-stu-id="e3295-143">The signature comprises 40 bytes (B).</span></span> <span data-ttu-id="e3295-144">下表显示了签名片断。</span><span class="sxs-lookup"><span data-stu-id="e3295-144">The following table shows signature fragments.</span></span>  
  
|<span data-ttu-id="e3295-145">Description</span><span class="sxs-lookup"><span data-stu-id="e3295-145">Description</span></span>|<span data-ttu-id="e3295-146">Size</span><span class="sxs-lookup"><span data-stu-id="e3295-146">Size</span></span>|  
|-----------------|----------|  
|<span data-ttu-id="e3295-147">全局唯一标识符 (GUID)，表示此消息被发送使用**MQSendLargeMessage**</span><span class="sxs-lookup"><span data-stu-id="e3295-147">Globally unique identifier (GUID) denoting that this message was sent using **MQSendLargeMessage**</span></span>|<span data-ttu-id="e3295-148">16 B</span><span class="sxs-lookup"><span data-stu-id="e3295-148">16 B</span></span>|  
|<span data-ttu-id="e3295-149">消息的 GUID： 普遍适用于消息的所有部分的唯一的每个大型消息 ID</span><span class="sxs-lookup"><span data-stu-id="e3295-149">GUID for the message: unique per-large message ID that is common to all parts of the message</span></span>|<span data-ttu-id="e3295-150">16 B</span><span class="sxs-lookup"><span data-stu-id="e3295-150">16 B</span></span>|  
|<span data-ttu-id="e3295-151">大消息的总大小</span><span class="sxs-lookup"><span data-stu-id="e3295-151">Total size of the large message</span></span>|<span data-ttu-id="e3295-152">4 B</span><span class="sxs-lookup"><span data-stu-id="e3295-152">4 B</span></span>|  
|<span data-ttu-id="e3295-153">部分号</span><span class="sxs-lookup"><span data-stu-id="e3295-153">Part number</span></span>|<span data-ttu-id="e3295-154">2 B</span><span class="sxs-lookup"><span data-stu-id="e3295-154">2 B</span></span>|  
|<span data-ttu-id="e3295-155">消息部分数</span><span class="sxs-lookup"><span data-stu-id="e3295-155">Number of message parts</span></span>|<span data-ttu-id="e3295-156">2 B</span><span class="sxs-lookup"><span data-stu-id="e3295-156">2 B</span></span>|  
  
 <span data-ttu-id="e3295-157">决定使用**PROPID_M_EXTENSION**具有一个附加的含义。</span><span class="sxs-lookup"><span data-stu-id="e3295-157">The decision to use **PROPID_M_EXTENSION** has an additional implication.</span></span> <span data-ttu-id="e3295-158">Microsoft Host Integration Server MSMQ-MQSeries Bridge 使用此属性传递一个结构，该结构包含那些在 MQSeries 和消息队列消息之间不直接映射的属性。</span><span class="sxs-lookup"><span data-stu-id="e3295-158">The Microsoft Host Integration Server MSMQ-MQSeries Bridge uses this property to pass a structure that contains properties that are not mapped directly between MQSeries and Message Queuing messages.</span></span> <span data-ttu-id="e3295-159">将消息发送到 MQSeries，或从 MQSeries 发送消息的应用程序显式或隐式使用此结构。</span><span class="sxs-lookup"><span data-stu-id="e3295-159">Applications that send messages to and from MQSeries explicitly or implicitly use this structure.</span></span> <span data-ttu-id="e3295-160">当接收应用程序从队列接收到消息时，消息队列能够生成确认信息。</span><span class="sxs-lookup"><span data-stu-id="e3295-160">Message Queuing can generate acknowledgments when a message has been received from a queue by a receiving application.</span></span> <span data-ttu-id="e3295-161">确认信息被发送到由发送应用程序指定的队列中。</span><span class="sxs-lookup"><span data-stu-id="e3295-161">The acknowledgments are sent to a queue specified by the sending application.</span></span> <span data-ttu-id="e3295-162">对于大消息，仅为大消息的最后部分发送此确认信息。</span><span class="sxs-lookup"><span data-stu-id="e3295-162">In the case of large messages, you send this acknowledgment only for the last part of the large message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3295-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3295-163">See Also</span></span>  
 [<span data-ttu-id="e3295-164">SDK 中的实用工具</span><span class="sxs-lookup"><span data-stu-id="e3295-164">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)