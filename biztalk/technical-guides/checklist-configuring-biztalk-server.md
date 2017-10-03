---
title: "清单： 配置 BizTalk Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: adfb5a5e-2a23-4f6c-865f-a3300bf3d01d
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11c1348ef4ce34676cd206c08530f66f20730378
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-configuring-biztalk-server"></a>清单： 配置 BizTalk Server
准备时，请按照下列步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生产环境。  
  
|步骤|参考|  
|-----------|---------------|  
|配置 BizTalk 主机和主机实例。|单独发送、 接收、 处理和跟踪到多个主机的功能。 这提供了灵活性，配置工作负荷时，并可用于停止一台主机而不会影响其他主机。 有关详细信息，请参阅[配置主机和主机实例](../technical-guides/configuring-hosts-and-host-instances.md)。|  
|请确保您遵守并了解有关 BizTalk 主机实例的内存使用量的最大实际限制。|[最大的实际的 32 位 BizTalk 主机实例的内存使用量限制](../technical-guides/configuring-hosts-and-host-instances.md#BKMK_MemLimit)|  
|配置专用的跟踪主机。|使用不执行任何操作，但跟踪的主机的专用的主机。 这可以防止承载跟踪从在同一主机中运行其他 BizTalk 项目的性能产生影响。 它还允许你在不干扰跟踪的情况下停止其他主机。 应运行的在至少两台计算机上运行跟踪主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]（用例中的冗余来说一个失败）。 有关详细信息，请参阅[配置专用跟踪主机](../technical-guides/configuring-a-dedicated-tracking-host.md)。|  
|设置 SOAP、 HTTP 和基于 HTTP 的 WCF 适配器并发连接|[将 IIS 配置设置应用](../technical-guides/apply-iis-configuration-settings.md)|  
|实现 BizTalk 应用程序升级和版本管理策略。|-如果你需要支持长时间运行业务流程和/或你需要执行 BizTalk 应用程序部署，且无 BizTalk 应用程序停机时间，则需要实施和做法可靠，端到端[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]版本控制策略不同的版本控制方案。<br />-如果你需要支持长时间运行业务流程、-并排部署或无停机升级，，则应实现的程序集版本控制和打包策略包括将分解。<br /><br /> 有关详细信息，请参阅[升级和应用程序的版本控制策略](../technical-guides/upgrading-and-versioning-strategies-for-applications.md)。|  
|BizTalk Server 应用程序部署的脚本。|如果可能，应编写脚本 BizTalk 应用程序部署。 你应带有文档的详细步骤不是编写脚本的任何内容。 有关详细信息，请参阅：<br /><br /> -   [使用脚本来部署应用程序](../technical-guides/using-scripts-to-deploy-applications.md)<br />-   [管理应用程序](../technical-guides/managing-applications.md)|  
|预定义用于在重新提交消息和重新启动工作流的过程。|建立和记录的过程以检查挂起的服务实例并采取相应的措施。 在大多数[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，这应该执行的日常维护的一部分你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。 有关每日执行维护检查的详细信息，请参阅[清单： 执行每日一次维护检查](../technical-guides/checklist-performing-daily-maintenance-checks.md)。|  
|定义在中可能会遇到的问题的升级路径[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。|-确定角色和职责<br />-定义升级过程和路径<br />-定义"短路"进程和路径时"严重的问题"方案所必需的<br />-针对供应商问题，包括 Microsoft，其他软件供应商、 硬件供应商 （例如，服务器，SAN，开关） 定义的升级路径|  
|使用时遵循某些注意事项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位 Windows 操作系统上|[在 64 位 Windows 操作系统上使用 BizTalk Server 时的注意事项](../technical-guides/considerations-while-using-biztalk-server-on-a-64-bit-windows-operating-system.md)|  
|遵循的最佳做法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]设置。|[BizTalk Server 设置的最佳操作](../technical-guides/best-practices-for-biztalk-server-settings.md)|  
  
## <a name="in-this-section"></a>本节内容  
  
-   [配置主机和主机实例](../technical-guides/configuring-hosts-and-host-instances.md)  
  
-   [配置专用的跟踪主机](../technical-guides/configuring-a-dedicated-tracking-host.md)  
  
-   [将 IIS 配置设置应用](../technical-guides/apply-iis-configuration-settings.md)  
  
-   [升级和应用程序的版本控制策略](../technical-guides/upgrading-and-versioning-strategies-for-applications.md)  
  
-   [使用脚本来部署应用程序](../technical-guides/using-scripts-to-deploy-applications.md)  
  
-   [在 64 位 Windows 操作系统上使用 BizTalk Server 时的注意事项](../technical-guides/considerations-while-using-biztalk-server-on-a-64-bit-windows-operating-system.md)  
  
-   [BizTalk Server 设置的最佳操作](../technical-guides/best-practices-for-biztalk-server-settings.md)