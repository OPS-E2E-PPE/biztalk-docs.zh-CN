---
title: 如何自定义数据库的备份 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom databases
- customizing, custom databases
- backing up, custom databases
ms.assetid: 86bebf3c-968e-4fad-9dab-ced1b04aaac7
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba90f39a90e2a80abda1a00214aafec48c6ea419
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387080"
---
# <a name="how-to-back-up-custom-databases"></a>如何备份自定义数据库
因为自定义数据库未安装与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，则不包含在要进行标记和由备份 BizTalk Server 作业备份的数据库的默认列表。 如果你想要备份自定义数据库的备份 BizTalk Server 作业，必须手动将数据库添加到备份 BizTalk Server 作业。  
  
## <a name="prerequisites"></a>先决条件  
  
1. SQL Server 必须配置为使用完整恢复模式来确保数据完整性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库备份集。  有关详细信息请参阅[日志传送](../core/log-shipping.md)。  
  
2. 若要备份自定义数据库，必须使用有权访问每个要备份的数据库用户帐户登录。  
  
    BizTalk Server 包含名为 BTS_BACKUP_USERS，以便你用来备份数据库的用户帐户不需要在 SQL Server 中，除了控制备份过程的主服务器的系统管理员权限的 SQL Server 角色。  
  
    您用来备份数据库的用户帐户进行设置，请注意以下事项：  
  
   -   必须创建此用户，一个 SQL Server 登录帐户，并将此用户分配到每个服务器上的 BizTalk BTS_BACKUP_USERS 角色。  
  
   -   BizTalk Server 备份作业可以配置为在不同于用于 SQL Server 代理服务的用户帐户下运行。  
  
   -   必须配置为域帐户下运行的 SQL Server 代理服务。 如果所有数据库都都在同一计算机上，可以配置 SQL Server 代理以使用本地帐户。  
  
### <a name="to-back-up-custom-databases"></a>若要备份自定义数据库  
  
1. 生成新的数据库中的对象：  
  
   - 浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema 目录，然后对所有你想要备份的自定义数据库运行 Backup_Setup_All_Procs.sql 和 Backup_Setup_All_Tables.sql。 这将创建必要的过程、 表和角色并将权限分配给存储过程。  
  
2. 执行以下配置：  
  
   -   链接托管到托管新数据库的 SQL server 的 BizTalk 管理数据库的 SQL server。 用于管理 SQL Server 上运行的 SQL Server 代理服务帐户必须是映射到每台计算机上备份的数据库所在的域帐户。 如果数据库位于同一台计算机上则可以跳过此步骤。 这是自动完成。  
  
   -   宿主管理 SQL Server 上运行的 SQL Server 代理服务的帐户的新数据库的 SQL server 上添加一个登录名。 如果数据库位于同一台计算机上则可以跳过此步骤。  
  
   -   在上一步中创建的登录名的新数据库中添加用户并将其添加到 BTS_BACKUP_USERS 角色。 此角色创建并授予了所需过程的 Execute 权限的步骤 1 中的脚本。  
  
3. 在 BizTalk 管理 (BizTalkMgmtDb) 数据库中，使用 SQL Server 企业管理器或 SQL Server Management Studio 中，修改**adm_OtherBackupDatabases**表为每个自定义数据库加入一行。  
  
4. 下表中所示在相应列中键入新的服务器和数据库名称。  
  
   |“列”|ReplTest1|  
   |------------|-----------|  
   |DefaultDatabaseName|自定义数据库的友好名称。|  
   |DatabaseName|自定义数据库的名称。|  
   |ServerName|运行 SQL Server 的计算机的名称。|  
   |BTSServerName|BizTalk Server 的名称。 不使用此值，但尽管如此，它必须包含值。|  
  
   在下次运行备份 BizTalk Server 作业，它会将自定义数据库。  
  
## <a name="see-also"></a>请参阅  
 [备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)   
 [有关备份和还原的高级信息](../core/advanced-information-about-backup-and-restore1.md)