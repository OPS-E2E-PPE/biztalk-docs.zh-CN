---
title: "用于 TIBCO 会合的 BizTalk Adapter 的体系结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passing messages
- architecture
- message passing
- messages, passing
ms.assetid: 174d6ceb-8e1d-4c93-827d-8155cfe47836
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 801f92453ffc85d83d57c1caa5c89ec618b96ed0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-of-biztalk-adapter-for-tibco-rendezvous"></a><span data-ttu-id="4edeb-102">TIBCO Rendezvous 的 BizTalk 适配器体系结构</span><span class="sxs-lookup"><span data-stu-id="4edeb-102">Architecture of BizTalk Adapter for TIBCO Rendezvous</span></span>
<span data-ttu-id="4edeb-103">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器提供 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与 TIBCO Rendezvous 之间的双向连接。</span><span class="sxs-lookup"><span data-stu-id="4edeb-103">Microsoft BizTalk Adapter for TIBCO Rendezvous provides bi-directional connectivity between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and TIBCO Rendezvous.</span></span> <span data-ttu-id="4edeb-104">此适配器同时使用 TIBCO Rendezvous API 和 BizTalk 适配器框架 API 来提供紧密集成。</span><span class="sxs-lookup"><span data-stu-id="4edeb-104">This adapter uses both the TIBCO Rendezvous API and the BizTalk Adapter Framework API to provide tight integration.</span></span>  
  
 <span data-ttu-id="4edeb-105">TIBCO Rendezvous 是一种为企业应用程序集成 (EAI) 提供消息库的软件产品。</span><span class="sxs-lookup"><span data-stu-id="4edeb-105">TIBCO Rendezvous is a software product that provides a message bus for enterprise application integration (EAI).</span></span> <span data-ttu-id="4edeb-106">TIBCO 提供 C、C++、Java、Visual Basic 和 Microsoft .NET Framework 中的消息传递 API 来接收 Microsoft Office Excel 工作表和所选的其他应用程序中的数据源。</span><span class="sxs-lookup"><span data-stu-id="4edeb-106">TIBCO provides messaging APIs in C, C++, Java, Visual Basic and the Microsoft .NET Framework to receive data feeds on Microsoft Office Excel worksheets and other applications of choice.</span></span>  
  
## <a name="message-passing"></a><span data-ttu-id="4edeb-107">消息传递</span><span class="sxs-lookup"><span data-stu-id="4edeb-107">Message Passing</span></span>  
 <span data-ttu-id="4edeb-108">消息传递的基本概念相当简单：</span><span class="sxs-lookup"><span data-stu-id="4edeb-108">The basic concept of message passing is fairly simple:</span></span>  
  
-   <span data-ttu-id="4edeb-109">消息具有单个主题，其中包含用句点分隔的元素。</span><span class="sxs-lookup"><span data-stu-id="4edeb-109">A message has a single subject composed of elements separated by periods.</span></span> <span data-ttu-id="4edeb-110">它会发送给单个 Rendezvous 守护程序（尽管它最终可能会在其他守护程序中广播）。 </span><span class="sxs-lookup"><span data-stu-id="4edeb-110">It is sent to a single Rendezvous daemon (though it might eventually be broadcast onto other daemons).</span></span>  
  
-   <span data-ttu-id="4edeb-111">侦听器向守护程序公布其感兴趣的主题（使用基本的通配符工具），如果两个守护程序互相“连接”，或者实际是同一个守护程序，则系统会将具有匹配主题的消息传递给该侦听器。</span><span class="sxs-lookup"><span data-stu-id="4edeb-111">A listener announces its subjects of interest to a daemon (with a basic wildcard facility), and messages that have matching subjects are delivered to it if the two daemons are 'connected' to each other, or are indeed the same daemon.</span></span> <span data-ttu-id="4edeb-112">有关详细信息，请参阅中的消息[TIBCO 会合的 BizTalk Adapter 中的消息](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md)。</span><span class="sxs-lookup"><span data-stu-id="4edeb-112">For more information, see Messages in [Messages in BizTalk Adapter for TIBCO Rendezvous](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md).</span></span>  
  
 <span data-ttu-id="4edeb-113">下图显示了用于 TIBCO Rendezvous 的 BizTalk 适配器的体系结构。</span><span class="sxs-lookup"><span data-stu-id="4edeb-113">The following figure shows the architecture for BizTalk Adapter for TIBCO Rendezvous.</span></span>  
  
 ![](../core/media/tibcorend-arch.gif "TibcoRend_Arch")  
  
## <a name="see-also"></a><span data-ttu-id="4edeb-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4edeb-114">See Also</span></span>  
 <span data-ttu-id="4edeb-115">[入门](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="4edeb-115">[Getting Started](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="4edeb-116">规划和体系结构</span><span class="sxs-lookup"><span data-stu-id="4edeb-116">Planning and Architecture</span></span>](../core/planning-and-architecture15.md)