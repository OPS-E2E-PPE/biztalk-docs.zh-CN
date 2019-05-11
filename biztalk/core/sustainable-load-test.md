---
title: 可承受负载测试 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- sustainable load test
- LoadGen tool, sustainable load test
ms.assetid: a9d752ff-aff1-4445-8af5-8f84609880e2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d059f7f2aa29be68ea87d72d9357d01601d2c958
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321775"
---
# <a name="sustainable-load-test"></a>可承受负载测试
本主题中的信息中所述的测试是指[测量的引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md)。  
  
 第一个测试时，系统驱动到 MST，以便可以进行观察系统正常运行。  
  
 下图显示了使用这种方法来查找测试系统的最大可承受吞吐量后的关键指标。  
  
 **可承受负载测试的负载状况**  
  
 ![性能监视器测量可承受负载](../core/media/bts06-sustainable-load.gif "BTS06_Sustainable_Load")  
  
 此图显示，以小时为单位的测试，后台处理深度非常稳定并且没有增长：  
  
- 在关系图的顶部的黑线显示每秒接收的系统 （例如，对于这两个接收服务器） 的消息总数。  
  
- 在关系图底部的线指示每个 SQL 服务器上的 MessageBox 后台处理深度。  
  
  一旦系统驱动到最大稳定后台处理深度点，是每秒接收的消息数来度量 MST。 对于此方案，如所述，在硬件上每秒 290 个消息的 MST 是来实现的。  
  
> [!NOTE]
>  一旦系统驱动到某个点的后台处理深度不再稳定随着时间的推移，说明已超出 MST。 与基于不同的负载的多个测试运行可能需要评估在哪个后台处理深度可以保持稳定的最大负载，您的系统可以处理的消息积压，而不会产生更多的消息积压工作。  
  
 所有 BizTalk 部署性能分析的一部分应包括检查某些关键指标以了解资源瓶颈。 关键度量值和最大可承受吞吐量下运行此部署使用其值是按如下所示：  
  
 **CPU 使用率**  
  
|“服务器”|平均 CPU 利用率|  
|------------|-----------------------------|  
|BizTalk Server|55%|  
|SQL Server (Master MessageBox Server)|76%|  
|SQL Server （其他 MessageBox 服务器）|83%|  
  
 **物理磁盘空闲时间**  
  
|“服务器”|平均磁盘空闲时间|  
|------------|----------------------------|  
|所有 SQL Server 的平均值|69%|  
  
 **SQL Server 上的 SQL 锁**  
  
|参数|ReplTest1|  
|---------------|-----------|  
|平均总锁定超时每个第二个 （每个 SQL Server)|1980|  
|平均总锁定等待时间 （毫秒）|495|  
  
 在此测试期间未在 BizTalk 或 SQL Server 应用程序日志中不生成任何错误。  
  
 通过此数据，我们可以得出以下结论：  
  
- 在我们的系统没有明显的资源瓶颈。  
  
- 所有这些指标是正常的限制范围内良好。  
  
- CPU 和磁盘空闲时间显示没有充足的空间，它们甚至没有接近限定标准。  
  
- SQL 锁指标美观**Lock Timeouts/sec**不会启动以会成为问题之前解决 5000 左右 （具体取决于您的 SQL Server) 并锁定等待时间在 1 秒以下也很正常。  
  
  现在，我们已展示了如何查找最大可承受吞吐量并可承受、 运行正常的系统的关键指标的如下所示，我们来探讨一些速度超过它正在处理和收集接收的系统相关联的行为垃圾回收。 请继续执行[据以加快负载测试](../core/overdrive-load-test.md)。  
  
## <a name="see-also"></a>请参阅  
 [测量引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md)   
 [过载测试](../core/overdrive-load-test.md)