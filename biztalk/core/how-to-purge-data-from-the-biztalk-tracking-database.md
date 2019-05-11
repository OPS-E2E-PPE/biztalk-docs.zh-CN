---
title: 从 BizTalk 跟踪数据库中清除数据 |Microsoft Docs
description: 配置 dtasp_PurgeTrackingDatabase 存储过程来清除在 BizTalk Server 中的跟踪数据库 (BizTalkDTADB)
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
ms.openlocfilehash: 74a239f1b54ddf14cf0a9707868649a3df562cfc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384450"
---
# <a name="purge-data-from-the-biztalk-tracking-database"></a>从 BizTalk 跟踪数据库中清除数据
DTA 清除和存档作业清除 BizTalk 跟踪 (BizTalkDTADb) 数据库中，当清除不同类型的跟踪信息，例如消息和服务实例信息、 业务流程事件信息和规则引擎跟踪数据从 BizTalk 跟踪 (BizTalkDTADb) 数据库中。  
  
> [!IMPORTANT]
>  使用此过程不存档 BizTalk 跟踪 (BizTalkDTADb) 数据库。  
  
> [!WARNING]
>  如果异常是中捕获和处理业务流程未启用跟踪，与已启动状态和异常信息的孤立的跟踪实例可能会插入 BizTalk 跟踪 (BizTalkDTADb) 数据库。 此记录在清除数据库后仍将保留。  
  
## <a name="prerequisites"></a>先决条件  
使用 SQL Server sysadmin 固定服务器角色的成员才能执行此过程的帐户登录。  
  
## <a name="purge-data-from-the-biztalk-tracking-database"></a>清除 BizTalk 跟踪数据库中的数据  
  
1.  在承载 BizTalk 跟踪 (BizTalkDTADb) 数据库的 SQL 服务器，打开**SQL Server Management Studio**。 
  
2.  在中**连接到服务器**，输入 BizTalk 跟踪 (BizTalkDTADb) 数据库所在的 SQL server 的名称、 输入身份验证类型，然后选择**Connect**以连接到 SQL server。 
  
3.  双击**SQL Server 代理**，然后选择**作业**。  
  
4.  在中**对象资源管理器详细信息**，右键单击**DTA 清除和存档 (BizTalkDTADb)**，然后选择**属性**。  
  
5.  在中**作业属性-DTA 清除和存档 (BizTalkDTADb)** 下**选择页**，选择**步骤**。  
  
6.  在中**作业步骤列表**，选择**存档和清除**，然后选择**编辑**。  
  
7.  在中**作业步骤属性-存档和清除**，然后在**常规**页上，在**命令**框中，更改**exec dtasp_BackupAndPurgeTrackingDatabase**到**exec dtasp_PurgeTrackingDatabase**。  
  
    > [!CAUTION]
    >  **Exec dtasp_PurgeTrackingDatabase**存储的过程将不会存档 BizTalk 跟踪 (BizTalkDTADb) 数据库。 然后再使用此选项，请确保不再需要存档的跟踪数据。  
  
8.  在中**命令**框中，更新以下参数，然后选择**确定**。  
  
    -   @nHours tinyint — 任何已完成实例早于 （生存小时数） + （生存天数） 也会删除所有关联的数据。  
  
    -   @nDays tinyint — 任何已完成实例早于 （生存小时数） + （生存天数） 也会删除所有关联的数据。 默认间隔为 1 天。  
  
    -   @nHardDays tinyint — 将删除这一天的所有数据，即使数据不完整。 为 HardDeleteDays 指定的时间间隔应大于数据生存时段。 数据生存时段是时间的你想要将 BizTalk 跟踪 (BizTalkDTADb) 数据库中保留跟踪数据间隔。 早于此时间间隔内有资格将在下一次存档，然后清除。  
  
    -   @dtLastBackup — 将其设置为**getutcdate （)** 从 BizTalk 跟踪 (BizTalkDTADb) 数据库清除数据。 如果设置为**NULL**，数据不从数据库中清除。  

    -  @fHardDeleteRunningInstances int-默认值为 0。 设置为 1 时，删除所有正在运行的服务实例早于@nHardDeleteDays值。  
    
        > [!NOTE] 
        > @fHardDeleteRunningInstances属性是从开始提供[BizTalk Server 2016 的累积更新 1年](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016)， [BizTalk Server 2013 R2 的累积更新 6年](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2)，并[BizTalk Server 2013 的累积更新 5](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013)。   

    已编辑的脚本类似于以下内容：  
  
    ```  
    declare @dtLastBackup datetime set @dtLastBackup = GetUTCDate() exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup, 1  
    ```  
    
9. 上**作业属性-DTA 清除和存档 (BizTalkDTADb)** 对话框中的**选择页**，选择**常规**，选择**已启用**复选框，然后依次**确定**。  
  
## <a name="see-also"></a>请参阅  
 [存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)
