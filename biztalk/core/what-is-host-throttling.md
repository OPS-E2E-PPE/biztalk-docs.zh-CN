---
title: "主机阻止概述 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host throttling, outbound
- host throttling, inbound
- host throttling, about host throttling
ms.assetid: 36d1818b-c8a2-4f23-bfb3-c034ee242f69
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4730a93b6491f53fc06004ca8bb0dcb0d970cc7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-host-throttling"></a>主机阻止概述
在 BizTalk Server 上执行的大部分处理都在称为 BizTalk Server 主机实例的逻辑实体内进行，该逻辑实体是在 BizTalk Server 上以 Windows 服务或独立的主机进程运行的进程。 为了管理主机实例进程使用的资源，BizTalk Server 使用可调整的阻止机制控制消息在主机实例中的传输和处理。  
  
 该阻止机制对主机实例的负载进行调节，以确保负载没有超过主机实例或任何下游主机实例的处理能力。 该阻止机制还防止称为资源争用的情况发生，这种情况会降低主机实例进程或其他系统进程的整体性能。 一个或多个进程消耗有限的资源从而损害进程自身和/或其他进程时，便会出现资源争用的情况。 例如，消耗过量的内存或线程将导致内存分配失败或大量的线程上下文切换，这会影响进程的性能。 这样的资源争用会降低 BizTalk Server 的整体性能。  
  
 主机阻止机制还检测可用资源利用不足的时间。 如果可用的资源未得到充分利用，则阻止机制将允许主机实例处理更多的消息。 主机阻止机制不断监视可用资源是否过度利用或利用不足，并据以调整通过主机实例的消息流。  
  
 BizTalk Server 主机阻止机制有助于确保系统以最佳可持续水平运行。  
  
 在 BizTalk Server 管理控制台中基于每台主机对主机阻止配置参数进行设置。 请注意，为主机设置的阻止配置参数将应用于所有接收处理程序、发送处理程序或相应主机实例中的业务流程。 如果要设置仅应用于特定接收处理程序、发送处理程序或业务流程的阻止参数，则应执行以下操作：  
  
-   创建新主机并相应地设置阻止参数。  
  
-   配置要在此主机中运行的接收处理程序、发送处理程序或业务流程。  
  
-   创建要在 BizTalk Server 上运行的此主机的一个或多个实例。  
  
## <a name="inbound-host-throttling"></a>入站主机阻止  
 入站的主机限制，也称为*消息发布限制*BizTalk Server 中，在应用于包含的主机实例接收适配器或将消息发布到 MessageBox 数据库的业务流程。 以下情况可以触发入站主机阻止条件：  
  
-   内存、 线程，数或主机实例所使用的数据库连接数超出限制中定义的阈值**设置仪表板**可以在 BizTalk 组和选择**设置**。 这些值是与下提供的性能监视器计数器可测量**BizTalk:Message 代理**性能对象类别。  
  
-   下游主机无法处理发布的消息。 这会增加的值**消息在数据库中的计数**参数。 从其阈值**消息在数据库中的计数**值限制条件是可在配置的触发器**主机**选项**设置仪表板**。 可以使用测量数据库中的消息计数**数据库大小**计数器下**BizTalk:Message 代理**性能对象类别。  
  
-   **消息发布传入速率**主机实例超出**消息发布传出速率\***指定**速率 overdrive 因素**值。 **速率 overdrive 因素**值用定义**设置仪表板**，**主机**然后**基于速率限制**。 可以使用在相应的性能监视器计数器测量发布传入和传出费率消息**BizTalk:Message 代理**性能对象类别。  
  
-   默认限制行为已被修改。 [使用 BizTalk Server 性能优化的设置仪表板](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)描述影响限制行为的不同值。  
  
 根据阻止条件的严重性，将执行以下操作：  
  
-   实现主机实例处理逻辑中的渐进式延迟。 端点管理器 (EPM) 线程从传输适配器接收消息批时和/或 EPM 提交要发布到 MessageBox 数据库中的消息批时，实现该延迟。 处理延迟的持续时间和持续时间递增的速率都随阻止条件的严重性而变化。  
  
