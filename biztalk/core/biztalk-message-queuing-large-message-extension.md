---
title: BizTalk 消息队列大消息扩展 |Microsoft Docs
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
ms.openlocfilehash: fee132b78756554dace25319d41193f89e00aebd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357980"
---
# <a name="biztalk-message-queuing-large-message-extension"></a><span data-ttu-id="b3590-102">BizTalk 消息队列大消息扩展</span><span class="sxs-lookup"><span data-stu-id="b3590-102">BizTalk Message Queuing Large Message Extension</span></span>
<span data-ttu-id="b3590-103">本地消息队列无法处理的消息其正文大于 4megabytes (MB)。</span><span class="sxs-lookup"><span data-stu-id="b3590-103">Native message queuing cannot process a message with a body larger than 4megabytes (MB).</span></span> <span data-ttu-id="b3590-104">但是，Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包括处理大于 4 MB 的消息外接程序的本地消息队列。</span><span class="sxs-lookup"><span data-stu-id="b3590-104">However, Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes an add-on for native message queuing that permits processing messages larger than 4 MB.</span></span> <span data-ttu-id="b3590-105">此加载项以 Mqrtlarge.dll 文件，交付，并公开**MQSendLargeMessage**并**MQReceiveLargeMessage**应用程序的编程接口 (Api) 和类似的 COM 模型。</span><span class="sxs-lookup"><span data-stu-id="b3590-105">This add-on is delivered as the Mqrtlarge.dll file, and exposes the **MQSendLargeMessage** and **MQReceiveLargeMessage** application programming interfaces (APIs), and the analogous COM model.</span></span> <span data-ttu-id="b3590-106">这些函数作为标准消息队列 Api，实现**MQSendMessage**并**MQReceiveMessage**分别。</span><span class="sxs-lookup"><span data-stu-id="b3590-106">These functions are implemented as standard message queuing APIs, **MQSendMessage** and **MQReceiveMessage** respectively.</span></span>  

 <span data-ttu-id="b3590-107">若要参与大消息交换，消息队列计算机必须已安装 Mqrtlarge.dll 文件，并且消息队列应用程序应使用加载项 Api。</span><span class="sxs-lookup"><span data-stu-id="b3590-107">To participate in large message exchanges, the message queuing computer must have the Mqrtlarge.dll file installed, and the message queuing application should use the add-on APIs.</span></span> <span data-ttu-id="b3590-108">否则，完整的消息将进行分片。</span><span class="sxs-lookup"><span data-stu-id="b3590-108">Otherwise, complete messages will be fragmented.</span></span>  

 <span data-ttu-id="b3590-109">**在 SDK 中的位置**</span><span class="sxs-lookup"><span data-stu-id="b3590-109">**Location in SDK**</span></span>  

 <span data-ttu-id="b3590-110">\<*Installation Path*\>\SDK\ Mqrtlarge.dll</span><span class="sxs-lookup"><span data-stu-id="b3590-110">\<*Installation Path*\>\SDK\ Mqrtlarge.dll</span></span>  

 <span data-ttu-id="b3590-111">**文件清单**</span><span class="sxs-lookup"><span data-stu-id="b3590-111">**File Inventory**</span></span>  

 <span data-ttu-id="b3590-112">下表显示的文件，此实用程序使用，并介绍其用途。</span><span class="sxs-lookup"><span data-stu-id="b3590-112">The following table shows the file this utility uses and describes its purpose.</span></span>  


