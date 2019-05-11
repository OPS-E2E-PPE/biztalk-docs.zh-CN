---
title: AS2 解决方案体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41e493ba-919b-4520-9c12-92d6757984ef
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60f25fb229a37896846f81e37c3cc71e8419d854
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528861"
---
# <a name="as2-solution-architecture"></a><span data-ttu-id="d61c2-102">AS2 解决方案体系结构</span><span class="sxs-lookup"><span data-stu-id="d61c2-102">AS2 Solution Architecture</span></span>
<span data-ttu-id="d61c2-103">AS2 处理是独立于 EDI 处理执行的。</span><span class="sxs-lookup"><span data-stu-id="d61c2-103">AS2 processing is performed separately from EDI processing.</span></span> <span data-ttu-id="d61c2-104">AS2 消息的接收、处理以及确认的发送均独立于 EDI 负载的处理进行。</span><span class="sxs-lookup"><span data-stu-id="d61c2-104">AS2 messages are received, processed, and an acknowledgment sent apart from the processing of the EDI payload.</span></span> <span data-ttu-id="d61c2-105">因此，AS2 处理与 EDI 处理的设计和配置也是分别完成的。</span><span class="sxs-lookup"><span data-stu-id="d61c2-105">As a result, AS2 processing is designed and configured apart from EDI processing.</span></span> <span data-ttu-id="d61c2-106">另外，可使用 AS2 传输 EDI 消息或非 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="d61c2-106">In addition, you can use AS2 to transport either EDI messages or non-EDI messages.</span></span>  
  
 <span data-ttu-id="d61c2-107">本节介绍 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的 AS2 解决方案的体系结构，包括端对端、接收端和发送端处理。</span><span class="sxs-lookup"><span data-stu-id="d61c2-107">This section describes the architecture of AS2 solutions on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], including end-to-end, receive-side, and send-side processing.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d61c2-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="d61c2-108">In This Section</span></span>  
  
-   [<span data-ttu-id="d61c2-109">AS2 消息传送</span><span class="sxs-lookup"><span data-stu-id="d61c2-109">AS2 Messaging</span></span>](../core/as2-messaging.md)  
  
-   [<span data-ttu-id="d61c2-110">协议在 AS2 处理中的角色</span><span class="sxs-lookup"><span data-stu-id="d61c2-110">The Role of Agreements in AS2 Processing</span></span>](../core/the-role-of-agreements-in-as2-processing.md)  
  
-   [<span data-ttu-id="d61c2-111">BizTalk Server 如何接收 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="d61c2-111">How BizTalk Server Receives AS2 Messages</span></span>](../core/how-biztalk-server-receives-as2-messages.md)  
  
-   [<span data-ttu-id="d61c2-112">BizTalk Server 如何发送 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="d61c2-112">How BizTalk Server Sends AS2 Messages</span></span>](../core/how-biztalk-server-sends-as2-messages.md)