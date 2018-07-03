---
title: 执行负载和吞吐量测试 |Microsoft Docs
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
ms.openlocfilehash: 2d4313c073abff7022de99ac1d38375599b6ee43
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966910"
---
# <a name="performing-load-and-throughput-testing"></a>执行负载和吞吐量测试
您应提供匹配的性能和压力测试在生产环境的环境。 此环境应已安装并运行，如监视代理和防病毒软件的所有标准服务。  
  
## <a name="how-adding-applications-affects-load"></a>添加应用程序是如何影响负载  
 您还应测试新的 BizTalk 应用程序和要在生产环境中的相同硬件上运行的其他 BizTalk 应用程序。 这是因为新的 BizTalk 应用程序将额外的负载的计算机上运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SQL Server。 这一点尤其重要根据主机阻止算法中使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 阻止算法监视总的可用资源，因此所产生的新的 BizTalk 应用程序的额外负载可能导致限制条件，这会影响所有正在运行的 BizTalk 应用程序。 有关详细信息，请参阅[如何 BizTalk Server 实现主机阻止](http://go.microsoft.com/fwlink/?LinkId=154389)(<http://go.microsoft.com/fwlink/?LinkId=154389>)。  
  
## <a name="testing-load-and-determining-recovery-time"></a>测试负载和确定恢复时间  
 应测试性能和压力之前将其放到生产环境的所有 BizTalk 应用的程序。 您应该执行测试针对预期负载和峰值负载。 您应确定为 BizTalk 应用程序的最大可承受吞吐量 (MST)。 此外，应确定需要多长时间的峰值负载从恢复的系统。 如果系统没有完全从此峰值负载下一步的峰值负载之前，则系统将以渐进方式更远全力支持，并且不能充分进行恢复。 有关详细信息，请参阅：  
  
-   [测量最大可承受引擎吞吐量](http://go.microsoft.com/fwlink/?LinkId=154388)(http://go.microsoft.com/fwlink/?LinkId=154388)  
  
-   [测量最大可承受跟踪吞吐量](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID=153815)  
  
## <a name="see-also"></a>请参阅  
 [清单：测试操作准备情况](../technical-guides/checklist-testing-operational-readiness.md)