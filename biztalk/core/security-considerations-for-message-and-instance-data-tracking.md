---
title: 有关消息和实例数据跟踪的安全注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4cce159d9012b3fd52405114898f1a2b257a2297
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280307"
---
# <a name="security-considerations-for-message-and-instance-data-tracking"></a>有关消息和实例数据跟踪的安全注意事项
出于安全原因，消息和服务实例跟踪不使用浏览器或 Url 与以前版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 此监视选项包含在 BizTalk Server 管理控制台中的组概述页的一部分。  为了向后兼容，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]仍在出于安全原因 shell 内承载 Microsoft Internet Explorer。  

 通过跟踪消息和服务实例数据，您可以访问故障排除和优化所需的技术详细信息在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。 因为此跟踪数据的功能强大，应限制在生产环境中的访问权限，以便恶意或未经授权的用户不会造成损害。 建议您遵循这些准则以保护和环境中使用 BizTalk Server 管理控制台。  

- 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Operators 组使用 BizTalk Server 管理控制台查看数据。 访问消息正文中的组概述部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，您必须作为的成员登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  

   当使用消息和服务实例跟踪时，可以访问以下数据库：  


  |               “数据库”               |                                                                                                   用户组/权限                                                                                                   |
  |--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  |  BizTalk 管理 (BizTalkMgmtDb)  |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运算符               |
  | BizTalk MessageBox (BizTalkMsgBoxDb) | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]操作员或读写权限 |
  |   BizTalk 跟踪 (BizTalkDTADb)    | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]操作员或只读权限  |


- 消息和服务实例跟踪生成有关中的所有主机报告[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境基于查询的参数。 若要仅成员的信息泄露的可能性降到最低[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组可以使用 BizTalk Server 管理控制台来执行这些查询。 但是，如果不希望所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员具有对数据的访问此跟踪进程生成，您可以通过添加/删除用户从 BizTalk 中的 HM_EVENT_WRITER 和 BAM_EVENT_WRITER SQL Server 角色来限制其访问的数据跟踪 (BizTalkDTADb) 数据库。  

- BizTalk 使用 BAM_EVENT_WRITER 和 hm_event_writer 这两个 SQL Server 角色来授予/拒绝其成员的权限读取/写入跟踪数据在跟踪数据库中，但不能通过角色成员身份。 不要删除这些 SQL Server 角色。 当你更改从承载为非跟踪主机 （或相反），调用 adm_ChangeHostTrackingPrivilege 存储过程。 此存储的过程将读取 BAM_EVENT_WRITER 和 hm_event_writer 这两个 SQL Server 角色的定义，并将相应的 GRANT/DENY 语句应用于主机 Windows 组。 这实现了相同的效果与将主机 Windows 组添加到这些 SQL 角色。  

- 在配置 BizTalk Server 管理控制台首选项以从存档数据库查看数据时，在这种情况下，跟踪查询连接到存放存档的数据，不适用于当前处于活动状态 BizTalk 跟踪 (BizTalkDTADb) 的数据库数据库。  

- 您不能跨网络地址转换 (NAT) 防火墙调试实时业务流程。 若要调试实时业务流程，必须在处理域具有一台管理计算机。  

- 具体取决于如何配置跟踪和管道，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可能会将存储在消息上下文中包含的敏感信息。 如果您使用 WMI 或跟踪消息正文保存到文件位置，请确保该位置具有加强的任意访问控制列表 (DACL) 以便仅[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 才具有读取这些消息正文的权限。 适用于任何保存消息正文，包括非 BizTalk 数据库可能会在此存档，并将其还原的位置相同的 DACL。  

- 您必须手动授予权限[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组访问跟踪分析服务器数据库 (BizTalkAnalysisDb); 默认情况下，只有 OLAP 管理员才具有这种权限。  

## <a name="see-also"></a>请参阅  
 [规划消息和实例跟踪](../core/planning-for-message-and-instance-tracking.md)   
 [查看跟踪的消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)