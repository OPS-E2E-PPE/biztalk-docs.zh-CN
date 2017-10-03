---
title: "计划测试 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca2f5f29-9eea-4f4d-9781-75c231db4605
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12bdf5f35d5d612ec077ebdac83339c5a6838109
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-testing"></a>计划测试
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]测试可划分为几个类别包括单元测试、 功能测试、 负载测试和可用性测试。 本主题介绍单元和负载测试以及如何为每个计划。  
  
## <a name="planning-for-unit-testing"></a>规划单元测试  
 单元测试是一个用来验证该单个代码单元的过程工作正常。 可以被认为的单元测试，如"的故障维修"测试： 软件是否执行所需的功能在不同条件下，可以在这些情况下发生的软件句柄错误？  
  
 由于通常在各个组件上执行单元测试，关联的测试平台上不需要实际生产环境的处理能力。 为此，你应该考虑执行需要显著较少的硬件资源的虚拟服务器环境中的单元测试。  
  
 可能在虚拟化环境中执行的单元测试的另一个方面临时。 过渡是单元测试实际部署 BizTalk 解决方案的过程。 若要最大化可用硬件资源，请考虑针对过渡环境中使用虚拟服务器。  
  
 有关使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在虚拟环境中，请参阅[使用虚拟服务器期间发布管理过程](../technical-guides/planning-the-development-testing-staging-and-production-environments.md#BKMK_VirtualServ)。 有关对单元测试 BizTalk 解决方案可能有用的工具的信息，请参阅[测试工具](~/technical-guides/tools-for-testing.md)。 执行单元测试的注意事项的清单，请参阅[执行单元测试](../technical-guides/performing-unit-testing.md)。  
  
## <a name="planning-for-load-testing"></a>规划负载测试  
 负载测试是测量的最大可持续性能并最大可持续跟踪 BizTalk 解决方案的性能，然后删除抑制解决方案的吞吐量的瓶颈的过程。 有关负载测试并消除瓶颈，从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案，请参阅[BizTalk Server 2009 性能指南](http://go.microsoft.com/fwlink/?LinkID=150492)(http://go.microsoft.com/fwlink/?LinkID=150492)。  
  
 有关可用于负载测试 BizTalk 解决方案的工具的信息，请参阅[测试工具](~/technical-guides/tools-for-testing.md)。 负载测试的注意事项的清单，请参阅[执行加载和吞吐量测试](../technical-guides/performing-load-and-throughput-testing.md)。  
  
## <a name="plan-to-test-for-the-lifetime-of-the-solution"></a>向测试计划的生存期内的解决方案  
 尽管单元测试和负载测试在该解决方案的早期阶段是特别重要计划定期测试整个发现可能会随着负载的增加、 新功能或组件的潜在问题的解决方案的生命周期将添加到解决方案。  
  
## <a name="see-also"></a>另请参阅  
 [规划 BizTalk 服务器层](../technical-guides/planning-the-biztalk-server-tier.md)   
 [清单： 测试操作的准备情况](../technical-guides/checklist-testing-operational-readiness.md)