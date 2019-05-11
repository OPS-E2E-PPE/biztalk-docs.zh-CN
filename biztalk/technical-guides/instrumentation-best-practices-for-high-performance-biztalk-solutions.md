---
title: 高性能 BizTalk 解决方案的检测最佳做法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd16ea1e-055a-429b-912f-bff2b91f0fdb
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b41d67b45c8d3fa18761154e61b449fdf17df9dc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391826"
---
# <a name="instrumentation-best-practices-for-high-performance-biztalk-solutions"></a><span data-ttu-id="4e817-102">高性能 BizTalk 解决方案的检测最佳做法</span><span class="sxs-lookup"><span data-stu-id="4e817-102">Instrumentation Best Practices for High Performance BizTalk Solutions</span></span>
<span data-ttu-id="4e817-103">若要下载本白皮书的副本，请转到[ http://go.microsoft.com/fwlink/?LinkId=205874 ](http://go.microsoft.com/fwlink/?LinkId=205874)。</span><span class="sxs-lookup"><span data-stu-id="4e817-103">To download a copy of this paper, go to [http://go.microsoft.com/fwlink/?LinkId=205874](http://go.microsoft.com/fwlink/?LinkId=205874).</span></span>  
  
 <span data-ttu-id="4e817-104">**发布日期：** 2010 年 11 月</span><span class="sxs-lookup"><span data-stu-id="4e817-104">**Published:** November 2010</span></span>  
  
 <span data-ttu-id="4e817-105">**作者：** Valery Mizonov, Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="4e817-105">**Author:** Valery Mizonov, Microsoft Corporation</span></span>  
  
 <span data-ttu-id="4e817-106">**审阅者：**</span><span class="sxs-lookup"><span data-stu-id="4e817-106">**Reviewed By:**</span></span>  
  
- <span data-ttu-id="4e817-107">Mark Simms, Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="4e817-107">Mark Simms, Microsoft Corporation</span></span>  
  
- <span data-ttu-id="4e817-108">Jayanthi Sampathkumar, Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="4e817-108">Jayanthi Sampathkumar, Microsoft Corporation</span></span>  
  
- <span data-ttu-id="4e817-109">Krish Srinivasan, Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="4e817-109">Krish Srinivasan, Microsoft Corporation</span></span>  
  
  <span data-ttu-id="4e817-110">**适用于：** Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="4e817-110">**Applies To:** Microsoft BizTalk Server</span></span>  
  
  <span data-ttu-id="4e817-111">**摘要：** 传统的检测 BizTalk 解决方案的方法可能始终无法从性能角度来看最有效。</span><span class="sxs-lookup"><span data-stu-id="4e817-111">**Summary:** The traditional ways of instrumenting BizTalk solutions may not always be the most effective from a performance standpoint.</span></span> <span data-ttu-id="4e817-112">常用的检测和跟踪组件利用 Win32 调试 Api 可能会造成潜在瓶颈并让其负责在压力下运行的多线程 BizTalk 应用程序中的性能下降。</span><span class="sxs-lookup"><span data-stu-id="4e817-112">The commonly used instrumentation and tracing components leveraging the Win32 Debugging APIs may introduce a potential bottleneck and become responsible for performance degradations in multi-threaded BizTalk applications running under stress.</span></span>  
  
  <span data-ttu-id="4e817-113">从另一侧，源代码检测提供非常精确地洞察应用程序的行为，并有助于降低整体故障排除工作。</span><span class="sxs-lookup"><span data-stu-id="4e817-113">From the other side, source code instrumentation delivers a great degree of visibility into the application behavior and helps reduce the overall troubleshooting efforts.</span></span> <span data-ttu-id="4e817-114">因此，一种全新检测的高性能 BizTalk 解决方案变得至关重要的一点是重要，以便使用几乎没有开销也不会影响非侵入性的方式收集诊断信息丰富和详细信息对应用程序性能。</span><span class="sxs-lookup"><span data-stu-id="4e817-114">Consequently, a fundamentally new approach to instrumenting high performance BizTalk solutions has become crucially important to enable collecting the rich and detailed diagnostic information in a non-intrusive manner with virtually no overhead and no impact on the application performance.</span></span>  
  
  <span data-ttu-id="4e817-115">[Windows Server AppFabric 客户顾问团队](http://blogs.msdn.com/appfabriccat)microsoft 旨在为社区提供经过验证的最佳实践可帮助扩充其解决方案的高性能检测与 BizTalk 开发人员在内部采用由许多 Microsoft 产品。</span><span class="sxs-lookup"><span data-stu-id="4e817-115">The [Windows Server AppFabric Customer Advisory Team](http://blogs.msdn.com/appfabriccat) at Microsoft aimed to provide the community with validated best practices to help BizTalk developers enrich their solutions with the high-performance instrumentation internally adopted by many Microsoft products.</span></span> <span data-ttu-id="4e817-116">一个可重复使用的框架，BizTalk 开发人员可以轻松地插入，在他们自己的实现中采用的形式有尚未反映这些最佳实践。</span><span class="sxs-lookup"><span data-stu-id="4e817-116">These best practices have been reflected in the form of a reusable framework which BizTalk developers can easily plug in and adopt in their own implementations.</span></span>  
  
  <span data-ttu-id="4e817-117">您可以下载的完整副本[高性能 BizTalk 解决方案的检测最佳做法](http://go.microsoft.com/fwlink/?LinkId=205874)(http://go.microsoft.com/fwlink/?LinkId=205874)从 Microsoft 下载中心获得。</span><span class="sxs-lookup"><span data-stu-id="4e817-117">You can download a complete copy of [Instrumentation Best Practices for High Performance BizTalk Solutions](http://go.microsoft.com/fwlink/?LinkId=205874) (http://go.microsoft.com/fwlink/?LinkId=205874) on the Microsoft Download Center.</span></span>