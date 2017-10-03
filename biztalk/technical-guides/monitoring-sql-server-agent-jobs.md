---
title: "监视 SQL Server 代理作业 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60d0a377-c86d-429b-9e48-c37bd5b0f912
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 489e9e8e8b5bf5b00125036d71ff5fa0f37f3545
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-sql-server-agent-jobs"></a>监视 SQL Server 代理作业
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包括执行重要的功能使你的服务器操作和正常运行的多个 SQL Server 代理作业。 您应该监视这些作业的运行状况，确保它们无错运行。  
  
## <a name="guidelines-for-monitoring-the-sql-server-agent-jobs"></a>用于监视 SQL Server 代理作业的准则  
 下面是用于监视作业的指导原则：  
  
-   **验证 SQL Server 代理服务正在运行**  
  
-   **验证由 BizTalk 服务器安装的 SQL Server 代理作业已启用并运行成功**  
  
     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL Server 代理作业至关重要： 如果它们未运行，随着时间的推移将降低系统性能。  
  
-   **验证，及时完成 BizTalk Server SQL Server 代理作业**  
  
     设置 Microsoft System Center Operations Manager 以监视作业。  
  
     你应注意的特定于某些作业的计划：  
  
    -   默认情况下，MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb 作业是连续运行。 监视软件应考虑此计划，并且不生成警告。  
  
    -   MessageBox_Message_Cleanup_BizTalkMsgBoxDb 作业未启用或计划，但它会启动 MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb 作业每隔 10 秒。 因此，此作业不应启用、 计划，或手动启动。  
  
-   **验证已正确配置 SQL Server 代理服务的启动类型**  
  
     验证 SQL Server 代理服务使用配置**Startuptype**的**自动**除非的 SQL Server 代理服务配置为在 Windows Server 群集上的群集资源。 如果 SQL Server 代理服务配置为群集资源，则应配置**Startuptype**作为**手动**由于服务将由群集服务。  
  
## <a name="additional-resources"></a>其他资源  
  
-   有关监视的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SQL 代理作业，请参阅[监视 SQL Server 代理作业和数据库](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md)。  
  
-   有关附带的 SQL Server 代理作业的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]请参阅["数据库结构和作业"](http://go.microsoft.com/fwlink/?LinkID=153451) (http://go.microsoft.com/fwlink/?LinkID=153451)。