---
title: 据以加快负载测试 |Microsoft Docs
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
ms.openlocfilehash: 734c0dffc64ca7efd52b6325227a26ee0387b50e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393403"
---
# <a name="overdrive-load-test"></a>过载测试
本主题中的信息中所述的测试是指[测量的引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md)。  
  
 负载生成工具 LoadGen 2007 使您可以模拟 BizTalk Server 系统上。  
  
> [!NOTE]
>  下载[LoadGen](https://www.microsoft.com/download/details.aspx?id=14925)。 此工具的以前版本，BizTalk Server 2004 负载生成工具是可在下载[ http://go.microsoft.com/fwlink/?linkid=108999 ](http://go.microsoft.com/fwlink/?linkid=108999)。  
  
 为了模拟连续的过载系统，LoadGen 2007 配置为发送每秒大约 410，120 每秒超过测量的最大可承受吞吐量。  
  
 为了使系统过载不仅要了解从大约 2 万条记录的后台处理积压深度中恢复需要多长时间设计测试。  
  
 若要实现此目的，加速驱动系统，以增加速率直到后台处理深度非常大约 2 万条记录。 一旦后台处理深度达到所需的级别，则不能进一步生成负载。  
  
 若要确保 BizTalk 阻止机制是否不会阻止接收主机会防止后台处理表积压累积， **DB 中的消息数**接收主机已从更改阻止阈值默认值 50000 为 2000000。 有关更改信息**DB 中的消息数**阻止阈值，请参阅[如何修改资源基于阻止设置](../core/how-to-modify-resource-based-throttling-settings.md)。 有关默认主机阻止设置的信息，请参阅[使用设置仪表板进行 BizTalk Server 性能调整](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)。  
  
 下图显示了上图相同的指标。  
  
 **过载测试的负载配置文件**  
  
 ![过载的性能监视器显示](../core/media/bts06-overdrive-load.gif "BTS06_Overdrive_Load")  
  
 从关系图可以看出，后台处理深度会立即开始，在高峰 200 万条记录的正上方。 按照这个频率，花费几乎 2.5 小时达到目标 2 百万记录积压工作。 负载已停止后，花费了大约 8 小时对清除作业从积压中恢复。  
  
## <a name="see-also"></a>请参阅  
 [测量引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md)   
 [使用设置仪表板进行 BizTalk Server 性能优化](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)   
 [可承受负载测试](../core/sustainable-load-test.md)