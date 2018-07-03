---
title: 清单： 执行每月性能检查 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa103777-af4d-480d-abc7-3c4718f493c1
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e580b95288ec7ac23be93d99c56c3cfc781374c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992526"
---
# <a name="checklist-performing-monthly-performance-checks"></a>清单： 执行每月性能检查
本主题列出了应遵循每月，避免性能问题的最佳做法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。  


|                                     步骤                                     |                                                                                                                                                                                                                                                                                                                              参考                                                                                                                                                                                                                                                                                                                              |
|-------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|          确定您需要在规划期间跟踪的信息          |       应当在计划阶段确定需要跟踪的信息，以便在部署项目后可以设置跟踪选项并限制跟踪的数据量，从而仅为您提供所需的信息。 **注意：** 有关与跟踪相关的最佳做法的详细信息，请参阅[规划跟踪](../technical-guides/planning-for-tracking.md)本指南中并[运行状况与活动跟踪](http://go.microsoft.com/fwlink/?LinkId=154187)(<http://go.microsoft.com/fwlink/?LinkId=154187>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档。        |
|                           不要跟踪所有消息                           |                                                                                                                                                    我们建议不跟踪所有消息，因为每次访问消息时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将生成另一个副本。 而是可以通过跟踪特定端口来缩小范围。 这可以帮助您的系统性能最大化和保持数据库整洁。                                                                                                                                                     |
|                  不跟踪业务流程的所有的事件                   |                                                                                                                                                                          跟踪的业务流程的所有事件可能会增加 dta_DebugTrace 和 dta_MessageInoutEvents 表的大小。 有关如何禁用跟踪业务流程的说明，请参阅[若要禁用对业务流程的跟踪](../technical-guides/how-to-disable-tracking.md#BKMK_DisableOrchTracking)。                                                                                                                                                                           |
|     将发送端口上设置跟踪和接收管道上的而不是端口     |                                                                                                                                                                         如果设置管道的跟踪选项，则还将设置为使用的管道的每个端口全局跟踪选项。 反过来，这可能会在导致被跟踪比你预期，这将降低系统性能的更多数据。 相反，您可以设置跟踪选项上的发送端口和接收端口。                                                                                                                                                                         |
|                调整基于资源使用率的阻止功能                |     中的阻止行为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]默认提供良好的保护系统配置。 监视性能计数器限制状态，以查看是否限制的位置，然后自行衡量阻止行为的资源为基础 （例如，数据库大小或内存使用情况） 下或使用过度，，然后调整限制阈值相应地增减。 有关详细信息，请参阅[调整阻止阈值： 时间和原因](http://go.microsoft.com/fwlink/?LinkId=154188)(<http://go.microsoft.com/fwlink/?LinkId=154188>)。     |
|                 如果可能，请使用 PassThruTransmit 管道                 |                                                                                                                                                                                                                                                       如果消息发送到其目标之前不需要处理任何文档，而不是 XML 发送管道使用 PassThruTransmit 管道。                                                                                                                                                                                                                                                        |
| 请考虑各种因素时调整 BizTalk 跟踪数据库的大小 | -当调整 BizTalk 跟踪数据库的大小，可以通过将应变乘数添加到你的计算考虑 SQL Server 因素，例如，索引大小。<br />-当确定 BizTalk 跟踪数据库中的消息的大小，向消息上下文的平均大小的消息大小如果这一点非常重要的消息大小。<br />-若要将 BizTalk 跟踪数据库中的消息大小限制，限制提升的属性的数目。<br />-如果启用了业务流程调试器选项，请考虑在业务流程中每个形状的状态保存在 BizTalk 跟踪数据库中。 |
|               应用硬件解决方案来避免磁盘争用               |           若要避免磁盘争用导致 MessageBox 数据库中的，执行以下操作：<br /><br /> -使用高速磁盘<br />-部署在高速 SAN 上的数据库<br />-单独的专用服务器，它独立于跟踪数据库将 MessageBox 数据库<br />-纵向扩展 Cpu，并将更多的 Cpu 添加到专用的 MessageBox 数据库服务器<br />-将页面文件和/或 MSDTC 日志移到不同的驱动器<br /><br /> 有关如何避免数据库争用的详细信息，请参阅[如何避免磁盘争用](http://go.microsoft.com/fwlink/?LinkId=158809)(<http://go.microsoft.com/fwlink/?LinkId=158809>)。           |

## <a name="see-also"></a>请参阅  
 [例程性能清单](../technical-guides/routine-performance-checklists.md)   
 [清单：执行每周性能检查](../technical-guides/checklist-performing-weekly-performance-checks.md)