|    <span data-ttu-id="b3590-113">文件</span><span class="sxs-lookup"><span data-stu-id="b3590-113">File(s)</span></span>    |                                                                                                                                                                                              <span data-ttu-id="b3590-114">Description</span><span class="sxs-lookup"><span data-stu-id="b3590-114">Description</span></span>                                                                                                                                                                                               |
|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b3590-115">Mqrtlarge.dll</span><span class="sxs-lookup"><span data-stu-id="b3590-115">Mqrtlarge.dll</span></span> | <span data-ttu-id="b3590-116">公开的 Win32 动态链接库**MQSendLargeMessage**并**MQReceiveLargeMessage**。</span><span class="sxs-lookup"><span data-stu-id="b3590-116">A Win32 dynamic-link library that exposes **MQSendLargeMessage** and **MQReceiveLargeMessage**.</span></span><br /><br /> <span data-ttu-id="b3590-117">标头文件位于*\<安装路径\>* \SDK\Include 目录。</span><span class="sxs-lookup"><span data-stu-id="b3590-117">The header files are located in the *\<Installation Path\>* \SDK\Include directory.</span></span> <span data-ttu-id="b3590-118">**注意：** 必须安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 64 位版本的 Windows，才能访问 64 位版本的 Mqrtlarge.dll。</span><span class="sxs-lookup"><span data-stu-id="b3590-118">**Note:**  You must install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] onto a 64 bit version of Windows in order to access the 64 bit version of Mqrtlarge.dll.</span></span> |

 <span data-ttu-id="b3590-119">**使用此实用程序**</span><span class="sxs-lookup"><span data-stu-id="b3590-119">**Using This Utility**</span></span>  

 <span data-ttu-id="b3590-120">使用以下过程运行 Mqrtlarge.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="b3590-120">Use the following procedure to run the Mqrtlarge.dll file.</span></span>  

### <a name="to-use-the-mqrtlargedll-file"></a><span data-ttu-id="b3590-121">若要使用 Mqrtlarge.dll 文件</span><span class="sxs-lookup"><span data-stu-id="b3590-121">To use the Mqrtlarge.dll file</span></span>  

1. > [!NOTE]
   >  <span data-ttu-id="b3590-122">对于 MSMQ 解决方案未使用 BizTalk Server，MQRTLarge.dll 仍可正常运行。</span><span class="sxs-lookup"><span data-stu-id="b3590-122">For an MSMQ solution without BizTalk Server, the MQRTLarge.dll may still function correctly.</span></span> <span data-ttu-id="b3590-123">但是，这不的建议的配置，Microsoft 支持，并且如果在 BizTalk Server 环境外部使用，可能会发生意外的结果。</span><span class="sxs-lookup"><span data-stu-id="b3590-123">However, this is not a recommended configuration that Microsoft supports, and unexpected results may occur if used outside of the BizTalk Server environment.</span></span>  

    <span data-ttu-id="b3590-124">将文件 Mqrtlarge.dll 添加到不包含 BizTalk Server 安装的计算机。</span><span class="sxs-lookup"><span data-stu-id="b3590-124">Add the file Mqrtlarge.dll to the computer that does not contain an installation of BizTalk Server.</span></span> <span data-ttu-id="b3590-125">消息队列使用 Mqrtlarge.dll 发送或接收到或从 BizTalk Server 消息。</span><span class="sxs-lookup"><span data-stu-id="b3590-125">Message Queuing uses Mqrtlarge.dll to send or receive messages to or from BizTalk Server.</span></span>  

