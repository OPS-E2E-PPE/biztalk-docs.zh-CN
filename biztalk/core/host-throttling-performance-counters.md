---
title: 主机限制性能计数器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host throttling, performance counters
ms.assetid: b9090d1c-86be-40db-b814-cc116a426d95
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ca80f44b9f1244a340e9a9892593ae42ba4b4e9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971867"
---
# <a name="host-throttling-performance-counters"></a>主机阻止性能计数器
本部分将介绍用于测量影响主机阻止的系统参数的性能监视器计数器。 以下性能计数器进行访问每个主机实例下**BizTalk:Message 代理**性能对象类别：  
  
|计数器|Description|  
|-------------|-----------------|  
|Active instance count|内存中处于活动状态的服务实例数。 对于业务流程引擎，服务实例表示每个正在运行的业务流程调度实例。 对于端点管理器，服务实例可以对应于单个无状态消息，也可以对应于有状态消息的集合。 **注意：** 有状态的实例是指那些维护有关与实例关联的消息的某些状态信息。 属于有状态实例的各消息在某种形式上是彼此相关的。 例如，维护有关排序的信息的按序发送端口被视为有状态实例。 大多数消息传送方案都涉及无状态实例，在这些实例中，将对消息进行完全相互独立地处理。 每个无状态实例都对应于 EPM 内的单个消息。|  
|Database session|正在使用的并行 MessageBox 数据库连接数。|  
|Database session threshold|并行数据库会话的当前阈值。 这最初设置为**数据库连接**值上**基于资源的限制**选项卡中**设置仪表板**。 此值将根据进程的数据库会话使用率自动进行优化。 在任何时间，只要并行数据库会话数超过此阈值，则会进行主机阻止。|  
|数据库大小|此进程已发布的数据库队列中的消息数。 此值按所有主机队列表中的项数以及后台处理表和跟踪表中的项数来衡量。 如果要将某一进程发布到多个队列，则此计数器将反映所有队列的加权平均值。 **注意：** 如果重新启动主机时，保存在内存中的统计信息都将丢失。 由于涉及一些系统开销，因此只有至少存在 100 个发布（使用重新启动的主机进程内全部发布的 5%）时，BizTalk Server 才会恢复收集统计信息。|  
|High database session|-0： 正常<br />-1： 数据库会话数超过阈值|  
|High database size|-0： 正常<br />-1： 数据库已增大超出阈值<br /><br /> 此计数器将设置为一个值，如果任何一个条件为列出**消息在数据库中的计数**阈值时发生。 [如何修改资源基于限制设置](../core/how-to-modify-resource-based-throttling-settings.md)提供有关此限制阈值的信息。|  
|High in-process message count|-0： 正常<br />-1： 进程内消息计数超过限制|  
|High message delivery rate|-0： 正常<br />-1： 消息传送速率超过消息处理速率|  
|High message publishing rate|-0： 正常<br />-1： 发布请求率超过完成率|  
|High process memory|-0： 正常<br />-1： 进程内存超过阈值|  
|系统内存过高|-0： 正常<br />-1： 系统内存超过阈值|  
|High thread count|-0： 正常<br />-1： 线程计数超过阈值|  
|In-process message count|已传送到 XLANG 引擎或出站消息引擎但尚未处理的内存中消息数。|  
|In-process message count threshold|进程内消息数的当前阈值。|  
|Message delivery delay (ms)|对每个消息送达批规定的以毫秒计的当前延迟时间（只在阻止消息送达的情况下适用）。|  
|Message delivery incoming rate|在给定的示例间隔中每秒传送到业务流程引擎或消息引擎的消息数。|  
|Message delivery outgoing rate|在给定的示例间隔中业务流程引擎或消息引擎每秒处理的消息数。|  
|消息传递限制状态|指示系统是否要阻止消息送达（影响 XLANG 消息处理和出站传输）的标志。<br /><br /> -0： 不限制<br />-1： 由于失衡的消息传送速率限制 （输入的率超过输出速率）<br />-3： 由于高限制进程内消息计数<br />-4： 由于进程内存压力限制<br />-5： 由于系统内存压力限制<br />-9： 由于高的线程数限制<br />-10： 限制由于用户在传递上重写|  
|Message delivery throttling state duration|从系统进入此状态之后的秒数。 如果主机处于阻止状态，则为已阻止的时间；如果主机未进行阻止，则为应用阻止之后的时间。|  
|Message delivery throttling user override|此计数器反映了引擎监视的用户替代，其解释如下所示：<br /><br /> -0： 不重写<br />-1： 始终限制消息传递<br />-2： 不限制消息传递<br /><br /> 此替代是在可配置**基于速率限制**选项卡中**设置仪表板**。|  
|Message publishing delay (ms)|对每个消息发布批规定的以毫秒计的当前延迟时间（只在阻止消息发布并且阻止批的情况下适用）。|  
|Message publishing incoming rate|在给定的示例间隔中每秒要发送到数据库以进行发布的消息数。|  
|Message publishing outgoing rate|在给定的示例间隔中每秒已在数据库中实际发布的消息数。|  
|Message publishing throttling state|指示系统是否要阻止消息发布（影响 XLANG 消息处理和入站传输）的标志。<br /><br /> -0： 不限制<br />-2： 由于失衡消息发布速率限制 （输入的率超过输出速率）<br />-4： 由于进程内存压力限制<br />-5： 由于系统内存压力限制<br />-6： 由于数据库增长限制<br />-8： 由于高会话计数限制<br />-9： 由于高的线程数限制<br />-11： 由于用户限制在发布上重写|  
|Message publishing throttling state duration|从系统进入此状态之后的秒数。 如果主机处于阻止状态，则为已阻止的时间；如果主机未进行阻止，则为应用阻止之后的时间。|  
|Message publishing throttling user override|此计数器反映了引擎监视的用户替代，其解释如下所示：<br /><br /> -0： 不重写<br />-1： 始终限制消息发布<br />-2： 不限制消息发布<br /><br /> 此替代是在可配置**基于速率限制**选项卡中**设置仪表板**。|  
|Physical memory usage (MB)|在计算机上所有进程要使用的物理内存量（以 MB 计）。|  
|进程内存使用率 (MB)|进程内存占用量（以 MB 计）。 这是进程的工作集大小以及为进程页文件分配的总空间大小的最大值。|  
|Process memory usage threshold (MB)|进程内存占用量的当前阈值（以 MB 计）。 这最初设置为**进程虚拟**中的值**设置仪表板**。 如果指定了百分比值，则根据要提交的可用内存来计算此值。|  
|Service class ID|此性能计数器实例对应的服务类别 GUID 的初始部分的十进制值。 一个进程可以作为多个服务类别的宿主，而消息代理性能计数器则显示最频繁使用的服务类别的数据。|  
|Thread count|进程内正在使用的线程数。|  
|Thread count threshold|进程内的线程数的当前阈值。 这最初设置为**线程**值上**基于资源的限制**选项卡中**设置仪表板**。 此值将根据当前进程的线程要求自动进行优化。 在任何时点，只要进程中的线程数超过此阈值，则会进行主机阻止。|  
|Total batches committed|服务类别提交的数据库批数。|  
|Total messages delivered|传送到业务流程引擎或端点管理器 (EPM) 的出站消息数。|  
|Total messages published|已发布的消息数。|  
  
