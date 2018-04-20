---
title: 从 BizTalk 跟踪数据库清除数据 |Microsoft 文档
description: 配置 dtasp_PurgeTrackingDatabase 存储过程以清除 BizTalk Server 中的跟踪数据库 (BizTalkDTADB)
ms.custom: ''
ms.date: 10/11/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cdf12866-442d-4c1f-b10f-ebf8d665d521
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06217a7d5012eb402698ad35e76ccfc886952f6e
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="purge-data-from-the-biztalk-tracking-database"></a>从 BizTalk 跟踪数据库清除数据
在清除 BizTalk 跟踪 (BizTalkDTADb) 数据库中的数据时，DTA 清除和存档作业将从 BizTalk 跟踪 (BizTalkDTADb) 数据库中清除不同类型的跟踪信息，例如消息和服务实例信息、业务流程事件信息和规则引擎跟踪数据。  
  
> [!IMPORTANT]
>  使用此过程将不会存档 BizTalk 跟踪 (BizTalkDTADb) 数据库。  
  
> [!WARNING]
>  如果未启用跟踪就在业务流程中捕获和处理了异常，则可以将具有“已启动”状态和异常信息的孤立跟踪实例插入 BizTalk 跟踪 (BizTalkDTADb) 数据库中。 在清除数据库后，此记录仍将保留。  
  
## <a name="prerequisites"></a>必要條件  
使用 SQL Server sysadmin 固定服务器角色的成员，才能执行此过程的帐户登录。  
  
## <a name="purge-data-from-the-biztalk-tracking-database"></a>从 BizTalk 跟踪数据库中清除数据  
  
1.  在承载 BizTalk 跟踪 (BizTalkDTADb) 数据库的 SQL 服务器，打开 **SQL Server Management Studio**。 
  
2.  在 **连接到服务器**, ，输入 SQL 服务器的名称跟踪 (BizTalkDTADb) BizTalk 数据库所在的位置，输入身份验证类型，然后选择 **连接** 以连接到 SQL server。 
  
3.  双击**SQL Server 代理**，然后选择**作业**。  
  
4.  在**对象资源管理器详细信息**，右键单击**DTA 清除和存档 (BizTalkDTADb)**，然后选择**属性**。  
  
5.  在**作业属性-DTA 清除和存档 (BizTalkDTADb)**下**选择页**，选择**步骤**。  
  
6.  在**作业步骤列表**，选择**存档和清除**，然后选择**编辑**。  
  
7.  在**作业步骤属性-存档和清除**上**常规**页上，在**命令**框中，更改**exec dtasp_BackupAndPurgeTrackingDatabase**到**exec dtasp_PurgeTrackingDatabase**。  
  
    > [!CAUTION]
    >  **Exec dtasp_PurgeTrackingDatabase** 存储的过程不会存档 BizTalk 跟踪 (BizTalkDTADb) 数据库。 在使用此选项之前，应确保不再需要存档跟踪数据。  
  
8.  在**命令**框中，更新的以下参数，然后选择**确定**。  
  
    -   @nHours tinyint-任何完成实例早于 （实时小时数） + （实时天） 将被删除以及所有关联的数据。  
  
    -   @nDays tinyint-任何完成实例早于 （实时小时数） + （实时天） 将被删除以及所有关联的数据。 默认间隔为 1 天。  
  
    -   @nHardDays tinyint-将删除早于这一天的所有数据，即使数据不完整。 为 HardDeleteDays 指定的时间间隔应大于数据生存时段。 数据生存时段是维护 BizTalk 跟踪 (BizTalkDTADb) 数据库中的跟踪数据所需的时间间隔。 早于此间隔的所有内容都应在下一次存档时进行存档，然后清除。  
  
    -   @dtLastBackup -将此设置为 **GetUTCDate()** 要从 BizTalk 跟踪 (BizTalkDTADb) 数据库中清除数据。 当设置为 **NULL**, ，数据不会清除从数据库。  

    -  @fHardDeleteRunningInstances int-默认值为 0。 设置为 1 时，删除所有正在运行的服务实例早于@nHardDeleteDays值。  
    
        > [!NOTE] 
        > @fHardDeleteRunningInstances属性是从开始提供[BizTalk Server 2016 的累积更新 1年](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016)， [BizTalk Server 2013 R2 的累积更新 6年](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2)，和[BizTalk Server 2013 的累积更新 5](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013)。   

    你已编辑的脚本与以下类似：  
  
    ```  
    declare @dtLastBackup datetime set @dtLastBackup = GetUTCDate() exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup, 1  
    ```  
    
9. 上**作业属性-DTA 清除和存档 (BizTalkDTADb)**对话框中，在**选择页**，选择**常规**，选择**已启用**复选框，，然后选择**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)
