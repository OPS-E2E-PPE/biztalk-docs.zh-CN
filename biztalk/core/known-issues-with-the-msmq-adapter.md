---
title: 使用 MSMQ 适配器的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce77cdac-79c1-4529-8f09-0fb1f87ca037
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4accec1f9bed8ade9270e0c33e868e55c6a21942
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752557"
---
# <a name="known-issues-with-the-msmq-adapter"></a>MSMQ 适配器已知问题
本部分包含可帮助你避免出现错误的信息。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="msmq-adapter-receive-locations-do-not-process-documents"></a>MSMQ 适配器接收位置不处理文档  
  
##### <a name="problem"></a>问题  
 MSMQ 适配器接收位置不处理文档。  
  
##### <a name="cause"></a>原因  
 如果与运行 MSMQ 适配器接收处理程序的 BizTalk 主机实例相关联的 .NET 线程池中没有足够的线程，则 MSMQ 适配器接收位置将由于线程不足而无法处理文档。  
  
##### <a name="resolution"></a>解决方法  
 若要增加的主机实例的.NET 线程池的可用线程数，请按照中的步骤**宿主 CLR 宿主线程值**主题的部分[该影响适配器的配置参数性能](../core/configuration-parameters-that-affect-adapter-performance.md)。  
  
 由于每个 MSMQ 接收位置绑定到 MSMQ 接收处理程序需要.NET 线程池中的线程，设置**MinIOThreads**并**MinWorkerThreads**为值大于或等于MSMQ 接收位置数将绑定到接收处理程序。 相应地，设置的值**MaxIOThreads**并**MaxWorkerThreads**的值等于数 MSMQ 接收位置绑定到接收处理程序\*2，以留出余量：  
  
|DWORD 项|推荐值|  
|-----------------|-----------------------|  
|MaxIOThreads|MSMQ 接收位置绑定到 MSMQ 适配器接收处理程序\*2。|  
|MaxWorkerThreads|MSMQ 接收位置绑定到 MSMQ 适配器接收处理程序\*2。|  
|MinIOThreads|绑定到 MSMQ 适配器接收处理程序的 MSMQ 接收位置数量。|  
|MinWorkerThreads|绑定到 MSMQ 适配器接收处理程序的 MSMQ 接收位置数量。|  
  
 由于这些建议值并不包括主机实例中运行的其他适配器处理程序或业务流程所使用的线程，因此应相应增大这些值。  
  
#### <a name="msmq-adapter-receive-locations-shut-down-shortly-after-they-are-enabled"></a>MSMQ 适配器接收位置在启用后立即关闭  
  
##### <a name="problem"></a>问题  
 MSMQ 接收位置在启用后立即关闭。  
  
##### <a name="cause"></a>原因  
 如果消息队列服务的本地非群集实例没有在 MSMQ 接收处理程序的主机实例所运行的同一台计算机上运行，则可能发生此问题。  
  
##### <a name="resolution"></a>解决方法  
 在 MSMQ 接收处理程序的主机实例所运行的计算机上启动消息队列服务。 MSMQ 适配器接收处理程序要求消息队列服务的本地实例处于运行状态，即使消息队列服务的群集实例在同一台计算机上运行也是如此。  
  
#### <a name="sc-tool-causes-error-when-attempting-to-stop-service-for-host-instance"></a>尝试停止主机实例的服务时，SC 工具导致了错误。  
  
##### <a name="problem"></a>问题  
 尝试使用 SC 工具 (Sc.exe) 关闭 BizTalk 主机实例的服务时，您可能会收到类似于以下内容的错误消息：  
  
 **Control 失败 1053年服务：**  
  
 **该服务未响应及时的开始或控制请求。**  
  
 您收到该错误消息之后，将停止 BizTalk 主机实例的服务。 但是，SC 工具可能需要两分钟或更多时间才能关闭此服务。  
  
 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中启用 Microsoft 消息队列接收位置后，发生了此问题。  
  
 此外，可能会在系统日志中记录类似于以下内容的错误消息：  
  
 **事件类型： 错误**  
  
 **事件源： 服务控制管理器**  
  
 **事件类别： 无**  
  
 **事件 ID: 7011**  
  
 **说明：**  
  
 **超时 （30000 毫秒） 等待来自 BTSSvc$ BizTalkServerApplication 服务的事务响应。**  
  
##### <a name="resolution"></a>解决方法  
 现在可以从 Microsoft 获得受支持的修补程序。 但是，本修补程序仅用于解决本文章中介绍的问题。 仅将此修补程序应用于正经历此特定问题的系统。 此修补程序可能会接收其他测试。 因此，如果您没有严重受到本问题的影响，我们建议您等待包含本修补程序的下一 Service Pack。  
  
 若要解决此问题，请提交请求到 Microsoft 联机客户服务，以获取修补程序。  
  
> [!NOTE]
>  如果发生其他问题或需要任何疑难解答，您可能必须创建一个单独的服务请求。 对于不符合本特定修补程序的其他支持问题，需要支付常规支持费用。  
  
## <a name="see-also"></a>请参阅  
 [MSMQ 适配器故障排除](../core/troubleshooting-the-msmq-adapter.md)