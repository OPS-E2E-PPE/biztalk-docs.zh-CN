---
title: "如何启用自动存档验证 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, archives [Tracking database]
- archiving [Tracking database], validating archive
ms.assetid: 406ca54a-6b1f-4bdb-9bad-bea5ea0f6e66
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e654d22a08a7b07210ded9c319953c288065927a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-enable-automatic-archive-validation"></a>如何启用自动存档验证
使用存档验证可以在创建存档时对其进行验证。 启用自动存档验证之前，必须先设置一个辅助数据库服务器，也称为验证服务器。 由于存档进程是一个简单备份，因此存储在磁盘上的实际图像可能由于硬件问题而受损。  
  
 使用存档验证功能，可确保存档（备份）成功并且可以进行还原。 在创建存档后，将通知验证服务器已创建了新的存档。 验证服务器将尝试还原该存档。 验证服务器必须是另一个 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 实例，与运行该作业的实例不同。 验证服务器上的 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 版本必须和用于驻留数据库的 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 版本相同。  
  
 如果还原成功，则验证服务器会将此信息发送回 BizTalk 跟踪 (BizTalkDTADb) 数据库。 在成功完成还原之前，清除作业将不清除其他任何数据。  
  
 如果还原不成功，则验证服务器会将此信息发送回 BizTalk 跟踪数据库。 清除作业将创建另一个存档并等待对该新存档进行验证。 这样可避免由于存档损坏而导致丢失跟踪数据的可能性。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，登录使用的帐户必须是 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定服务器角色的成员。  
  
### <a name="to-enable-automatic-archive-validation"></a>启用自动存档验证的步骤  
  
1.  在验证服务器上，单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP2**，然后单击**SQL Server Management Studio**.  
  
2.  在**连接到服务器**对话框框中，指定的名称[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]其中你可以通过执行测试还原过程中，验证存档，然后单击**连接**连接到相应的 SQL Server。  
  
    > [!NOTE]
    >  由于在验证存档时会降低系统性能，因此，此服务器不应同时用作其他 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的数据库服务器。  
  
3.  在**Microsoft SQL Server Management Studio**，单击**文件**，单击**打开**，然后单击**文件**。  
  
4.  在**打开的文件**对话框中，浏览到以下 SQL 脚本：  
  
    ```  
    %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\BTS_Tracking_ValidateArchive.sql  
    ```  
  
    > [!NOTE]
    >  你可能需要将脚本从运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机复制到验证服务器。  
  
5.  单击**查询**菜单，，然后单击**执行**。  
  
    > [!NOTE]
    >  只有当将 BizTalk 跟踪 (BizTalkDTADb) 数据库存档到其中的文件夹是网络共享时，BTS_Tracking_ValidateArchive.sql 脚本才能正常工作。  
  
     BTS_Tracking_ValidateArchive.sql 脚本将创建一个名为 ValidateArchive 的 SQL Server 代理作业。  
  
6.  存档和清除进程可能访问和/或更新数据库在不同的 SQL 服务器，因此你必须设置所涉及的 SQL Server 实例之间的链接服务器。 在**SQL Server Management Studio**，双击**Server 对象**，右键单击**链接服务器**，然后单击**新链接服务器**.  
  
     你必须设置之间的链接服务器：  
  
    -   每个 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库和 BizTalk 跟踪 (BizTalkDTADb) 数据库（如果它们驻留在不同的服务器上）。  
  
    -   BizTalk 跟踪 (BizTalkDTADb) 数据库以及用于存档验证的验证服务器。  
  
    -   BizTalk MessageBox (BizTalkMsgBoxDb) 数据库的宿主计算机上的 SQL Server 代理的服务帐户必须对链接服务器上的 BizTalk 跟踪 (BizTalkDTADb) 数据库具有 db_datareader 和 db_datawriter 权限。  
  
    > [!NOTE]
    >  运行作业所使用的帐户对链接的双方数据库都应具有数据库操作员 (DBO) 权限。  
  
7.  在**新链接服务器**对话框中，在**常规**页上，在**链接服务器**，输入你想要链接到的服务器的名称。  
  
     例如，BizTalk MessageBox (BizTalkMsgBoxDb) 数据库、BizTalk 跟踪 (BizTalkDTADb) 数据库或验证服务器的宿主服务器。  
  
8.  下**服务器类型**，单击**SQL Server**，然后单击**确定**。  
  
9. 在**Microsoft SQL Server Management Studio**，双击**SQL Server 代理**，然后单击**作业**。  
  
10. 在**对象资源管理器详细信息**窗格中，右键单击**ValidateArchive**，然后单击**属性**。  
  
11. 在**作业属性-ValidateArchive**对话框中，在**选择页**，单击**步骤**。  
  
12. 在**作业步骤列表**，单击**验证**，然后单击**编辑**。  
  
13. 上**常规**页上，在**命令**框中，在命令中， **exec dtasp_ValidateArchive null，null**，替换 null，null 与托管 BizTalk server 的名称跟踪数据库，括在单引号后, 跟用引号引起来，BizTalk 跟踪数据库的名称，然后单击**确定**。 例如：  
  
     **exec dtasp_ValidateArchive**  *\<TrackingServerName\>*  **'，'**  *\<TrackingDatabaseName\>* **'**  
  
> [!NOTE]
>  ValidateArchive 作业没有计划并且不应为其配置计划。 相反，在创建存档时 DTA 清除和存档 (BizTalkDTADb) 作业将自动启动此作业。  
  
## <a name="see-also"></a>另请参阅  
 [存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)