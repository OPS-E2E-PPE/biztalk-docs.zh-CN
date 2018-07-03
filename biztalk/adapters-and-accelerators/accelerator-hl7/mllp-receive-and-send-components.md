---
title: MLLP 接收和发送组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send components
- Minimal Lower Layer Protocol (MLLP)
- MLLP adapters
- MLLP adapters, wrappers
- wrappers [MLLP adapters]
- receive components
ms.assetid: 2f1c4099-8f52-437a-bdc1-efe707fbf347
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0eebc51d23c66fb9dd7047f29982fbcc05a8215f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971798"
---
# <a name="mllp-receive-and-send-components"></a><span data-ttu-id="0839c-102">MLLP 接收和发送组件</span><span class="sxs-lookup"><span data-stu-id="0839c-102">MLLP Receive and Send Components</span></span>
<span data-ttu-id="0839c-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持所有 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]本机适配器类型，包括文件、 HTTP、 SQL 和 FTP。</span><span class="sxs-lookup"><span data-stu-id="0839c-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) supports all Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] native adapter types, including File, HTTP, SQL, and FTP.</span></span> <span data-ttu-id="0839c-104">对于 HL7 编码接收和发送的消息，但是，您通常使用 MLLP 适配器。</span><span class="sxs-lookup"><span data-stu-id="0839c-104">For HL7-encoded message receiving and sending, however, you typically use the MLLP adapter.</span></span> <span data-ttu-id="0839c-105">此适配器是使用最少的较低层协议 (MLLP) 的 TCP/IP 套接字适配器。</span><span class="sxs-lookup"><span data-stu-id="0839c-105">This adapter is a TCP/IP socket adapter that uses the Minimal Lower Layer Protocol (MLLP).</span></span> <span data-ttu-id="0839c-106">此协议提供的双向消息支持和端到端卫生保健应用程序集成。</span><span class="sxs-lookup"><span data-stu-id="0839c-106">This protocol provides bi-directional message support and end-to-end health care application integration.</span></span>  
  
 <span data-ttu-id="0839c-107">你可以配置 MLLP 接收适配器为双向适配器或单向适配器。</span><span class="sxs-lookup"><span data-stu-id="0839c-107">You can configure the MLLP receive adapter as either a two-way adapter or a one-way adapter.</span></span> <span data-ttu-id="0839c-108">您可以配置 MLLP 发送适配器，如双向要求-响应发送适配器、 一个单向发送适配器配置为在同一套接字连接，接收确认 (Ack) 或一个单向发送适配器不返回任何消息。</span><span class="sxs-lookup"><span data-stu-id="0839c-108">You can configure the MLLP send adapter as a two-way solicit-response send adapter, a one-way send adapter configured to receive acknowledgments (ACKs) on the same socket connection, or a one-way send adapter that does not return any messages.</span></span> <span data-ttu-id="0839c-109">当您使用双向要求响应发送 MLLP 适配器，您可以配置接收端口以返回是 Ack 或响应消息。</span><span class="sxs-lookup"><span data-stu-id="0839c-109">When you use the two-way solicit-response send MLLP adapter, you can configure the receive port to return either ACKs or response messages.</span></span> <span data-ttu-id="0839c-110">有关示例 MLLP 发送和接收适配器，请参阅[询问教程](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="0839c-110">For examples of MLLP send and receive adapters, see [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md).</span></span>  
  
 <span data-ttu-id="0839c-111">消息[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接收或发送 MLLP 适配器上的需要以下包装器：</span><span class="sxs-lookup"><span data-stu-id="0839c-111">Messages that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives or sends on an MLLP adapter require the following wrappers:</span></span>  
  
- <span data-ttu-id="0839c-112">\<SB\>开始块字符</span><span class="sxs-lookup"><span data-stu-id="0839c-112">\<SB\> Start Block character</span></span>  
  
- <span data-ttu-id="0839c-113">\<EB\>结束块字符</span><span class="sxs-lookup"><span data-stu-id="0839c-113">\<EB\> End Block character</span></span>  
  
- <span data-ttu-id="0839c-114">\<CR\>回车符返回字节 （可选）</span><span class="sxs-lookup"><span data-stu-id="0839c-114">\<CR\> Carriage Return Byte (optional)</span></span>  
  
  <span data-ttu-id="0839c-115">MLLP 适配器提供的错误处理缺少\<SB\>或\<EB\>包装、 连接中断或超时。</span><span class="sxs-lookup"><span data-stu-id="0839c-115">MLLP adapters provide error handling for missing \<SB\> or \<EB\> wrappers, dropped connections, or timeouts.</span></span> <span data-ttu-id="0839c-116">使用 MLLP 适配器，您可以配置上的连接数限制。</span><span class="sxs-lookup"><span data-stu-id="0839c-116">With an MLLP adapter, you can configure a limitation on the number of connections.</span></span> <span data-ttu-id="0839c-117">使用 MLLP 适配器，可以使用具有多种类型的确认。</span><span class="sxs-lookup"><span data-stu-id="0839c-117">You can use an assortment of acknowledgments with an MLLP adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0839c-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="0839c-118">See Also</span></span>  
 <span data-ttu-id="0839c-119">[处理用 MLLP 编码的消息](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md) </span><span class="sxs-lookup"><span data-stu-id="0839c-119">[Processing MLLP-encoded Messages](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md) </span></span>  
 [<span data-ttu-id="0839c-120">BizTalk Accelerator for HL7 组件</span><span class="sxs-lookup"><span data-stu-id="0839c-120">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)