---
title: 安排备份 BizTalk Server 作业 |Microsoft Docs
description: 配置备份 BizTalk Server 作业参数，并将计划设置为运行每月、 每周、 每日或每小时
ms.custom: ''
ms.date: 11/02/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e89fff4-da87-4cdc-acc4-46f03c3269fc
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83dd415648c55b53a9212ce20f4b1f754fb4fbb6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005126"
---
# <a name="schedule-the-backup-biztalk-server-job"></a>安排备份 BizTalk Server 作业
备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]制定的 SQL Server 代理服务的计划作业运行。 如果要修改备份频率，可使用 SQL Server Management Studio 来更改备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业的计划。  
  
## <a name="prerequisites"></a>必要條件  
使用 SQL Server sysadmin 固定服务器角色的成员的帐户登录。  
  
## <a name="schedule-the-backup-biztalk-server-job"></a>计划备份 BizTalk Server 作业
  
1. 在承载 BizTalk 管理数据库的 SQL 服务器，打开**SQL Server Management Studio**。

2. 在中**连接到服务器**，输入 BizTalk Server 数据库所驻留，在其中选择身份验证类型的 SQL Server 的名称，然后**Connect**。  
  
3. 在对象资源管理器，双击**SQL Server 代理**，然后选择**作业**。  
  
4. 在细节窗格中，右键单击**备份 BizTalk Server (BizTalkMgmtDb)**，然后选择**属性**。  
  
5. 在中**作业属性-备份 BizTalk Server (BizTalkMgmtDb)** 下**选择页**，选择**步骤**。  
  
6. 在中**作业步骤列表**，选择**BackupFull**，然后选择**编辑**。  
  
7. 在中**作业步骤属性-BackupFull**，在**命令**框中，通过更改运行完整备份的频率更新命令： **'h'** （每小时）、**有** （每天） **w** （每周），**是 '** （每月）， **y** （每年）。 选择“确定”。  
  
   > [!NOTE]
   >  第一次备份 BizTalk Server 作业运行时，它将完成的完整备份。  
    
8. 配置其他<strong>@frequency</strong>参数：  
  
   - <strong>@ForceFullBackupAfterPartialSetFailure</strong>： 默认值是**false**。 当**false**，如果完整备份失败，系统会等待下一个周期之前进行完整备份。  
    
     > [!NOTE]
     >  如果你<strong>@frequency</strong>设置为长时间 （如每周、 每月、 每年），然后将此参数设置**false**可能是危险的。 在此方案中，可能是最好将此标志设置为 **，则返回 true**。 当 **，则返回 true**，每次都失败，系统强制本身创建完整备份。 可能存在很小的性能的影响，但它是 safter 若要使用的是可恢复的系统。
  
   - <strong>@BackupHour</strong>： 默认值为 NULL。 此参数直接与相关<strong>@Frequency</strong>。 如果将频率设置为**h** （每小时），设置你希望完整备份，运行在一天的小时。 可以选择介于 0 （午夜） 到 23 （晚上 11 点） 之间的值。 如果为空，则运行完整备份每隔一小时。  
    
      > [!NOTE]
       >  如果将此参数设置与 0 到 23 范围 （例如，100 或-1） 以外的数字时，系统会将其强制为 0。
  
   - <strong>@UseLocalTime</strong>： 一个额外的参数，表明若要使用本地时间。 默认情况下，作业可使用 UTC 时间。 因此，如果您住在澳大利亚 （这是 UTC + 10 小时），你的备份运行在上午 10 点而不是午夜。 作为最佳做法，建议将其设置为**1** (true)。  
  
9. 在中**作业属性-备份 BizTalk Server (BizTalkMgmtDb)** 下**选择页**，单击**计划**。  
  
10. 在中**计划列表**，单击**MarkAndBackupLogSched**，然后单击**编辑**。  
  
11. 在中**作业计划属性-MarkAndBackupLogSched**，在计划类型中，选择**重复执行**从下拉列表。  
  
     默认情况下，作业每 15 分钟运行一次。  
     
    > [!NOTE]
    >  您可以更改此值根据要求，但在非生产环境中的第一个测试。 设置此值太低将导致频繁地进行备份，并将添加到您的 SQL 环境中的后台负载。 设置此值过高可能会增加事务日志的大小，并会影响性能。 在某些情况下，建议保留默认值。    
  
12. 更新计划，如果需要，并选择**确定**。  
  
    > [!NOTE]
    >  [计划作业](https://docs.microsoft.com/sql/ssms/agent/schedule-a-job)提供了更多详细信息。
  
13. 在中**作业属性-备份 BizTalk Server (BizTalkMgmtDb)**，单击**确定**。  
  
## <a name="more-good-stuff"></a>更多有用内容  
 [配置备份 BizTalk Server 作业](../core/how-to-configure-the-backup-biztalk-server-job.md)   
 [为日志传送配置的目标系统](../core/how-to-configure-the-destination-system-for-log-shipping.md)   
 [还原数据库](../core/how-to-restore-your-databases.md)   
 [有关备份和还原的高级信息](../core/advanced-information-about-backup-and-restore1.md)
