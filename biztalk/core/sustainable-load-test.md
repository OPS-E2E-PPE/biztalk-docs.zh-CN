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
ms.openlocfilehash: d17d8d38323f7933c8e60cb2b87e0ec312d270c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015646"
---
# <a name="sustainable-load-test"></a>可持续负载测试
本主题中的信息中所述的测试是指[测量的引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md)。  
  
 对于第一个测试，系统将驱动到 MST，以便可以观察运行状况良好的系统。  
  
 下图显示了使用此方法找到测试系统的最大可承受吞吐量后的关键指标。  
  
 **可承受负载测试的负载状况**  
  
 ![性能监视器测量可承受负载](../core/media/bts06-sustainable-load.gif "BTS06_Sustainable_Load")  
  
 从此图中可以看出，在测试时间内，后台处理深度非常稳定并且没有增长：  
  
- 图顶部的黑线表示系统每秒收到的全部消息（例如，两个接收服务器）。  
  
- 图底部的线表示每个 SQL Server 的 MessageBox 后台处理深度。  
  
  一旦系统驱动到最大稳定后台处理深度点，就会根据每秒收到的消息数来度量 MST。 对于此方案，在描述的硬件上，MST 已达到每秒 290 条消息。  
  
> [!NOTE]
>  如果系统驱动到某个点，在该点上后台处理深度经过一段时间后不再稳定，则说明已超出 MST。 对于评估最大负载，需要基于不同的负载进行若干测试，而在此最大负载上，后台处理深度可以保持稳定，并且系统可在不产生其他消息积压的情况下处理消息积压。  
  
 所有 BizTalk 部署性能分析部分均应包括检查某些关键指标以了解资源瓶颈。 用于运行于最大可承受吞吐量下的此部署的关键度量及其度量值如下所示：  
  
 **CPU 使用率**  
  
|“服务器”|平均 CPU 使用率|  
|------------|-----------------------------|  
|BizTalk Server|55%|  
|SQL Server（主 MessageBox 服务器）|76%|  
|SQL Server（其他 MessageBox 服务器）|83%|  
  
 **物理磁盘空闲时间**  
  
|“服务器”|平均磁盘空闲时间|  
|------------|----------------------------|  
|用于所有 SQL Server 的平均值|69%|  
  
 **SQL Server 上的 SQL 锁**  
  
|参数|ReplTest1|  
|---------------|-----------|  
|每秒平均总锁定超时（每个 SQL Server）|1980|  
|平均总锁定等待时间（毫秒）|495|  
  
 在此测试期间，在 BizTalk 或 SQL Server 应用程序日志中未生成任何错误。  
  
 通过此数据，我们可以得出以下结论：  
  
- 在我们的系统中没有明显的资源瓶颈。  
  
- 所有这些指标均处于运行状况良好的范围内。  
  
- CPU 和磁盘空闲时间显示存在大量余量，甚至没有接近限定标准。  
  
- SQL 锁指标美观**Lock Timeouts/sec**不会启动以会成为问题之前解决 5000 左右 （具体取决于您的 SQL Server) 并锁定等待时间在 1 秒以下也很正常。  
  
  我们已介绍了如何确定最大可承受吞吐量以及可承受、运行状况良好的系统的关键指标，现在，让我们来探讨与接收速度快于处理速度和垃圾回收速度的系统相关联的某些行为。 请继续执行[据以加快负载测试](../core/overdrive-load-test.md)。  
  
## <a name="see-also"></a>请参阅  
 [测量引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md)   
 [过载测试](../core/overdrive-load-test.md)