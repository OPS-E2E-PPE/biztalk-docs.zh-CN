---
title: 如何移动 BAM 主导入 Database1 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, Primary Import database [BAM]
- Primary Import database [BAM], migrating
ms.assetid: fab13fea-5c35-4a9f-977d-cc45545c54b2
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a63c556bfb95f4b22a3256540d3ecb336a17f7f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972659"
---
# <a name="how-to-move-the-bam-primary-import-database"></a>如何移动 BAM 主导入数据库
您可以使用此过程将 BAM 主导入数据库移至其他服务器。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须以 SQL Server sysadmin 固定服务器角色成员的帐户登录。  
  
### <a name="to-move-the-bam-primary-import-database"></a>移动 BAM 主导入数据库  
  
1.  停止所有 BizTalk Server 服务。 有关详细信息，请参阅[如何开始、 停止、 暂停、 继续或重新启动 BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)。  
  
2.  停止 IIS 服务。  
  
3.  停止 BAM 警报 Notification Service：  
  
    1.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
    2.  在命令提示符下，键入：  
  
        ```  
        Net stop NS$BamAlerts  
        ```  
  
4.  按照 SQL Server 联机从书中的说明在旧服务器上备份 BAM 主导入数据库。  
  
5.  将 BAM 主导入数据库复制到新 SQL Server 中。  
  
6.  按照 SQL Server 联机从书中的说明在新服务器上还原 BAM 主导入数据库。  
  
7.  在运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机中，浏览至以下文件夹：  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\Restore  
  
8.  右键单击**SampleUpdateInfo.xml**，然后单击**编辑**。  
  
9. 在文件的主导入数据库部分中，替换 **"SourceServer"** 同名的源系统，然后将 **"DestinationServer"** 与目标系统的名称。  
  
    > [!IMPORTANT]
    >  用引号将源系统和目标系统的名称括起来。  
  
    > [!NOTE]
    >  如果对任何 BizTalk Server 数据库进行了重命名，则必须也相应地更新这些数据库的名称。  
  
10. 取消 xml 文件中以下行的注释：  
  
    ```  
    - <UpdateConfiguration>  
      <MessageBoxDB oldDBName="BizTalkMsgboxDb" oldDBServer="Server01" newDBName="BizTalkMsgboxDb" newDBServer="Server01" IsMaster="1" />   
      <TrackingDB oldDBName="BizTalkDTADb" oldDBServer="Server01" newDBName="BizTalkDTADb" newDBServer="Server01" />   
      <ManagementDB oldDBName="BizTalkMgmtDb" oldDBServer="Server01" newDBName="BizTalkMgmtDb" newDBServer="Server01" />   
    - <BAM>  
    - <DeploymentUnit Name="OldPrimaryImportDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMPrimaryImport</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="PrimaryImportDatabase">  
      <Property Name="ServerName">Server02</Property>   
      <Property Name="DatabaseName">BAMPrimaryImport</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="ArchivingDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMArchive</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="AnalysisDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMAnalysis</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="StarSchemaDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMStarSchema</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="Alert">  
      <Property Name="DBServer">Server01</Property>   
      <Property Name="InstanceDatabaseName">BAMAlerts</Property>   
      </DeploymentUnit>  
      </BAM>  
    - <OtherDatabases>  
      <Database Name="SSO" oldDBName="SSODB" oldDBServer="Server01" newDBName="SSODB" newDBServer="Server01" />   
      </OtherDatabases>  
      </UpdateConfiguration>  
    ```  
  
11. 编辑完此文件后，请进行保存然后退出。  
  
12. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
13. 在命令提示符下，导航到以下目录：  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\Restore  
  
14. 在命令提示符下，键入：  
  
     **cscript UpdateDatabase.vbs SampleUpdateInfo.xml**  
  
15. 更新对 BAM 主导入数据库中所有 BAM Livedata Microsoft Excel 文件的引用。 对于每个文件：  
  
    1.  打开 Excel 实时数据文件。 以 _LiveData.xls 结尾的文件名称。  
  
    2.  上**BAM**菜单上，单击**BAM 数据库连接**。  
  
    3.  在**选择 BAM 数据库**对话框中，输入 SQL Server 和 BAMPrimaryImport 数据库，然后单击**确定**。  
  
    4.  上**文件**菜单上，单击**关闭并返回到 Microsoft Excel**。  
  
    5.  在“文件”菜单上，单击“保存”。  
  
16. 按照以下步骤，更新所有 BAM 分析 DTS 包（带有“BAM_AN_”或“BAM_DM_”前缀）中的服务器名称和数据库名称：  
  
    1.  在 BAM 的宿主服务器上，打开 SQL Server 企业管理器。  
  
    2.  打开**Data Transformation Services**文件夹。  
  
    3.  打开**本地包**文件夹，然后打开 DTS 包。  
  
    4.  上**包**菜单上，单击**属性**。  
  
    5.  上**全局变量**选项卡上，更新主导入服务器和数据库的值。  
  
    6.  更改以下行，以匹配新的服务器和数据库：  
  
         PrimaryImportServer ="*\<ServerName\>*"  
  
         PrimaryImportDatabase ="*\<DatabaseName\>*"  
  
17. 启动所有 BizTalk Server 服务。 有关详细信息，请参阅[如何开始、 停止、 暂停、 继续或重新启动 BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)。  
  
18. 启动 IIS 服务。  
  
19. 启动 BAM 警报 Notification Service：  
  
    1.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
    2.  在命令提示符下，键入：  
  
        ```  
        Net start NS$BamAlerts  
        ```  
  
## <a name="see-also"></a>另请参阅  
 [移动 BizTalk Server 数据库](../core/moving-biztalk-server-databases.md)