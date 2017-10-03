---
title: "BizTalk Server EDI 功能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9fd91569-f246-40dc-acb1-4f9296479296
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c259b3f46105afc0cf164ec0781c2c0d8f1f226b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-server-edi-functionality"></a><span data-ttu-id="6be53-102">BizTalk Server EDI 功能</span><span class="sxs-lookup"><span data-stu-id="6be53-102">BizTalk Server EDI Functionality</span></span>
[!INCLUDE[prague](../includes/prague-md.md)]<span data-ttu-id="6be53-103"> 使用组合使用核心 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 功能和特定于 EDI [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 功能处理 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="6be53-103"> processes EDI messages using a combination of core [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features and EDI-specific [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features.</span></span> <span data-ttu-id="6be53-104">这使得 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 既可以执行 EDI 消息传送独有的处理，同时又可以利用其核心消息传送功能。</span><span class="sxs-lookup"><span data-stu-id="6be53-104">This enables [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to perform the processing that is unique to EDI messaging, while leveraging its core messaging functionality.</span></span>  
  
 <span data-ttu-id="6be53-105">本部分介绍基本 EDI 消息工作原理以及 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 如何执行。</span><span class="sxs-lookup"><span data-stu-id="6be53-105">This section describes how basic EDI messaging works and how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implements it.</span></span> <span data-ttu-id="6be53-106">还介绍 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的贸易合作伙协议定义如何用于 EDI 消息、接收端 EDI 处理和发送端 EDI 处理。</span><span class="sxs-lookup"><span data-stu-id="6be53-106">It also describes how a trading partner agreement definition in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can be leveraged for EDI messaging, receive-side EDI processing, and send-side EDI processing.</span></span>  
  
 <span data-ttu-id="6be53-107">有关如何将 EDI 处理支持中的说明[!INCLUDE[prague](../includes/prague-md.md)]和其他版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，和 EDI 标准支持和 EDI 文档架构支持的说明，请参阅[EDI 支持问题](../core/edi-support-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="6be53-107">For a description of how EDI processing is supported in [!INCLUDE[prague](../includes/prague-md.md)] and other versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and for a description of EDI standards support and EDI document schema support, see [EDI Support Issues](../core/edi-support-issues.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6be53-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="6be53-108">In This Section</span></span>  
  
-   [<span data-ttu-id="6be53-109">在 BizTalk Server EDI 支持</span><span class="sxs-lookup"><span data-stu-id="6be53-109">EDI Support in BizTalk Server</span></span>](../core/edi-support-in-biztalk-server1.md)  
  
-   [<span data-ttu-id="6be53-110">BizTalk Server 中的 HIPAA 支持</span><span class="sxs-lookup"><span data-stu-id="6be53-110">HIPAA Support in BizTalk Server</span></span>](../core/hipaa-support-in-biztalk-server.md)  
  
-   [<span data-ttu-id="6be53-111">BizTalk Server 中的 EDI 处理</span><span class="sxs-lookup"><span data-stu-id="6be53-111">EDI Processing in BizTalk Server</span></span>](../core/edi-processing-in-biztalk-server.md)  
  
-   [<span data-ttu-id="6be53-112">EDI 支持问题</span><span class="sxs-lookup"><span data-stu-id="6be53-112">EDI Support Issues</span></span>](../core/edi-support-issues.md)  
  
## <a name="see-also"></a><span data-ttu-id="6be53-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6be53-113">See Also</span></span>  
 <span data-ttu-id="6be53-114">[BizTalk Server AS2 功能](../core/biztalk-server-as2-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="6be53-114">[BizTalk Server AS2 Functionality](../core/biztalk-server-as2-functionality.md) </span></span>  
 <span data-ttu-id="6be53-115">[EDI 解决方案体系结构](../core/edi-solution-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="6be53-115">[EDI Solution Architecture](../core/edi-solution-architecture.md) </span></span>  
 [<span data-ttu-id="6be53-116">开发和配置 BizTalk Server EDI 解决方案</span><span class="sxs-lookup"><span data-stu-id="6be53-116">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)