2. <span data-ttu-id="b3590-126">若要访问 Mqrtlarge.dll 文件中的 Api，请在发送或接收消息到或从其他计算机连接到 BizTalk 消息队列终结点的应用程序中添加对 Mqrtlarge.dll 文件的引用。</span><span class="sxs-lookup"><span data-stu-id="b3590-126">To access the APIs in the Mqrtlarge.dll file, add a reference to the Mqrtlarge.dll file in the applications that send or receive messages to or from other computers to the BizTalk Message Queuing endpoint.</span></span>  

   <span data-ttu-id="b3590-127">**注释**</span><span class="sxs-lookup"><span data-stu-id="b3590-127">**Remarks**</span></span>  

   <span data-ttu-id="b3590-128">大消息发送到标准消息队列 (也称为 MSMQ) 队列。</span><span class="sxs-lookup"><span data-stu-id="b3590-128">Large messages are sent to standard Message Queuing (also known as MSMQ) queues.</span></span> <span data-ttu-id="b3590-129">尽管不强制这一点，应在这类队列中，使用大消息 Api。</span><span class="sxs-lookup"><span data-stu-id="b3590-129">You should use only the large message APIs on such queues, although this is not enforced.</span></span>  

   <span data-ttu-id="b3590-130">您仍然可以使用**MQSendMessage**将消息发送到向其发送大消息的队列。</span><span class="sxs-lookup"><span data-stu-id="b3590-130">You can still use **MQSendMessage** to send messages to a queue to which you sent large messages.</span></span> <span data-ttu-id="b3590-131">同样，可以使用**MQReceiveMessage**从这类队列接收消息，但因为它可能会影响性能的不建议**MQReceiveLargeMessage** API。</span><span class="sxs-lookup"><span data-stu-id="b3590-131">Likewise, you can use **MQReceiveMessage** to receive messages from such queues, although it is not recommended because it may impact the performance of the **MQReceiveLargeMessage** API.</span></span>  

   <span data-ttu-id="b3590-132">为了进行恢复，建议你使用**DEAD_LETTER**日记功能。</span><span class="sxs-lookup"><span data-stu-id="b3590-132">For recovery purposes, it is recommended that you use **DEAD_LETTER** journaling.</span></span>  

   <span data-ttu-id="b3590-133">**碎片**</span><span class="sxs-lookup"><span data-stu-id="b3590-133">**Fragmentation**</span></span>  

   <span data-ttu-id="b3590-134">一般情况下，大消息会分段为大量消息，每个小于 4 MB。</span><span class="sxs-lookup"><span data-stu-id="b3590-134">In general, a large message will be fragmented into numerous messages, each smaller than 4 MB.</span></span> <span data-ttu-id="b3590-135">请务必了解只会将正文分段。</span><span class="sxs-lookup"><span data-stu-id="b3590-135">It is important to understand that only the body is fragmented.</span></span> <span data-ttu-id="b3590-136">属性的其余部分会发送与每个片段。</span><span class="sxs-lookup"><span data-stu-id="b3590-136">The rest of the properties are sent with each fragment.</span></span>  

   <span data-ttu-id="b3590-137">由消息的大小和片断的大小定义的片段数。</span><span class="sxs-lookup"><span data-stu-id="b3590-137">The number of fragments is defined by the size of the message and the size of the fragments.</span></span> <span data-ttu-id="b3590-138">片断大小可能由文件 Mqrtlarge.dll 或 BizTalk 消息队列的相应部分自动确定。</span><span class="sxs-lookup"><span data-stu-id="b3590-138">The fragment size may be automatically determined by the file Mqrtlarge.dll or the appropriate part of BizTalk Message Queuing.</span></span> <span data-ttu-id="b3590-139">应用程序可以显式指定片断大小。</span><span class="sxs-lookup"><span data-stu-id="b3590-139">Applications can also explicitly specify the fragment size.</span></span>  

   <span data-ttu-id="b3590-140">请注意，大消息扩展要求通过添加固定大小的其他内部数据来扩展消息。</span><span class="sxs-lookup"><span data-stu-id="b3590-140">Note that the large message extension requires extending the message by adding additional internal data of a constant size.</span></span>  

   <span data-ttu-id="b3590-141">**PROPID_M_EXTENSION**</span><span class="sxs-lookup"><span data-stu-id="b3590-141">**PROPID_M_EXTENSION**</span></span>  

   <span data-ttu-id="b3590-142">可以使用**PROPID_M_EXTENSION/PROPID_M_EXTENSION_LEN**属性对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="b3590-142">You can use the **PROPID_M_EXTENSION/PROPID_M_EXTENSION_LEN** properties to sign the message.</span></span> <span data-ttu-id="b3590-143">签名包含 40 个字节 (B)。</span><span class="sxs-lookup"><span data-stu-id="b3590-143">The signature comprises 40 bytes (B).</span></span> <span data-ttu-id="b3590-144">下表显示了签名片断。</span><span class="sxs-lookup"><span data-stu-id="b3590-144">The following table shows signature fragments.</span></span>  

