---
title: TIBCO Rendezvous 适配器体系结构 |Microsoft Docs
description: 了解用于 TIBCO Rendezvous 的工作原理，包括传递消息，BizTalk Server 中的 BizTalk 适配器
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 174d6ceb-8e1d-4c93-827d-8155cfe47836
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d368e27dd0652753d223fa15b7c82d8ddbbe8b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359014"
---
# <a name="architecture-of-the-tibco-rendezvous-adapter"></a><span data-ttu-id="66ab6-103">TIBCO Rendezvous 适配器的体系结构</span><span class="sxs-lookup"><span data-stu-id="66ab6-103">Architecture of the TIBCO Rendezvous adapter</span></span>

## <a name="overview"></a><span data-ttu-id="66ab6-104">概述</span><span class="sxs-lookup"><span data-stu-id="66ab6-104">Overview</span></span>
<span data-ttu-id="66ab6-105">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器提供之间的双向连接[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 TIBCO Rendezvous。</span><span class="sxs-lookup"><span data-stu-id="66ab6-105">Microsoft BizTalk Adapter for TIBCO Rendezvous provides bi-directional connectivity between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and TIBCO Rendezvous.</span></span> <span data-ttu-id="66ab6-106">此适配器使用 TIBCO Rendezvous API 和 BizTalk 适配器框架 API 来提供紧密集成。</span><span class="sxs-lookup"><span data-stu-id="66ab6-106">This adapter uses both the TIBCO Rendezvous API and the BizTalk Adapter Framework API to provide tight integration.</span></span>  
  
 <span data-ttu-id="66ab6-107">TIBCO Rendezvous 是可用于企业应用程序集成 (EAI) 提供消息总线的软件产品。</span><span class="sxs-lookup"><span data-stu-id="66ab6-107">TIBCO Rendezvous is a software product that provides a message bus for enterprise application integration (EAI).</span></span> <span data-ttu-id="66ab6-108">TIBCO 提供消息传送 Api 在 C 中， C++、 Java、 Visual Basic 和 Microsoft.NET Framework，才能接收 Microsoft Office Excel 工作表和所选的其他应用程序上的数据馈送。</span><span class="sxs-lookup"><span data-stu-id="66ab6-108">TIBCO provides messaging APIs in C, C++, Java, Visual Basic and the Microsoft .NET Framework to receive data feeds on Microsoft Office Excel worksheets and other applications of choice.</span></span>  
  
## <a name="message-passing"></a><span data-ttu-id="66ab6-109">消息传递</span><span class="sxs-lookup"><span data-stu-id="66ab6-109">Message Passing</span></span>  
 <span data-ttu-id="66ab6-110">消息传递的基本概念是相当简单：</span><span class="sxs-lookup"><span data-stu-id="66ab6-110">The basic concept of message passing is fairly simple:</span></span>  
  
- <span data-ttu-id="66ab6-111">消息具有单个主题，其中用句点分隔的元素组成。</span><span class="sxs-lookup"><span data-stu-id="66ab6-111">A message has a single subject composed of elements separated by periods.</span></span> <span data-ttu-id="66ab6-112">（尽管它最终可能其他守护程序广播），它是发送到单个的 Rendezvous 后台程序。</span><span class="sxs-lookup"><span data-stu-id="66ab6-112">It is sent to a single Rendezvous daemon (though it might eventually be broadcast onto other daemons).</span></span>  
  
- <span data-ttu-id="66ab6-113">侦听器宣布其感兴趣的后台程序 （使用基本的通配符工具） 的主题，并具有匹配主题的消息将传送到它，如果两个守护程序连接，或者它们实际上是同一个守护程序。</span><span class="sxs-lookup"><span data-stu-id="66ab6-113">A listener announces its subjects of interest to a daemon (with a basic wildcard facility), and messages that have matching subjects are delivered to it if the two daemons are 'connected' to each other, or are indeed the same daemon.</span></span> <span data-ttu-id="66ab6-114">有关详细信息，请参阅中的消息[适用于 TIBCO Rendezvous 的 BizTalk 适配器中的消息](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md)。</span><span class="sxs-lookup"><span data-stu-id="66ab6-114">For more information, see Messages in [Messages in BizTalk Adapter for TIBCO Rendezvous](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md).</span></span>  
  
  <span data-ttu-id="66ab6-115">下图显示用于 TIBCO Rendezvous 的 BizTalk 适配器体系结构。</span><span class="sxs-lookup"><span data-stu-id="66ab6-115">The following figure shows the architecture for BizTalk Adapter for TIBCO Rendezvous.</span></span>  
  
  <span data-ttu-id="66ab6-116">![](../core/media/tibcorend-arch.gif "TibcoRend_Arch")</span><span class="sxs-lookup"><span data-stu-id="66ab6-116">![](../core/media/tibcorend-arch.gif "TibcoRend_Arch")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66ab6-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="66ab6-117">See Also</span></span>  
 [<span data-ttu-id="66ab6-118">入门</span><span class="sxs-lookup"><span data-stu-id="66ab6-118">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)  