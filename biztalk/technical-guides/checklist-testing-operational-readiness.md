---
title: 清单：测试操作准备情况 |Microsoft Docs
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
ms.openlocfilehash: c8903e3c8885c846cd6ce810281eeae48e30482c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242583"
---
# <a name="checklist-testing-operational-readiness"></a><span data-ttu-id="50ce5-102">清单：测试操作准备情况</span><span class="sxs-lookup"><span data-stu-id="50ce5-102">Checklist: Testing Operational Readiness</span></span>
<span data-ttu-id="50ce5-103">操作就绪性测试是经常被忽视或只按最小方式执行的重要过程。</span><span class="sxs-lookup"><span data-stu-id="50ce5-103">Testing for operational readiness is a vital procedure that is often overlooked or is performed only minimally.</span></span> <span data-ttu-id="50ce5-104">彻底的测试是一项关键要求的任何企业级别的应用程序，并使用一种解决方案开发[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]也不例外。</span><span class="sxs-lookup"><span data-stu-id="50ce5-104">Thorough testing is a critical requirement of any enterprise-level application, and a solution developed using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is no exception.</span></span> <span data-ttu-id="50ce5-105">至少，应执行以下测试的 BizTalk 解决方案移动到生产环境之前：</span><span class="sxs-lookup"><span data-stu-id="50ce5-105">At a minimum, you should perform the following testing before moving a BizTalk solution into production:</span></span>  


|                                                                                                                                                                                         <span data-ttu-id="50ce5-106">步骤</span><span class="sxs-lookup"><span data-stu-id="50ce5-106">Steps</span></span>                                                                                                                                                                                          |                                                  <span data-ttu-id="50ce5-107">参考</span><span class="sxs-lookup"><span data-stu-id="50ce5-107">Reference</span></span>                                                  |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|
|                                                                                                                                                                                      <span data-ttu-id="50ce5-108">单元测试</span><span class="sxs-lookup"><span data-stu-id="50ce5-108">Unit testing</span></span>                                                                                                                                                                                      |                  [<span data-ttu-id="50ce5-109">执行单元测试</span><span class="sxs-lookup"><span data-stu-id="50ce5-109">Performing Unit Testing</span></span>](../technical-guides/performing-unit-testing.md)                  |
|                                                                                                                                                                                   <span data-ttu-id="50ce5-110">功能测试</span><span class="sxs-lookup"><span data-stu-id="50ce5-110">Functional testing</span></span>                                                                                                                                                                                   |            [<span data-ttu-id="50ce5-111">执行功能测试</span><span class="sxs-lookup"><span data-stu-id="50ce5-111">Performing Functional Testing</span></span>](../technical-guides/performing-functional-testing.md)            |
|                                                                                                                                                                             <span data-ttu-id="50ce5-112">瓶颈测试和优化</span><span class="sxs-lookup"><span data-stu-id="50ce5-112">Bottleneck testing and tuning</span></span>                                                                                                                                                                              | [<span data-ttu-id="50ce5-113">执行瓶颈测试并优化</span><span class="sxs-lookup"><span data-stu-id="50ce5-113">Performing Bottleneck Testing and Tuning</span></span>](../technical-guides/performing-bottleneck-testing-and-tuning.md) |
|                                                                                                                                                                 <span data-ttu-id="50ce5-114">负载和最大可承受吞吐量 (MST) 测试</span><span class="sxs-lookup"><span data-stu-id="50ce5-114">Load and maximum sustainable throughput (MST) testing</span></span>                                                                                                                                                                  |   [<span data-ttu-id="50ce5-115">执行负载和吞吐量测试</span><span class="sxs-lookup"><span data-stu-id="50ce5-115">Performing Load and Throughput Testing</span></span>](../technical-guides/performing-load-and-throughput-testing.md)   |
| <span data-ttu-id="50ce5-116">可用性测试：</span><span class="sxs-lookup"><span data-stu-id="50ce5-116">Availability testing:</span></span><br /><br /> <span data-ttu-id="50ce5-117">-测试单个硬件组件故障。</span><span class="sxs-lookup"><span data-stu-id="50ce5-117">-   Test individual hardware component failure.</span></span><br /><span data-ttu-id="50ce5-118">-测试[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]失败。</span><span class="sxs-lookup"><span data-stu-id="50ce5-118">-   Test [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] failure.</span></span><br /><span data-ttu-id="50ce5-119">-测试群集节点故障转移。</span><span class="sxs-lookup"><span data-stu-id="50ce5-119">-   Test cluster node failover.</span></span><br /><span data-ttu-id="50ce5-120">-测试的恢复[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库使用 SQL Server 日志传送。</span><span class="sxs-lookup"><span data-stu-id="50ce5-120">-   Test recovery of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases using SQL Server log shipping.</span></span> |          [<span data-ttu-id="50ce5-121">执行可用性测试</span><span class="sxs-lookup"><span data-stu-id="50ce5-121">Performing Availability Testing</span></span>](../technical-guides/performing-availability-testing.md)          |

## <a name="in-this-section"></a><span data-ttu-id="50ce5-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="50ce5-122">In This Section</span></span>  

-   [<span data-ttu-id="50ce5-123">执行单元测试</span><span class="sxs-lookup"><span data-stu-id="50ce5-123">Performing Unit Testing</span></span>](../technical-guides/performing-unit-testing.md)  

-   [<span data-ttu-id="50ce5-124">执行功能测试</span><span class="sxs-lookup"><span data-stu-id="50ce5-124">Performing Functional Testing</span></span>](../technical-guides/performing-functional-testing.md)  

-   [<span data-ttu-id="50ce5-125">执行瓶颈测试并优化</span><span class="sxs-lookup"><span data-stu-id="50ce5-125">Performing Bottleneck Testing and Tuning</span></span>](../technical-guides/performing-bottleneck-testing-and-tuning.md)  

-   [<span data-ttu-id="50ce5-126">执行负载和吞吐量测试</span><span class="sxs-lookup"><span data-stu-id="50ce5-126">Performing Load and Throughput Testing</span></span>](../technical-guides/performing-load-and-throughput-testing.md)  

-   [<span data-ttu-id="50ce5-127">执行可用性测试</span><span class="sxs-lookup"><span data-stu-id="50ce5-127">Performing Availability Testing</span></span>](../technical-guides/performing-availability-testing.md)  

-   [<span data-ttu-id="50ce5-128">测试工具</span><span class="sxs-lookup"><span data-stu-id="50ce5-128">Tools for Testing</span></span>](~/technical-guides/tools-for-testing.md)