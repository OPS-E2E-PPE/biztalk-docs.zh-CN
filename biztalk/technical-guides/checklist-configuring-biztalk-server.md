---
title: 清单：配置 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: adfb5a5e-2a23-4f6c-865f-a3300bf3d01d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7aa8a786633f1ea153a1e6c6927c3e0c1335846c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291476"
---
# <a name="checklist-configuring-biztalk-server"></a>清单：配置 BizTalk Server
准备时，请执行以下步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在中使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生产环境。  


|                                                                                步骤                                                                                |                                                                                                                                                                                                                                                                                                                                                                            参考                                                                                                                                                                                                                                                                                                                                                                            |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                             配置 BizTalk 主机和主机实例。                                                             |                                                                                                                                                                                                         单独的发送、 接收、 处理和跟踪到多个主机的功能。 这提供了灵活性，配置工作负荷时，并使您可以停用一台主机而不会影响其他主机。 有关详细信息，请参阅[配置主机和主机实例](../technical-guides/configuring-hosts-and-host-instances.md)。                                                                                                                                                                                                         |
|                          请确保遵守并了解有关 BizTalk 主机实例的内存使用量的最大实际限制。                           |                                                                                                                                                                                                                                                                                                     [32 位 BizTalk 主机实例的内存使用率的最大实际限制](../technical-guides/configuring-hosts-and-host-instances.md#BKMK_MemLimit)                                                                                                                                                                                                                                                                                                     |
|                                                                配置专用的跟踪主机。                                                                 |                                                                                   使用的专用的主机，不执行任何操作，但主机跟踪。 这可以防止托管跟踪从对在同一主机中运行的其他 BizTalk 项目的性能产生影响。 它还允许您停止而不会影响与跟踪的其他主机。 跟踪主机应运行至少两台计算机上运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]（用例中的冗余一个失败）。 有关详细信息，请参阅[配置专用跟踪主机](../technical-guides/configuring-a-dedicated-tracking-host.md)。                                                                                    |
|                                               设置 SOAP、 HTTP 和基于 HTTP 的 WCF 适配器的并发连接                                                |                                                                                                                                                                                                                                                                                                                                   [应用 IIS 配置设置](../technical-guides/apply-iis-configuration-settings.md)                                                                                                                                                                                                                                                                                                                                   |
|                                                  实现 BizTalk 应用程序升级和版本控制策略。                                                   | -如果你需要支持长时间运行的业务流程，和/或需要执行任何 BizTalk 应用程序停机的情况下的 BizTalk 应用程序部署，则需要实现和做练习实线、 端到端[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]版本控制的策略不同的版本控制方案。<br />-如果你需要支持长时间运行的业务流程、 通过并行部署或无需停机的升级，，则应实现的程序集版本控制和打包策略，其中包含组成要素。<br /><br /> 有关详细信息，请参阅[升级和应用程序的版本控制策略](../technical-guides/upgrading-and-versioning-strategies-for-applications.md)。 |
|                                                           BizTalk Server 应用程序部署的脚本。                                                            |                                                                                                                                                                                            在可能的情况，应编写脚本 BizTalk 应用程序部署。 你应记录的详细步骤与不编写脚本的任何内容。 有关详细信息，请参阅：<br /><br /> -   [使用脚本来部署应用程序](../technical-guides/using-scripts-to-deploy-applications.md)<br />-   [管理应用程序](../technical-guides/managing-applications.md)                                                                                                                                                                                            |
|                                               预定义重新提交消息并重新启动工作流的过程。                                               |                                                                                       建立和记录的过程来检查挂起的服务实例并采取适当措施。 在大多数[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，这应执行的日常维护的一部分在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。 有关执行每日维护检查的详细信息，请参阅[核对清单：执行每日维护检查](../technical-guides/checklist-performing-daily-maintenance-checks.md)。                                                                                        |
|   定义中可能会遇到的问题的升级路径[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。   |                                                                                                                                                                                                      -确定角色和职责<br />-定义升级过程和路径<br />-定义"短路"流程和路径时"严重的问题"方案所必需的<br />-供应商问题，包括 Microsoft、 其他软件供应商，硬件供应商 （例如，服务器、 SAN、 开关） 定义的升级路径                                                                                                                                                                                                      |
| 使用时遵循的一些注意事项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位 Windows 操作系统上 |                                                                                                                                                                                                                                                                                     [在 64 位 Windows 操作系统上使用 BizTalk Server 的注意事项](../technical-guides/considerations-while-using-biztalk-server-on-a-64-bit-windows-operating-system.md)                                                                                                                                                                                                                                                                                     |
|                    遵循的最佳实践[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]设置。                    |                                                                                                                                                                                                                                                                                                                         [BizTalk Server 设置的最佳做法](../technical-guides/best-practices-for-biztalk-server-settings.md)                                                                                                                                                                                                                                                                                                                         |

## <a name="in-this-section"></a>本节内容  

-   [配置主机和主机实例](../technical-guides/configuring-hosts-and-host-instances.md)  

-   [配置专用跟踪主机](../technical-guides/configuring-a-dedicated-tracking-host.md)  

-   [应用 IIS 配置设置](../technical-guides/apply-iis-configuration-settings.md)  

-   [应用程序的升级和版本控制策略](../technical-guides/upgrading-and-versioning-strategies-for-applications.md)  

-   [使用脚本部署应用程序](../technical-guides/using-scripts-to-deploy-applications.md)  

-   [在 64 位 Windows 操作系统上使用 BizTalk Server 的注意事项](../technical-guides/considerations-while-using-biztalk-server-on-a-64-bit-windows-operating-system.md)  

-   [BizTalk Server 设置的最佳做法](../technical-guides/best-practices-for-biztalk-server-settings.md)