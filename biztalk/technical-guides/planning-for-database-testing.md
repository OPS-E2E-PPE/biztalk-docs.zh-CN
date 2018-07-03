---
title: 规划数据库测试 |Microsoft Docs
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
ms.openlocfilehash: bce48244f67fd757fae5c2657634274625677850
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996614"
---
# <a name="planning-for-database-testing"></a>规划数据库测试
全面的压力负载测试的 BizTalk 解决方案中的图表突出的最终成功或失败的解决方案。 由于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能所依赖的性能因此[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库、 测试和优化 BizTalk 解决方案通常侧重于测试和运行的计算机的优化[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]容纳[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。  
  
## <a name="considerations-when-planning-for-database-testing"></a>规划数据库测试时的注意事项  
 规划数据库测试时，请考虑以下方法：  
  
1. **确保测试环境与生产环境尽可能真实地匹配。** 使用如 Microsoft HYPER-V Server 2008 的虚拟环境进行单元测试是完全可以接受;但是，所有负载/压力测试都应该在针对尽可能接近地匹配最终生产环境的硬件。  
  
2. **计划度量值最大可承受吞吐量和 BizTalk Server 系统的最大可承受跟踪吞吐量**。 最大可承受吞吐量的衡量标准 BizTalk Server 系统可在生产环境中无限制处理的消息流量的最高负载。 请按照在 BizTalk Server 帮助中的以下主题中的步骤操作：  
  
   - [测量最大可承受引擎吞吐量](http://go.microsoft.com/fwlink/?LinkID=154388)(http://go.microsoft.com/fwlink/?LinkID=154388)。  
  
   - [测量最大可承受跟踪吞吐量](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID=153815)。  
  
     这些主题描述用于生成系统，应该度量的参数和一般建议在测试 MST 时应遵循针对负载的方法。  
  
3. **了解如何影响 BizTalk Server**  
    **实现主机阻止。** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机阻止算法尝试中等的工作负荷[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机实例以确保负载没有超过主机实例的容量或任何下游主机实例。 该阻止机制具有自我优化和默认配置选项都适用于大多数[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理方案。 但是，应该具有的限制机制实现负载/压力测试之前更好地理解。 有关详细信息，请参阅[优化资源使用情况通过主机阻止](http://go.microsoft.com/fwlink/?LinkId=155770)(<http://go.microsoft.com/fwlink/?LinkId=155770>) 在 BizTalk Server 帮助。