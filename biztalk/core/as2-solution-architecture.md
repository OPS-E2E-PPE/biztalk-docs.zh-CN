---
title: "AS2 解决方案体系结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41e493ba-919b-4520-9c12-92d6757984ef
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c22557059bd13dd99e0b24a2291b7f121d561bbc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="as2-solution-architecture"></a><span data-ttu-id="51410-102">AS2 解决方案体系结构</span><span class="sxs-lookup"><span data-stu-id="51410-102">AS2 Solution Architecture</span></span>
<span data-ttu-id="51410-103">AS2 处理是独立于 EDI 处理执行的。</span><span class="sxs-lookup"><span data-stu-id="51410-103">AS2 processing is performed separately from EDI processing.</span></span> <span data-ttu-id="51410-104">AS2 消息的接收、处理以及确认的发送均独立于 EDI 负载的处理进行。</span><span class="sxs-lookup"><span data-stu-id="51410-104">AS2 messages are received, processed, and an acknowledgment sent apart from the processing of the EDI payload.</span></span> <span data-ttu-id="51410-105">因此，AS2 处理与 EDI 处理的设计和配置也是分别完成的。</span><span class="sxs-lookup"><span data-stu-id="51410-105">As a result, AS2 processing is designed and configured apart from EDI processing.</span></span> <span data-ttu-id="51410-106">另外，可使用 AS2 传输 EDI 消息或非 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="51410-106">In addition, you can use AS2 to transport either EDI messages or non-EDI messages.</span></span>  
  
 <span data-ttu-id="51410-107">本节介绍 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的 AS2 解决方案的体系结构，包括端对端、接收端和发送端处理。</span><span class="sxs-lookup"><span data-stu-id="51410-107">This section describes the architecture of AS2 solutions on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], including end-to-end, receive-side, and send-side processing.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="51410-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="51410-108">In This Section</span></span>  
  
-   [<span data-ttu-id="51410-109">AS2 消息传送</span><span class="sxs-lookup"><span data-stu-id="51410-109">AS2 Messaging</span></span>](../core/as2-messaging.md)  
  
-   [<span data-ttu-id="51410-110">中 AS2 协议处理的角色</span><span class="sxs-lookup"><span data-stu-id="51410-110">The Role of Agreements in AS2 Processing</span></span>](../core/the-role-of-agreements-in-as2-processing.md)  
  
-   [<span data-ttu-id="51410-111">BizTalk Server 接收 AS2 消息的方式</span><span class="sxs-lookup"><span data-stu-id="51410-111">How BizTalk Server Receives AS2 Messages</span></span>](../core/how-biztalk-server-receives-as2-messages.md)  
  
-   [<span data-ttu-id="51410-112">BizTalk Server 将 AS2 消息的发送</span><span class="sxs-lookup"><span data-stu-id="51410-112">How BizTalk Server Sends AS2 Messages</span></span>](../core/how-biztalk-server-sends-as2-messages.md)