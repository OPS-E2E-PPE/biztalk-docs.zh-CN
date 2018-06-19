---
title: 计划测试 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ca2f5f29-9eea-4f4d-9781-75c231db4605
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12bdf5f35d5d612ec077ebdac83339c5a6838109
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302357"
---
# <a name="planning-for-testing"></a><span data-ttu-id="3f0ee-102">计划测试</span><span class="sxs-lookup"><span data-stu-id="3f0ee-102">Planning for Testing</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3f0ee-103">测试可划分为几个类别包括单元测试、 功能测试、 负载测试和可用性测试。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-103"> testing can be divided into several categories including unit testing, functional testing, load testing, and availability testing.</span></span> <span data-ttu-id="3f0ee-104">本主题介绍单元和负载测试以及如何为每个计划。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-104">This topic describes unit and load testing and how to plan for each.</span></span>  
  
## <a name="planning-for-unit-testing"></a><span data-ttu-id="3f0ee-105">规划单元测试</span><span class="sxs-lookup"><span data-stu-id="3f0ee-105">Planning for Unit Testing</span></span>  
 <span data-ttu-id="3f0ee-106">单元测试是一个用来验证该单个代码单元的过程工作正常。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-106">Unit testing is a procedure used to validate that individual units of code are working as designed.</span></span> <span data-ttu-id="3f0ee-107">可以被认为的单元测试，如"的故障维修"测试： 软件是否执行所需的功能在不同条件下，可以在这些情况下发生的软件句柄错误？</span><span class="sxs-lookup"><span data-stu-id="3f0ee-107">Unit testing can be thought of as "break/fix" testing: Does the software perform the desired functionality under different conditions and can the software handle errors that occur under these conditions?</span></span>  
  
 <span data-ttu-id="3f0ee-108">由于通常在各个组件上执行单元测试，关联的测试平台上不需要实际生产环境的处理能力。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-108">Since unit testing is typically performed on individual components, the associated test bed does not need the processing capabilities of an actual production environment.</span></span> <span data-ttu-id="3f0ee-109">为此，你应该考虑执行需要显著较少的硬件资源的虚拟服务器环境中的单元测试。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-109">For this reason, you should consider performing unit testing in a Virtual Server environment, which requires considerably fewer hardware resources.</span></span>  
  
 <span data-ttu-id="3f0ee-110">可能在虚拟化环境中执行的单元测试的另一个方面临时。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-110">Another aspect of unit testing that may be performed in a virtualized environment is staging.</span></span> <span data-ttu-id="3f0ee-111">过渡是单元测试实际部署 BizTalk 解决方案的过程。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-111">Staging is the process of unit testing the actual deployment of a BizTalk solution.</span></span> <span data-ttu-id="3f0ee-112">若要最大化可用硬件资源，请考虑针对过渡环境中使用虚拟服务器。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-112">To maximize available hardware resources, consider using Virtual Server for your staging environment.</span></span>  
  
 <span data-ttu-id="3f0ee-113">有关使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在虚拟环境中，请参阅[使用虚拟服务器期间发布管理过程](../technical-guides/planning-the-development-testing-staging-and-production-environments.md#BKMK_VirtualServ)。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-113">For more information about using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a virtual environment, see [Using Virtual Server During the Release Management Process](../technical-guides/planning-the-development-testing-staging-and-production-environments.md#BKMK_VirtualServ).</span></span> <span data-ttu-id="3f0ee-114">有关对单元测试 BizTalk 解决方案可能有用的工具的信息，请参阅[测试工具](~/technical-guides/tools-for-testing.md)。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-114">For information about tools that may be useful for unit testing a BizTalk solution, see [Tools for Testing](~/technical-guides/tools-for-testing.md).</span></span> <span data-ttu-id="3f0ee-115">执行单元测试的注意事项的清单，请参阅[执行单元测试](../technical-guides/performing-unit-testing.md)。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-115">For a checklist of considerations for performing unit testing see [Performing Unit Testing](../technical-guides/performing-unit-testing.md).</span></span>  
  
## <a name="planning-for-load-testing"></a><span data-ttu-id="3f0ee-116">规划负载测试</span><span class="sxs-lookup"><span data-stu-id="3f0ee-116">Planning for Load Testing</span></span>  
 <span data-ttu-id="3f0ee-117">负载测试是测量的最大可持续性能并最大可持续跟踪 BizTalk 解决方案的性能，然后删除抑制解决方案的吞吐量的瓶颈的过程。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-117">Load testing is the process of measuring maximum sustainable performance and maximum sustainable tracking performance of a BizTalk solution and then removing bottlenecks that inhibit the throughput of the solution.</span></span> <span data-ttu-id="3f0ee-118">有关负载测试并消除瓶颈，从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案，请参阅[BizTalk Server 2009 性能指南](http://go.microsoft.com/fwlink/?LinkID=150492)(http://go.microsoft.com/fwlink/?LinkID=150492)。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-118">For more information about load testing and removing bottlenecks from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution, see the [BizTalk Server 2009 Performance Guide](http://go.microsoft.com/fwlink/?LinkID=150492) (http://go.microsoft.com/fwlink/?LinkID=150492).</span></span>  
  
 <span data-ttu-id="3f0ee-119">有关可用于负载测试 BizTalk 解决方案的工具的信息，请参阅[测试工具](~/technical-guides/tools-for-testing.md)。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-119">For information about tools that may be useful for load testing a BizTalk solution, see [Tools for Testing](~/technical-guides/tools-for-testing.md).</span></span> <span data-ttu-id="3f0ee-120">负载测试的注意事项的清单，请参阅[执行加载和吞吐量测试](../technical-guides/performing-load-and-throughput-testing.md)。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-120">For a checklist of considerations for load testing see [Performing Load and Throughput Testing](../technical-guides/performing-load-and-throughput-testing.md).</span></span>  
  
## <a name="plan-to-test-for-the-lifetime-of-the-solution"></a><span data-ttu-id="3f0ee-121">向测试计划的生存期内的解决方案</span><span class="sxs-lookup"><span data-stu-id="3f0ee-121">Plan to Test for the Lifetime of the Solution</span></span>  
 <span data-ttu-id="3f0ee-122">尽管单元测试和负载测试在该解决方案的早期阶段是特别重要计划定期测试整个发现可能会随着负载的增加、 新功能或组件的潜在问题的解决方案的生命周期将添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-122">While unit testing and load testing are particularly important during the early stages of the solution, plan regular testing throughout the lifetime of the solution to uncover potential problems that may occur as load increases or as new functionality or components are added to the solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f0ee-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f0ee-123">See Also</span></span>  
 <span data-ttu-id="3f0ee-124">[规划 BizTalk 服务器层](../technical-guides/planning-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="3f0ee-124">[Planning the BizTalk Server Tier](../technical-guides/planning-the-biztalk-server-tier.md) </span></span>  
 [<span data-ttu-id="3f0ee-125">清单： 测试操作的准备情况</span><span class="sxs-lookup"><span data-stu-id="3f0ee-125">Checklist: Testing Operational Readiness</span></span>](../technical-guides/checklist-testing-operational-readiness.md)