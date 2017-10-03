---
title: "发布阶段建议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5ac72aa-decd-4b3e-be34-e585e54568b3
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46a38a8a06fac8dc35fed4d965ea9b7952c5fdfe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="release-phase-recommendations"></a><span data-ttu-id="173e5-102">发行阶段的建议</span><span class="sxs-lookup"><span data-stu-id="173e5-102">Release Phase Recommendations</span></span>
<span data-ttu-id="173e5-103">发布阶段涉及传播到生产硬件上的现在已验证的系统。</span><span class="sxs-lookup"><span data-stu-id="173e5-103">The release phase involves propagating the now validated system onto the production hardware.</span></span>  
  
## <a name="propagate-test-bed-optimizations-to-production-systems"></a><span data-ttu-id="173e5-104">传播到生产系统的测试平台优化</span><span class="sxs-lookup"><span data-stu-id="173e5-104">Propagate Test Bed Optimizations to Production Systems</span></span>  
 <span data-ttu-id="173e5-105">传播的系统项目和到生产硬件上的配置和达启动过程是一个相对较简单的过程。</span><span class="sxs-lookup"><span data-stu-id="173e5-105">Propagating the system artifacts and configuration onto the production hardware and starting it up to process is a relatively straightforward process.</span></span> <span data-ttu-id="173e5-106">但是，在实践中，有要考虑在此阶段可以轻松地丢失性能有关的事项：</span><span class="sxs-lookup"><span data-stu-id="173e5-106">However, in practice, there are things to consider regarding performance during this phase that can be easily missed:</span></span>  
  
-   <span data-ttu-id="173e5-107">**验证平台优化会传播**。</span><span class="sxs-lookup"><span data-stu-id="173e5-107">**Verify that platform optimizations are propagated**.</span></span> <span data-ttu-id="173e5-108">在实现和验证中，很容易实现任意数量的平台级别的性能优化。</span><span class="sxs-lookup"><span data-stu-id="173e5-108">During implementation and verification, it is common to implement any number of platform level performance optimizations.</span></span>  
  
     <span data-ttu-id="173e5-109">例如，在 Internet 信息服务 (IIS) 上使用诸如 HTTP 这样的独立适配器时，有许多常见的可以使用的性能优化，如在 IIS 中增加适配器将在其中运行的进程数。</span><span class="sxs-lookup"><span data-stu-id="173e5-109">For example, when using an isolated adapter such as HTTP on Internet Information Server (IIS), there are a number of common performance optimizations that can be used such as increasing the number of processes in IIS in which the adapters will run.</span></span> <span data-ttu-id="173e5-110">任何这种性能优化之前必须跟踪版本，且将其传播到生产环境也，找到。</span><span class="sxs-lookup"><span data-stu-id="173e5-110">Any such performance optimizations found before release must be tracked and propagated to the production environment as well.</span></span>  
  
-   <span data-ttu-id="173e5-111">**设置和自动执行数据备份，日志传送，数据保持期配置和清除任务**。</span><span class="sxs-lookup"><span data-stu-id="173e5-111">**Set up and automate data backup, log shipping, data retention configurations, and purging tasks**.</span></span> <span data-ttu-id="173e5-112">作为用于生产环境的认证的一部分，备份和清除数据库的频率（例如，BizTalk 跟踪数据库和 BAM 数据库）是可持续性的关键，因此那些设置必须迁移到它们尚未存在的生产环境。</span><span class="sxs-lookup"><span data-stu-id="173e5-112">As part of certification for production, the frequency at which databases are backed up and purged (for example, the BizTalk Tracking database and BAM database) is key to sustainability so those settings must be migrated to production they don’t already exist there.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="173e5-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="173e5-113">See Also</span></span>  
 <span data-ttu-id="173e5-114">[项目规划阶段的建议](../core/project-planning-recommendations-by-phase.md) </span><span class="sxs-lookup"><span data-stu-id="173e5-114">[Project Planning Recommendations by Phase](../core/project-planning-recommendations-by-phase.md) </span></span>  
 <span data-ttu-id="173e5-115">[要求阶段建议](../core/requirements-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="173e5-115">[Requirements Phase Recommendations](../core/requirements-phase-recommendations.md) </span></span>  
 <span data-ttu-id="173e5-116">[设计阶段建议](../core/design-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="173e5-116">[Design Phase Recommendations](../core/design-phase-recommendations.md) </span></span>  
 <span data-ttu-id="173e5-117">[实现阶段建议](../core/implementation-phase-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="173e5-117">[Implementation Phase Recommendations](../core/implementation-phase-recommendations.md) </span></span>  
 [<span data-ttu-id="173e5-118">验证阶段建议</span><span class="sxs-lookup"><span data-stu-id="173e5-118">Verification Phase Recommendations</span></span>](../core/verification-phase-recommendations.md)