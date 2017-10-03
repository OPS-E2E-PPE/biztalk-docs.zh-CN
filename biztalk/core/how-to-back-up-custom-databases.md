---
title: "如何备份自定义数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom databases
- customizing, custom databases
- backing up, custom databases
ms.assetid: 86bebf3c-968e-4fad-9dab-ced1b04aaac7
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2993de90de3f7b768cc5368012d1f27f8940a99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-back-up-custom-databases"></a>如何备份自定义数据库
由于自定义数据库不随 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 一起安装，因此它们不包含在可由备份 BizTalk Server 作业进行标记并备份的数据库的默认列表中。 如果希望备份 BizTalk Server 作业对自定义数据库进行备份，则必须手动将自定义数据库添加到备份 BizTalk Server 作业中。  
  
## <a name="prerequisites"></a>先决条件  
  
1.  必须配置 SQL Server，使其使用完全恢复模式，以确保 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库备份集中数据的完整性。  有关详细信息请参阅[日志传送](../core/log-shipping.md)。  
  
2.  若要备份自定义数据库，登录所用的用户帐户必须有权访问每个要备份的数据库。  
  
     BizTalk Server 包含一个名为 BTS_BACKUP_USERS 的 SQL Server 角色，因此用来备份数据库的用户帐户不需要 SQL Server 中的系统管理员权限，除非是控制备份过程的主服务器。  
  
     在设置要用于备份数据库的用户帐户时，请注意以下事项：  
  
    -   必须为此用户创建一个 SQL Server 登录帐户，并在每个服务器上为此用户分配 BizTalk BTS_BACKUP_USERS 角色。  
  
    -   可以对 BizTalk Server 备份作业进行配置，使其在与 SQL Server 代理服务所用不同的用户帐户下运行。  
  
    -   必须将 SQL Server 代理服务配置为在域帐户下运行。 如果所有的数据库都在同一台计算机上，则可将 SQL Server 代理配置为使用本地帐户。  
  
### <a name="to-back-up-custom-databases"></a>备份自定义数据库  
  
1.  在新数据库中生成对象：  
  
    -   浏览到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema 目录，然后对要备份的所有自定义数据库运行 Backup_Setup_All_Procs.sql 和 Backup_Setup_All_Tables.sql。 此操作将创建必需的过程、表和角色，并向存储过程分配权限。  
  
2.  执行以下配置：  
  
    -   将 BizTalk 管理数据库的宿主 SQL Server 链接到新数据库的宿主 SQL Server。 管理 SQL Server 上用来运行 SQL Server 代理服务的帐户必须是域帐户，该帐户应映射到要备份的数据库所在的每台计算机上。 如果这些数据库在同一台计算机上，则可跳过此步骤。 它是自动完成的。  
  
    -   对于管理 SQL Server 上运行 SQL Server 代理服务的帐户，在新数据库的宿主 SQL Server 上为其添加登录名。 如果这些数据库在同一台计算机上，则可跳过此步骤。  
  
    -   在新数据库中为上一步创建的登录名添加用户，并将这类用户添加到 BTS_BACKUP_USERS 角色中。 步骤 1 中的脚本创建了此角色，并向其授予了所需过程的执行权限。  
  
3.  在 BizTalk 管理 (BizTalkMgmtDb) 数据库中，使用 SQL Server 企业管理器或 SQL Server Management Studio，修改**adm_OtherBackupDatabases**要某一行中包含的每个自定义数据库表。  
  
4.  根据下表，在相应列中键入新服务器和数据库的名称。  
  
    |列|值|  
    |------------|-----------|  
    |DefaultDatabaseName|自定义数据库的友好名称。|  
    |DatabaseName|自定义数据库的名称。|  
    |ServerName|运行 SQL Server 的计算机的名称。|  
    |BTSServerName|BizTalk Server 的名称。 虽然并不使用此值，但它不能为空。|  
  
 下次运行备份 BizTalk Server 作业时，它就会备份自定义数据库了。  
  
## <a name="see-also"></a>另请参阅  
 [备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)   
 [有关备份和还原的高级的信息](../core/advanced-information-about-backup-and-restore1.md)