---
title: 执行负载测试和吞吐量测试 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ff86ebd-a77f-4e29-bfea-0306e88bbf67
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3da46b2dc3208208305e60e9efbfadd0c60d7d32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302109"
---
# <a name="performing-load-and-throughput-testing"></a>执行负载测试和吞吐量测试
你应提供与匹配性能和压力测试的生产环境的环境。 此环境应已安装并运行，如监视代理和防病毒软件的所有标准服务。  
  
## <a name="how-adding-applications-affects-load"></a>添加应用程序会负载的影响  
 你还应测试新的 BizTalk 应用程序以及要在生产环境中的相同硬件上运行的其他 BizTalk 应用程序。 这是因为新的 BizTalk 应用程序将额外的负载的计算机上运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SQL Server。 这一点尤其重要限制中使用的算法的主机依照[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 限制算法监视总的可用资源，并因此额外的负载引起新的 BizTalk 应用程序可能导致限制条件，这会影响所有正在运行的 BizTalk 应用程序。 有关详细信息，请参阅[如何 BizTalk Server 实现主机限制](http://go.microsoft.com/fwlink/?LinkId=154389)(http://go.microsoft.com/fwlink/?LinkId=154389)。  
  
## <a name="testing-load-and-determining-recovery-time"></a>测试负载和确定恢复时间  
 你应测试所有 BizTalk 应用程序的性能和压力之前将其放到生产环境。 你应执行测试针对预期负载和峰值负载。 你应该确定 BizTalk 应用程序的最大可持续吞吐量 (MST)。 此外，你应该确定时间系统来恢复从峰值负载。 如果系统未完全恢复从峰值负载之前的下一步的峰值负载发生，则系统会逐渐变得更远，并将不能完全恢复。 有关详细信息，请参阅：  
  
-   [衡量最大可持续引擎吞吐量](http://go.microsoft.com/fwlink/?LinkId=154388)(http://go.microsoft.com/fwlink/?LinkId=154388)  
  
-   [衡量最大可持续跟踪吞吐量](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID=153815)  
  
## <a name="see-also"></a>另请参阅  
 [清单： 测试操作的准备情况](../technical-guides/checklist-testing-operational-readiness.md)