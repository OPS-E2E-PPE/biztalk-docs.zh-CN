---
title: 什么主机限制？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host throttling, outbound
- host throttling, inbound
- host throttling, about host throttling
ms.assetid: 36d1818b-c8a2-4f23-bfb3-c034ee242f69
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 339d67758de45c78434b7c4a9b76e280e67edd60
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394802"
---
# <a name="what-is-host-throttling"></a>什么主机限制？
大部分都发生在 BizTalk server 处理出现在名为 BizTalk Server 主机实例，它是作为 Windows 服务运行的进程或 BizTalk server 上独立的主机进程的逻辑实体。 若要管理的主机实例进程资源的使用，BizTalk Server 使用可调整的阻止机制控制的流和主机实例的消息的处理。  
  
 该阻止机制减少主机实例以确保负载没有超过主机实例或任何下游主机实例的容量的工作负荷。 阻止机制还防止称为资源争用，这可以降低主机实例进程或其他系统进程的整体性能的条件。 当一个或多个进程消耗有限的资源而影响自身和/或另一个进程时，会发生资源争用。 例如，过多的内存或线程的消耗可能会导致内存分配失败或高的线程上下文切换，这可能会影响进程的性能。 此类的资源争用会降低 BizTalk Server 的整体性能。  
  
 主机阻止机制还检测可用资源正在使用不足。 如果可用的资源使用不足的限制机制允许其他消息由主机实例进行处理。 主机阻止机制不断监视可用资源过度或使用不足并且相应地调整通过主机实例的消息流。  
  
 BizTalk Server 主机阻止机制有助于确保系统工作的最佳和可持续级别。  
  
 在 BizTalk Server 管理控制台中基于每个主机设置主机阻止配置参数。 请注意，为主机设置的阻止配置参数不适用于任何或所有接收处理程序、 发送处理程序或业务流程的存在于相应的主机实例中。 如果你想要设置阻止参数，将仅应用于特定接收处理程序，则应执行以下发送处理程序或业务流程：  
  
-   创建新的主机并相应地设置阻止参数。  
  
-   配置接收处理程序、 发送处理程序或在此主机中运行的业务流程。  
  
-   创建要在 BizTalk server 上运行此主机的一个或多个实例。  
  
## <a name="inbound-host-throttling"></a>入站的主机阻止  
 入站的主机阻止，也称为*消息发布阻止功能*在 BizTalk Server 中，应用于包含的主机实例接收适配器或业务流程的消息发布到 MessageBox 数据库。 在以下情况下，可以触发入站的主机阻止条件：  
  
- 的内存量、 线程数或主机实例使用的数据库连接数超过中定义了阻止阈值**设置仪表板**推出的 BizTalk 组和选择**设置**。 这些值是下可用的性能监视器计数器可测量**biztalk: Message Agent**性能对象类别。  
  
- 下游主机将无法处理发布的消息。 这会增加的值**DB 中的消息数**参数。 阈值**DB 中的消息数**值的触发阻止条件是可在配置**主机**选项**设置仪表板**。 在数据库中的消息计数可度量**数据库大小**计数器下**biztalk: Message Agent**性能对象类别。  
  
- **消息发布传入速率**主机实例超出**消息发布传出速率\\*** 指定**加速因子**值。 **加速因子**中定义值**设置仪表板**，**主机**，然后**基于速率的阻止**。 消息发布传入速率和传出速率可通过下的相应性能监视器计数器进行度量**biztalk: Message Agent**性能对象类别。  
  
- 默认阻止行为已被修改。 [BizTalk Server 性能调整为使用设置仪表板](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)描述了影响阻止行为的不同值。  
  
  根据阻止条件的严重性，执行以下操作：  
  
- 实现主机实例的处理逻辑中的渐进式延迟。 当终结点管理器 (EPM) 线程从传输适配器，接收一批消息和/或 EPM 提交要发布到 MessageBox 数据库中的消息批时，可能会实现延迟。 这两个持续时间的处理延迟和的速率的持续时间为递增的随阻止条件的严重性。  
  
