---
title: 清单： 测试操作的准备情况 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ecdf2609-ba77-4756-a949-ab4e10c54313
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bc8ff5b2b3ca8d629c30b1cb37f83cb7847b2f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299269"
---
# <a name="checklist-testing-operational-readiness"></a><span data-ttu-id="1dd56-102">清单： 测试操作的准备情况</span><span class="sxs-lookup"><span data-stu-id="1dd56-102">Checklist: Testing Operational Readiness</span></span>
<span data-ttu-id="1dd56-103">对操作的准备情况测试是非常小执行或经常被忽视的重要过程。</span><span class="sxs-lookup"><span data-stu-id="1dd56-103">Testing for operational readiness is a vital procedure that is often overlooked or is performed only minimally.</span></span> <span data-ttu-id="1dd56-104">彻底的测试是一项关键要求的任何企业级别的应用程序，并使用一个解决方案开发[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]也不例外。</span><span class="sxs-lookup"><span data-stu-id="1dd56-104">Thorough testing is a critical requirement of any enterprise-level application, and a solution developed using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is no exception.</span></span> <span data-ttu-id="1dd56-105">至少，你应执行以下测试的将 BizTalk 解决方案移到生产环境之前：</span><span class="sxs-lookup"><span data-stu-id="1dd56-105">At a minimum, you should perform the following testing before moving a BizTalk solution into production:</span></span>  
  
|<span data-ttu-id="1dd56-106">步骤</span><span class="sxs-lookup"><span data-stu-id="1dd56-106">Steps</span></span>|<span data-ttu-id="1dd56-107">参考</span><span class="sxs-lookup"><span data-stu-id="1dd56-107">Reference</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="1dd56-108">单元测试</span><span class="sxs-lookup"><span data-stu-id="1dd56-108">Unit testing</span></span>|[<span data-ttu-id="1dd56-109">执行单元测试</span><span class="sxs-lookup"><span data-stu-id="1dd56-109">Performing Unit Testing</span></span>](../technical-guides/performing-unit-testing.md)|  
|<span data-ttu-id="1dd56-110">功能测试</span><span class="sxs-lookup"><span data-stu-id="1dd56-110">Functional testing</span></span>|[<span data-ttu-id="1dd56-111">执行功能测试</span><span class="sxs-lookup"><span data-stu-id="1dd56-111">Performing Functional Testing</span></span>](../technical-guides/performing-functional-testing.md)|  
|<span data-ttu-id="1dd56-112">瓶颈测试和优化</span><span class="sxs-lookup"><span data-stu-id="1dd56-112">Bottleneck testing and tuning</span></span>|[<span data-ttu-id="1dd56-113">执行测试和优化的瓶颈</span><span class="sxs-lookup"><span data-stu-id="1dd56-113">Performing Bottleneck Testing and Tuning</span></span>](../technical-guides/performing-bottleneck-testing-and-tuning.md)|  
|<span data-ttu-id="1dd56-114">负载测试和最大可持续吞吐量 (MST) 测试</span><span class="sxs-lookup"><span data-stu-id="1dd56-114">Load and maximum sustainable throughput (MST) testing</span></span>|[<span data-ttu-id="1dd56-115">执行负载测试和吞吐量测试</span><span class="sxs-lookup"><span data-stu-id="1dd56-115">Performing Load and Throughput Testing</span></span>](../technical-guides/performing-load-and-throughput-testing.md)|  
|<span data-ttu-id="1dd56-116">可用性测试：</span><span class="sxs-lookup"><span data-stu-id="1dd56-116">Availability testing:</span></span><br /><br /> <span data-ttu-id="1dd56-117">-测试单个硬件组件失败。</span><span class="sxs-lookup"><span data-stu-id="1dd56-117">-   Test individual hardware component failure.</span></span><br /><span data-ttu-id="1dd56-118">-测试[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]失败。</span><span class="sxs-lookup"><span data-stu-id="1dd56-118">-   Test [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] failure.</span></span><br /><span data-ttu-id="1dd56-119">-测试群集节点故障转移。</span><span class="sxs-lookup"><span data-stu-id="1dd56-119">-   Test cluster node failover.</span></span><br /><span data-ttu-id="1dd56-120">-测试恢复[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库使用 SQL Server 日志传送。</span><span class="sxs-lookup"><span data-stu-id="1dd56-120">-   Test recovery of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases using SQL Server log shipping.</span></span>|[<span data-ttu-id="1dd56-121">执行可用性测试</span><span class="sxs-lookup"><span data-stu-id="1dd56-121">Performing Availability Testing</span></span>](../technical-guides/performing-availability-testing.md)|  
  
## <a name="in-this-section"></a><span data-ttu-id="1dd56-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="1dd56-122">In This Section</span></span>  
  
-   [<span data-ttu-id="1dd56-123">执行单元测试</span><span class="sxs-lookup"><span data-stu-id="1dd56-123">Performing Unit Testing</span></span>](../technical-guides/performing-unit-testing.md)  
  
-   [<span data-ttu-id="1dd56-124">执行功能测试</span><span class="sxs-lookup"><span data-stu-id="1dd56-124">Performing Functional Testing</span></span>](../technical-guides/performing-functional-testing.md)  
  
-   [<span data-ttu-id="1dd56-125">执行测试和优化的瓶颈</span><span class="sxs-lookup"><span data-stu-id="1dd56-125">Performing Bottleneck Testing and Tuning</span></span>](../technical-guides/performing-bottleneck-testing-and-tuning.md)  
  
-   [<span data-ttu-id="1dd56-126">执行负载测试和吞吐量测试</span><span class="sxs-lookup"><span data-stu-id="1dd56-126">Performing Load and Throughput Testing</span></span>](../technical-guides/performing-load-and-throughput-testing.md)  
  
-   [<span data-ttu-id="1dd56-127">执行可用性测试</span><span class="sxs-lookup"><span data-stu-id="1dd56-127">Performing Availability Testing</span></span>](../technical-guides/performing-availability-testing.md)  
  
-   [<span data-ttu-id="1dd56-128">用于测试工具</span><span class="sxs-lookup"><span data-stu-id="1dd56-128">Tools for Testing</span></span>](~/technical-guides/tools-for-testing.md)