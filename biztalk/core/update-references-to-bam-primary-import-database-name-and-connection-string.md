---
title: 更新 BAM 主导入数据库名称和连接字符串 |Microsoft Docs
ms.custom: ''
ms.date: 02/01/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3c58db0-f14f-429a-813c-bae29f6950d3
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3021542b405e7511c71b1de11752c16b387d3013
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399545"
---
# <a name="update-references-to-the-bam-primary-import-database-name-and-connection-string"></a>更新对 BAM 主导入数据库名称和连接字符串引用
如果备份了 BAMPrimaryImport 数据库，则在系统或数据发生故障时，可以将该备份还原到其他计算机和重命名该备份。  
  
 BAM 事件总线服务将事件数据从 MessageBox 数据库移到 BAMPrimaryImport 数据库。 BAM 事件总线服务包括故障容错逻辑，使它能够恢复并重新启动从意外故障而不会丢失任何数据。 有关 BAM 事件总线服务的详细信息，请参阅[管理 BAM 事件总线服务](../core/managing-the-bam-event-bus-service.md)。  
  
 若要还原 BAMPrimaryImport 数据库，请执行中的步骤[如何还原您数据库](../core/how-to-restore-your-databases.md)。 此外，还必须执行下列常规步骤后, 跟介绍详细信息中的步骤的过程：  
  
-   更新所有 BAM DTS 包中的 SQL 连接 1，以引用新数据库名称。  
  
-   使用新的数据库名称更新 web.config 文件。  
  
-   更新对 BAMPrimaryImport 数据库中所有 BAM 实时数据 Microsoft Excel 文件的引用。  
  
## <a name="prerequisites"></a>先决条件  
以 BizTalk Server Administrators 组的成员身份登录。  
  
## <a name="update-the-references"></a>更新引用  
  
1. 停止任何 BAM 多维数据集更新和数据维护数据转换服务 (DTS) 包，或者阻止它们运行，直到 BAMPrimaryImport 数据库的还原。  
  
2. 停止 BizTalk 应用程序服务 （其中包括 BAM 事件总线服务） 以便不会尝试导入数据库的更多的数据。  
  
   1.  从**启动**菜单中，键入**services.msc**，然后打开**Services**。  
  
   2.  右键单击**BizTalk 服务 BizTalk 组：BizTalkServerApplication**服务，然后**停止**。  
  
3. 还原 BAMPrimaryImport 数据库 (中的步骤[如何还原您数据库](../core/how-to-restore-your-databases.md))。  
  
4. 更新以下 Web.Config 文件：  
  
   - [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\BAMPortal\BamManagementService\Web.Config.  
  
      替换*\<ServerName\>* 具有新的服务器名称的字符串并*\<DatabaseName\>* 使用新的数据库名称。 更新以下连接字符串：  
  
      \<appSettings\>  
  
      <add key="BamServer" value="*\<ServerName\>*" /\>  
  
      <add key="BamDatabase" value="*\<DatabaseName\>*" /\>  
  
      \<add key="MaxResultRows" value="2000" /\>  
  
      \</appSettings\>  
  
   - [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\BAMPortal\BamQueryService\Web.Config.  
  
      替换*\<ServerName\>* 具有新的服务器名称的字符串并*\<DatabaseName\>* 使用新的数据库名称。 更新以下连接字符串：  
  
      \<appSettings\>  
  
      \<add key="BamServer" value="*\<ServerName\>*" /\>  
  
      \<add key="BamDatabase" value="*\<DatabaseName\>*" /\>  
  
      \<add key="MaxResultRows" value="2000" /\>  
  
      \</appSettings\>  
  
5. 打开命令提示符 (开始菜单 > 命令提示符下)，并导航到以下目录： [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Schema\Restore。  
  
6. 右键单击**SampleUpdateInfo.xml**，并**编辑**。  
  
   1.  注释掉所有除外 OldPrimaryImportDatabase、 PrimaryImportDatabase、 ArchivingDatabase、 AnalysisDatabase、 StarSchemaDatabase 和警报的数据库部分。 
   2.  对于 OldPrimaryImportDatabase、 PrimaryImportDatabase、 ArchivingDatabase、 AnalysisDatabase、 StarSchemaDatabase 和警报部分，设置**SourceServer**并**目标服务器**到这些数据库所在的现有服务器的名称。  
  
   3.  对于 PrimaryImportDatabase，设置**SourceServer**到移动 BAM 主导入数据库的服务器的名称。  
  
       > [!IMPORTANT]
       >  包括源和目标系统的名称周围的引号。  
  
       > [!NOTE]
       >  如果您重命名任何 BizTalk Server 数据库，请务必也更新数据库的名称。  
  
   4.  在完成编辑文件，请保存该文件，并退出。  
  
7. 在命令提示符下，键入：  
  
    **cscript UpdateDatabase.vbs SampleUpdateInfo.xml**  
  
   > [!NOTE]
   >  一次只能运行 UpdateDatabase.vbs。  
   > 
   >  在 64 位计算机上 64 位命令提示符下运行 UpdateDatabase.vbs。  
  
8. 在命令提示符处，导航到以下目录：  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking  
  
9. 在命令提示符下，编辑 bm.exe.config、 将项值更改为新的服务器名称，="DefaultServer"，然后保存该文件。  
  
10. 更新对 BAMPrimaryImport 数据库中所有 BAM 实时数据 Microsoft Excel 文件的引用。 对于每个文件：  
  
    1.  打开 Excel 实时数据文件。 以 _LiveData.xls 结尾的文件的名称。  
  
    2.  上**BAM**菜单上，单击**BAM 数据库连接**。  
  
    3.  在中**选择 BAM 数据库**对话框中，输入 SQL Server 和 BAMPrimaryImport 数据库，然后单击**确定**。  
  
    4.  上**文件**菜单上，单击**关闭并返回到 Microsoft Excel**。  
  
    5.  在“文件”菜单上，单击“保存”。  
  
11. 重新启动 BizTalk 应用程序服务。  
  
    1.  打开 **“services.msc”**。  
  
    2.  右键单击**BizTalk 服务 BizTalk 组：BizTalkServerApplication**服务，然后**启动**。  
  
12. 启用任何 BAM 多维数据集更新和数据维护 DTS 包。  
  
13. 若要解决任何未完成的跟踪实例，请参阅[解决未完成的活动实例](../core/how-to-resolve-incomplete-activity-instances.md)。  
  
## <a name="see-also"></a>请参阅  
 [备份和还原 BAM](../core/backing-up-and-restoring-bam.md)
