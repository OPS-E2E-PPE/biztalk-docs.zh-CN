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
ms.openlocfilehash: 1457191c414204f76cdf1c47bedc10f56ce357cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242620"
---
# <a name="planning-for-testing"></a>规划测试
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 测试可以划分为多个类别，包括单元测试、 功能测试、 负载测试，以及可用性测试。 本主题介绍单元和负载测试，以及如何为每个计划。  
  
## <a name="planning-for-unit-testing"></a>规划单元测试  
 单元测试是用来验证该单个代码单元的过程工作正常。 单元测试可以被视为"的故障维修服务"测试：该软件是否执行不同条件下所需的功能和软件是否可以处理这些情况下会发生的错误？  
  
 通常在各个组件上执行单元测试，因为关联的测试平台上不需要实际的生产环境的处理能力。 出于此原因，你应该考虑执行需要显著较少的硬件资源的虚拟服务器环境中的单元测试。  
  
 临时的单元测试可能会在虚拟化环境中执行的另一个方面。 过渡是单元测试实际部署的 BizTalk 解决方案的过程。 若要最大化可用硬件资源，请考虑为过渡环境中使用 Virtual Server。  
  
 有关使用详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在虚拟环境中，请参阅[使用虚拟服务器在发布管理过程](../technical-guides/planning-the-development-testing-staging-and-production-environments.md#BKMK_VirtualServ)。 有关对于单元测试 BizTalk 解决方案可能很有用的工具的信息，请参阅[用于测试工具](~/technical-guides/tools-for-testing.md)。 执行单元测试的注意事项的检查表，请参阅[执行单元测试](../technical-guides/performing-unit-testing.md)。  
  
## <a name="planning-for-load-testing"></a>规划负载测试  
 负载测试是最大可承受性能和最大可承受跟踪 BizTalk 解决方案的性能，然后删除禁止解决方案的吞吐量的瓶颈的过程。 详细了解负载测试和删除从瓶颈[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案，请参阅[BizTalk Server 2009 性能指南](http://go.microsoft.com/fwlink/?LinkID=150492)(<http://go.microsoft.com/fwlink/?LinkID=150492>)。  
  
 对于负载测试 BizTalk 解决方案可能很有用的工具有关的信息，请参阅[用于测试工具](~/technical-guides/tools-for-testing.md)。 负载测试的注意事项的检查表，请参阅[执行加载和吞吐量测试](../technical-guides/performing-load-and-throughput-testing.md)。  
  
## <a name="plan-to-test-for-the-lifetime-of-the-solution"></a>在解决方案生存期内向测试计划  
 而单元测试和负载测试是非常重要的解决方案的早期阶段计划定期测试解决方案，以便随着负载的增加或作为新功能或组件可能出现的潜在问题的整个生存期将添加到解决方案。  
  
## <a name="see-also"></a>请参阅  
 [规划 BizTalk Server 层](../technical-guides/planning-the-biztalk-server-tier.md)   
 [清单：测试操作准备情况](../technical-guides/checklist-testing-operational-readiness.md)