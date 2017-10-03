---
title: "消息和实例数据跟踪的最佳实践 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HAT, best practices
- best practices, HAT
ms.assetid: 2ac5c87b-2059-4912-9cec-2ae4eaac56df
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a6f673b0a70903575918eb87dc4bd8edc9841e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-message-and-instance-data-tracking"></a>消息和实例数据跟踪的最佳实践
请查看以下使用历史数据和跟踪数据的最佳操作。  
  
-   **查看有关使用历史数据和跟踪数据的安全注意事项**  
  
    -   有关历史数据和跟踪数据的安全注意事项的详细信息，请参阅[消息和实例数据跟踪的安全注意事项](../core/security-considerations-for-message-and-instance-data-tracking.md)。  
  
-   **确保所有 MessageBox 数据库上正在运行的 SQL Server 代理服务**  
  
    -   SQL Server 代理使得消息正文可用于 WMI、历史数据和跟踪数据。 这使您能够运行作业来清理 MessageBox 数据库。 有关 SQL Server 代理的详细信息，请参阅 SQL Server 联机丛书。  
  
-   **启用消息正文跟踪**  
  
    -   若要在服务实例处理完成后保存消息，则需要消息正文跟踪功能。  
  
-   **配置跟踪以适合你的业务需求**  
  
    -   可以查看历史数据和跟踪数据前，必须先使用 BizTalk Server 管理控制台配置跟踪。 启用或禁用跟踪选项时，要时刻牢记几个注意事项。 跟踪的数据越多，BizTalk 跟踪 (BizTalkDTADb) 数据库的大小增长的越快，这将对系统的运行时性能产生不利影响。 有关详细信息，请参阅[配置跟踪使用 BizTalk Server 管理控制台](http://msdn.microsoft.com/en-us/49b7f9d3-60b5-41bd-ba8b-029253926bef)。  
  
-   **选择适当类型的跟踪以进行故障排除或审核**  
  
    -   为了解决在开发环境、过渡环境或生产环境中出现的问题，应启用所有跟踪选项，以便可查看项目事件、消息属性、消息正文和业务流程事件的详细信息。 这些跟踪信息内容丰富，使用这些信息可重建系统中的事件序列并调试应用程序。  
  
    -   对于生产级别的审核，应仔细选择要审核的事件，然后仅启用对这些事件的跟踪。 例如，许多企业希望能够对进入和退出系统的消息进行审批。 为此，应启用对相应接收端口的入站跟踪，和对相应发送端口的出站跟踪。 必要时，可添加对消息属性和消息正文的跟踪。  
  
    -   为了度量业务关键性能指标 (KPI) 或由指定业务里程碑的完成所标识的进度，应使用业务活动监视 (BAM) 跟踪。 BAM 跟踪在跟踪和存储消息正文方面能力有限，所以如果这些方面的数据非常重要的话，则应同时使用历史数据和跟踪数据以及 BAM 跟踪。 有关 BAM 跟踪的详细信息，请参阅[使用业务活动监视](../core/using-business-activity-monitoring.md)。  
  
-   **存档和清除数据从定期 BizTalk 跟踪 (BizTalkDTADb) 数据库**  
  
    -   如果启用了跟踪，则应定期存档和清除 BizTalk 跟踪数据库中的数据，以使该数据库保持适当的大小，这有助于改善系统性能。 有关详细信息，请参阅[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)。  
  
## <a name="see-also"></a>另请参阅  
 [查看跟踪的消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)