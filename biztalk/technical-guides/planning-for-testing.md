---
title: 计划测试 |Microsoft Docs
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
ms.openlocfilehash: b386ee074538af7960ca39bfb50c25ac59df1dbb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010278"
---
# <a name="planning-for-testing"></a><span data-ttu-id="8d887-102">规划测试</span><span class="sxs-lookup"><span data-stu-id="8d887-102">Planning for Testing</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="8d887-103"> 测试可以划分为多个类别，包括单元测试、 功能测试、 负载测试，以及可用性测试。</span><span class="sxs-lookup"><span data-stu-id="8d887-103"> testing can be divided into several categories including unit testing, functional testing, load testing, and availability testing.</span></span> <span data-ttu-id="8d887-104">本主题介绍单元和负载测试，以及如何为每个计划。</span><span class="sxs-lookup"><span data-stu-id="8d887-104">This topic describes unit and load testing and how to plan for each.</span></span>  
  
## <a name="planning-for-unit-testing"></a><span data-ttu-id="8d887-105">规划单元测试</span><span class="sxs-lookup"><span data-stu-id="8d887-105">Planning for Unit Testing</span></span>  
 <span data-ttu-id="8d887-106">单元测试是用来验证该单个代码单元的过程工作正常。</span><span class="sxs-lookup"><span data-stu-id="8d887-106">Unit testing is a procedure used to validate that individual units of code are working as designed.</span></span> <span data-ttu-id="8d887-107">单元测试可以被视为"的故障维修服务"测试： 软件不会执行不同条件下所需的功能，可以在这些情况下出现的软件句柄错误？</span><span class="sxs-lookup"><span data-stu-id="8d887-107">Unit testing can be thought of as "break/fix" testing: Does the software perform the desired functionality under different conditions and can the software handle errors that occur under these conditions?</span></span>  
  
 <span data-ttu-id="8d887-108">通常在各个组件上执行单元测试，因为关联的测试平台上不需要实际的生产环境的处理能力。</span><span class="sxs-lookup"><span data-stu-id="8d887-108">Since unit testing is typically performed on individual components, the associated test bed does not need the processing capabilities of an actual production environment.</span></span> <span data-ttu-id="8d887-109">出于此原因，你应该考虑执行需要显著较少的硬件资源的虚拟服务器环境中的单元测试。</span><span class="sxs-lookup"><span data-stu-id="8d887-109">For this reason, you should consider performing unit testing in a Virtual Server environment, which requires considerably fewer hardware resources.</span></span>  
  
 <span data-ttu-id="8d887-110">临时的单元测试可能会在虚拟化环境中执行的另一个方面。</span><span class="sxs-lookup"><span data-stu-id="8d887-110">Another aspect of unit testing that may be performed in a virtualized environment is staging.</span></span> <span data-ttu-id="8d887-111">过渡是单元测试实际部署的 BizTalk 解决方案的过程。</span><span class="sxs-lookup"><span data-stu-id="8d887-111">Staging is the process of unit testing the actual deployment of a BizTalk solution.</span></span> <span data-ttu-id="8d887-112">若要最大化可用硬件资源，请考虑为过渡环境中使用 Virtual Server。</span><span class="sxs-lookup"><span data-stu-id="8d887-112">To maximize available hardware resources, consider using Virtual Server for your staging environment.</span></span>  
  
 <span data-ttu-id="8d887-113">有关使用详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在虚拟环境中，请参阅[使用虚拟服务器在发布管理过程](../technical-guides/planning-the-development-testing-staging-and-production-environments.md#BKMK_VirtualServ)。</span><span class="sxs-lookup"><span data-stu-id="8d887-113">For more information about using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a virtual environment, see [Using Virtual Server During the Release Management Process](../technical-guides/planning-the-development-testing-staging-and-production-environments.md#BKMK_VirtualServ).</span></span> <span data-ttu-id="8d887-114">有关对于单元测试 BizTalk 解决方案可能很有用的工具的信息，请参阅[用于测试工具](~/technical-guides/tools-for-testing.md)。</span><span class="sxs-lookup"><span data-stu-id="8d887-114">For information about tools that may be useful for unit testing a BizTalk solution, see [Tools for Testing](~/technical-guides/tools-for-testing.md).</span></span> <span data-ttu-id="8d887-115">执行单元测试的注意事项的检查表，请参阅[执行单元测试](../technical-guides/performing-unit-testing.md)。</span><span class="sxs-lookup"><span data-stu-id="8d887-115">For a checklist of considerations for performing unit testing see [Performing Unit Testing](../technical-guides/performing-unit-testing.md).</span></span>  
  
## <a name="planning-for-load-testing"></a><span data-ttu-id="8d887-116">规划负载测试</span><span class="sxs-lookup"><span data-stu-id="8d887-116">Planning for Load Testing</span></span>  
 <span data-ttu-id="8d887-117">负载测试是最大可承受性能和最大可承受跟踪 BizTalk 解决方案的性能，然后删除禁止解决方案的吞吐量的瓶颈的过程。</span><span class="sxs-lookup"><span data-stu-id="8d887-117">Load testing is the process of measuring maximum sustainable performance and maximum sustainable tracking performance of a BizTalk solution and then removing bottlenecks that inhibit the throughput of the solution.</span></span> <span data-ttu-id="8d887-118">详细了解负载测试和删除从瓶颈[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案，请参阅[BizTalk Server 2009 性能指南](http://go.microsoft.com/fwlink/?LinkID=150492)(<http://go.microsoft.com/fwlink/?LinkID=150492>)。</span><span class="sxs-lookup"><span data-stu-id="8d887-118">For more information about load testing and removing bottlenecks from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution, see the [BizTalk Server 2009 Performance Guide](http://go.microsoft.com/fwlink/?LinkID=150492) (<http://go.microsoft.com/fwlink/?LinkID=150492>).</span></span>  
  
 <span data-ttu-id="8d887-119">对于负载测试 BizTalk 解决方案可能很有用的工具有关的信息，请参阅[用于测试工具](~/technical-guides/tools-for-testing.md)。</span><span class="sxs-lookup"><span data-stu-id="8d887-119">For information about tools that may be useful for load testing a BizTalk solution, see [Tools for Testing](~/technical-guides/tools-for-testing.md).</span></span> <span data-ttu-id="8d887-120">负载测试的注意事项的检查表，请参阅[执行加载和吞吐量测试](../technical-guides/performing-load-and-throughput-testing.md)。</span><span class="sxs-lookup"><span data-stu-id="8d887-120">For a checklist of considerations for load testing see [Performing Load and Throughput Testing](../technical-guides/performing-load-and-throughput-testing.md).</span></span>  
  
## <a name="plan-to-test-for-the-lifetime-of-the-solution"></a><span data-ttu-id="8d887-121">在解决方案生存期内向测试计划</span><span class="sxs-lookup"><span data-stu-id="8d887-121">Plan to Test for the Lifetime of the Solution</span></span>  
 <span data-ttu-id="8d887-122">而单元测试和负载测试是非常重要的解决方案的早期阶段计划定期测试解决方案，以便随着负载的增加或作为新功能或组件可能出现的潜在问题的整个生存期将添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="8d887-122">While unit testing and load testing are particularly important during the early stages of the solution, plan regular testing throughout the lifetime of the solution to uncover potential problems that may occur as load increases or as new functionality or components are added to the solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d887-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d887-123">See Also</span></span>  
 <span data-ttu-id="8d887-124">[规划 BizTalk Server 层](../technical-guides/planning-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="8d887-124">[Planning the BizTalk Server Tier](../technical-guides/planning-the-biztalk-server-tier.md) </span></span>  
 [<span data-ttu-id="8d887-125">清单：测试操作准备情况</span><span class="sxs-lookup"><span data-stu-id="8d887-125">Checklist: Testing Operational Readiness</span></span>](../technical-guides/checklist-testing-operational-readiness.md)