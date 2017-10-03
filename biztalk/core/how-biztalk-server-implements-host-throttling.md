---
title: "BizTalk Server 如何实施限制的主机 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host throttling, rate based throttling
- host throttling, outbound
- host throttling, algorithm
- host throttling, components
- host throttling, inbound
- host throttling, resource based throttling
- host throttling, user controlled throttling
- host throttling, strategies
ms.assetid: 46d3c3de-66b9-4c8a-8369-e68563fc9c40
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1944b61f9710b02f4e6db18a38972849847c532e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-biztalk-server-implements-host-throttling"></a>BizTalk Server 如何实现主机阻止
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]持续限制机制的主机监视限制条件，计算的重要程度限制条件，并将应用渐进式限制，具体取决于计算严重性的主机。 此限制的机制是自我调整和默认配置选项都适用于大多数[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理方案。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机限制公开可用于优化限制用于特定方案的几个可配置选项。 有关更改这些配置选项的信息，请参阅[如何修改主机设置](../core/how-to-modify-host-settings.md)。  
  
## <a name="components-of-the-host-throttling-algorithm"></a>主机阻止算法的组成部分  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在应用主机阻止时使用以下算法：  
  
1.  持续监视以下参数以确定它们是否超出特定阈值。 如果参数值超出该参数的阈值，则阻止条件成立。  
  
    -   占用的内存量（系统范围的内存和主机进程内存）。  
  
    -   要送达或处理的进程内消息数（用于出站阻止的阈值）。  
  
    -   使用的线程数。  
  
    -   数据库大小，按所有主机队列表中的项数以及后台处理和跟踪表中的项数来衡量。  
  
    -   并行数据库连接数。  
  
    -   消息发布（入站）和送达或处理（出站）速率。  
  
2.  确定阻止条件的严重性。 阻止条件按严重性排列如下（从最严重到最不严重）：  
  
    -   占用的主机进程内存超出阈值。  
  
    -   进程内消息数超出阈值。  
  
    -   使用的线程数超出阈值。  
  
    -   数据库大小超出阈值。  
  
    -   其他所有阻止条件。  
  
3.  基于阻止条件的严重性以渐进方式应用阻止。 随着严重级别的提高，也将更为主动地应用阻止。 渐进式阻止按如下方式来实现：  
  
    -   检测到一个或多个阻止条件并指定严重性。  
  
    -   基于严重性最高的条件发出实现阻止的指令。 根据阻止条件，如果该条件持续存在，则可能会降低各种线程池的大小，并可能会通过冻结正在运行的业务流程来释放内存。  
  
    -   根据消息是入站还是出站，在发布或处理消息时应用延迟。 延迟时间的长短与阻止条件的严重性成比例；因此，与严重性较低的阻止条件相比，严重性较高的阻止条件将会产生更长的阻止时间。 随着阻止条件的变化，将根据阻止机制在特定范围内延长和缩短此延迟时间。 通过公开当前延迟期**消息传递的延迟 (ms)**和**消息发布延迟 (ms)**与关联的性能计数器**BizTalk:Message 代理**性能对象类别。 这些性能对象计数器记录在该主题[主机限制性能计数器](../core/host-throttling-performance-counters.md)。  
  
    -   阻止机制继续检查是否存在阻止条件。 如果阻止条件得以缓解，则取消对阻止的消息的阻止，并允许线程池和其他资源在不受限制的模式下工作。 如果系统继续工作并且不存在任何阻止条件，则将大幅度缩短延迟时间。 如果阻止条件持续存在，则延迟时间将根据该条件的严重性按比例递增，并对后续消息应用更长时间的延迟。  
  
    -   如果延迟时间已过，则将不再进行阻止。  
  
## <a name="type-of-throttling-conditions"></a>阻止条件的类型  
 有三种主要类型的限制条件： 速率基于、 基于，资源和业务流程。  
  
1.  **限制基于费率**划分为两个类别; （已发布） 的入站和出站 （提供）：  
  
    -   对于入站 （已发布） 的消息，BizTalk Server 限制的消息的发布，如果**消息发布传入速率**主机实例超出**消息发布传出速率\***指定**速率 overdrive 因素 （百分比）**值。 **速率 overdrive 因素 （百分比）**参数是可在配置**消息发布限制设置**对话框。 对入站消息进行基于速率的阻止主要是通过在将消息成批发布到 MessageBox 数据库之前引入延迟来实现的。 不会采取其他任何措施来实现对入站消息的基于速率的阻止。  
  
    -   对于出站 （发送） 的消息，BizTalk Server 限制的消息传送，如果**消息传送传入速率**主机实例超出**传出速率的消息传递** \*指定**速率 overdrive 因素 （百分比）**值。 **速率 overdrive 因素 （百分比）**参数是可在配置**消息处理限制设置**对话框。 对出站消息进行基于速率的阻止主要是通过在将消息从内存中队列中删除并将消息送达端点管理器 (EPM) 或业务流程引擎以便进行处理之前引入延迟来实现的。 不会采取其他任何措施来实现对出站消息的基于速率的阻止。  
  
         有关速率 overdrive 因素和其他基于率的限制值的详细信息，请参阅[如何修改速率基于限制设置](../core/how-to-modify-rate-based-throttling-settings.md)。  
  
2.  **基于资源的限制**监视系统资源，如线程、 内存和数据库大小，并可以应用于任何服务类。 有关基于资源的限制值的详细信息，请参阅[如何修改资源基于限制设置](../core/how-to-modify-resource-based-throttling-settings.md)。  
  
3.  **业务流程限制**可以防止冻结和何时暂停/恢复订阅。 有关限制值的业务流程的详细信息，请参阅[如何修改业务流程限制设置](../core/how-to-modify-orchestration-throttling-settings.md)。  
  
## <a name="throttling-condition-triggers-actions-and-mitigation-strategies"></a>阻止条件触发器、操作和缓解策略  
 本部分介绍了各种阻止条件的触发器、阻止机制生成的操作以及可用来缓解阻止条件的措施。  
  
### <a name="inbound-throttling"></a>入站阻止  
 BizTalk 阻止机制对业务流程引擎 (XLANG) 和入站适配器应用入站阻止。  
  
 使用**限制状态消息发布**和**限制状态持续时间的消息发布**与关联的计数器**BizTalk:MessageAgent**性能要测量的当前限制的状态和持续时间限制的对象类别。 有关可用的主机限制性能计数器的详细信息，请参阅[主机限制性能计数器](../core/host-throttling-performance-counters.md)。  
  
 入站阻止可导致入站消息在源积压。 如果对接收适配器应用入站阻止，则接收适配器可能会停止接收消息，直到阻止条件得以缓解。  
  
|消息发布<br /><br /> 阻止状态|阻止条件的触发器|采取的阻止操作|缓解策略|性能对象|性能计数器|  
|---------------------------------------------|--------------------------------------|------------------------------|-------------------------|------------------------|-------------------------|  
|2|**消息发布传入速率**主机实例超出**消息发布传出速率\***指定**速率 overdrive 因素 （百分比）**值。 数据库无法保持发布速率。|在动态计算的时间段内之前阻止发布线程**消息发布的传入速率**位于等同于**消息发布传出速率**\*指定的**速率 overdrive 因素 （百分比）**值。|使用性能计数器确定消息发布传入速率和消息发布传出速率。 为你的环境使用适当的加速因子。<br /><br /> 验证值提供有关**采样窗口持续时间**和**最小样本数**参数适于你的方案。<br /><br /> 有关这些参数的详细信息，请参阅[如何修改速率基于限制设置](../core/how-to-modify-rate-based-throttling-settings.md)。|BizTalk:MessageAgent|Message publishing incoming rate<br /><br /> Message publishing outgoing rate|  
|4|进程内存超出指定阈值。<br /><br /> 如果要发布的批具有很高的内存要求，或者正在处理消息的线程过多，则可能发生此情况。|减少由 EPM 使用的线程池的大小。<br /><br /> 阻止 EPM 线程以防止处理新的消息批。<br /><br /> 如果将批中的消息保存到数据库具有很高的内存要求，则在将消息保存到数据库之前，也会对发布线程应用渐进式延迟。<br /><br /> 是否出于进程内存压力而阻止发布批取决于多种因素，包括批中的消息数，或者批中是否存在冻结或消息删除命令。|考虑通过减少 EPM 线程池和/或适配器批的大小来降低负荷量。<br /><br /> 如果进程不占用了过多内存，请考虑增加**进程虚拟**主机的阈值。<br /><br /> 有关更改的详细信息**进程虚拟**值，请参阅[如何修改资源基于限制设置](../core/how-to-modify-resource-based-throttling-settings.md)。|BizTalk:MessageAgent|High process memory<br /><br /> 进程内存使用率 (MB)<br /><br /> Process memory usage threshold (MB)|  
|6|主机消息队列大小、后台处理表大小或跟踪表大小超出指定阈值。<br /><br /> 此条件的可能原因包括：<br /><br /> -SQL 代理作业 BizTalk Server 用于维护未运行的 BizTalk Server 数据库，或运行速度变慢。<br />-下游组件不会及时处理从内存中队列的消息。<br />-挂起的消息数很高。<br />的已达到最大可持续加载系统。|减少由 EPM 使用的线程池的大小。<br /><br /> 阻止 EPM 线程以防止处理新的消息批。<br /><br /> 在将消息保存到数据库之前，也会对发布线程应用渐进式延迟。|确保 BizTalk Server 用于维护 BizTalk Server 数据库的 SQL 代理作业正在运行且没有故障。<br /><br /> 根据需要终止和恢复挂起的实例。<br /><br /> 增加的默认值为**消息在数据库中的计数**考虑到保存 BizTalk 数据库的 SQL server 的空间要求的阈值。<br /><br /> 如果你的数据库是适当地设置大小以处理额外的消息积压工作，请考虑增加**假脱机乘数**和**跟踪数据乘数**值，以允许在假脱机中使用其他积压工作和跟踪表。<br /><br /> 有关更改的值的详细信息，请参阅[如何修改资源基于限制设置](../core/how-to-modify-resource-based-throttling-settings.md)。|BizTalk:MessageAgent<br /><br /> BizTalk:Message Box:General Counters <br /><br /> BizTalk:Message Box:Host Counters|MessageAgent /Database size<br /><br /> Message Box:General Counters /Spool size<br /><br /> Message Box:General Counters /Tracking data size<br /><br /> Message Box:Host Counters/Host queue – length<br /><br /> Message Box:Host Counters/Host queue - suspended msgs – length|  
|8|主机实例使用的数据库会话数超出指定阈值。|减少由 EPM 使用的线程池的大小。<br /><br /> 阻止 EPM 线程以防止处理新的消息批。<br /><br /> 在将消息保存到数据库之前，也会对发布线程应用渐进式延迟。|请考虑增加**数据库连接**主机的阈值。<br /><br /> 更改此值的详细信息，请参阅[如何修改资源基于限制设置](../core/how-to-modify-resource-based-throttling-settings.md)。|BizTalk:MessageAgent|Database session|  
|9|进程线程数超出指定阈值。|减少由 EPM 使用的线程池的大小。<br /><br /> 阻止 EPM 线程以防止处理新的消息批。<br /><br /> 在将消息保存到数据库之前，也会对发布线程应用渐进式延迟。|考虑调整不同线程池的大小，以确保系统不会创建大量线程。<br /><br /> 有关修改线程池大小的详细信息，请参阅[如何修改常规设置](../core/how-to-modify-general-settings.md)和[如何修改资源基于限制设置](../core/how-to-modify-resource-based-throttling-settings.md)。|BizTalk:MessageAgent|Thread count<br /><br /> Thread count threshold|  
|5|系统内存超出指定阈值。|减少由 EPM 使用的线程池的大小。<br /><br /> 阻止 EPM 线程以防止处理新的消息批。<br /><br /> 如果将批中的消息保存到数据库具有很高的内存要求，则在将消息保存到数据库之前，也会对发布线程应用渐进式延迟。<br /><br /> 是否出于进程内存压力而阻止发布批取决于多种因素，包括批中的消息数，或者批中是否存在冻结或消息删除命令。|考虑通过减少 EPM 线程池的默认大小和/或适配器批的大小来降低负荷量。<br /><br /> 如果进程不占用了过多内存，请考虑增加**全局物理**主机的阈值。<br /><br /> 有关详细信息更改**全局物理**阈值，请参阅[如何修改资源基于限制设置](../core/how-to-modify-resource-based-throttling-settings.md)。|BizTalk:MessageAgent|Physical memory usage (MB)<br /><br /> Physical memory usage threshold (MB)|  
  
### <a name="outbound-throttling"></a>出站阻止  
 BizTalk 阻止机制对业务流程引擎 (XLANG) 和出站适配器应用出站阻止。  
  
 使用**限制状态的消息传递**和**限制状态持续时间的消息传递**与关联的计数器**BizTalk:MessageAgent**性能对象若要测量的当前限制的状态和持续时间限制的类别。 有关可用的主机限制性能计数器请参阅[主机限制性能计数器](../core/host-throttling-performance-counters.md)。  
  
 出站阻止可能导致消息送达延迟，消息可能会在内存中队列中堆积，并可能导致出列线程被阻止，直到阻止条件得以缓解。 当出列线程被阻止后，不会从 MessageBox 中请求任何其他消息放入内存中队列中以进行出站送达。  
  
|消息送达<br /><br /> 阻止状态|阻止条件的触发器|采取的阻止操作|缓解策略|性能对象|性能计数器|  
|-------------------------------------------|--------------------------------------|------------------------------|-------------------------|------------------------|-------------------------|  
|1|**消息传送传入速率**主机实例超出**传出速率的消息传递\***指定**速率 overdrive 因素 （百分比）**值<br /><br /> 如果处理复杂度太高，出站适配器速度太慢或者系统资源出现暂时短缺，都会导致此情况。|直到传入速率位于等同于消息传递在动态计算的时间段内阻止传递线程**传出速率的消息传递\***指定**速率据以加快因素 （百分比）**值。|使用性能计数器确定消息送达传入速率和消息送达传出速率。 请考虑适当针对你的环境的驱动器因素。<br /><br /> 验证值提供有关**采样窗口持续时间**和**最小样本数**参数适于你的方案。<br /><br /> 有关这些参数的详细信息，请参阅[如何修改速率基于限制设置](../core/how-to-modify-rate-based-throttling-settings.md)。|BizTalk:MessageAgent|Message delivery incoming rate<br /><br /> Message publishing outgoing rate|  
|4|进程内存超出指定阈值。<br /><br /> 在需要占用大量内存的处理方案中、在处理大量消息时或者在发送适配器尝试同时处理大量消息时可能发生此情况。|降低向适配器或 XLANG 的消息送达速度。<br /><br /> 根据需要，通过冻结服务实例和缩减缓存来降低进程内存占用率。<br /><br /> 减少由 EPM 和/或消息代理使用的线程池的大小。<br /><br /> 定期强制执行 .NET 垃圾回收 (GC)。|如果系统由于基于进程内存的阻止而没有处于空闲状态，则可能无需采取任何操作。<br /><br /> 如果**进程内消息计数**计数器值较高和 CPU 使用率是否即使在没有进程内存限制基于，任何其他操作可能需要过大。<br /><br /> 如果系统看起来过度限制，请考虑增加与关联的值**进程虚拟**主机的阈值，并验证主机实例不会生成"内存不足"错误。 如果通过增加引发"内存不足"错误**进程虚拟**阈值，请考虑减少的值**内部消息队列大小**和**进程内消息**阈值。 此策略特别适用于大型消息处理方案。<br /><br /> 有关这些参数的详细信息，请参阅[如何修改资源基于限制设置](../core/how-to-modify-resource-based-throttling-settings.md)。|BizTalk:MessageAgent|High process memory<br /><br /> Process memory usage(MB)<br /><br /> Process memory usage threshold (MB)<br /><br /> In-process message count<br /><br /> Active instance count|  
|3|送达服务类别的进程内消息数超出指定阈值。<br /><br /> 如果处理复杂度太高，出站适配器速度太慢或者系统资源出现暂时短缺，都会导致此情况。|降低向适配器或 XLANG 的消息送达速度。<br /><br /> 减少由消息代理使用的线程池的大小。|如果发生过度限制，请考虑增加与关联的值**进程内消息**阈值。<br /><br /> 有关此参数的详细信息，请参阅[如何修改资源基于限制设置](../core/how-to-modify-resource-based-throttling-settings.md)**注意：**增加此值可能产生负面影响发送适配器性能和/或增加内存进程使用。|BizTalk:MessageAgent|In-process message count<br /><br /> In-process message count threshold|  
|9|进程线程数超出指定阈值。|减少由 EPM 和/或消息代理使用的线程池的大小|考虑调整不同线程池的大小，以确保系统不会创建大量线程。<br /><br /> 有关修改线程池大小的详细信息，请参阅[如何修改常规设置](../core/how-to-modify-general-settings.md)和[如何修改资源基于限制设置](../core/how-to-modify-resource-based-throttling-settings.md)。|BizTalk:MessageAgent|Thread count<br /><br /> Thread count threshold|  
|5|系统内存超出阈值。|降低向适配器或 XLANG 的消息送达速度。<br /><br /> 根据需要，通过冻结服务实例和缩减缓存来降低进程内存占用率。<br /><br /> 减少由 EPM 和/或消息代理使用的线程池的大小。|考虑通过减少 EPM 线程池的默认大小和/或适配器批的大小来降低负荷量。<br /><br /> 如果进程不占用了过多内存，请考虑增加**全局物理**主机的阈值。<br /><br /> 有关更改的详细信息**全局物理**阈值，请参阅[如何修改资源基于限制设置](../core/how-to-modify-resource-based-throttling-settings.md)。|BizTalk:MessageAgent|Physical memory usage (MB)|