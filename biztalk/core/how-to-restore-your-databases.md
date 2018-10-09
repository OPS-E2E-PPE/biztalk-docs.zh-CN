---
title: 还原数据库 |Microsoft Docs
description: 请参阅还原 BizTalk Server 数据库，包括使用 SQL 代理作业，并运行 UpdateDatabase.vbs 和 UpdateRegistry.vbs 脚本的步骤。 另请参阅要执行的操作后数据库被还原，包括更新 BizTalk 管理控制台中的 SQL Server 实例名称。
ms.custom: ''
ms.date: 09/30/18
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0176932a-6b3d-4502-975b-a76296189092
caps.latest.revision: 52
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c318511902b31ffbe3fab4e055bdbf097d0f6865
ms.sourcegitcommit: 51ce182c5b71d3999a3920dd884bc9ec8334a899
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48575680"
---
# <a name="how-to-restore-your-databases"></a>如何还原数据库
必须将所有数据库还原到相同的标记，以确保各个数据库间的事务状态一致。 请参阅[标记的事务，完整备份，备份和日志备份](../core/marked-transactions-full-backups-and-log-backups.md)。  
  
 如果目标系统中只有一个服务器，请确保还原了所有日志备份集（除了最新日志备份集以外）。 请参阅[查看的历史记录备份还原](../core/viewing-the-history-of-restored-backups.md)。 如果没有还原所有日志备份集，并且当前没有运行还原作业，请运行还原作业（必要时，请手动运行）。 如果存在尚未完成的可还原备份集，则作业将处理它们，直到所有备份集全部还原为止。  
  
 如果目标系统中有多个服务器，则必须将所有服务器还原到相同的备份集。 查看每个服务器的还原历史记录，确保所有服务器上还原的最新日志备份集都是相同的。 如果不同，则必须在需要还原最新日志备份集的每个服务器上手动运行还原作业。  
  
 当所有的服务器都还原为相同的备份集后，最终的备份集可以手动还原。  
  
 adm_BackupHistory 表是记录源系统日志传送过程历史记录的核心。 所有执行的备份工作都记录到此表中。 目标系统中的所有服务器都从此表读取信息，以获取执行其还原工作所需的信息。  
  
> [!NOTE]
>  - 如果从备份还原 BAM 主导入数据库，则还应该使用该 BAM 主导入数据库备份之前的备份来还原 BAM 存档数据库、BAM 星型架构数据库和 BAM 分析数据库。 请参阅[备份和还原 BAM](../core/backing-up-and-restoring-bam.md)。  
>  - 如果将源数据库的完整备份或日志备份从备份 BizTalk Server 作业放置它们的位置上移走，则应该更新目标系统上 bts_LogShippingDatabases 表中该数据库的相关行，将 LogFileLocation 或 DBFileLocation 设置为目标系统应从中读取完整/日志备份文件的新位置。 运行 bts_ConfigureBtsLogShipping 存储过程时，将填充此表。 默认情况下，这些列设置为空，这表明目标系统应该从 adm_BackupHistory 表中存储的位置上读取这些备份文件。  
>  - 请总是在某个安全位置保留备份文件的一个副本。 即使你进行了日志备份，在没有备份文件的情况下也无法还原数据库。  
  
## <a name="prerequisites"></a>必要條件  
 使用作为 sysadmin SQL Server 角色成员的帐户登录到 SQL Server。  
  
## <a name="restore-your-databases"></a>还原数据库  
  
1. 在目标系统上，打开**SQL Server Management Studio**，并连接到 SQL Server。  
  
2. 展开 **“SQL Server 代理”**，然后展开 **“作业”**。 请执行以下操作：  
  
   1. 右键单击 **“BTS 日志传送 - 获取备份历史记录”** 作业，然后选择 **“禁用”**。 状态将更改为“成功”。  
  
   2. 右键单击 **“BTS 日志传送 - 还原数据库”** 作业，然后选择 **“禁用”**。 状态将更改为“成功”。  
  
   3. 右键单击 **“BTS 日志传送 - 还原到标记”** ，然后选择 **“作业开始步骤”**。 选择 **“步骤 ID 1”** ，然后选择 **“开始”**。  
  
       当状态更改为**成功**，SQL Server 代理作业和 BizTalk Server 数据库还原到目标系统。  
  
   > [!IMPORTANT]
   >  如果 **“状态”** 为“错误”，请选择“消息”字段中的链接以确定原因。 在继续前，这些作业的状态应为“成功”。  
  
3. 在 BizTalk 服务器上以前编辑 SampleUpdateInfo.xml 文件，打开命令提示符，并转到：  
  
    32 位计算机： `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`  
  
    64 位计算机： `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`  
  
