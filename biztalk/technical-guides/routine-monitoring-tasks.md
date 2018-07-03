---
title: 例程监视任务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2f9f56a-c839-4108-933d-69b00a1e3817
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d500e79cdf20c6a1914708976101715c2f00ae69
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001654"
---
# <a name="routine-monitoring-tasks"></a>例程监视任务
执行以下监视任务按定期计划将帮助您保护您[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序和基础结构做好运行准备。  
  
## <a name="daily-monitoring-tasks"></a>每日监视任务  
  
- 检查所有打开的警报。  
  
- 使用**组中心**页中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来调查业务流程、 端口和消息失败。 **组中心**提供了对系统中，访问 MessageBox 数据库中的数据的当前实时状态的访问。 您可以查看所有服务实例（例如业务流程、端口和消息传送）及其关联的消息。 使用**组中心**页面可以执行以下活动：  
  
  - 请参阅当前正在运行的服务实例，如业务流程和消息传送和及其关联的消息。  
  
  - 在 MessageBox 数据库中进行搜索，以显示系统的当前数据以及实时状态的视图。  
  
  - 挂起、终止和恢复服务实例。  
  
    有关使用详细信息**组中心**页上，请参阅[ http://go.microsoft.com/fwlink/?LinkId=155281 ](http://go.microsoft.com/fwlink/?LinkId=155281)。  
  
- 检查警告（可选）。  
  
  有关详细信息，请参阅[清单： 执行每日维护检查](../technical-guides/checklist-performing-daily-maintenance-checks.md)。  
  
## <a name="weekly-monitoring-tasks"></a>监视的每周任务  
  
- 查看至少一次每周的事件日志。 此任务的原因是为了防止问题，例如将未能检测到的 DBNetLib 错误。 服务中断可能会被忽略，除非你有一个很短的延迟系统。 但是，这些错误的一些可以指示一个更大的问题 （示例中，过多主机或 BizTalk Server 服务器的消息框、 上的 SQL 框等的性能问题数）。  
  
  有关详细信息，请参阅[清单： 执行每周维护检查](../technical-guides/checklist-performing-weekly-maintenance-checks.md)。  
  
## <a name="as-needed-tasks"></a>根据任务  
  
- 修改规则以自定义的监视你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序和基础结构。  
  
- 运行日志的性能分析工具 (PAL)。 如果你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署是相当稳定 （例如，新的贸易合作伙伴不定期，添加新代码没有部署），您可能会运行性能监视器和 PAL 一季度一次或甚至每隔六个月。 如果你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署更改更频繁地，你可能想要运行 Perfmon 和 PAL 每隔几个月要与基准进行比较。 有关 PAL 的详细信息，请参阅[使用性能分析的日志 (PAL) 工具](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)。  
  
- 中的运行性能监视器每隔几个月，具体取决于更改数量的一次每个季度或甚至每隔六个月至发生在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署。  
  
- 运行 BizTalk Server Best Practices Analyzer 时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署更改 （例如，添加新的应用程序） 或创建新主机。 您可以下载 BizTalk Server Best Practices Analyzer 处[ http://go.microsoft.com/fwlink/?LinkId=83317 ](http://go.microsoft.com/fwlink/?LinkId=83317)。  
  
- 运行[BizTalk MsgBoxViewer 工具](http://go.microsoft.com/fwlink/?LinkId=151930)(http://go.microsoft.com/fwlink/?LinkId=151930)。 此工具分析 BizTalk MessageBox 和其他数据库，并生成 HTML 报表包含警告，如果与数据库相关的任何，和其他信息。  
  
  > [!TIP]  
  >  此外可以保存以供将来使用的报表。 BizTalk 应用程序的问题进行故障排除时，这些报表可能很有用。  
  
  > [!NOTE]  
  >  使用此工具不受 Microsoft，因此 Microsoft 不保证此程序的适用性。 使用此程序风险自负。  
  
- 运行[终止符工具](http://go.microsoft.com/fwlink/?LinkId=151931)(http://go.microsoft.com/fwlink/?LinkId=151931)。 此工具使用户能够轻松地解决由 BizTalk MsgBoxViewer 工具标识的任何问题。 有关如何使用 BizTalk MsgBoxViewer 工具相集成的终结器工具的详细信息，请参阅[使用 BizTalk 终止符，以解决问题由 BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932)(http://go.microsoft.com/fwlink/?LinkId=151932)。  
  
  > [!NOTE]  
  >  使用此工具不受 Microsoft，因此 Microsoft 不保证此程序的适用性。 使用此程序风险自负。  
  
## <a name="annual-monitoring-tasks"></a>每年的监视任务  
  
- 查看有效性的监视你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序和基础结构。  
  
- 创建计划以在监视中进行任何所需的更改。  
  
## <a name="see-also"></a>请参阅  
 [例程维护清单](../technical-guides/routine-maintenance-checklists.md)