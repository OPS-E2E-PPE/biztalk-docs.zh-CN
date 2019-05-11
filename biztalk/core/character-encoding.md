---
title: 字符编码 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a0c21c8-3318-4533-9734-89302527cb67
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7418a6e6d1321450e0156fedc38fb5cb69a260e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357472"
---
# <a name="character-encoding"></a><span data-ttu-id="00a22-102">字符编码</span><span class="sxs-lookup"><span data-stu-id="00a22-102">Character Encoding</span></span>
<span data-ttu-id="00a22-103">TIBCO Enterprise Message Service (EMS) 支持不同的字符编码中传输到 EMS 的 BizTalk 适配器用于 TIBCO EMS 的消息。</span><span class="sxs-lookup"><span data-stu-id="00a22-103">TIBCO Enterprise Message Service (EMS) supports different character encoding in the messages transmitted to EMS by BizTalk Adapter for TIBCO EMS.</span></span> <span data-ttu-id="00a22-104">使用默认的 utf-8 编码进行编码的消息。</span><span class="sxs-lookup"><span data-stu-id="00a22-104">Messages are encoded using the default UTF-8 encoding.</span></span> <span data-ttu-id="00a22-105">适配器接收消息时，确定消息的编码，并提供到消息前将相应的字符串转换为 utf-8 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="00a22-105">When receiving messages, the adapter determines the encoding of the message and converts the appropriate strings to UTF-8 before providing the message to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="00a22-106">所有字符转换中都使用 Microsoft.NET Framework 类;因此，适配器支持通过此相同框架提供的字符转换。</span><span class="sxs-lookup"><span data-stu-id="00a22-106">All character conversions use the Microsoft .NET Framework classes; therefore the adapter supports the character conversions provided by this same framework.</span></span>  
  
## <a name="running-in-a-clustered-environment"></a><span data-ttu-id="00a22-107">在群集环境中运行</span><span class="sxs-lookup"><span data-stu-id="00a22-107">Running in a Clustered Environment</span></span>  
 <span data-ttu-id="00a22-108">发布到队列的消息使用者以预先确定的 EMS 服务器的顺序使用 — 在群集中的只有一个适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中接收的消息。</span><span class="sxs-lookup"><span data-stu-id="00a22-108">Messages published to queues are consumed by the consumers in an order pre-determined by the EMS server—only one adapter in the clustered [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment receives the message.</span></span> <span data-ttu-id="00a22-109">队列可以配置为*独占*。</span><span class="sxs-lookup"><span data-stu-id="00a22-109">The queue can be configured as *exclusive*.</span></span> <span data-ttu-id="00a22-110">这意味着只有注册自身以使用该队列消息的第一个适配器接收的消息。</span><span class="sxs-lookup"><span data-stu-id="00a22-110">This means that only the first adapter that registers itself for message consumption on the queue receives the messages.</span></span> <span data-ttu-id="00a22-111">EMS 服务器仅将消息发送到其他使用者如果独占使用者未确认已接收到消息。</span><span class="sxs-lookup"><span data-stu-id="00a22-111">The EMS server only sends messages to the other consumers if the exclusive consumer does not acknowledge message reception.</span></span> <span data-ttu-id="00a22-112">独占队列配置在 EMS 配置中执行，而不是可配置的客户端。</span><span class="sxs-lookup"><span data-stu-id="00a22-112">Exclusive queue configuration is performed in the EMS configuration and is not client configurable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00a22-113">关于订阅主题： 因为中的所有适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组的配置都相同，它们都订阅的消息和每个主题订阅接收消息。</span><span class="sxs-lookup"><span data-stu-id="00a22-113">Regarding subscriptions to topics: because all adapters in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group are configured identically, they are all subscribed for the message, and each topic subscription receives the message.</span></span>  
  
## <a name="transaction-support"></a><span data-ttu-id="00a22-114">事务支持</span><span class="sxs-lookup"><span data-stu-id="00a22-114">Transaction Support</span></span>  
 <span data-ttu-id="00a22-115">适配器提供支持的事务时所需的业务流程发送端口。</span><span class="sxs-lookup"><span data-stu-id="00a22-115">The adapter provides support for transactions when required by the orchestration send ports.</span></span> <span data-ttu-id="00a22-116">不没有 EMS 服务器不支持任何事务时该适配器侦听消息;但是，适配器将确认接收到所有消息从 EMS 消息成功提交到后的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="00a22-116">There is no transaction support with the EMS server when the adapter is listening for messages; however, the adapter acknowledges reception of all messages from EMS after successful message submission to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="00a22-117">EMS 重新未确认的消息发送到适配器。</span><span class="sxs-lookup"><span data-stu-id="00a22-117">EMS resends unacknowledged messages to the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00a22-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="00a22-118">See Also</span></span>  
 <span data-ttu-id="00a22-119">[用于 TIBCO EMS 的 BizTalk 适配器中的安全性](../core/security-in-biztalk-adapter-for-tibco-ems.md) </span><span class="sxs-lookup"><span data-stu-id="00a22-119">[Security in BizTalk Adapter for TIBCO EMS](../core/security-in-biztalk-adapter-for-tibco-ems.md) </span></span>  
 [<span data-ttu-id="00a22-120">入门</span><span class="sxs-lookup"><span data-stu-id="00a22-120">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)