> [!NOTE]
>  **BizTalk:Message 代理**性能计数器为了便于分析限制主机的行为的显式目的，因此将不会捕获数据除非指定的主机正在主动处理的文档。 此行为设计用于在阻止活动未发生时使用性能监视器来防止占用系统线程。  
  
## <a name="to-access-performance-counters"></a>访问性能计数器  
 依照下述步骤访问性能计数器。  
  
#### <a name="if-you-are-using-windows-2008"></a>如果您使用的是 Windows 2008  
  
1.  单击**启动**，指向**管理工具**，然后单击**性能监视器**。  
  
2.  在**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。  
  
3.  在**添加计数器**对话框中，从**可用计数器**列表中，展开**BizTalk:Message 代理**性能计数器对象，然后选择要将的计数器监视。  
  
4.  在**实例的所选对象**列表中，选择要监视的所选计数器，然后单击的特定实例**添加**。  若要选择的所有可用的计数器实例，选择\<**所有实例**\>。  
  
5.  添加计数器后, 单击**确定**。  
  
     所选的性能计数器显示在**性能监视器**屏幕。  
  
## <a name="see-also"></a>另请参阅  
 [限制的设计建议](../core/throttling-design-recommendations.md)   
 [BizTalk Server 如何实施限制的主机](../core/how-biztalk-server-implements-host-throttling.md)   
 [使用设置仪表板进行 BizTalk Server 性能调整](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)