|<span data-ttu-id="b3590-145">Description</span><span class="sxs-lookup"><span data-stu-id="b3590-145">Description</span></span>|<span data-ttu-id="b3590-146">大小</span><span class="sxs-lookup"><span data-stu-id="b3590-146">Size</span></span>|  
|-----------------|----------|  
|<span data-ttu-id="b3590-147">表示是否已发送此消息使用的全局唯一标识符 (GUID) **MQSendLargeMessage**</span><span class="sxs-lookup"><span data-stu-id="b3590-147">Globally unique identifier (GUID) denoting that this message was sent using **MQSendLargeMessage**</span></span>|<span data-ttu-id="b3590-148">16 B</span><span class="sxs-lookup"><span data-stu-id="b3590-148">16 B</span></span>|  
|<span data-ttu-id="b3590-149">消息的 GUID： 普遍适用于消息的所有部分的唯一的每个大型消息 ID</span><span class="sxs-lookup"><span data-stu-id="b3590-149">GUID for the message: unique per-large message ID that is common to all parts of the message</span></span>|<span data-ttu-id="b3590-150">16 B</span><span class="sxs-lookup"><span data-stu-id="b3590-150">16 B</span></span>|  
|<span data-ttu-id="b3590-151">大消息的总大小</span><span class="sxs-lookup"><span data-stu-id="b3590-151">Total size of the large message</span></span>|<span data-ttu-id="b3590-152">4 B</span><span class="sxs-lookup"><span data-stu-id="b3590-152">4 B</span></span>|  
|<span data-ttu-id="b3590-153">部件号</span><span class="sxs-lookup"><span data-stu-id="b3590-153">Part number</span></span>|<span data-ttu-id="b3590-154">2 B</span><span class="sxs-lookup"><span data-stu-id="b3590-154">2 B</span></span>|  
|<span data-ttu-id="b3590-155">消息部分的数量</span><span class="sxs-lookup"><span data-stu-id="b3590-155">Number of message parts</span></span>|<span data-ttu-id="b3590-156">2 B</span><span class="sxs-lookup"><span data-stu-id="b3590-156">2 B</span></span>|  

 <span data-ttu-id="b3590-157">若要使用的决定**PROPID_M_EXTENSION**还有其他用途。</span><span class="sxs-lookup"><span data-stu-id="b3590-157">The decision to use **PROPID_M_EXTENSION** has an additional implication.</span></span> <span data-ttu-id="b3590-158">Microsoft 主机 Integration Server Msmq-mqseries Bridge 使用此属性将包含未直接在 MQSeries 和消息队列消息之间映射的属性的结构。</span><span class="sxs-lookup"><span data-stu-id="b3590-158">The Microsoft Host Integration Server MSMQ-MQSeries Bridge uses this property to pass a structure that contains properties that are not mapped directly between MQSeries and Message Queuing messages.</span></span> <span data-ttu-id="b3590-159">发送消息到和从 MQSeries 显式或隐式的应用程序使用此结构。</span><span class="sxs-lookup"><span data-stu-id="b3590-159">Applications that send messages to and from MQSeries explicitly or implicitly use this structure.</span></span> <span data-ttu-id="b3590-160">从队列接收应用程序收到一条消息时，消息队列能够生成确认信息。</span><span class="sxs-lookup"><span data-stu-id="b3590-160">Message Queuing can generate acknowledgments when a message has been received from a queue by a receiving application.</span></span> <span data-ttu-id="b3590-161">确认发送到发送应用程序指定的队列。</span><span class="sxs-lookup"><span data-stu-id="b3590-161">The acknowledgments are sent to a queue specified by the sending application.</span></span> <span data-ttu-id="b3590-162">对于大消息，发送此确认仅为大消息的最后一个部分。</span><span class="sxs-lookup"><span data-stu-id="b3590-162">In the case of large messages, you send this acknowledgment only for the last part of the large message.</span></span>  

## <a name="see-also"></a><span data-ttu-id="b3590-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="b3590-163">See Also</span></span>  
 [<span data-ttu-id="b3590-164">SDK 中的实用工具</span><span class="sxs-lookup"><span data-stu-id="b3590-164">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)