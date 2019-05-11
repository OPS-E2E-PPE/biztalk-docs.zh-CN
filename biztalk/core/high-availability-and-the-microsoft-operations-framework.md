---
title: 高可用性和 Microsoft Operations Framework |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 54d8bae3-b241-4371-b8fc-a9cbdca6b495
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba63d822a6edf76cd9673a4c1cdffcddf3697055
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344325"
---
# <a name="high-availability-and-the-microsoft-operations-framework"></a>高可用性和 Microsoft Operations Framework
将 Microsoft Operations Framework (MOF) 流程模型应用于计划和实现高度可用的 Microsoft BizTalk Server 解决方案可以帮助您确保在版本生命周期的不同阶段具有适当的流程。 通过提前查看所有生命周期阶段的高可用性图面，可以使安装过程中，维护，以及对您更轻松的环境中的可用性问题的疑难解答。  
  
 本部分包含有关 MOF 进程必须要考虑高可用性任务的信息。  
  
## <a name="microsoft-operations-framework-process-model"></a>Microsoft Operations Framework 进程模型  
 [Microsoft Operations Framework (MOF)](https://technet.microsoft.com/solutionaccelerators/dd320379.aspx)提供可帮助组织实现任务关键型系统的可靠性、 可用性、 可支持性和可管理性的 Microsoft 产品和技术的指导. MOF 提供的白皮书、 操作指南、 评估工具、 最佳实践、 案例研究、 模板、 支持工具和服务的窗体中的操作指南。 此指南可解决与复杂、 分布式和异类 IT 环境相关的人员、 过程、 技术和管理问题。 
  
 MOF 过程模型使公司能够：  
  
- 跨服务解决方案促进一致的 IT 服务管理。  
  
- 建立一个结构，用于 IT 函数、 过程和步骤。  
  
- 表示一种生命周期方法。  
  
  MOF 过程模型的核心是操作过程和步骤，名为服务管理功能 (Smf) 其划分为四个象限。 Smf 为 foundation 级别的最佳实践和说明性指南来操作和维护 IT 环境。  
  
  下图显示了需要考虑高可用性的 MOF 过程。  
  
  ![MOF Processes](../core/media/tdi-highava-mof.gif "TDI_HighAva_MOF")  
  
## <a name="changing-quadrant"></a>更改象限  
 更改象限包括标识、 查看、 批准和将更改合并到托管的 IT 环境所需的服务管理功能 (Smf)。 这包括软件、 硬件、 文档、 角色和职责，并还特定进程和过程更改中的更改。  
  
### <a name="change-management"></a>更改管理  
 更改管理负责技术、 系统、 应用程序、 硬件、 工具、 文档和进程中的更改，也会更改在角色和职责。  
  
 在更改管理过程中，作为一部分的设计您的 BizTalk Server 实现，可以执行以下操作：  
  
-   确定是否与合作伙伴或客户的服务级别协议需要一定的可用性、 运行时间和加载处理功能。  
  
-   确定 BizTalk Server 数据库来满足业务需求的最佳群集配置。 运行时进程写入到 BizTalk 管理数据库、 MessageBox 数据库、 跟踪 Analysis Services 数据库、 BAM 分析数据库、 BAM 星型架构数据库、 BAM 主导入数据库和 BAM 存档数据库。 因此，这些数据库是尤为重要，如果在灾难发生，并且确定哪些数据库移到群集时，必须具有更高的优先级。 只有用户或工具写入其他数据库。 对于 MessageBox 数据库中，可以考虑尽量减少所需的硬件的主动/主动/主动/被动四服务器群集。  
  
-   确定是否群集主密钥服务器，或手动还原主密钥另一个企业单一登录服务器上的是否满足你的方案。 此解决方案是可用，但不是高度可用。  
  
-   确定主机和主机实例来处理预期的消息负载，并提供高可用性所需的数目。  
  
-   在更改管理过程中创建将涉及的人员的列表。 此列表将包括但不限于，域管理员、 数据库管理员、 基础结构管理员，BizTalk Server 管理员和 IT 操作人员。  
  
### <a name="configuration-management"></a>配置管理  
 配置管理负责标识、 控制和跟踪软件、 硬件、 文档、 流程、 过程和控制的更改管理 IT 环境的所有其他组件的所有版本。  
  
 在配置管理过程中，必须创建详细的规划如何将您要为 BizTalk Server 实现高度可用的解决方案。 此外必须文档所需创建解决方案的步骤。 在高级别中，步骤如下：  
  
-   域控制器创建的域组和将在 BizTalk Server 环境中使用的帐户。  
  
-   基础结构管理员创建 Windows 群集的 BizTalk Server 数据库和主密钥服务器的 Windows 群集。  
  
-   数据库管理员安装和配置 BizTalk Server 数据库的 Windows 群集上的 Microsoft SQL Server。  
  
-   BizTalk Server 管理员配置主密钥服务器群集。  
  
-   BizTalk Server 管理员上安装和配置 BizTalk Server 处理、 接收和发送服务器。  
  
-   BizTalk Server 管理员创建主机，并提供高可用性，或以增加容量，或同时在相应服务器上安装主机实例。  
  
## <a name="operating-quadrant"></a>操作象限  
 操作象限包括监视、 控制、 管理和管理每日服务解决方案以实现并维护预先确定的参数内的服务级别所需的 Smf。  
  
### <a name="job-scheduling"></a>作业计划  
 作业计划涉及到的作业持续的组织，并以最有效的序列，处理最大化系统的吞吐量和使用以满足服务级别协议要求。  
  
 请确保安排计划内停机时间，例如计划的更新，在消息负载较低时 （例如，在晚上后期） 以最大程度减少对业务的潜在影响的时间。  
  
## <a name="supporting-quadrant"></a>支持象限  
 支持象限中包括标识、 分配、 诊断、 跟踪和解决事件、 问题和已批准要求的服务级别协议中包含的范围内的请求所需的 Smf。  
  
## <a name="optimizing-quadrant"></a>优化象限  
 优化象限包括这些 Smf，参与到通过将重点放在降低 IT 成本，同时保持或提高服务级别维护业务和 IT 对齐方式。 这包括服务中断和事件的检查、 成本结构、 人员评估、 可用性和性能分析和容量预测的检查。  
  
### <a name="service-level-management"></a>服务级别管理  
 服务级别管理旨在维护并持续改进 IT 服务，贯穿常量周期的协商和监视服务级别要求的质量。 成功的服务级别管理函数会导致改进服务质量、 更高级别的客户工作效率，理想情况下，提供服务的总体成本的减少。  
  
 在服务级别管理过程中，您可以执行以下操作：  
  
-   评估当前环境如何满足服务级别协议要求。  
  
-   建议添加新服务器的处理、 接收或发送消息，以满足要求。  
  
-   如有必要，建议创建了不最初缓解以满足可用性要求的服务级别协议中的故障点的高度可用的解决方案。  
  
### <a name="availability-management"></a>可用性管理  
 可用性管理单个目标是确保你的客户可以使用特定的 IT 服务，只要他们希望。  
  
 可用性管理过程，建立机制，以便它们可以修复或更换硬件，尽可能快地发生硬件故障时通知 IT 人员和服务器负载时通知 IT 人员的机制超过特定阈值。  
  
### <a name="service-continuity-management"></a>服务连续性管理  
 服务连续性管理功能的目的是确保指定的 IT 服务为客户提供价值如果常规可用性解决方案失败。  
  
 服务连续性函数期间必须检查哪些高可用性配置才能实现以确保继续向客户提供他们希望即使在计划内或计划外停机时间发生的服务。 非计划停机时间的示例包括硬件故障或自然灾害。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 高可用性示例方案](../core/sample-biztalk-server-high-availability-scenarios.md)