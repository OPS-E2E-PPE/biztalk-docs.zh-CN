---
title: "如何从 BizTalk 跟踪数据库清除数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, purging
- purging
- DTA Purge and Archive job, purging data
- purging, DTA Purge and Archive job
ms.assetid: cdf12866-442d-4c1f-b10f-ebf8d665d521
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01c56629aaa0934010ba79637b4e4a134bf29f26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-purge-data-from-the-biztalk-tracking-database"></a>如何从 BizTalk 跟踪数据库中清除数据
在清除 BizTalk 跟踪 (BizTalkDTADb) 数据库中的数据时，DTA 清除和存档作业将从 BizTalk 跟踪 (BizTalkDTADb) 数据库中清除不同类型的跟踪信息，例如消息和服务实例信息、业务流程事件信息和规则引擎跟踪数据。  
  
> [!IMPORTANT]
>  使用此过程将不会存档 BizTalk 跟踪 (BizTalkDTADb) 数据库。  
  
> [!WARNING]
>  如果未启用跟踪就在业务流程中捕获和处理了异常，则可以将具有“已启动”状态和异常信息的孤立跟踪实例插入 BizTalk 跟踪 (BizTalkDTADb) 数据库中。 在清除数据库后，此记录仍将保留。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须以 SQL Server sysadmin 固定服务器角色成员的帐户登录。  
  
### <a name="to-purge-data-from-the-biztalk-tracking-database"></a>从 BizTalk 跟踪数据库中清除数据  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP2**，然后单击**SQL Server Management Studio**。  
  
2.  在**连接到服务器**对话框中，指定 BizTalk 跟踪 (BizTalkDTADb) 数据库所在的 SQL Server 和适当的身份验证类型的名称，然后单击**连接**到连接到 SQL Server。  
  
3.  在**Microsoft SQL Server Management Studio**，双击**SQL Server 代理**，然后单击**作业**。  
  
4.  在**对象资源管理器详细信息**窗格中，右键单击**DTA 清除和存档 (BizTalkDTADb)**，然后单击**属性**。  
  
5.  在**作业属性-DTA 清除和存档 (BizTalkDTADb)**对话框中，在**选择页**，单击**步骤**。  
  
6.  在**作业步骤列表**，单击**存档和清除**，然后单击**编辑**。  
  
7.  在**作业步骤属性-存档和清除**对话框中，在**常规**页上，在**命令**框中，更改**exec dtasp_BackupAndPurgeTrackingDatabase**到**exec dtasp_PurgeTrackingDatabase**。  
  
    > [!CAUTION]
    >  **Exec dtasp_PurgeTrackingDatabase**存储的过程不会存档 BizTalk 跟踪 (BizTalkDTADb) 数据库。 在使用此选项之前，应确保不再需要存档跟踪数据。  
  
8.  在**命令**框中，编辑以下参数视情况而定，然后单击**确定**。  
  
    -   @nHourstinyint-任何完成实例早于 （实时小时数） + （实时天） 将被删除以及所有关联的数据。  
  
    -   @nDaystinyint-任何完成实例早于 （实时小时数） + （实时天） 将被删除以及所有关联的数据。 默认间隔为 1 天。  
  
    -   @nHardDaystinyint-将删除早于这一天的所有数据，即使数据不完整。 为 HardDeleteDays 指定的时间间隔应大于数据生存时段。 数据生存时段是维护 BizTalk 跟踪 (BizTalkDTADb) 数据库中的跟踪数据所需的时间间隔。 早于此间隔的所有内容都应在下一次存档时进行存档，然后清除。  
  
    -   @dtLastBackup-将此设置为**GetUTCDate()**要从 BizTalk 跟踪 (BizTalkDTADb) 数据库中清除数据。 当设置为**NULL**，数据不会清除从数据库。  
  
     您编辑的脚本应类似于以下形式：  
  
    ```  
    declare @dtLastBackup datetime set @dtLastBackup = GetUTCDate() exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup  
    ```  
  
9. 上**作业属性-DTA 清除和存档 (BizTalkDTADb)**对话框中，在**选择页**，单击**常规**，选择**已启用**复选框，并依次**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)