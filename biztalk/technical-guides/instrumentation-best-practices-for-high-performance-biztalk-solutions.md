---
title: "检测的高性能 BizTalk 解决方案的最佳实践 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd16ea1e-055a-429b-912f-bff2b91f0fdb
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ef6f243f894071aebb0089f063ed0242ee09d9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="instrumentation-best-practices-for-high-performance-biztalk-solutions"></a><span data-ttu-id="d8f66-102">检测的高性能 BizTalk 解决方案的最佳实践</span><span class="sxs-lookup"><span data-stu-id="d8f66-102">Instrumentation Best Practices for High Performance BizTalk Solutions</span></span>
<span data-ttu-id="d8f66-103">若要下载本白皮书的副本，请转到[http://go.microsoft.com/fwlink/?LinkId=205874](http://go.microsoft.com/fwlink/?LinkId=205874)。</span><span class="sxs-lookup"><span data-stu-id="d8f66-103">To download a copy of this paper, go to [http://go.microsoft.com/fwlink/?LinkId=205874](http://go.microsoft.com/fwlink/?LinkId=205874).</span></span>  
  
 <span data-ttu-id="d8f66-104">**发布日期：** 2010 年 11 月</span><span class="sxs-lookup"><span data-stu-id="d8f66-104">**Published:** November 2010</span></span>  
  
 <span data-ttu-id="d8f66-105">**作者：** Valery Mizonov、 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="d8f66-105">**Author:** Valery Mizonov, Microsoft Corporation</span></span>  
  
 <span data-ttu-id="d8f66-106">**审阅者：**</span><span class="sxs-lookup"><span data-stu-id="d8f66-106">**Reviewed By:**</span></span>  
  
-   <span data-ttu-id="d8f66-107">Mark Simms、 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="d8f66-107">Mark Simms, Microsoft Corporation</span></span>  
  
-   <span data-ttu-id="d8f66-108">Jayanthi Sampathkumar，Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="d8f66-108">Jayanthi Sampathkumar, Microsoft Corporation</span></span>  
  
-   <span data-ttu-id="d8f66-109">Krish Srinivasan，Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="d8f66-109">Krish Srinivasan, Microsoft Corporation</span></span>  
  
 <span data-ttu-id="d8f66-110">**适用于：** Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d8f66-110">**Applies To:** Microsoft BizTalk Server</span></span>  
  
 <span data-ttu-id="d8f66-111">**摘要：**检测 BizTalk 解决方案的传统方法可能不是始终都从性能角度来看最有效。</span><span class="sxs-lookup"><span data-stu-id="d8f66-111">**Summary:** The traditional ways of instrumenting BizTalk solutions may not always be the most effective from a performance standpoint.</span></span> <span data-ttu-id="d8f66-112">常用的检测和跟踪组件利用 Win32 调试 Api 可能介绍潜在瓶颈，并可负责压力下运行的多线程 BizTalk 应用程序中的性能下降。</span><span class="sxs-lookup"><span data-stu-id="d8f66-112">The commonly used instrumentation and tracing components leveraging the Win32 Debugging APIs may introduce a potential bottleneck and become responsible for performance degradations in multi-threaded BizTalk applications running under stress.</span></span>  
  
 <span data-ttu-id="d8f66-113">从另一侧，源代码检测提供更大程度的可见性的应用程序行为，并有助于降低总体故障排除工作。</span><span class="sxs-lookup"><span data-stu-id="d8f66-113">From the other side, source code instrumentation delivers a great degree of visibility into the application behavior and helps reduce the overall troubleshooting efforts.</span></span> <span data-ttu-id="d8f66-114">因此，一种全新到检测的高性能 BizTalk 解决方案变得至关重要的一点是重要，以启用与几乎无开销并且不会影响非侵入性的方式收集的丰富且详细的诊断信息上的应用程序性能。</span><span class="sxs-lookup"><span data-stu-id="d8f66-114">Consequently, a fundamentally new approach to instrumenting high performance BizTalk solutions has become crucially important to enable collecting the rich and detailed diagnostic information in a non-intrusive manner with virtually no overhead and no impact on the application performance.</span></span>  
  
 <span data-ttu-id="d8f66-115">[Windows Server AppFabric 客户咨询团队](http://blogs.msdn.com/appfabriccat)microsoft 旨在提供社区的经验证的最佳做法，以帮助 BizTalk 开发人员扩充其解决方案的高性能检测内部采用由许多 Microsoft 产品。</span><span class="sxs-lookup"><span data-stu-id="d8f66-115">The [Windows Server AppFabric Customer Advisory Team](http://blogs.msdn.com/appfabriccat) at Microsoft aimed to provide the community with validated best practices to help BizTalk developers enrich their solutions with the high-performance instrumentation internally adopted by many Microsoft products.</span></span> <span data-ttu-id="d8f66-116">这些最佳做法使在一个可重用的框架，它 BizTalk 开发人员可以轻松插入和采用其自己的实现中的窗体中反映出来。</span><span class="sxs-lookup"><span data-stu-id="d8f66-116">These best practices have been reflected in the form of a reusable framework which BizTalk developers can easily plug in and adopt in their own implementations.</span></span>  
  
 <span data-ttu-id="d8f66-117">你可以下载的完整副本[检测的高性能 BizTalk 解决方案的最佳实践](http://go.microsoft.com/fwlink/?LinkId=205874)(http://go.microsoft.com/fwlink/?LinkId=205874) 在 Microsoft 下载中心上。</span><span class="sxs-lookup"><span data-stu-id="d8f66-117">You can download a complete copy of [Instrumentation Best Practices for High Performance BizTalk Solutions](http://go.microsoft.com/fwlink/?LinkId=205874) (http://go.microsoft.com/fwlink/?LinkId=205874) on the Microsoft Download Center.</span></span>