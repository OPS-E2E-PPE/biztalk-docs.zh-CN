---
title: 规划数据库测试 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a4cf5e1f-a960-4702-a050-a2cdacddcbca
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3849b68af9fdd4e457a8e1e492134a87dc1655bd
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010134"
---
# <a name="planning-for-database-testing"></a>计划测试数据库
全面的压力负载测试的 BizTalk 解决方案中的图表突出解决方案 ultimate 成功与否。 由于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能所依赖的性能因此[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库、 测试和优化 BizTalk 解决方案经常侧重于测试和运行的计算机的优化[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]容纳[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。  
  
## <a name="considerations-when-planning-for-database-testing"></a>规划数据库测试时的注意事项  
 规划数据库测试时，请考虑以下方法：  
  
1.  **确保测试环境与生产环境尽可能真实地匹配。** 使用适用于单元测试的虚拟环境，例如 Microsoft HYPER-V Server 2008 是完全可以接受;但是，应对尽可能匹配最终生产环境的硬件执行所有负载/压力测试。  
  
2.  **计划度量值最大可持续吞吐量和 BizTalk Server 系统最大可持续跟踪吞吐量**。 最大可持续吞吐量被指 BizTalk Server 系统可以在生产中无限期地处理的消息流量的最高负载。 请按照 BizTalk Server 帮助中的以下主题中的步骤操作：  
  
    -   [衡量最大可持续引擎吞吐量](http://go.microsoft.com/fwlink/?LinkID=154388)(http://go.microsoft.com/fwlink/?LinkID=154388)。  
  
    -   [衡量最大可持续跟踪吞吐量](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID=153815)。  
  
     这些主题描述用于生成针对系统、 应进行衡量，参数和一般建议在测试 MST 时应遵循的负载的方法。  
  
3.  **了解如何影响 BizTalk Server**  
     **实现限制的主机。** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]限制算法的主机尝试进行的工作负荷的中等[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机实例以确保工作负荷不超过的主机实例的容量或任何下游托管实例。 此限制的机制是自我调整和默认配置选项都适用于大多数[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理方案。 但是，应，具有更好地理解实现负载/压力测试前的限制机制。 有关详细信息，请参阅[优化资源使用通过主机限制](http://go.microsoft.com/fwlink/?LinkId=155770)(http://go.microsoft.com/fwlink/?LinkId=155770) BizTalk Server 帮助中。