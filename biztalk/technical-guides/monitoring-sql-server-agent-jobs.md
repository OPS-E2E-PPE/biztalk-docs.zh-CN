---
title: 监视 SQL Server 代理作业 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60d0a377-c86d-429b-9e48-c37bd5b0f912
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fb4026b95a5f368c265b49425ab1d3e1ec776cd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015388"
---
# <a name="monitoring-sql-server-agent-jobs"></a>监视 SQL Server 代理作业
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包括执行重要功能，以使服务器正常操作和运行的多个 SQL Server 代理作业。 您应该监视这些作业的运行状况，确保它们无错运行。  

## <a name="guidelines-for-monitoring-the-sql-server-agent-jobs"></a>用于监视 SQL Server 代理作业的指导原则  
 下面是用于监视作业的指导原则：  

- **验证 SQL Server 代理服务正在运行**  

- **验证 BizTalk server 安装的 SQL Server 代理作业已启用并正在运行成功**  

   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL Server 代理作业至关重要： 如果未运行，随着时间的推移会降低系统性能。  

- **验证 BizTalk Server SQL Server 代理作业及时完成**  

   设置 Microsoft System Center Operations Manager 以监视作业。  

   应注意的特定于某些作业的计划：  

  -   默认情况下，MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb 作业会连续运行。 监视软件，应考虑此计划，并生成警告。  

  -   MessageBox_Message_Cleanup_BizTalkMsgBoxDb 作业未启用或未计划，但它由 MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb 作业启动每隔 10 秒。 因此，此作业不应启用、 计划，或手动启动。  

- **验证已正确配置 SQL Server 代理服务的启动类型**  

   验证 SQL Server 代理服务是否与配置**Startuptype**的**自动**除非 SQL Server 代理服务配置为在 Windows Server 群集上群集资源。 如果 SQL Server 代理服务配置为群集资源，则应配置**Startuptype**作为**手动**由于该服务将由群集服务。  

## <a name="additional-resources"></a>其他资源  

- 有关监视的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SQL 代理作业，请参阅[监视 SQL Server 代理作业和数据库](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md)。  

- 详细了解附带的 SQL Server 代理作业[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]请参阅["数据库结构和作业"](http://go.microsoft.com/fwlink/?LinkID=153451) (<http://go.microsoft.com/fwlink/?LinkID=153451>)。
