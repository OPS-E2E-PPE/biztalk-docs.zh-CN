---
title: 主要监视方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fee90fd2-fb85-409f-827e-6ee3c8e13b4c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70c13588f37a262e52870dff8c99762bd3fd5aa5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391863"
---
# <a name="key-monitoring-scenarios"></a>主要监视方案
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operations Manager 2007 R2/2012年的管理包包括多种主要监视方案中后面的表中所述。  
  
### <a name="biztalk-server-monitoring-scenarios"></a>BizTalk Server 监视方案  
  
|应用场景|Description|  
|--------------|-----------------|  
|挂起的消息警报|监视和解决与挂起的消息相关的问题是 BizTalk Server 环境中常见的操作任务。 BizTalk Server 管理包可监视和挂起的消息事件进行疑难解答的简化方式。 处理消息时，在 BizTalk Server 中发生两种类型的消息挂起：入站消息挂起和出站消息挂起。<br /><br /> 对于入站消息，各种类型的处理失败或订阅缺失都可能会导致消息挂起。 可以配置某些传输方式挂起消息或挂起消息。 对于出站消息，所有处理失败将始终都导致消息挂起。<br /><br /> 对于入站消息挂起警报规则是每个适配器编写的。 此方法提供了更灵活地处理入站方向的消息挂起。 您可以添加适配器，例如通知上基于不同的响应操作。 此外，您可以通过创建自定义规则来定制 BizTalk Server 管理包。 对于出站消息，任何类型的传输时间失败时始终挂起所有消息。|  
|警报取消策略|挂起的消息的规则使用不同的抑制策略比通常应用于其他规则。 警报将被抑制基于警报名称、 警报源以及计算机和域。<br /><br /> 禁止显示功能基于警报源，每个挂起的消息规则的警报源还包含从挂起的消息事件中提取的参数。 此参数是该消息已接收或传输的 URI。<br /><br /> 由于同一原因通常是相同的 URI 上发生的错误。 因此，我们建议创建单个警报的相同的根本原因，即使存在多个相关的失败事件。 这使你能够在某一警报，一个根本原因，使你更轻松地解决问题发生时。 基于 Uri 的流程化的警报减少不必要警报，并促进有效地跟踪待解决问题。 为消息挂起以前没有挂起警报某个 URI 处创建一个新警报。|  
|BAM 技术协助警报|业务活动监视 (BAM) 门户用户，称为业务用户通常了解的业务级别指标和业务活动。 使用监视器聚合指标，完成进程内业务事务或搜索具有特定属性的事务到 BAM 门户，若要进一步调查。 但是，业务用户通常不了解 IT 基础结构级别时出现问题的方面。 在给定的事务的调查，BAM 门户，业务用户可以从 IT 操作人员进行调查 IT 基础结构级事务的请求技术协助。<br /><br /> BAM 门户，此提交从商业用户通过技术协助请求。 发送技术协助请求的应用程序日志中的 BAM 门户所在的计算机的事件查看器中创建一个条目。 此事件包含的活动的技术协助请求的用户和其他重要信息，例如消息实例标识符、 服务实例标识符和 BizTalk Server 组信息的详细信息。<br /><br /> BizTalk Server 管理包包含规则触发上检测到 BAM 技术协助事件的警报。 创建此警报的规则是"错误：BAM 技术协助。" 对于从 BAM 门户提交的每个请求创建一个新警报。|  
|BizTalk Messagebox 和主机|BizTalk Server 管理包集成了性能阈值规则的数据库和队列提供的 BizTalk MessageBox 的运行状况的综合视图。 提供两种类型的阈值规则：<br /><br /> -适用于的规则以一般方式，即，所有 BizTalk 主机和所有 BizTalk MessageBox 数据库。<br />-特定于特定的 BizTalk 主机或 MessageBox 的规则。<br /><br /> 一般的规则监视所有 BizTalk Server 主机或 MessageBox 数据库基于通用阈值。 例如，规则"Monitor HostQ Size"，所有 BizTalk Server 主机的工作队列监视器基于通用阈值。 如果存在三个主机，其所有工作队列都监视由相同规则和任何主机工作队列超过通用阈值时将发出警报。<br /><br /> BizTalk Server 主机特定的规则，可为不同的主机和 MessageBox 数据库配置不同的阈值。 例如，规则"Monitor HostQ Size – BizTalkServerApplication"是特定于宿主的规则，用于监视 BizTalkServerApplication 主机工作队列。 通过定义为特定的性能计数器实例特定的 Operations Manager 提供程序和阈值规则中使用该提供程序执行此操作。<br /><br /> 如要用作一个指南，用于创建规则的模板规则均适用您的环境中提供了特定于 \messagebox 的规则。 通用规则需要配置特定于环境的阈值。 特定于 BizTalk 主机/MessageBox 的规则需要在创建基于模板规则和相应的阈值。<br /><br /> BizTalk Server 集成了自阻止功能，这有助于防止重载基于各种参数。 由临时重载引发的阻止不是严重问题。 持久性阻止，但是，不应出现在稳定的环境，可能表示底层基础结构级别的问题。 BizTalk Server 管理包提供了基于以下条件的性能阈值监视器使用主动监视此类持久性阻止条件：<br /><br /> BizTalk Server 服务进程内存<br />-正在处理的消息数<br />-BizTalk Server 进程中的线程数<br />的 BizTalk 数据库队列大小|  
|业务流程故障|监视挂起的业务流程是另一种常见方案。 包含业务流程引擎问题、.NET 组件故障以及程序逻辑的原因有很多情况下，业务流程可能会失败。 请务必让操作员快速确定问题的来源，并继续挂起的业务流程时固定。|  
|服务监视|BizTalk Server 需要运行多个服务才能正常运行。 这些服务的状态将映射到表示不同的 BizTalk 服务的类的监视器。|  
|应用程序监视|BizTalk Server 引入了用于解决方案项目分组的应用程序的概念。 应用程序监视会检测应用程序级别失败造成的影响。|