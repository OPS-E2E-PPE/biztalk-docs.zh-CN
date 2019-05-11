---
title: 如何启用自动存档验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, archives [Tracking database]
- archiving [Tracking database], validating archive
ms.assetid: 406ca54a-6b1f-4bdb-9bad-bea5ea0f6e66
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 257e6de9ce64b8d9e1f2c27bd401b453a1a47cda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337983"
---
# <a name="how-to-enable-automatic-archive-validation"></a>如何启用自动存档验证
存档验证可以验证存档，因为它们创建。 可以启用自动存档验证之前，必须设置一个辅助数据库服务器，也称为验证服务器。 由于存档进程是一个简单备份，就可以在磁盘上存储的实际图像可能会损坏由于硬件问题。  
  
 使用存档验证功能，可以确保存档 （备份） 成功并且可以进行还原。 创建存档后，通知验证服务器已创建一个新的存档。 验证服务器尝试还原该存档。 验证服务器必须是另一个实例的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]不同于在其中运行作业。 版本[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]的验证服务器必须与相同的版本[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]用来承载数据库。  
  
 如果还原成功，则验证服务器会此信息发送回 BizTalk 跟踪 (BizTalkDTADb) 数据库。 成功还原完成之前，清除作业将不会清除任何更多的数据。  
  
 如果还原不成功，则验证服务器会此信息发送回 BizTalk 跟踪数据库。 清除作业创建另一个存档并等待新存档的验证。 这可以防止存档损坏而导致丢失跟踪数据的可能性。  
  
## <a name="prerequisites"></a>先决条件  
 您必须是的成员的帐户登录[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]sysadmin 固定的服务器角色才能执行此过程。  
  
### <a name="to-enable-automatic-archive-validation"></a>若要启用自动存档验证  
  
1. 在验证服务器上，单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP2**，然后单击**SQL Server Management Studio**.  
  
2. 在中**连接到服务器**对话框框中，指定的名称[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]其中您可以通过执行测试还原过程中，验证存档，然后单击**Connect**连接到相应的 SQL Server。  
  
   > [!NOTE]
   >  此服务器不应为另一个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库服务器，如验证存档时会降低系统性能。  
  
3. 在中**Microsoft SQL Server Management Studio**，单击**文件**，单击**打开**，然后单击**文件**。  
  
4. 在中**打开的文件**对话框中，浏览到以下 SQL 脚本：  
  
   ```  
   %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\BTS_Tracking_ValidateArchive.sql  
   ```  
  
   > [!NOTE]
   >  可能需要将该脚本从运行的计算机复制[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到验证服务器。  
  
5. 单击**查询**菜单，并单击**Execute**。  
  
   > [!NOTE]
   >  只有存档 BizTalk 跟踪 (BizTalkDTADb) 数据库到其中的文件夹是网络共享时，BTS_Tracking_ValidateArchive.sql 脚本才能正常工作。  
  
    BTS_Tracking_ValidateArchive.sql 脚本将创建名为 ValidateArchive 的 SQL Server 代理作业。  
  
6. 存档和清除进程可能会访问和/或更新其他的 SQL Server 中的数据库，因此必须设置所涉及的 SQL Server 实例之间的链接服务器。 在中**SQL Server Management Studio**，双击**Server 对象**，右键单击**链接服务器**，然后单击**新建链接服务器**.  
  
    必须设置之间的链接服务器：  
  
   -   每个 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库和 BizTalk 跟踪 (BizTalkDTADb) 数据库，如果它们驻留在不同服务器上。  
  
   -   BizTalk 跟踪 (BizTalkDTADb) 数据库和用于存档验证的验证服务器。  
  
   -   承载 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库的计算机上的 SQL Server 代理服务帐户必须在链接服务器上具有 BizTalk 跟踪 (BizTalkDTADb) 数据库的 db_datareader 和 db_datawriter 权限。  
  
   > [!NOTE]
   >  用于运行作业的帐户应具有两个数据库上的数据库操作员 (DBO) 权限。  
  
7. 在中**新建链接服务器**对话框中，在**常规**页上，在**链接服务器**，输入你想要链接到的服务器的名称。  
  
    例如，托管 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库、 BizTalk 跟踪 (BizTalkDTADb) 数据库或验证服务器的服务器。  
  
8. 下**服务器类型**，单击**SQL Server**，然后单击**确定**。  
  
9. 在中**Microsoft SQL Server Management Studio**，双击**SQL Server 代理**，然后单击**作业**。  
  
10. 在中**对象资源管理器详细信息**窗格中，右键单击**ValidateArchive**，然后单击**属性**。  
  
11. 在中**作业属性-ValidateArchive**对话框中的**选择页**，单击**步骤**。  
  
12. 在中**作业步骤列表**，单击**验证**，然后单击**编辑**。  
  
13. 上**常规**页上，在**命令**框中的，在命令中， **exec dtasp_ValidateArchive null，null**，替换为 null，null 与托管 BizTalk server 的名称跟踪数据库，括在单引号后, 跟用引号引起来，BizTalk 跟踪数据库的名称，然后单击**确定**。 例如：  
  
     **exec dtasp_ValidateArchive '** *\<TrackingServerName\>* **', '** *\<TrackingDatabaseName\>* **'**  
  
> [!NOTE]
>  ValidateArchive 作业没有计划并且不应为其配置计划。 相反，DTA 清除和存档 (BizTalkDTADb) 作业就会自动创建存档时此作业。  
  
## <a name="see-also"></a>请参阅  
 [存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)