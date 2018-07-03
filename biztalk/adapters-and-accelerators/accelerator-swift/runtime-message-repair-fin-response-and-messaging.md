---
title: 运行时，消息修复、 FIN 响应和消息传送 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, about architecture
- architecture
- BizTalk Accelerator for SWIFT, architecture
ms.assetid: c7f34517-6663-44a6-b6ea-6d55fdb08caf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 360a2e3974f1e4ea5858c583c5dc5fcc364e9756
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974630"
---
# <a name="runtime-message-repair-fin-response-and-messaging"></a><span data-ttu-id="77d18-102">运行时、 消息修复、 FIN 响应和消息传送</span><span class="sxs-lookup"><span data-stu-id="77d18-102">Runtime, message repair, FIN response, and messaging</span></span>

## <a name="overview"></a><span data-ttu-id="77d18-103">概述</span><span class="sxs-lookup"><span data-stu-id="77d18-103">Overview</span></span>
<span data-ttu-id="77d18-104">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]提供了客户和合作伙伴与金融行业特定消息传送和连接功能，可帮助加速实现[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]为金融机构的中间件。</span><span class="sxs-lookup"><span data-stu-id="77d18-104">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides customers and partners with financial-industry-specific messaging and connectivity functionality, which helps accelerate implementation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] as middleware for financial organizations.</span></span>  
  
 <span data-ttu-id="77d18-105">通过利用开放标准基于工具和运行时的设施[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]实现对等 SWIFT 消息格式的支持，A4SWIFT 可减小屏障的采用更新 SWIFT 标准采用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为了常规用途中间件的集成平台。</span><span class="sxs-lookup"><span data-stu-id="77d18-105">By leveraging the open-standards based tools and runtime facilities of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] to implement support for message formats like SWIFT, A4SWIFT reduces the barrier to adoption of updated SWIFT standards by employing [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] as a general-purpose middleware integration platform.</span></span>  
  
 <span data-ttu-id="77d18-106">A4SWIFT 和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]减少同时，还通过减少交付应用程序托管的集成，以及工作流的类服务器的企业的总体的维护和支持成本降低总成本 (tco) 到市场的时间金融服务行业中的实现。</span><span class="sxs-lookup"><span data-stu-id="77d18-106">A4SWIFT and [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] reduce the time-to-market while also decreasing the total cost of ownership (TCO) by reducing the overall maintenance and support cost of delivering enterprise class servers for application hosting and integration as well as workflow implementation in the financial services industry.</span></span>  
  
 <span data-ttu-id="77d18-107">您可以广泛的分类与 SWIFT 消息传送和 SWIFT 连接 A4SWIFT 功能。</span><span class="sxs-lookup"><span data-stu-id="77d18-107">You can broadly categorize A4SWIFT functionality as SWIFT messaging and SWIFT connectivity.</span></span> <span data-ttu-id="77d18-108">完整 A4SWIFT 消息传递结合了 SWIFT 消息解析和验证 （包括入站/出站批处理）、 消息项和修复 (包括与 Microsoft 集成[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]作为前端用户工具)，和其他的业务线 (LOB) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="77d18-108">Full A4SWIFT messaging encompasses SWIFT message parsing and validation (including inbound/outbound batching), message entry and repair (including integration with Microsoft [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] as the front-end user tool), and other line-of-business (LOB) applications.</span></span>  
  
 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]<span data-ttu-id="77d18-109"> 提供的 XSD 架构和完全验证，包括网络规则，所有 358 的财务 (FIN) 消息。</span><span class="sxs-lookup"><span data-stu-id="77d18-109"> provides XSD schemas and full validation, including network rules, for all 358 of the financial (FIN) messages.</span></span> <span data-ttu-id="77d18-110">它还提供入站解除批处理。</span><span class="sxs-lookup"><span data-stu-id="77d18-110">It also provides inbound debatching.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="77d18-111">后续步骤</span><span class="sxs-lookup"><span data-stu-id="77d18-111">Next steps</span></span>  
 <span data-ttu-id="77d18-112">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="77d18-112">This section contains:</span></span>  
  
-   [<span data-ttu-id="77d18-113">组件</span><span class="sxs-lookup"><span data-stu-id="77d18-113">Components</span></span>](components.md)  
  
-   [<span data-ttu-id="77d18-114">BizTalk Accelerator for SWIFT 运行时</span><span class="sxs-lookup"><span data-stu-id="77d18-114">BizTalk Accelerator for SWIFT Runtime</span></span>](biztalk-accelerator-for-swift-runtime.md)  
  
-   [<span data-ttu-id="77d18-115">消息修复和新提交</span><span class="sxs-lookup"><span data-stu-id="77d18-115">Message Repair and New Submission</span></span>](message-repair-and-new-submission.md)  
  
-   [<span data-ttu-id="77d18-116">FIN 响应对帐</span><span class="sxs-lookup"><span data-stu-id="77d18-116">FIN Response Reconciliation</span></span>](fin-response-reconciliation.md)  
  
-   [<span data-ttu-id="77d18-117">SWIFT 消息</span><span class="sxs-lookup"><span data-stu-id="77d18-117">SWIFT Messages</span></span>](swift-messages.md)

- [<span data-ttu-id="77d18-118"> A4SWIFT_\* 的已提升属性</span><span class="sxs-lookup"><span data-stu-id="77d18-118">A4SWIFT_\* Promoted Properties</span></span>](a4swift-promoted-properties.md)