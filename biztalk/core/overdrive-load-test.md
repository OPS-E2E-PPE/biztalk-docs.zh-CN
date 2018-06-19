---
title: 据以加快负载测试 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d16d0a8-4255-4f5a-86a2-26cc11bb9a70
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cff4592c58dd165a85d63666958721231cfcbd4c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007655"
---
# <a name="overdrive-load-test"></a>Overdrive 负载测试
本主题中的信息是指中所述的测试[测试方案的引擎测量 MST](../core/test-scenarios-for-measuring-mst-of-the-engine.md)。  
  
 使用负载生成工具 Loadgen 2007，你可以模拟 BizTalk Server 系统过载时的情况。  
  
> [!NOTE]
>  下载[LoadGen](https://www.microsoft.com/download/details.aspx?id=14925)。 此工具的以前版本，BizTalk Server 2004 负载生成工具是可在下载[http://go.microsoft.com/fwlink/?linkid=108999](http://go.microsoft.com/fwlink/?linkid=108999)。  
  
 为了模拟连续的过载系统，将 LoadGen 2007 配置为每秒大约发送 410 条消息，比测量的最大可承受吞吐量每秒多出 120 条消息。  
  
 该测试不仅是为了使系统过载运行，而且还要了解从大约二百万条记录的后台处理积压深度中恢复需要多长时间。  
  
 为了达到此积压深度，需要加速驱动系统，直到后台处理深度达到大约二百万条记录。 一旦后台处理深度达到所需级别，则不再进一步生成负载。  
  
 若要确保限制机制 BizTalk 未限制接收主机，可能会妨碍的假脱机表积压工作的累积，**消息在数据库中的计数**接收主机已从更改为限制阈值默认值为 2000000 50000。 有关更改信息**消息在数据库中的计数**限制阈值，请参阅[如何修改资源基于限制设置](../core/how-to-modify-resource-based-throttling-settings.md)。 有关限制设置的默认主机的信息，请参阅[BizTalk Server 性能优化使用设置仪表板](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)。  
  
 下图显示了与上图相同的指标。  
  
 **Overdrive 负载测试的负载配置文件**  
  
 ![Overdrive 负荷的性能 montor 显示](../core/media/bts06-overdrive-load.gif "BTS06_Overdrive_Load")  
  
 从图中可以看出，后台处理深度会立即开始增加，在正好超过二百万条记录后达到峰值。 以此速度，它正好用了大约 2.5 小时达到二百万条的目标记录积压量。 在停止增加负载后，清理作业从积压中恢复大约用了 8 小时。  
  
## <a name="see-also"></a>另请参阅  
 [用于测量引擎 MST 测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md)   
 [设置仪表板用于 BizTalk Server 性能优化](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)   
 [可承受负载测试](../core/sustainable-load-test.md)