- 只有到终结点管理器 (EPM) 可用的线程数。 EPM 从适配器接收消息批，并将消息发布到 MessageBox 数据库。 默认情况下，EPM 配置为使用每个 CPU 的 20 个线程。 如果主机阻止机制检测到压力条件用于入站处理，则可以暂时减少 EPM 可用的线程数，直到繁忙状况结束。 EPM 不能处理来自传输适配器的消息或将消息批传送到 MessageBox 数据库，除非 EPM 线程可用于处理入站的消息批。  
  
- 根据需要的内存和其他资源使用减少。 BizTalk Server 可以将指令发送到其他服务类来限制内存使用，通过冻结正在运行的调度、 缩小内存缓存大小和限制的占用大量内存的线程使用情况。  
  
  **从适配器到 MessageBox 的入站的消息流**  
  
  ![从适配器到 MessageBox 的消息流的入站](../core/media/inboundmsgflow.gif "InboundMsgFlow")  
  
## <a name="outbound-host-throttling"></a>出站主机阻止  
 出站主机阻止，也称为*消息处理阻止*在 BizTalk Server 中，应用于包含业务流程或发送适配器的接收和传送或处理消息，已进行的主机实例发布到 MessageBox。 可以在以下情况下触发出站主机阻止条件：  
  
- 的内存量、 线程数或主机实例使用的数据库连接数超过中定义了阻止阈值**基于资源的阻止**中**设置仪表板**. 这些值是下可用的性能监视器计数器可测量**biztalk: Message Agent**性能对象类别。  
  
- **消息送达传入速率**主机实例超出**消息送达传出速率**\*指定**加速因子**值. **加速因子**上定义值**基于速率的阻止**选项卡中**设置仪表板**。 消息送达传入速率和传出速率可测量的相应性能监视器计数器下**biztalk: Message Agent**性能对象类别。  
  
- 主机实例同时处理的消息数超过**进程内消息数每个 CPU** \*框上可用的 Cpu 数。 **进程内消息数**上定义的阈值**基于资源的阻止**选项卡中**设置仪表板**。 可以使用测量的主机实例同时处理的消息数**进程内消息计数**下的性能计数器**biztalk: Message Agent**性能对象类别。  
  
- 默认阻止行为已被修改。 [BizTalk Server 性能调整为使用设置仪表板](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)描述了影响阻止行为的不同值。  
  
  根据阻止条件的严重性，将执行以下操作：  
  
- 将消息送达的出站传输适配器或业务流程引擎用于处理消息之前，实现主机实例的处理逻辑中的渐进式延迟。 这两个持续时间的速率处理逻辑延迟的持续时间为递增的随阻止条件的严重性。  
  
- 可以保留的内存中队列的消息数会受到限制。 内存中队列充当临时占位符，用于将消息从 MessageBox 到代理，在接着将消息送达到 XLANG 和发送适配器的消息代理。 默认情况下，内存中队列设置保留每个 CPU 的 100 个消息。 如果队列已满，没有任何其他消息会从 MessageBox 取消排队，直到内存中队列得到释放。  
  
- 消息代理线程池的大小被限制。 通过限制消息代理线程池大小，主机阻止机制有效地减少送达到 XLANG 和适配器的消息量。  
  
   可以通过更改修改默认消息代理线程池大小**最大引擎线程**值**常规**选项卡中**设置仪表板**。 有关修改此值的详细信息，请参阅[如何修改常规设置](../core/how-to-modify-general-settings.md)。  
  
- 根据需要的内存和其他资源使用减少。 BizTalk Server 可以将指令发送到其他服务类来限制内存使用，通过冻结正在运行的调度、 缩小内存缓存大小和限制的内存密集型线程使用情况。  
  
  **从 MessageBox 到适配器和 XLANG 的出站消息流**  
  
  ![到适配器和 XLANG 的出站消息流](../core/media/outboundmsgflow.gif "OutboundMsgFlow")  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何实现主机阻止](../core/how-biztalk-server-implements-host-throttling.md)   
 [使用设置仪表板进行 BizTalk Server 性能调整](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)