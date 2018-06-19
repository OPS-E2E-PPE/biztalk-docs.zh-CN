---
title: 发送和接收使用 MSMQ 适配器的大型消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, large messages
- configuring [MSMQ adapters], large messages
- MSMQ adapters, large messages
ms.assetid: 208efbed-7b58-4da5-ba27-65a315c2713b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a23265be84f2767849e4d61c2e9a95bfc9ed4ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269525"
---
# <a name="sending-and-receiving-large-messages-using-the-msmq-adapter"></a><span data-ttu-id="5491c-102">发送和接收使用 MSMQ 适配器的大型消息</span><span class="sxs-lookup"><span data-stu-id="5491c-102">Sending and Receiving Large Messages Using the MSMQ Adapter</span></span>
<span data-ttu-id="5491c-103">MSMQ 适配器默认消息处理部分依赖于消息的大小。</span><span class="sxs-lookup"><span data-stu-id="5491c-103">The MSMQ adapter default message handling depends, in part, on the size of the message.</span></span> <span data-ttu-id="5491c-104">如果消息小于 4 MB 时，则 MSMQ 适配器将使用 .NET Framework 类库。</span><span class="sxs-lookup"><span data-stu-id="5491c-104">When a message is less than four megabytes (4 MB), the MSMQ adapter uses the .NET Framework Class Library.</span></span> <span data-ttu-id="5491c-105">否则，将使用 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的大消息扩展。</span><span class="sxs-lookup"><span data-stu-id="5491c-105">Otherwise, it uses the large message extensions in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5491c-106">如果应用程序持续地接收或发送大消息，则您必须控制适配器使用的内存量。</span><span class="sxs-lookup"><span data-stu-id="5491c-106">If your application consistently receives or sends large messages, you may have to control the amount of memory that the adapter uses.</span></span> <span data-ttu-id="5491c-107">有关节省内存的详细信息，请参阅[优化性能的 MSMQ 适配器](../core/optimizing-performance-of-the-msmq-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="5491c-107">For more information about conserving memory, see [Optimizing Performance of the MSMQ Adapter](../core/optimizing-performance-of-the-msmq-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5491c-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5491c-108">See Also</span></span>  
 <span data-ttu-id="5491c-109">[优化性能的 MSMQ 适配器](../core/optimizing-performance-of-the-msmq-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5491c-109">[Optimizing Performance of the MSMQ Adapter](../core/optimizing-performance-of-the-msmq-adapter.md) </span></span>  
 [<span data-ttu-id="5491c-110">配置 MSMQ 适配器</span><span class="sxs-lookup"><span data-stu-id="5491c-110">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)