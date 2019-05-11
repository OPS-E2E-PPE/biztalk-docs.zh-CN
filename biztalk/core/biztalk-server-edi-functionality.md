---
title: BizTalk Server EDI 功能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9fd91569-f246-40dc-acb1-4f9296479296
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 282fcc0c2845245035e9d850c2e6fbf315e90301
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530438"
---
# <a name="biztalk-server-edi-functionality"></a><span data-ttu-id="41f9d-102">BizTalk Server EDI 功能</span><span class="sxs-lookup"><span data-stu-id="41f9d-102">BizTalk Server EDI Functionality</span></span>
<span data-ttu-id="41f9d-103">BizTalk Server 处理 EDI 消息使用的核心组合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]功能和特定于 EDI 的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]功能。</span><span class="sxs-lookup"><span data-stu-id="41f9d-103">BizTalk Server processes EDI messages using a combination of core [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features and EDI-specific [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features.</span></span> <span data-ttu-id="41f9d-104">这使[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以执行 EDI 消息传送，同时利用其核心消息传送功能独有的处理。</span><span class="sxs-lookup"><span data-stu-id="41f9d-104">This enables [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to perform the processing that is unique to EDI messaging, while leveraging its core messaging functionality.</span></span>  
  
 <span data-ttu-id="41f9d-105">本部分介绍基本 EDI 消息的工作原理以及如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]实现它。</span><span class="sxs-lookup"><span data-stu-id="41f9d-105">This section describes how basic EDI messaging works and how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implements it.</span></span> <span data-ttu-id="41f9d-106">它还介绍了如何中的贸易合作伙伴协议定义[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以用于 EDI 消息传递、 接收端 EDI 处理和发送端 EDI 处理。</span><span class="sxs-lookup"><span data-stu-id="41f9d-106">It also describes how a trading partner agreement definition in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can be leveraged for EDI messaging, receive-side EDI processing, and send-side EDI processing.</span></span>  
  
 <span data-ttu-id="41f9d-107">有关 EDI 处理的支持在 BizTalk Server 和其他版本的中的说明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，以及有关 EDI 标准支持和 EDI 文档架构支持的说明，请参阅[EDI 支持问题](../core/edi-support-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="41f9d-107">For a description of how EDI processing is supported in BizTalk Server and other versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and for a description of EDI standards support and EDI document schema support, see [EDI Support Issues](../core/edi-support-issues.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="41f9d-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="41f9d-108">In This Section</span></span>  
  
-   [<span data-ttu-id="41f9d-109">BizTalk Server 中的 EDI 支持</span><span class="sxs-lookup"><span data-stu-id="41f9d-109">EDI Support in BizTalk Server</span></span>](../core/edi-support-in-biztalk-server1.md)  
  
-   [<span data-ttu-id="41f9d-110">BizTalk Server 中的 HIPAA 支持</span><span class="sxs-lookup"><span data-stu-id="41f9d-110">HIPAA Support in BizTalk Server</span></span>](../core/hipaa-support-in-biztalk-server.md)  
  
-   [<span data-ttu-id="41f9d-111">BizTalk Server 中的 EDI 处理</span><span class="sxs-lookup"><span data-stu-id="41f9d-111">EDI Processing in BizTalk Server</span></span>](../core/edi-processing-in-biztalk-server.md)  
  
-   [<span data-ttu-id="41f9d-112">EDI 支持问题</span><span class="sxs-lookup"><span data-stu-id="41f9d-112">EDI Support Issues</span></span>](../core/edi-support-issues.md)  
  
## <a name="see-also"></a><span data-ttu-id="41f9d-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="41f9d-113">See Also</span></span>  
 <span data-ttu-id="41f9d-114">[BizTalk Server AS2 功能](../core/biztalk-server-as2-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="41f9d-114">[BizTalk Server AS2 Functionality](../core/biztalk-server-as2-functionality.md) </span></span>  
 <span data-ttu-id="41f9d-115">[EDI 解决方案体系结构](../core/edi-solution-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="41f9d-115">[EDI Solution Architecture](../core/edi-solution-architecture.md) </span></span>  
 [<span data-ttu-id="41f9d-116">开发和配置 BizTalk Server EDI 解决方案</span><span class="sxs-lookup"><span data-stu-id="41f9d-116">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)