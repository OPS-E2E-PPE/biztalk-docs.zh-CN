---
title: "如何配置 DTA 清除和存档作业 |Microsoft 文档"
ms.custom: 
ms.date: 2015-11-09
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- purging, configuring
- DTA Purge and Archive job, configuring
- archiving [Tracking database], DTA Purge and Archive job
- archiving [Tracking database], configuring
- purging, DTA Purge and Archive job
ms.assetid: 156ccf9b-284f-4b96-a395-92936e8cebcf
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f4985e657f26945aa2fdc168b273dbfdb159efc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-dta-purge-and-archive-job"></a>如何配置 DTA 清除和存档作业
在对 BizTalk 跟踪 (BizTalkDTADb) 数据库中的数据进行存档或清除之前，必须首先配置 DTA 清除和存档 (BizTalkDTADb) 作业。 此作业被配置为调用 dtasp_BackupAndPurgeTrackingDatabase 存储过程中，使用六个参数必须配置。  
  
## <a name="prerequisites"></a>先决条件  
 你必须是 SQL Server sysadmin 固定服务器角色的成员才能执行这些步骤的帐户登录。  
  
### <a name="to-configure-the-dta-purge-and-archive-job"></a>配置 DTA 清除和存档作业  
  
1.  在承载 BizTalk 跟踪 (BizTalkDTADb) 数据库的 SQL 服务器，打开**SQL Server Management Studio**。  
  
2.  在**连接到服务器**，输入 SQL 服务器的名称跟踪 (BizTalkDTADb) BizTalk 数据库所在的位置，输入身份验证类型，然后选择**连接**以连接到 SQL server。  
  
3.  在**Microsoft SQL Server Management Studio**，双击**SQL Server 代理**，然后单击**作业**。  
  
4.  在**对象资源管理器详细信息**窗格中，右键单击**DTA 清除和存档 (BizTalkDTADb)**，然后单击**属性**。  
  
5.  在**作业属性-DTA 清除和存档 (BizTalkDTADb)**对话框中，在**选择页**，单击**步骤**。  
  
6.  在**作业步骤列表**，单击**存档和清除**，然后单击**编辑**。  
  
7.  上**常规**页上，在**命令**框中，编辑以下参数视情况而定，然后单击**确定**。  
  
    -   @nLiveHourstinyint-任何完成实例早于 （实时小时数） + （实时天） 将被删除以及所有关联的数据。 这是没有默认值的必需的参数。  
  
    -   @nLiveDaystinyint-任何完成实例早于 （实时小时数） + （实时天） 将被删除以及所有关联的数据。 默认间隔为 0 天。  
  
        > [!NOTE]
        >  对于 BizTalk 跟踪 (BizTalkDTADb) 数据库来说，LiveHours 与 LiveDays 相加之和即为要在 BizTalk Server 环境中维护的数据生存时段。 将删除与在数据生存时段之前完成的实例相关联的所有数据。  
  
    -   @nHardDeleteDaystinyint-所有数据 （即使不完整） 较旧，这将被删除。 为 HardDeleteDays 指定的时间间隔应大于数据生存时段。 数据生存时段是维护 BizTalk 跟踪 (BizTalkDTADb) 数据库中的跟踪数据所需的时间间隔。 早于此间隔的所有内容都应在下一次存档时进行存档，然后清除。 默认值为 0 天。  
  
    -   @nvcFoldernvarchar(1024) — 在其中放入备份文件的文件夹。 这是没有默认值的必需的参数。  
  
    -   @nvcValidatingServersysname-将在其执行验证的服务器。 NULL 值表示不执行任何验证。 默认值为 NULL。  
  
    -   @fForceBackupint-默认值为 0。 这被保留供将来使用。  
  
     编辑的命令应如下所示。 在下面的示例中，没有 1 小时的实时窗口和 1 天硬清除：  
  
    ```  
    exec dtasp_BackupAndPurgeTrackingDatabase 1, 0, 1, '\\MyBizTalkServer\backup', null, 0  
    ```  
  
8.  上**作业属性-DTA 清除和存档 (BizTalkDTADb)**对话框中，在**选择页**，单击**常规**，选择**已启用**复选框，并依次**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)