4. 在命令提示符下，键入：  
  
    `cscript UpdateDatabase.vbs SampleUpdateInfo.xml`  
  
    此脚本可更新存储其他数据库的位置信息的所有表。  
  
   > [!IMPORTANT]
   >  - 在 BizTalk 组中的 **一个** 服务器上运行 UpdateDatabase.vbs。  
   >  - 在 64 位计算机上，必须从 64 位命令提示符下运行 UpdateDatabase.vbs。 请注意，64 位计算机上的默认命令提示符是 64 位命令提示符，位于 %SystemDrive%\windows\System32\cmd.exe。  
   >  - 还原数据库时，BizTalk EDI 引擎不需要任何 SampleUpdateInfo.xml 自己修改。  它依赖于与要访问的 EDI 表的 BizTalkDTADb 数据库的连接。  
  
5. 将已编辑的 SampleUpdateInfo.xml 文件复制到以下文件夹上**每个**此 BizTalk 组中运行 BizTalk Server 计算机：  
  
    32 位计算机： 复制到 `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`  
  
    64 位计算机： 复制到 `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`  
  
6. 上**每个**计算机在 BizTalk Server 组中，打开命令提示符，并转到：  
  
    32 位计算机： `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`  
  
    64 位计算机： `%SystemDrive%\Program Files (x86)Microsoft BizTalk Server <version>\Bins32\Schema\Restore`  
  
7. 在命令提示符下，键入：  
  
    `cscript UpdateRegistry.vbs SampleUpdateInfo.xml`  
  
    此脚本可更新存储其他数据库的位置信息的所有注册表项。  
  
   > [!IMPORTANT]
   >  - 在 BizTalk 组中的 **每个** 服务器上运行 UpdateRegistry.vbs。  
   >  - 在 64 位计算机上，必须从 64 位命令提示符下运行 UpdateRegistry.vbs。  请注意，64 位计算机上的默认命令提示符是 64 位命令提示符，位于 %SystemDrive%\windows\System32\cmd.exe。  
  
8. 重新启动所有 BizTalk Server 服务。 请参阅[如何启动、 停止、 暂停、 恢复或重新启动 BizTalk Server 服务](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)。  
  
9. 还原数据库后，重新启动 Windows 管理规范服务：  
  
    1.  打开 **“services.msc”**。  
  
    2.  右键单击 **“Windows 管理规范”**，然后选择 **“重新启动”**。  
  
10. 打开 **“BizTalk Server 管理”**。 请执行以下操作：  
  
    1. 右键单击 **“BizTalk 组”** ，然后选择 **“删除”**。  
  
    2. 右键单击 **“BizTalk Server 管理”** ，然后选择 **“连接到现有组”**。  
  
    3. 在 **“SQL Server 名称”** 中，键入托管 BizTalk 管理数据库的 SQL Server 实例的名称。 当选中 SQL Server 实例时，BizTalk Server 会自动检测该计算机上的 BizTalk Server 数据库。  
  
    4. 在 **“数据库名称”** 中，选择 BizTalk 管理数据库（默认为 **“BizTalkMgmtDb”** ），然后选择 **“确定”**。  
  
       在 BizTalk Server 管理控制台将 BizTalk 组添加到管理控制台。  
  
       BizTalk Server 现已还原，并且应运行。 接下来，配置备份 BizTalk Server 作业，以开始向新目标服务器写入备份。 还应该重新配置新的目标系统。  

## <a name="important"></a>重要提示**

- 如果您使用规则引擎中，在还原数据库后，必须重新规则引擎更新服务的每个服务器上启动 BizTalk Server 组中。 请参阅[如何启动、 停止、 暂停、 恢复或重新启动 BizTalk Server 服务](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)。  
- 如果您使用 BAM，现在是还原 BAM 数据库的时间。 请参阅[备份和还原 BAM](../core/backing-up-and-restoring-bam.md)。  
- 如果要移动数据库，并使用 BizTalk EDI 或 RosettaNet 加速器，某些 SQL 端口可能会对 BizTalk 数据库的安装程序。 导出绑定，搜索旧数据库链接，并相应地替换数据库链接。 

## <a name="next-steps"></a>后续步骤  
 [备份和还原 BAM](../core/backing-up-and-restoring-bam.md)  
  
## <a name="see-also"></a>请参阅  
 [配置备份 BizTalk Server 作业](../core/how-to-configure-the-backup-biztalk-server-job.md)   
 [配置日志传送的目标系统](../core/how-to-configure-the-destination-system-for-log-shipping.md)
