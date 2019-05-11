---
title: 在 WCF LOB 适配器 SDK 中查看支持的消息交换模式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6662f17-b4f8-45fe-a22f-5d027dc9f2ff
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eca67c0f5ebbb3220ebd6d1a836cc37f271df9ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362652"
---
# <a name="view-the-supported-message-exchange-patterns-in-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="b887b-102">在 WCF LOB 适配器 SDK 中查看支持的消息交换模式</span><span class="sxs-lookup"><span data-stu-id="b887b-102">View the supported message exchange patterns in the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="b887b-103">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]支持多个消息传递模式支持由基础[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]包括请求-答复和单向通信。</span><span class="sxs-lookup"><span data-stu-id="b887b-103">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] supports several of the messaging patterns supported by the underlying [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] including request-reply, and one-way communication.</span></span> <span data-ttu-id="b887b-104">不同的传输支持不同的消息传递模式，并因而会影响它们支持的交互的类型。</span><span class="sxs-lookup"><span data-stu-id="b887b-104">Different transports support different messaging patterns, and thus affect the types of interactions that they support.</span></span>  
  
 <span data-ttu-id="b887b-105">下表中列出的模式将由[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b887b-105">The patterns listed in the following table are handled by the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span>  
  
|<span data-ttu-id="b887b-106">模式</span><span class="sxs-lookup"><span data-stu-id="b887b-106">Pattern</span></span>|<span data-ttu-id="b887b-107">Description</span><span class="sxs-lookup"><span data-stu-id="b887b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b887b-108">单向入站</span><span class="sxs-lookup"><span data-stu-id="b887b-108">One-way inbound</span></span>|<span data-ttu-id="b887b-109">入站的消息业务线系统收到但无响应预期来自适配器。</span><span class="sxs-lookup"><span data-stu-id="b887b-109">Inbound messages are received from the line-of-business system but no response is expected from the adapter.</span></span>|  
|<span data-ttu-id="b887b-110">请求-响应入站</span><span class="sxs-lookup"><span data-stu-id="b887b-110">Request-response inbound</span></span>|<span data-ttu-id="b887b-111">入站的消息接收从业务线系统需要来自适配器的相应响应。</span><span class="sxs-lookup"><span data-stu-id="b887b-111">Inbound messages are received from the line-of-business system which expects an appropriate response from the adapter.</span></span>|  
|<span data-ttu-id="b887b-112">单向出站</span><span class="sxs-lookup"><span data-stu-id="b887b-112">One-way outbound</span></span>|<span data-ttu-id="b887b-113">出站消息发送到业务线系统，但无响应预期来自适配器。</span><span class="sxs-lookup"><span data-stu-id="b887b-113">Outbound messages are sent to the line-of-business system but no response is expected from the adapter.</span></span>|  
|<span data-ttu-id="b887b-114">请求-响应出站</span><span class="sxs-lookup"><span data-stu-id="b887b-114">Request-response outbound</span></span>|<span data-ttu-id="b887b-115">出站消息与预期来自适配器的响应发送到业务线系统。</span><span class="sxs-lookup"><span data-stu-id="b887b-115">Outbound messages are sent to the line-of-business system with a response expected from the adapter.</span></span>|  
|<span data-ttu-id="b887b-116">会话通道入站</span><span class="sxs-lookup"><span data-stu-id="b887b-116">Sessionful inbound</span></span>|<span data-ttu-id="b887b-117">唯一的会话中，从业务线系统接收入站的消息。</span><span class="sxs-lookup"><span data-stu-id="b887b-117">Inbound messages are received from the line-of-business system within a unique session.</span></span> <span data-ttu-id="b887b-118">通过从适配器的业务线系统预期无响应。</span><span class="sxs-lookup"><span data-stu-id="b887b-118">No response is expected by the line-of-business system from the adapter.</span></span>|  
|<span data-ttu-id="b887b-119">出站会话通道</span><span class="sxs-lookup"><span data-stu-id="b887b-119">Sessionful outbound</span></span>|<span data-ttu-id="b887b-120">出站消息发送到业务线系统内的唯一会话。</span><span class="sxs-lookup"><span data-stu-id="b887b-120">Outbound messages are sent to the line-of-business system within a unique session.</span></span> <span data-ttu-id="b887b-121">适配器从业务线系统预期无响应。</span><span class="sxs-lookup"><span data-stu-id="b887b-121">No response is expected from the line-of-business system by the adapter.</span></span>|  
  
 <span data-ttu-id="b887b-122">所选的消息模式需要根据目标应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="b887b-122">Your choice of message pattern will be guided by the functionality of the target application.</span></span>  
  
## <a name="planning-for-sessions"></a><span data-ttu-id="b887b-123">规划的会话</span><span class="sxs-lookup"><span data-stu-id="b887b-123">Planning for Sessions</span></span>  
 <span data-ttu-id="b887b-124">消息传送模式可能会使用它时想要确保在适配器和业务线系统之间交换的所有消息都必须属于同一会话的会话。</span><span class="sxs-lookup"><span data-stu-id="b887b-124">A messaging pattern may use a session when it wants to ensure that all messages exchanged between the adapter and the line-of-business system must be part of the same conversation.</span></span> <span data-ttu-id="b887b-125">通常使用会话时需要传递保证，但它们还可用于支持适配器开发人员可能有其他要求消息交换。</span><span class="sxs-lookup"><span data-stu-id="b887b-125">Typically sessions are used when delivery guarantee is needed, but they can also be used to support other requirements that an adapter developer may have for message exchange.</span></span>  
  
 <span data-ttu-id="b887b-126">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]依赖于[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]会话支持。</span><span class="sxs-lookup"><span data-stu-id="b887b-126">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] relies on the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] for session support.</span></span> <span data-ttu-id="b887b-127">有关会话的详细信息，请参阅[会话、 实例存储功能和并发](https://msdn.microsoft.com/library/ms731193.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b887b-127">For more information about sessions, see [Sessions, Instancing, and Concurrency](https://msdn.microsoft.com/library/ms731193.aspx).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b887b-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="b887b-128">See Also</span></span>  
 [<span data-ttu-id="b887b-129">规划和设计适配器使用 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="b887b-129">Plan and design an adapter using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)