---
title: 监视任务的例程 |Microsoft 文档
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
ms.openlocfilehash: d91a49393e2b43c9cf39add35e06c5bd864782e8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22301901"
---
# <a name="routine-monitoring-tasks"></a>例程的监视任务
按定期计划定期执行以下监视任务将帮助您保留您[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序和基础结构做好运行准备。  
  
## <a name="daily-monitoring-tasks"></a>每日的监视任务  
  
-   检查所有打开的警报。  
  
-   使用**组中心数据库**页面[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来调查业务流程、 端口和消息失败。 **组中心数据库**页提供了当前的实时状态的系统，访问 MessageBox 数据库中的数据访问。 您可以查看所有服务实例（例如业务流程、端口和消息传送）及其关联的消息。 使用**组中心数据库**页你可以执行以下活动：  
  
    -   请参阅当前正在运行的服务实例，如业务流程和消息，以及其关联的消息。  
  
    -   在 MessageBox 数据库中进行搜索，以显示系统的当前数据以及实时状态的视图。  
  
    -   挂起、终止和恢复服务实例。  
  
     有关使用**组中心数据库**页上，请参阅[http://go.microsoft.com/fwlink/?LinkId=155281](http://go.microsoft.com/fwlink/?LinkId=155281)。  
  
-   检查警告（可选）。  
  
 有关详细信息，请参阅[清单： 执行每日一次维护检查](../technical-guides/checklist-performing-daily-maintenance-checks.md)。  
  
## <a name="weekly-monitoring-tasks"></a>每周的监视任务  
  
-   查看至少一次每周的事件日志。 此任务的原因是为防止出现问题，如 DBNetLib 转未检测到的错误。 除非你拥有的延迟时间非常低系统，服务中断可能会被忽略。 但是，某些这些错误可能表示出现更大问题 （例如，过多主机或的消息框，在 SQL 中，等的性能问题数的 BizTalk Server 服务器）。  
  
 有关详细信息，请参阅[清单： 执行每周维护检查](../technical-guides/checklist-performing-weekly-maintenance-checks.md)。  
  
## <a name="as-needed-tasks"></a>根据需要任务  
  
-   修改规则以自定义的监视你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序和基础结构。  
  
-   运行日志的性能分析工具 (PAL)。 如果你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署是相当常量 （例如，新的贸易合作伙伴并未例行，添加新代码不部署），你可能会运行 Perfmon 和 PAL 一季度一次或甚至每六个月。 如果你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署更改更频繁地，你可能想要运行 Perfmon 和 PAL 每隔几个月内要针对基线进行比较。 PAL 的详细信息，请参阅[使用性能分析的日志 (PAL) 工具](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)。  
  
-   运行的 Perfmon 中发生的每个几个月，具体取决于更改数的一季度一次或甚至每六个月至你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署。  
  
-   运行 BizTalk Server 最佳做法分析器时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署更改 （例如，添加新的应用程序） 或创建新的主机。 你可以下载 BizTalk Server 最佳做法分析器在[http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317)。  
  
-   运行[BizTalk MsgBoxViewer 工具](http://go.microsoft.com/fwlink/?LinkId=151930)(http://go.microsoft.com/fwlink/?LinkId=151930)。 此工具可分析 BizTalk MessageBox 和其他数据库并生成 HTML 报告包含警告，如果与数据库相关的任何，和其他信息。  
  
    > [!TIP]  
    >  你还可以保存以供将来使用的报表。 与 BizTalk 应用程序的问题进行故障排除时，这些报表可能很有用。  
  
    > [!NOTE]  
    >  使用此工具不支持由 Microsoft 和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。  
  
-   运行[终止符工具](http://go.microsoft.com/fwlink/?LinkId=151931)(http://go.microsoft.com/fwlink/?LinkId=151931)。 此工具使用户能够轻松地解决由 BizTalk MsgBoxViewer 工具标识的任何问题。 有关如何使用 BizTalk MsgBoxViewer 工具相集成终止符工具的详细信息，请参阅[使用 BizTalk 终止符，若要解决问题由 BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932)(http://go.microsoft.com/fwlink/?LinkId=151932)。  
  
    > [!NOTE]  
    >  使用此工具不支持由 Microsoft 和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。  
  
## <a name="annual-monitoring-tasks"></a>每年的监视任务  
  
-   查看监视的有效性你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序和基础结构。  
  
-   创建计划在监视中进行任何所需的更改。  
  
## <a name="see-also"></a>另请参阅  
 [日常维护清单](../technical-guides/routine-maintenance-checklists.md)