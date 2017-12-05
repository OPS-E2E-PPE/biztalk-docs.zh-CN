---
title: "MLLP 接收和发送组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send components
- Minimal Lower Layer Protocol (MLLP)
- MLLP adapters
- MLLP adapters, wrappers
- wrappers [MLLP adapters]
- receive components
ms.assetid: 2f1c4099-8f52-437a-bdc1-efe707fbf347
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e135b98c04531aa6200f3b79c5b6d5153bf299a7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="mllp-receive-and-send-components"></a><span data-ttu-id="ab25e-102">MLLP 接收和发送组件</span><span class="sxs-lookup"><span data-stu-id="ab25e-102">MLLP Receive and Send Components</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="ab25e-103">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持所有[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]本机适配器类型，包括文件、 HTTP、 SQL 和 FTP。</span><span class="sxs-lookup"><span data-stu-id="ab25e-103"> BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) supports all [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] native adapter types, including File, HTTP, SQL, and FTP.</span></span> <span data-ttu-id="ab25e-104">对于 HL7 编码接收和发送的消息，但是，你通常使用 MLLP 适配器。</span><span class="sxs-lookup"><span data-stu-id="ab25e-104">For HL7-encoded message receiving and sending, however, you typically use the MLLP adapter.</span></span> <span data-ttu-id="ab25e-105">此适配器是使用最小的较低层协议 (MLLP) 的 TCP/IP 套接字适配器。</span><span class="sxs-lookup"><span data-stu-id="ab25e-105">This adapter is a TCP/IP socket adapter that uses the Minimal Lower Layer Protocol (MLLP).</span></span> <span data-ttu-id="ab25e-106">此协议提供的双向消息支持和端到端卫生保健的应用程序集成。</span><span class="sxs-lookup"><span data-stu-id="ab25e-106">This protocol provides bi-directional message support and end-to-end health care application integration.</span></span>  
  
 <span data-ttu-id="ab25e-107">你可以配置 MLLP 为双向适配器或单向适配器接收适配器。</span><span class="sxs-lookup"><span data-stu-id="ab25e-107">You can configure the MLLP receive adapter as either a two-way adapter or a one-way adapter.</span></span> <span data-ttu-id="ab25e-108">你可以配置 MLLP 发送适配器，如双向请求-响应发送适配器、 单向发送适配器配置为在同一套接字连接，收到确认 (Ack) 或单向发送不返回任何消息的适配器。</span><span class="sxs-lookup"><span data-stu-id="ab25e-108">You can configure the MLLP send adapter as a two-way solicit-response send adapter, a one-way send adapter configured to receive acknowledgments (ACKs) on the same socket connection, or a one-way send adapter that does not return any messages.</span></span> <span data-ttu-id="ab25e-109">当你使用双向请求作出响应发送 MLLP 适配器，你可以配置要返回确认或响应消息的接收端口。</span><span class="sxs-lookup"><span data-stu-id="ab25e-109">When you use the two-way solicit-response send MLLP adapter, you can configure the receive port to return either ACKs or response messages.</span></span> <span data-ttu-id="ab25e-110">有关示例 MLLP 发送和接收适配器，请参阅[Interrogative 教程](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="ab25e-110">For examples of MLLP send and receive adapters, see [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md).</span></span>  
  
 <span data-ttu-id="ab25e-111">消息[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接收或发送 MLLP 适配器上的需要以下包装：</span><span class="sxs-lookup"><span data-stu-id="ab25e-111">Messages that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives or sends on an MLLP adapter require the following wrappers:</span></span>  
  
-   <span data-ttu-id="ab25e-112">\<SB\>启动块字符</span><span class="sxs-lookup"><span data-stu-id="ab25e-112">\<SB\> Start Block character</span></span>  
  
-   <span data-ttu-id="ab25e-113">\<EB\>结束块字符</span><span class="sxs-lookup"><span data-stu-id="ab25e-113">\<EB\> End Block character</span></span>  
  
-   <span data-ttu-id="ab25e-114">\<CR\>回车符返回字节 （可选）</span><span class="sxs-lookup"><span data-stu-id="ab25e-114">\<CR\> Carriage Return Byte (optional)</span></span>  
  
 <span data-ttu-id="ab25e-115">MLLP 适配器提供错误处理缺少\<SB\>或\<EB\>包装器、 删除的连接或超时。</span><span class="sxs-lookup"><span data-stu-id="ab25e-115">MLLP adapters provide error handling for missing \<SB\> or \<EB\> wrappers, dropped connections, or timeouts.</span></span> <span data-ttu-id="ab25e-116">使用 MLLP 适配器，你可以配置上的连接数的限制。</span><span class="sxs-lookup"><span data-stu-id="ab25e-116">With an MLLP adapter, you can configure a limitation on the number of connections.</span></span> <span data-ttu-id="ab25e-117">装有 MLLP 适配器，可以使用多种类型的确认。</span><span class="sxs-lookup"><span data-stu-id="ab25e-117">You can use an assortment of acknowledgments with an MLLP adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab25e-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab25e-118">See Also</span></span>  
 <span data-ttu-id="ab25e-119">[处理 MLLP 编码消息](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md) </span><span class="sxs-lookup"><span data-stu-id="ab25e-119">[Processing MLLP-encoded Messages](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md) </span></span>  
 [<span data-ttu-id="ab25e-120">BizTalk Accelerator for HL7 组件</span><span class="sxs-lookup"><span data-stu-id="ab25e-120">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)