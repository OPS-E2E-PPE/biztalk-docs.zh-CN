---
title: "运行时，消息修复、 FIN 响应和消息传送 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, about architecture
- architecture
- BizTalk Accelerator for SWIFT, architecture
ms.assetid: c7f34517-6663-44a6-b6ea-6d55fdb08caf
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 539d6f6d7a2b84262750f8b3c6da3c16a67f0de9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="runtime-message-repair-fin-response-and-messaging"></a><span data-ttu-id="1fff7-102">运行时、 消息修复、 FIN 响应和消息传送</span><span class="sxs-lookup"><span data-stu-id="1fff7-102">Runtime, message repair, FIN response, and messaging</span></span>

## <a name="overview"></a><span data-ttu-id="1fff7-103">概述</span><span class="sxs-lookup"><span data-stu-id="1fff7-103">Overview</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="1fff7-104">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]提供客户和合作伙伴财务行业特定消息传送和连接功能，这有助于加快实施[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为财务组织的中间件。</span><span class="sxs-lookup"><span data-stu-id="1fff7-104"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides customers and partners with financial-industry-specific messaging and connectivity functionality, which helps accelerate implementation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] as middleware for financial organizations.</span></span>  
  
 <span data-ttu-id="1fff7-105">通过利用开放标准基于工具和运行时功能的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]若要实现对 SWIFT 类似的消息格式的支持，A4SWIFT 可以减少屏障到采用更新 SWIFT 标准通过采用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为通用中间件集成平台。</span><span class="sxs-lookup"><span data-stu-id="1fff7-105">By leveraging the open-standards based tools and runtime facilities of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] to implement support for message formats like SWIFT, A4SWIFT reduces the barrier to adoption of updated SWIFT standards by employing [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] as a general-purpose middleware integration platform.</span></span>  
  
 <span data-ttu-id="1fff7-106">A4SWIFT 和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]减少同时，还通过减少交付应用程序宿主和集成以及工作流的类服务器的企业的总体维护和支持成本降低总拥有成本 (TCO) 到市场时间金融服务行业中的实现。</span><span class="sxs-lookup"><span data-stu-id="1fff7-106">A4SWIFT and [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] reduce the time-to-market while also decreasing the total cost of ownership (TCO) by reducing the overall maintenance and support cost of delivering enterprise class servers for application hosting and integration as well as workflow implementation in the financial services industry.</span></span>  
  
 <span data-ttu-id="1fff7-107">你可以广泛的分类与 SWIFT 消息传送和 SWIFT 连接 A4SWIFT 功能。</span><span class="sxs-lookup"><span data-stu-id="1fff7-107">You can broadly categorize A4SWIFT functionality as SWIFT messaging and SWIFT connectivity.</span></span> <span data-ttu-id="1fff7-108">消息传送的完整 A4SWIFT 结合了分析的 SWIFT 消息和验证 （包括入站/出站批处理）、 消息项和修复 (其中包括与集成[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]作为前端用户工具)，和其他的业务线 (LOB) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1fff7-108">Full A4SWIFT messaging encompasses SWIFT message parsing and validation (including inbound/outbound batching), message entry and repair (including integration with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] as the front-end user tool), and other line-of-business (LOB) applications.</span></span>  
  
 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]<span data-ttu-id="1fff7-109">可提供 XSD 架构和完整的验证，包括网络规则，所有 358 的财务 (FIN) 消息。</span><span class="sxs-lookup"><span data-stu-id="1fff7-109"> provides XSD schemas and full validation, including network rules, for all 358 of the financial (FIN) messages.</span></span> <span data-ttu-id="1fff7-110">它还提供入站 debatching。</span><span class="sxs-lookup"><span data-stu-id="1fff7-110">It also provides inbound debatching.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="1fff7-111">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1fff7-111">Next steps</span></span>  
 <span data-ttu-id="1fff7-112">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="1fff7-112">This section contains:</span></span>  
  
-   <span data-ttu-id="1fff7-113">组件[](components.md)</span><span class="sxs-lookup"><span data-stu-id="1fff7-113">[Components](components.md)</span></span>  
  
-   [<span data-ttu-id="1fff7-114">BizTalk Accelerator for SWIFT 运行时</span><span class="sxs-lookup"><span data-stu-id="1fff7-114">BizTalk Accelerator for SWIFT Runtime</span></span>](biztalk-accelerator-for-swift-runtime.md)  
  
-   [<span data-ttu-id="1fff7-115">消息修复和新的提交</span><span class="sxs-lookup"><span data-stu-id="1fff7-115">Message Repair and New Submission</span></span>](message-repair-and-new-submission.md)  
  
-   [<span data-ttu-id="1fff7-116">FIN 响应对帐</span><span class="sxs-lookup"><span data-stu-id="1fff7-116">FIN Response Reconciliation</span></span>](fin-response-reconciliation.md)  
  
-   [<span data-ttu-id="1fff7-117">SWIFT 消息</span><span class="sxs-lookup"><span data-stu-id="1fff7-117">SWIFT Messages</span></span>](swift-messages.md)

- [<span data-ttu-id="1fff7-118">A4SWIFT_ * 提升属性</span><span class="sxs-lookup"><span data-stu-id="1fff7-118">A4SWIFT_* Promoted Properties</span></span>](a4swift-promoted-properties.md)