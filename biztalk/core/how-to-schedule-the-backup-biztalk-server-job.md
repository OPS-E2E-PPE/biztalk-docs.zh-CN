---
title: "计划备份的 BizTalk Server 作业 |Microsoft 文档"
description: "配置备份 BizTalk Server 作业参数，并将计划设置为运行每月、 每周、 每日或每小时"
ms.custom: 
ms.date: 11/02/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e89fff4-da87-4cdc-acc4-46f03c3269fc
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f09ca97f65605ac3bf427d1c1fcc322a14feb53
ms.sourcegitcommit: 9aaed443492b74729171fef79c634bff561af929
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2017
---
# <a name="schedule-the-backup-biztalk-server-job"></a>计划备份的 BizTalk Server 作业
备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作为 SQL Server 代理服务计划的作业运行。 如果要修改备份频率，可使用 SQL Server Management Studio 来更改备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业的计划。  
  
## <a name="prerequisites"></a>先决条件  
使用 SQL Server sysadmin 固定服务器角色的成员的帐户登录。  
  
## <a name="schedule-the-backup-biztalk-server-job"></a>计划备份 BizTalk Server 作业
  
1.  在承载 BizTalk 管理数据库的 SQL 服务器，打开**SQL Server Management Studio**。

2.  在**连接到服务器**，输入 SQL Server 数据库所驻留，BizTalk 服务器在其中选择身份验证类型的名称，然后**连接**。  
  
3.  在对象资源管理器中，双击**SQL Server 代理**，然后选择**作业**。  
  
4.  在细节窗格中，右键单击**备份 BizTalk Server (BizTalkMgmtDb)**，然后选择**属性**。  
  
5.  在**作业属性-备份 BizTalk Server (BizTalkMgmtDb)**下**选择页**，选择**步骤**。  
  
6.  在**作业步骤列表**，选择**BackupFull**，然后选择**编辑**。  
  
7.  在**作业步骤属性-BackupFull**中**命令**框中，通过更改运行完整备份的频率更新命令： **'h'** （每小时），**具有** （每天）、 **w** （每周一次），**我**（按月） **y** （每年）。 选择“确定”。  
  
    > [!NOTE]
    >  首次备份的 BizTalk Server 作业运行时，它将完成的完整备份。  
    
8.  配置其他 **@frequency** 参数：  
  
    - **@ForceFullBackupAfterPartialSetFailure**： 默认值是**false**。 当**false**，如果下一个周期进行完整备份是将等待，则完整备份将失败，系统。  
    
        > [!NOTE]
        >  如果你 **@frequency** 设置长时间 （如每周、 每月、 每年），然后将设置此参数为**false**会非常危险。 在此方案中，它可能是最好将此标志设置为**true**。 当**true**，每次失败，则系统强制本身创建完整备份。 存在可能会很小的性能影响，但它是 safter 具有可恢复的系统。
  
    - **@BackupHour**： 默认值为 NULL。 此参数直接相关 **@Frequency** 。 当将频率设置为**h** （每小时），设置你想要运行的完整备份的日期的小时。 你可以选择介于 0 （午夜） 到 23 （晚上 11 点） 之间的值。 如果留空，每小时都会运行完整备份。  
    
       > [!NOTE]
        >  如果超出了 0 到 23 范围 （例如，100 或-1） 数量设置此参数，系统会将其强制为 0。
  
    - **@UseLocalTime**： 状态为使用本地时间了额外的参数。 默认情况下，作业适用于 UTC 时间。 因此如果你的居住在澳大利亚 （这是 UTC + 10 小时），你的备份将在上午 10，而不是午夜运行。 作为最佳做法，建议将其设置为**1** (true)。  
  
9.  在**作业属性-备份 BizTalk Server (BizTalkMgmtDb)**下**选择页**，单击**计划**。  
  
10. 在**计划列表**，单击**MarkAndBackupLogSched**，然后单击**编辑**。  
  
11. 在**作业计划属性-MarkAndBackupLogSched**，在计划类型中，选择**重复执行**从下拉列表。  
  
     默认情况下，作业每 15 分钟运行一次。  
     
    > [!NOTE]
    >  你可以更改此值根据要求，但在非生产环境中的第一个测试。 设置此值过低导致频繁地备份，并将添加到您的 SQL 环境中的后台负载。 设置此值过高可能会增加事务日志的大小，影响性能。 在某些情况下，建议保留默认值。    
  
12. 更新的计划，如果需要，，然后选择**确定**。  
  
    > [!NOTE]
    >  [计划作业](https://docs.microsoft.com/sql/ssms/agent/schedule-a-job)提供更多详细信息。
  
13. 在**作业属性-备份 BizTalk Server (BizTalkMgmtDb)**，单击**确定**。  
  
## <a name="more-good-stuff"></a>更多有用内容  
 [配置备份 BizTalk Server 作业](../core/how-to-configure-the-backup-biztalk-server-job.md)   
 [为日志传送配置的目标系统](../core/how-to-configure-the-destination-system-for-log-shipping.md)   
 [还原数据库](../core/how-to-restore-your-databases.md)   
 [有关备份和还原的高级信息](../core/advanced-information-about-backup-and-restore1.md)
