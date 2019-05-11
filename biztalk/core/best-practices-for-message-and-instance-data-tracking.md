---
title: 消息和实例数据跟踪的最佳做法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HAT, best practices
- best practices, HAT
ms.assetid: 2ac5c87b-2059-4912-9cec-2ae4eaac56df
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8415547ec5f4300a89d8a96ffc3ee78325c7c57d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358197"
---
# <a name="best-practices-for-message-and-instance-data-tracking"></a>消息和实例数据跟踪的最佳实践
查看使用历史记录和跟踪数据的以下最佳实践。  
  
-   **查看使用历史记录和跟踪数据的安全注意事项**  
  
    -   有关历史记录和跟踪数据的安全注意事项的详细信息，请参阅[消息和实例数据跟踪的安全注意事项](../core/security-considerations-for-message-and-instance-data-tracking.md)。  
  
-   **确保所有 MessageBox 数据库上运行的 SQL Server 代理服务**  
  
    -   SQL Server 代理使得消息正文用于 WMI、 历史记录和跟踪数据可用。 这使您可以运行作业来清理 MessageBox 数据库。 有关 SQL Server 代理的详细信息，请参阅 SQL Server 联机丛书。  
  
-   **启用消息正文跟踪**  
  
    -   消息正文跟踪需要处理的服务实例后保存消息已完成。  
  
-   **配置跟踪以适合你的业务需求**  
  
    -   你可以查看历史记录和跟踪数据之前，必须先配置使用 BizTalk Server 管理控制台的跟踪。 有多个注意事项需要牢记，在启用或禁用跟踪选项。 跟踪数据越多，速度就越快 BizTalk 跟踪 (BizTalkDTADb) 数据库将在大小增大，这可能会在运行时性能产生负面影响。 有关详细信息，请参阅[配置使用 BizTalk Server 管理控制台跟踪](http://msdn.microsoft.com/49b7f9d3-60b5-41bd-ba8b-029253926bef)。  
  
-   **选择适当类型的跟踪进行故障排除或审核**  
  
    -   有关故障排除在开发环境中，或在过渡或生产环境中，应启用所有跟踪选项，以便可以查看项目事件、 消息属性、 消息正文和业务流程事件的详细信息。 这提供了一套丰富的跟踪可用于在您的系统中重新创建的事件顺序和调试应用程序的信息。  
  
    -   对于生产级别的审核，请仔细选择你想要审核，然后启用仅对这些事件的跟踪事件。 例如，许多企业希望能够证明消息进入和退出系统。 若要实现此目的，应启用入站的跟踪相应的接收端口和出站跟踪对相应发送端口。 如有必要，可以添加消息属性和消息正文跟踪。  
  
    -   用于测量业务关键绩效指标 (Kpi) 或由指定的业务里程碑的成就度量的进度，应使用业务活动监视 (BAM) 跟踪。 BAM 跟踪具有有限的功能来跟踪和存储消息正文，因此，如果这是重要的是，应与 BAM 跟踪结合使用历史记录和跟踪数据。 有关 BAM 跟踪的详细信息，请参阅[使用业务活动监视](../core/using-business-activity-monitoring.md)。  
  
-   **存档和清除 BizTalk 跟踪 (BizTalkDTADb) 数据库定期的数据**  
  
    -   如果已启用跟踪，你应存档，并清除 BizTalk 跟踪数据库定期帮助保持适当的大小，该数据库，可帮助提高系统性能的数据。 有关详细信息，请参阅[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)。  
  
## <a name="see-also"></a>请参阅  
 [查看跟踪的消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)