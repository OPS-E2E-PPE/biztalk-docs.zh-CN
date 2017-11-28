---
title: "字符编码 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transaction support
- character encoding
- encoding characters
- messages, character encoding
ms.assetid: 0a0c21c8-3318-4533-9734-89302527cb67
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19d3204cae7b82e9d18325b223e5c3b7a2d40808
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="character-encoding"></a><span data-ttu-id="3bbac-102">字符编码</span><span class="sxs-lookup"><span data-stu-id="3bbac-102">Character Encoding</span></span>
<span data-ttu-id="3bbac-103">TIBCO Enterprise Message Service (EMS) 支持在由 TIBCO EMS 的 BizTalk 适配器传输到 EMS 的消息中使用不同的字符编码。</span><span class="sxs-lookup"><span data-stu-id="3bbac-103">TIBCO Enterprise Message Service (EMS) supports different character encoding in the messages transmitted to EMS by BizTalk Adapter for TIBCO EMS.</span></span> <span data-ttu-id="3bbac-104">消息是使用默认的 UTF-8 进行编码的。</span><span class="sxs-lookup"><span data-stu-id="3bbac-104">Messages are encoded using the default UTF-8 encoding.</span></span> <span data-ttu-id="3bbac-105">当接收消息，适配器确定消息编码，以及提供到的消息之前将相应的字符串转换为 utf-8 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3bbac-105">When receiving messages, the adapter determines the encoding of the message and converts the appropriate strings to UTF-8 before providing the message to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="3bbac-106">所有字符转换都使用 Microsoft .NET Framework 类；因此，适配器支持通过此相同框架转换字符。</span><span class="sxs-lookup"><span data-stu-id="3bbac-106">All character conversions use the Microsoft .NET Framework classes; therefore the adapter supports the character conversions provided by this same framework.</span></span>  
  
## <a name="running-in-a-clustered-environment"></a><span data-ttu-id="3bbac-107">在群集环境中运行</span><span class="sxs-lookup"><span data-stu-id="3bbac-107">Running in a Clustered Environment</span></span>  
 <span data-ttu-id="3bbac-108">发布到队列消息由 EMS 服务器预先确定的顺序的使用者 — 在群集中的只有一个适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中接收的消息。</span><span class="sxs-lookup"><span data-stu-id="3bbac-108">Messages published to queues are consumed by the consumers in an order pre-determined by the EMS server—only one adapter in the clustered [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment receives the message.</span></span> <span data-ttu-id="3bbac-109">队列可以配置为*独占*。</span><span class="sxs-lookup"><span data-stu-id="3bbac-109">The queue can be configured as *exclusive*.</span></span> <span data-ttu-id="3bbac-110">这意味着只有注册自身以使用该队列中的消息的第一个适配器接收消息。</span><span class="sxs-lookup"><span data-stu-id="3bbac-110">This means that only the first adapter that registers itself for message consumption on the queue receives the messages.</span></span> <span data-ttu-id="3bbac-111">仅当独占使用者未确认接收到消息时，EMS 服务器才将消息发送给其他使用者。</span><span class="sxs-lookup"><span data-stu-id="3bbac-111">The EMS server only sends messages to the other consumers if the exclusive consumer does not acknowledge message reception.</span></span> <span data-ttu-id="3bbac-112">独占队列配置是在 EMS 配置中执行的，不能在客户端对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="3bbac-112">Exclusive queue configuration is performed in the EMS configuration and is not client configurable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3bbac-113">有关主题的订阅： 因为中的所有适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组配置相同，它们所有订阅的消息，以及每个主题订阅接收消息。</span><span class="sxs-lookup"><span data-stu-id="3bbac-113">Regarding subscriptions to topics: because all adapters in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group are configured identically, they are all subscribed for the message, and each topic subscription receives the message.</span></span>  
  
## <a name="transaction-support"></a><span data-ttu-id="3bbac-114">事务支持</span><span class="sxs-lookup"><span data-stu-id="3bbac-114">Transaction Support</span></span>  
 <span data-ttu-id="3bbac-115">当业务流程发送端口需要时，适配器将为事务提供支持。</span><span class="sxs-lookup"><span data-stu-id="3bbac-115">The adapter provides support for transactions when required by the orchestration send ports.</span></span> <span data-ttu-id="3bbac-116">当适配器侦听消息时，EMS 服务器并不支持任何事务；但是，将消息成功提交到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 后，适配器将确认从 EMS 接收到所有消息。</span><span class="sxs-lookup"><span data-stu-id="3bbac-116">There is no transaction support with the EMS server when the adapter is listening for messages; however, the adapter acknowledges reception of all messages from EMS after successful message submission to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="3bbac-117">EMS 将未经确认的消息重新发送到适配器。</span><span class="sxs-lookup"><span data-stu-id="3bbac-117">EMS resends unacknowledged messages to the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bbac-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3bbac-118">See Also</span></span>  
 <span data-ttu-id="3bbac-119">[用于 TIBCO EMS 的 BizTalk Adapter 中的安全性](../core/security-in-biztalk-adapter-for-tibco-ems.md) </span><span class="sxs-lookup"><span data-stu-id="3bbac-119">[Security in BizTalk Adapter for TIBCO EMS](../core/security-in-biztalk-adapter-for-tibco-ems.md) </span></span>  
 [<span data-ttu-id="3bbac-120">入门</span><span class="sxs-lookup"><span data-stu-id="3bbac-120">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)