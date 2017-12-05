---
title: "如何更新对 BAM 主导入数据库名称和连接字符串引用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- restoring [BAM], connection strings
- Primary Import database [BAM], updating references
- connection strings, restoring
- connection strings, BAM
- restoring, BAM
- restoring [BAM], Primary Import database
- restoring [BAM], updating references
- Primary Import database [BAM], restoring
- BAM, restoring
- restoring, connection strings
ms.assetid: e3c58db0-f14f-429a-813c-bae29f6950d3
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23efa3df9c59732c8459018a886f7f499d268eff
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-update-references-to-the-bam-primary-import-database-name-and-connection-string"></a>如何更新对 BAM 主导入数据库名称和连接字符串的引用
如果备份了 BAMPrimaryImport 数据库，则在系统或数据发生故障时，可以将该备份还原到其他计算机上，然后重命名该备份。  
  
 BAM 事件总线服务将事件数据从 MessageBox 数据库移到 BAMPrimaryImport 数据库。 BAM 事件 Bus 服务包括故障容错逻辑，使它能够恢复并重新启动从意外的故障，而不会丢失任何数据。 有关 BAM 事件总线服务的详细信息，请参阅[管理 BAM 事件总线服务](../core/managing-the-bam-event-bus-service.md)。  
  
 若要还原 BAMPrimaryImport 数据库，请执行中的步骤[如何还原您的数据库](../core/how-to-restore-your-databases.md)。 此外，你必须执行下列常规步骤后, 跟一个描述各步骤的详细信息的过程：  
  
-   更新所有 BAM DTS 包中的 SQL 连接 1，以引用新的数据库名称。  
  
-   使用新的数据库名称更新 web.config 文件。  
  
-   更新对 BAMPrimaryImport 所有 BAM Livedata Microsoft Excel 文件中的数据库的引用。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 BizTalk Server Administrators 组成员的身份登录，才能执行此过程。  
  
### <a name="to-update-references-to-the-bamprimaryimport-database-name-and-connection-string"></a>更新对 BAMPrimaryImport 数据库名称和连接字符串的引用  
  
1.  停止任何 BAM 多维数据集更新和数据维护数据转换服务 (DTS) 包，或者阻止它们运行，直到 BAMPrimaryImport 数据库的还原完成为止。  
  
2.  停止 BizTalk 应用程序服务 （其中包括 BAM 事件总线服务） 以便不会尝试将更多的数据导入到数据库。  
  
    1.  单击**启动**，单击**运行**，然后键入**services.msc**。  
  
    2.  右键单击**BizTalk 服务 BizTalk 组： BizTalkServerApplication**服务，然后单击**停止**。  
  
3.  还原 BAMPrimaryImport 数据库，请执行中的步骤[如何还原您的数据库](../core/how-to-restore-your-databases.md)。  
  
4.  更新以下的 Web.Config 文件：  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BamManagementService\Web.Config。  
  
         替换 *\<ServerName\>* 字符串替换为新的服务器名称和 *\<DatabaseName\>* 使用新的数据库名称。 更新的以下连接字符串：  
  
         \<appSettings\>  
  
         < 添加 key ="BamServer"value ="*\<ServerName\>*"/\>  
  
         < 添加 key ="BamDatabase"value ="*\<DatabaseName\>*"/\>  
  
         \<添加项 ="MaxResultRows"value ="2000"/\>  
  
         \</appSettings\>  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BamQueryService\Web.Config。  
  
         替换 *\<ServerName\>* 字符串替换为新的服务器名称和 *\<DatabaseName\>* 使用新的数据库名称。 更新的以下连接字符串：  
  
         \<appSettings\>  
  
         \<添加项 ="BamServer"value ="*\<ServerName\>*"/\>  
  
         \<添加项 ="BamDatabase"value ="*\<DatabaseName\>*"/\>  
  
         \<添加项 ="MaxResultRows"value ="2000"/\>  
  
         \</appSettings\>  
  
5.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
6.  导航到以下目录： [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\Restore。  
  
7.  右键单击**SampleUpdateInfo.xml**，然后单击**编辑**。  
  
    1.  注释掉所有除外 BizTalkMgmtDb、 OldPrimaryImportDatabase、 PrimaryImportDatabase、 ArchivingDatabase、 AnalysisDatabase、 StarSchemaDatabase 和警报的数据库部分。  
  
    2.  BizTalkMgmtDb、 OldPrimaryImportDatabase、 PrimaryImportDatabase、 ArchivingDatabase、 AnalysisDatabase、 StarSchemaDatabase，和警报的部分，设置**"SourceServer"**和**"目标服务器"**为这些数据库驻留的现有服务器的名称。  
  
    3.  对于 PrimaryImportDatabase，设置**"SourceServer"**移动了 BAM 主导入数据库的服务器的名称。  
  
        > [!IMPORTANT]
        >  用引号将源系统和目标系统的名称括起来。  
  
        > [!NOTE]
        >  如果对任何 BizTalk Server 数据库进行了重命名，则必须也相应地更新这些数据库的名称。  
  
    4.  编辑完此文件后，请进行保存然后退出。  
  
8.  在命令提示符下，键入：  
  
     **cscript UpdateDatabase.vbs SampleUpdateInfo.xml**  
  
    > [!NOTE]
    >  只需运行 UpdateDatabase.vbs 一次。  
  
    > [!NOTE]
    >  在 64 位计算机上，必须从 64 位命令提示符下运行 UpdateDatabase.vbs。  
  
9. 在命令提示符下，导航到以下目录：  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking  
  
10. 在命令提示符下，编辑 bm.exe.config，将密钥的值更改为新的服务器名称 ="DefaultServer"，然后保存该文件。  
  
11. 更新对 BAMPrimaryImport 所有 BAM Livedata Microsoft Excel 文件中的数据库的引用。 对于每个文件：  
  
    1.  打开 Excel 实时数据文件。 以 _LiveData.xls 结尾的文件名称。  
  
    2.  上**BAM**菜单上，单击**BAM 数据库连接**。  
  
    3.  在**选择 BAM 数据库**对话框中，输入 SQL Server 和 BAMPrimaryImport 数据库，然后单击**确定**。  
  
    4.  上**文件**菜单上，单击**关闭并返回到 Microsoft Excel**。  
  
    5.  在“文件”菜单上，单击“保存”。  
  
12. 重新启动 BizTalk 应用程序服务。  
  
    1.  单击**启动**，单击**运行**，然后键入**services.msc**。  
  
    2.  右键单击**BizTalk 服务 BizTalk 组： BizTalkServerApplication**服务，然后单击**启动**。  
  
13. 启用任何 BAM 多维数据集更新和数据维护 DTS 包。  
  
14. 若要解决任何不完整的跟踪实例，请参阅[如何解决未完成的活动实例](../core/how-to-resolve-incomplete-activity-instances.md)。  
  
## <a name="see-also"></a>另请参阅  
 [备份和还原 BAM](../core/backing-up-and-restoring-bam.md)