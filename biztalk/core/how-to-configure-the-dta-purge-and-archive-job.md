---
title: "配置 DTA 清除和存档作业 |Microsoft 文档"
description: "在 SQL Server 代理来维护 BizTalk Server 中的跟踪数据库中设置 DTA 清除和存档作业参数"
ms.custom: 
ms.date: 10/11/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 156ccf9b-284f-4b96-a395-92936e8cebcf
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 149719b7eea50ce53c14298597c94729162d43b0
ms.sourcegitcommit: 1fb633fcf919ce3124405420a5d9faa79d9d508e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2017
---
# <a name="configure-the-dta-purge-and-archive-job"></a>配置 DTA 清除和存档作业
在对 BizTalk 跟踪 (BizTalkDTADb) 数据库中的数据进行存档或清除之前，必须首先配置 DTA 清除和存档 (BizTalkDTADb) 作业。 此作业被配置为调用 dtasp_BackupAndPurgeTrackingDatabase 存储过程中，使用六个参数必须配置。  
  
## <a name="prerequisites"></a>先决条件  
 使用 SQL Server sysadmin 固定服务器角色的成员的帐户登录。  
  
## <a name="configure-the-dta-purge-and-archive-job"></a>配置 DTA 清除和存档作业  
  
1.  在承载 BizTalk 跟踪 (BizTalkDTADb) 数据库的 SQL 服务器，打开**SQL Server Management Studio**。  
  
2.  在**连接到服务器**，输入 SQL 服务器的名称跟踪 (BizTalkDTADb) BizTalk 数据库所在的位置，输入身份验证类型，然后选择**连接**以连接到 SQL server。  
  
3. 双击**SQL Server 代理**，然后选择**作业**。  
  
4.  在**对象资源管理器详细信息**，右键单击**DTA 清除和存档 (BizTalkDTADb)**，然后选择**属性**。  
  
5.  在**作业属性-DTA 清除和存档 (BizTalkDTADb)**下**选择页**，选择**步骤**。  
  
6.  在**作业步骤列表**，选择**存档和清除**，然后选择**编辑**。  
  
7.  在**常规**中**命令**框中，更新的以下参数，然后选择**确定**。  
  
    -   @nLiveHourstinyint-任何完成实例早于 （实时小时数） + （实时天） 将被删除以及所有关联的数据。 这是没有默认值的必需的参数。  
  
    -   @nLiveDaystinyint-任何完成实例早于 （实时小时数） + （实时天） 将被删除以及所有关联的数据。 默认间隔为 0 天。  
  
        > [!NOTE]
        >  对于 BizTalk 跟踪 (BizTalkDTADb) 数据库来说，LiveHours 与 LiveDays 相加之和即为要在 BizTalk Server 环境中维护的数据生存时段。 将删除与在数据生存时段之前完成的实例相关联的所有数据。  
  
    -   @nHardDeleteDaystinyint-所有数据 （即使不完整） 较旧，这将被删除。 为 HardDeleteDays 指定的时间间隔应大于数据生存时段。 数据生存时段是维护 BizTalk 跟踪 (BizTalkDTADb) 数据库中的跟踪数据所需的时间间隔。 早于此间隔的所有内容都应在下一次存档时进行存档，然后清除。 默认值为 0 天。  
  
    -   @nvcFoldernvarchar(1024) — 在其中放入备份文件的文件夹。 这是没有默认值的必需的参数。  
  
    -   @nvcValidatingServersysname-将在其执行验证的服务器。 NULL 值表示不执行任何验证。 默认值为 NULL。  
  
    -   @fForceBackupint-默认值为 0。 这被保留供将来使用。  
  
    -   @fHardDeleteRunningInstancesint-默认值为 0。 设置为 1 时，删除所有正在运行的服务实例早于@nHardDeleteDays值。 
    
        > [!NOTE]
        > @fHardDeleteRunningInstances属性是从开始提供[BizTalk Server 2016 的累积更新 1年](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016)， [BizTalk Server 2013 R2 的累积更新 6年](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2)，和[BizTalk Server 2013 的累积更新 5](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013)。  
  
    编辑的命令应类似于以下。 在以下示例中，没有 1 小时的实时窗口、 1 天和删除的硬清除所有正在运行服务实例超过 1 天：  
  
    ```  
    exec dtasp_BackupAndPurgeTrackingDatabase 1, 0, 1, '\\MyBizTalkServer\backup', null, 0, 1  
    ```  
  
8.  上**作业属性-DTA 清除和存档 (BizTalkDTADb)**对话框中，在**选择页**，选择**常规**，选择**已启用**复选框，，然后选择**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)
