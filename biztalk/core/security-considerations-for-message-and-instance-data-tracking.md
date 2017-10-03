---
title: "消息和实例数据跟踪的安全注意事项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- permissions, HAT
- MessageBox database, HAT
- Tracking database, HAT
- security, HAT
- HAT, permissions
- HAT, security
- Management database, HAT
ms.assetid: 83e47dc2-c8e2-42a2-9c85-d511e7dae83f
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c342a62470fa26365f439cda242eeb119689737
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="security-considerations-for-message-and-instance-data-tracking"></a>消息和实例数据跟踪的安全注意事项
出于安全方面的原因，消息和服务实例跟踪不使用浏览器或 URL，这与以前版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不同。 此监视选项是作为 BizTalk Server 管理控制台中“组概述”页的一部分包含在内的。  对于向后兼容性，出于安全方面的原因，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 仍在 shell 中承载 Microsoft Internet Explorer。  
  
 通过跟踪消息和服务实例数据，您可以访问疑难解答和优化 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境所需的详细技术信息。 由于此跟踪数据非常强大，因此，应在生产环境中限制访问该数据，以免恶意用户或未经授权用户造成破坏。 建议您遵循以下准则，以便能够在您的环境中安全地使用 BizTalk Server 管理控制台。  
  
-   您必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 操作员组成员身份登录，才能使用 BizTalk Server 管理控制台查看数据。 若要访问 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台的“组概述”部分中的消息主体，您必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
     使用消息和服务实例跟踪时，可以访问以下数据库：  
  
    |数据库|用户组/权限|  
    |--------------|-----------------------------|  
    |BizTalk 管理 (BizTalkMgmtDb)|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 操作员|  
    |BizTalk MessageBox (BizTalkMsgBoxDb)|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 操作员或读写权限|  
    |BizTalk 跟踪 (BizTalkDTADb)|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 操作员或只读权限|  
  
-   消息和服务实例跟踪会根据查询参数，生成关于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中所有主机的报告。 为了将信息泄漏的可能性降至最低，只有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组的成员才能使用 BizTalk Server 管理控制台来执行这些查询。 但是，如果您不希望所有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员都能够访问此跟踪进程生成的数据，可以限制他们对这些数据的访问权限，方法是向 BizTalk 跟踪数据库 (BizTalkDTADb) 中的 HM_EVENT_WRITER 和 BAM_EVENT_WRITER 这两个 SQL Server 角色中添加相应的用户或从中删除这些用户。  
  
-   BizTalk 使用 BAM_EVENT_WRITER 和 HM_EVENT_WRITER 这两个 SQL Server 角色来授予或拒绝其成员在跟踪数据库中读取/写入跟踪数据的权限，而不通过角色成员身份来授予或拒绝。 请不要删除这两个 SQL Server 角色。 将跟踪主机更改为非跟踪主机（或与之相反）时，将调用 adm_ChangeHostTrackingPrivilege 存储过程。 此存储过程将读取 BAM_EVENT_WRITER 和 HM_EVENT_WRITER 这两个 SQL Server 角色的定义，并将相应的 GRANT/DENY 语句应用于主机 Windows 组。 这与向这两个 SQL 角色添加主机 Windows 组的效果相同。  
  
-   如果您配置 BizTalk Server 管理控制台首选项，以从存档数据库查看数据，在这种情况下，跟踪查询将连接到存放存档数据的数据库，而非当前活动的 BizTalk 跟踪数据库 (BizTalkDTADb)。  
  
-   您不能跨网络地址转换 (NAT) 防火墙调试实时业务流程。 必须在处理域中具有管理计算机，才能调试实时业务流程。  
  
-   根据您对跟踪和管道的配置，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可能会存储消息上下文中包含的敏感信息。 如果您使用 WMI 或跟踪将消息正文保存到某文件位置，请确保该位置具有加强的任意访问控制列表 (DACL)，以便只有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员才具有读取这些消息正文的权限。 请向保存消息正文的所有位置（包括可用来存档和还原消息正文的非 BizTalk 数据库）应用相同的 DACL。  
  
-   必须手动授予 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组访问跟踪分析服务器数据库 (BizTalkAnalysisDb) 的权限；默认情况下，只有 OLAP 管理员才具有这种权限。  
  
## <a name="see-also"></a>另请参阅  
 [规划消息和跟踪的实例](../core/planning-for-message-and-instance-tracking.md)   
 [查看跟踪的消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)