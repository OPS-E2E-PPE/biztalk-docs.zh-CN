---
title: 将 BizTalk Server 数据库移 |Microsoft Docs
description: 将 BizTalk Server 数据库移到新的服务器，包括停止服务以及使用 SQL Server 代理作业的步骤
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec302e6d-c89d-4fe7-849f-97b5566e8ba4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a3509a6a0297b0f58a16cfd3eff1dc29420232b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978902"
---
# <a name="how-to-move-the-biztalk-server-databases"></a>如何移动 BizTalk Server 数据库

## <a name="overview"></a>概述
可以使用此过程来将主 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库移动到其他服务器。 还可以使用此基本的相同过程将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库从本地 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 移动到远程 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 或 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 群集。  

## <a name="prerequisites"></a>必要條件  
是的成员的帐户登录[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]sysadmin 固定的服务器角色才能执行此过程。  
  
## <a name="move-steps"></a>移动步骤
  
1. 停止所有的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务。 有关详细信息，请参阅[重新启动 BizTalk Server 服务和关闭的 BizTalk Server](how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)。
  
   > [!IMPORTANT]
   >  确保在移动数据库之前停止所有的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务和作业非常重要。  
  
2. 停止 IIS 服务。  
  
3. 停止 SQL Server 代理服务。  
  
4. 备份 BizTalk 数据库的数据库备份过程中所述[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-the-biztalk-server-databases.md)。  
  
5. 还原以下数据库的新服务器上的 BizTalk 数据库还原过程在[如何还原您数据库](../core/how-to-restore-your-databases.md)。  
  
6. SQL Server 代理作业下面列出传输到新服务器中所述的脚本[如何备份和还原 SQL 代理作业](../core/how-to-back-up-and-restore-sql-agent-jobs.md)。  在新服务器上运行每个脚本以重新创建作业。  
  
    在新服务器上运行每个脚本以重新创建作业。 某些作业，如**备份 BizTalk Server (BizTalkMsgBoxDb)** 作业，必须进行重新配置，除非新服务器的文件路径和服务器名称与旧服务器相同。  
  
   > [!NOTE]
   >  此外可以使用 SSIS/DTS**传输作业**任务将作业移动到新服务器，但大多数用户可能会发现它更轻松地使用 SQL Management Studio 作业编写脚本。  
  
7. 除了上一步中所述，脚本编写 SQL Server 代理作业，你必须还编写登录脚本中所述[如何备份和还原 SQL Server 登录名](../core/how-to-back-up-and-restore-sql-server-logins.md)。 需要在目标服务器上还原这些登录信息。  
  
8. 还原[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]按照数据库的步骤 9 到 22 英寸[如何还原您数据库](../core/how-to-restore-your-databases.md)。 此过程用 BizTalk 数据库的新位置来更新 BizTalk 管理 (BizTalkMgmtDb) 数据库和注册表。  
  
   > [!NOTE]
   >  在中**SampleUpdateInfo.xml**文件中，注释掉除之外的数据库的所有已迁移到新的服务器。  
  
## <a name="see-also"></a>请参阅  
 [移动 BizTalk Server 数据库](../core/moving-biztalk-server-databases.md)