-   限制可用于端点管理器 (EPM) 的线程数。 EPM 从适配器接收消息批，并将消息发布到 MessageBox 数据库。 默认情况下，EPM 配置为每 CPU 使用 20 个线程。 如果主机阻止机制检测到入站处理的任务繁忙，则可以暂时减少 EPM 可用的线程数，直到繁忙状况结束。 除非 EPM 线程可用于处理入站消息批，否则，EPM 不能处理来自传输适配器的消息或将消息批传送到 MessageBox 数据库。  
  
-   根据需要减少内存和其他资源的使用。 BizTalk Server 可以将说明发送到其他服务类，以通过冻结过程中运行计划，收缩内存缓存大小，并限制占用大量内存的线程的使用情况限制内存使用。  
  
 **从适配器到 MessageBox 的入站的消息流**  
  
 ![入站消息流从适配器到 MessageBox](../core/media/inboundmsgflow.gif "InboundMsgFlow")  
  
## <a name="outbound-host-throttling"></a>出站主机阻止  
 限制，也称为出站主机*消息处理限制*BizTalk Server 中，在应用于包含业务流程或发送接收和传递或处理消息已的适配器的主机实例发布到 MessageBox。 以下情况可以触发出站主机阻止条件：  
  
-   内存、 线程，数或主机实例所使用的数据库连接数超出限制中定义的阈值**基于资源的限制**中**设置仪表板**. 这些值是与下提供的性能监视器计数器可测量**BizTalk:Message 代理**性能对象类别。  
  
-   **消息传送传入速率**主机实例超出**传出速率的消息传递**\*指定**速率 overdrive 因素**值. **速率 overdrive 因素**上定义值**基于速率限制**选项卡中**设置仪表板**。 可以使用相应的性能监视器测量传入和传出费率消息传递计数器下**BizTalk:Message 代理**性能对象类别。  
  
-   由主机实例同时处理消息的数量超过**进程内消息每个 CPU** \*框上的可用 Cpu 数。 **进程内消息**上定义阈值**基于资源的限制**选项卡中**设置仪表板**。 可以使用测量正在由主机实例同时处理的消息数**进程内消息计数**下的性能计数器**BizTalk:Message 代理**性能对象类别。  
  
-   默认限制行为已被修改。 [使用 BizTalk Server 性能优化的设置仪表板](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)描述影响限制行为的不同值。  
  
 根据限制条件的严重性，执行以下操作：  
  
-   在将消息送达到出站传输适配器或业务流程引擎以便进行消息处理之前，实现主机实例处理逻辑中的渐进式延迟。 处理逻辑延迟的持续时间和持续时间递增的速率都随阻止条件的严重性而变化。  
  
-   限制内存中队列可以保留的消息数。 内存中队列充当临时占位符，用于将消息从 MessageBox 送达到消息代理，消息代理接着将消息送达到 XLANG 和发送适配器。 默认情况下，内存中队列设置为每 CPU 保留 100 个消息。 队列已满时，不会再有消息从 MessageBox 中出列，直到内存中队列得到释放。  
  
-   限制消息代理线程池的大小。 通过限制消息代理线程池的大小，主机阻止机制有效地减少送达到 XLANG 和适配器的消息数。  
  
     可通过更改修改默认消息代理线程池大小**引擎的最大线程**值上**常规**选项卡中**设置仪表板**。 有关修改此值的详细信息，请参阅[如何修改常规设置](../core/how-to-modify-general-settings.md)。  
  
-   根据需要减少内存和其他资源的使用。 BizTalk Server 可以向其他服务类别发送指令，通过冻结正在运行的调度、缩小内存缓存大小以及限制使用内存占用量大的线程，来限制内存使用。  
  
 **从 MessageBox 于适配器和 XLANG 的出站消息流**  
  
 ![出站消息流入适配器和 XLANG](../core/media/outboundmsgflow.gif "OutboundMsgFlow")  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 如何实施限制的主机](../core/how-biztalk-server-implements-host-throttling.md)   
 [设置仪表板用于 BizTalk Server 性能优化](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)