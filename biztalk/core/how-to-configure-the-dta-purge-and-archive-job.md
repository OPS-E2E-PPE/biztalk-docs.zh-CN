---
title: 配置 DTA 清除和存档作业 |Microsoft Docs
description: 在 SQL Server 代理来维护 BizTalk Server 中的跟踪数据库中设置 DTA 清除和存档作业参数
ms.custom: ''
ms.date: 10/11/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 156ccf9b-284f-4b96-a395-92936e8cebcf
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69b9b221a26ad844aa23b65ada5a8c6cce38cf8c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386089"
---
# <a name="configure-the-dta-purge-and-archive-job"></a>配置 DTA 清除和存档作业
存档或清除 BizTalk 跟踪 (BizTalkDTADb) 数据库中的数据之前，必须配置 DTA 清除和存档 (BizTalkDTADb) 作业。 此作业配置为调用 dtasp_BackupAndPurgeTrackingDatabase 存储过程使用六个形参，则必须配置。  
  
## <a name="prerequisites"></a>先决条件  
 使用 SQL Server sysadmin 固定服务器角色的成员的帐户登录。  
  
## <a name="configure-the-dta-purge-and-archive-job"></a>配置 DTA 清除和存档作业  
  
1.  在承载 BizTalk 跟踪 (BizTalkDTADb) 数据库的 SQL 服务器，打开**SQL Server Management Studio**。  
  
2.  在中**连接到服务器**，输入 BizTalk 跟踪 (BizTalkDTADb) 数据库所在的 SQL server 的名称、 输入身份验证类型，然后选择**Connect**以连接到 SQL server。  
  
3. 双击**SQL Server 代理**，然后选择**作业**。  
  
4.  在中**对象资源管理器详细信息**，右键单击**DTA 清除和存档 (BizTalkDTADb)**，然后选择**属性**。  
  
5.  在中**作业属性-DTA 清除和存档 (BizTalkDTADb)** 下**选择页**，选择**步骤**。  
  
6.  在中**作业步骤列表**，选择**存档和清除**，然后选择**编辑**。  
  
7.  在中**常规**，在**命令**框中，更新以下参数，然后选择**确定**。  
  
    -   @nLiveHours tinyint — 任何已完成实例早于 （生存小时数） + （生存天数） 也会删除所有关联的数据。 这是必需的参数，无默认值。  
  
    -   @nLiveDays tinyint — 任何已完成实例早于 （生存小时数） + （生存天数） 也会删除所有关联的数据。 默认间隔为 0 天。  
  
        > [!NOTE]
        >  对于 BizTalk 跟踪 (BizTalkDTADb) 数据库来说，LiveHours 和 LiveDays 之和是想要维护 BizTalk Server 环境中的数据生存时段。 删除与的数据生存时段之前完成实例相关联的所有数据。  
  
    -   @nHardDeleteDays tinyint — 所有数据 （即使数据不完整） 早于此将被删除。 为 HardDeleteDays 指定的时间间隔应大于数据生存时段。 数据生存时段是时间的你想要将 BizTalk 跟踪 (BizTalkDTADb) 数据库中保留跟踪数据间隔。 早于此时间间隔内有资格将在下一次存档，然后清除。 默认值为 0 天。  
  
    -   @nvcFolder nvarchar(1024) — 在其中放置备份文件的文件夹。 这是必需的参数，无默认值。  
  
    -   @nvcValidatingServer sysname — 将对其执行验证的服务器。 NULL 值表示正在进行任何验证。 默认值为 NULL。  
  
    -   @fForceBackup int，默认值为 0。 这被保留供将来使用。  
  
    -   @fHardDeleteRunningInstances int-默认值为 0。 设置为 1 时，删除所有正在运行的服务实例早于@nHardDeleteDays值。 
    
        > [!NOTE]
        > @fHardDeleteRunningInstances属性是从开始提供[BizTalk Server 2016 的累积更新 1年](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016)， [BizTalk Server 2013 R2 的累积更新 6年](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2)，并[BizTalk Server 2013 的累积更新 5](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013)。  
  
    你已编辑的命令应类似于以下。 在以下示例中，没有的实时时段的 1 小时、 1 天和删除的硬清除所有正在运行服务实例超过 1 天：  
  
    ```  
    exec dtasp_BackupAndPurgeTrackingDatabase 1, 0, 1, '\\MyBizTalkServer\backup', null, 0, 1  
    ```  
  
8.  上**作业属性-DTA 清除和存档 (BizTalkDTADb)** 对话框中的**选择页**，选择**常规**，选择**已启用**复选框，然后依次**确定**。  
  
## <a name="see-also"></a>请参阅  
 [存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)
