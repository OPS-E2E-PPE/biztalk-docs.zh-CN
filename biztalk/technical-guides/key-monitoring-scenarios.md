---
title: "主要监视方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fee90fd2-fb85-409f-827e-6ee3c8e13b4c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99f8f1427f5f5535b6c446dae3057b4d80754a7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="key-monitoring-scenarios"></a>主要监视方案
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于 Operations Manager 2007 R2/2012年管理包包括多种主要监视方案中后面的表中所述。  
  
### <a name="biztalk-server-monitoring-scenarios"></a>BizTalk Server 监视方案  
  
|应用场景|Description|  
|--------------|-----------------|  
|挂起的消息警报|监视和解决与挂起的消息相关的问题是常见的操作任务，BizTalk 服务器环境中。 BizTalk Server 管理包可以监视和优化的方式排查挂起的消息事件。 处理消息时，BizTalk Server 中出现两种类型的消息挂起： 入站消息挂起和出站消息挂起。<br /><br /> 对于入站消息，各种类型的处理失败或缺乏订阅可能会导致要挂起的消息。 某些传输方式可以配置为将消息挂起，也可以配置为不挂起消息。 对于出站消息，所有处理失败都将始终导致消息挂起。<br /><br /> 对于入站消息，挂起的警报规则是每适配器编写的。 此方法提供了更灵活地处理入站端的消息挂起。 你可以添加基于的适配器，如通知的不同响应操作。 此外，您可以通过创建自定义规则定制 BizTalk Server 管理包。 对于出站消息，所有消息始终将被都挂起的任何类型的传输时间失败。|  
|警报取消策略|挂起的消息的规则采用不同的抑制策略不是通常应用于其他规则。 警报可基于警报名称、警报源、计算机和域来取消。<br /><br /> 对于基于警报源的禁止显示，每个挂起的消息规则的警报源还包含从挂起的消息事件中提取的参数。 此参数是消息接收或传输所使用的 URI。<br /><br /> 在相同的 URI 发生的错误通常是由于相同的原因。 因此，我们建议你创建相同的根本原因的一个警报，即使存在多个关联的故障事件。 这使你能够一个警报和一个根本原因，这样可以更轻松地在出现时，更正问题。 简化的警报，基于 Uri，减少不必要的警报和促进有效地跟踪打开的问题。 在某个 URI 处，如果以前没有挂起警报，则将为消息挂起创建一个新警报。|  
|BAM 获得技术协助警报|业务活动监视 (BAM) 门户用户，称为业务用户通常了解业务级别指标和业务活动。 它们使用 BAM 门户监视器聚合指示器、 完整的过程中业务事务或搜索具有特定属性的事务进行进一步调查。 但是，业务用户通常不了解 IT 基础结构级别是问题的方面。 给定的事务的调查，过程 BAM 门户使业务用户能够从 IT 操作人员来调查在 IT 基础结构级别的事务请求获得技术协助。<br /><br /> 使用 BAM 门户，业务用户则可以通过技术协助请求来获得帮助。 请求获得技术协助 BAM 门户的托管位置的计算机的事件查看器中的应用程序日志中创建的项。 此事件包含有关在其获得技术协助请求的用户和其他重要信息，例如消息实例标识符、 服务实例标识符和 BizTalk Server 组信息的活动的详细信息。<br /><br /> BizTalk Server 管理包包含触发上检测到 BAM 获得技术协助事件警报的规则。 创建此警报的规则为“错误：请求 BAM 技术协助”。 为每个请求提交从 BAM 门户创建新警报。|  
|BizTalk 消息框和主机|BizTalk Server 管理包包含数据库和队列提供 BizTalk MessageBox 的运行状况的综合视图的性能阈值规则。 提供两种类型的阈值规则：<br /><br /> -将应用一般情况下，即，于所有 BizTalk 主机，所有 BizTalk MessageBox 数据库的规则。<br />-特定于特定的 BizTalk 主机或消息框的规则。<br /><br /> 泛型规则监视所有的 BizTalk Server 主机或 MessageBox 数据库基于常见的阈值。 例如，规则“Monitor HostQ Size”将基于通用阈值来监视所有 BizTalk Server 主机的工作队列。 如果三个主机存在，其所有工作队列都监视由相同规则，并在任何主机工作队列跨常见阈值时发生警报。<br /><br /> BizTalk Server 特定于宿主的规则可让你配置的不同主机和 MessageBox 数据库的不同的阈值。 例如，规则“Monitor HostQ Size – BizTalkServerApplication”是特定于主机的规则，它监视 BizTalkServerApplication 主机的工作队列。 通过定义的特定的 Operations Manager 提供程序特定的性能计数器实例和阈值规则中使用该提供程序执行此操作。<br /><br /> 特定于主机\MessageBox 的规则是作为模板规则来提供的，该模板规则用于指导创建适用于您环境的规则。 通用规则需要配置特定于您环境的阈值。 特定于 BizTalk 主机/MessageBox 的规则需要基于模板规则和相应的阈值来创建。<br /><br /> BizTalk Server 包含自限制，这有助于防止重载基于各种参数。 从操作方面而言，由临时重载引发的阻止并不是严重问题。 不过，在稳定的环境中不应发生持久性阻止，它说明在基础结构级可能出现问题。 BizTalk Server 管理包提供了基于以下条件的性能阈值监视器使用主动监视这种持续的限制条件：<br /><br /> -BizTalk Server 服务进程内存<br />-正在处理的消息数<br />-BizTalk Server 进程中的线程数<br />BizTalk 数据库队列的大小|  
|业务流程故障|对挂起的业务流程的监视是另一个常用方案。 包括业务流程引擎问题、.NET 组件故障以及程序逻辑的原因有很多情况下，业务流程可能会失败。 请务必启用运算符以快速确定问题根源并继续固定时挂起的业务流程。|  
|服务监视|BizTalk Server 需要多个服务正在正确运行。 这些服务的状态将映射到表示不同的 BizTalk 服务的类的监视器。|  
|应用程序监视|BizTalk Server 引入了用于分组解决方案项目关联的应用程序的概念。 应用程序监视功能将检测应用程序级别失败的影响。|