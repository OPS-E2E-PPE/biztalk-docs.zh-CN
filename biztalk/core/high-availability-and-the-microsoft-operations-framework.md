---
title: "高可用性和 Microsoft Operations Framework |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- high availability, managing
- service management functions (SMFs)
- service continuity management
- jobs, scheduling
- MOF, high availability
- change management
- MOF, process model
- high availability, MOF
ms.assetid: 54d8bae3-b241-4371-b8fc-a9cbdca6b495
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8361875cf34f14118fb93818c78a6ca7d12a86f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="high-availability-and-the-microsoft-operations-framework"></a>高可用性和 Microsoft Operations Framework
将 Microsoft Operations Framework (MOF) 流程模型应用于计划和实施高度可用的 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 解决方案，可帮助您确保在版本生命周期的不同阶段具有适当的流程。 通过查看在所有生命周期阶段其中高可用性的表面，你可以安装、 维护和故障排除的更方便您环境中的可用性问题。  
  
 本部分包含有关 MOF 进程必须要考虑高可用性任务的信息。  
  
## <a name="microsoft-operations-framework-process-model"></a>Microsoft Operations Framework 进程模型  
 Microsoft Operations Framework (MOF) 提供使组织能够实现任务关键型系统可靠性、 可用性、 可支持性和可管理性的 Microsoft 产品和技术的指导。 MOF 提供操作指导的白皮书，操作指南、 评估工具、 最佳实践、 案例研究、 模板、 支持工具和服务的形式。 本指南解决与复杂、 分布式和异类 IT 环境相关的人员、 流程、 技术和管理问题。 有关 Microsoft Operations Framework 的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=31988](http://go.microsoft.com/fwlink/?LinkId=31988)。  
  
 MOF 过程模型使公司到：  
  
-   跨服务解决方案，从而简化一致的 IT 服务管理。  
  
-   建立一个结构，用于 IT 函数、 过程和步骤。  
  
-   表示生命周期方法。  
  
 MOF 进程模型的核心是其分为四个象限的操作的进程和过程，名为服务管理功能 (Smf)。 Smf 是 foundation 级别的最佳实践和操作和维护的 IT 环境的规范性指引。  
  
 下图显示你需要考虑高可用性的 MOF 进程。  
  
 ![MOF 过程](../core/media/tdi-highava-mof.gif "TDI_HighAva_MOF")  
  
## <a name="changing-quadrant"></a>不断变化 Quadrant  
 更改象限包括标识、 查看、 批准，和将更改合并到的被管理的 IT 环境所需的服务管理功能 (Smf)。 这包括软件、 硬件、 文档、 角色和职责，并还特定的进程和过程的更改中的更改。  
  
### <a name="change-management"></a>更改管理  
 更改管理负责技术、 系统、 应用程序、 硬件、 工具、 文档和进程中的更改，也会更改在角色和职责。  
  
 在更改管理过程中，属于设计您的 BizTalk Server 实现，您可以执行以下操作：  
  
-   确定与你的合作伙伴或客户的服务级别协议是否需要特定级别的可用性、 运行时间、 和负载处理功能。  
  
-   如果要从升级[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]或[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]到 BizTalk Server 中，你必须确定是否将满足你现有的硬件，BizTalk Server 的最低硬件要求和服务级别协议的需求。  
  
-   确定你的业务需求的 BizTalk Server 数据库的最佳群集配置。 运行时进程写入到 BizTalk 管理数据库、 MessageBox 数据库、 跟踪 Analysis Services 数据库、 BAM 分析数据库、 BAM 星型架构数据库、 BAM 主导入数据库和 BAM 存档数据库。 因此，这些数据库是特别重要，如果灾难发生，并且确定群集的数据库时，必须具有更高的优先级。 仅用户或工具写入其他数据库。 对于 MessageBox 数据库中，你可以考虑尽量减少所需的硬件的主动/主动/主动/被动四台服务器群集。  
  
-   确定是否群集主密钥服务器，或者如果手动上还原主密钥另一台企业单一登录服务器已经为你的方案令人满意。 此解决方案是可用，但不是高度可用。  
  
-   确定主机和主机将需要处理预期的消息负载，从而提供高可用性的实例的数。  
  
-   在更改管理过程中创建将涉及的人员的列表。 此列表将包括但不限于，域管理员、 数据库管理员、 基础结构管理员、 BizTalk Server 管理员和 IT 操作人员。  
  
### <a name="configuration-management"></a>配置管理  
 配置管理负责标识、 控制和跟踪软件、 硬件、 文档、 进程、 过程和受控制的更改管理 IT 环境的所有其他组件的所有版本。  
  
 在配置管理过程中，你必须创建如何实现高度可用的解决方案的详细的计划[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 你必须记录你所花费的创建你的解决方案的步骤。 在高级别的步骤如下：  
  
-   域控制器创建的域组和将在你的 BizTalk 服务器环境中使用的帐户。  
  
-   基础结构管理员为 BizTalk Server 数据库创建 Windows 群集，并为主密钥服务器创建 Windows 群集。  
  
-   数据库管理员上安装和配置 Microsoft SQL Server 的 BizTalk Server 数据库的 Windows 群集。  
  
-   BizTalk Server 管理员配置的主密钥服务器群集。  
  
-   BizTalk Server 管理员安装和配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理，接收和发送服务器上。  
  
-   BizTalk Server 管理员创建主机，并提供高可用性或增加容量，或两者的相应服务器上安装主机实例。  
  
## <a name="operating-quadrant"></a>操作象限  
 操作象限包括 Smf 需监视、 控制、 管理和管理每日服务解决方案以实现和维护预先确定的参数中的服务级别。  
  
### <a name="job-scheduling"></a>作业计划  
 作业计划涉及作业持续的组织，并以最有效的序列中，处理最大化系统的吞吐量和用于满足服务级别协议要求。  
  
 请确保你计划停机时间，例如计划的更新，在消息负载较低时 （例如，夜间后期） 尽量减小对业务的潜在影响的时间安排。  
  
## <a name="supporting-quadrant"></a>支持象限  
 支持象限包括标识、 分配、 诊断、 跟踪和解决事件、 问题和请求中包含的服务级别协议中的已批准要求所需的 Smf。  
  
## <a name="optimizing-quadrant"></a>优化象限  
 优化象限包括 Smf 造成维护业务和 IT 对齐方式，通过将重点放在维护或提高服务级别同时减少 IT 成本。 这包括服务中断和事件的检查、 成本结构、 人员评估、 可用性和性能分析和容量预测的检查。  
  
### <a name="service-level-management"></a>服务级别管理  
 服务级别管理旨在维护并持续改进 IT 服务，通过协商和监视服务级别要求的常量周期的质量。 成功的服务级别管理函数导致的服务、 更高级别的客户工作效率和理想情况下，单击提供服务的总体成本的减少的质量中的改进。  
  
 在服务级别管理过程中，您可以执行以下操作：  
  
-   评估当前环境满足您的服务级别协议要求的方式。  
  
-   建议处理、 接收或发送消息以满足要求的新服务器的添加。  
  
-   如有必要，建议创建对故障点的已不最初缓解满足服务级别协议的可用性要求的高可用性解决方案。  
  
### <a name="availability-management"></a>可用性管理  
 可用性管理单个目标是确保你的客户可以使用特定的 IT 服务，只要它们希望。  
  
 可用性管理过程，你可以建立通知 IT 人员，以便他们可以修复或更换硬件尽可能快地发生硬件故障时的机制和服务器负载时通知 IT 人员的机制超过特定阈值。  
  
### <a name="service-continuity-management"></a>服务连续性管理  
 服务连续性管理功能的目的是确保指定的 IT 服务，如果常规可用性解决方案失败在向客户提供了值。  
  
 在服务连续性函数期间必须检查哪些高可用性配置以实现，若要确保你继续为客户提供他们期望甚至计划或非计划停机时间时的服务。 非计划停机时间的示例包括硬件故障或自然灾害。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 高可用性示例方案](../core/sample-biztalk-server-high-availability-scenarios.md)