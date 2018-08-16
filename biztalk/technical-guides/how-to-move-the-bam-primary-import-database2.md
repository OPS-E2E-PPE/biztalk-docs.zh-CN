---
title: 如何移动 BAM 主导入数据库 2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc4f2656-2faa-4503-9551-05e1b6eceb1a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72c43e5048d55c028bb689bd06e5f8c5844cc064
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986702"
---
# <a name="how-to-move-the-bam-primary-import-database"></a>如何移动 BAM 主导入数据库
您可以使用此过程将 BAM 主导入数据库移至其他服务器。 从端到端方案的角度看，移动 BAM 主导入数据库涉及两个主要步骤：  
  
-   [移动 BAM 主导入数据库](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_MovingBAMPI)  
  
-   [正在更新到新的 BAM 主导入数据库引用](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_BAMPIRef)  
  
## <a name="prerequisites"></a>必要條件  
 若要执行此过程，登录使用的帐户必须是 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定服务器角色的成员。  
  
##  <a name="BKMK_MovingBAMPI"></a> 移动 BAM 主导入数据库  
 以下过程来移动 BAM 主导入数据库中执行的步骤。  
  
#### <a name="to-move-the-bam-primary-import-database"></a>移动 BAM 主导入数据库  
  
1. 停止任何 BAM 多维数据集更新和数据维护 SSIS 包，或者阻止它们运行，直到 BAM 主导入数据库的还原。  
  
2. 停止所有的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务。 有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
3. 停止 IIS 服务。  
  
4. 停止 BAM 警报 Notification service:  
  
   1.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
   2.  在命令提示符下，键入：  
  
        **net stop NS$ BamAlerts**  
  
5. 备份 BAM 主导导入旧服务器上的数据库。 有关备份数据库的说明，按照如何备份在数据库上的说明[如何： 备份数据库 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]联机丛书。  
  
6. 将 BAM 主导入数据库复制到新[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。  
  
7. 还原新服务器上的 BAM 主导入数据库。 有关还原数据库，说明如何还原的数据库时按照的说明[如何： 还原数据库备份 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]联机丛书。  
  
   > [!NOTE]  
   >  如果从备份还原 BAM 主导入数据库，则还应该使用该 BAM 主导入数据库备份之前的备份来还原 BAM 存档数据库、BAM 星型架构数据库和 BAM 分析数据库。  
  
##  <a name="BKMK_BAMPIRef"></a> 正在更新到新的 BAM 主导入数据库引用  
 在移动数据库之后，必须更新到新的 BAM 主导入数据库的所有引用。 必须更新以下引用：  
  
-   使用新的服务器名称更新所有 BizTalk 数据库。 可以使用 UpdateDatabase.vbs 脚本来执行此操作。 请参阅[若要使用新的服务器名称更新 BizTalk 数据库](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDB)。  
  
-   更新 BAM 门户 Web.config 文件。 请参阅[更新 BAM 门户 Web.config 文件](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_Config)。  
  
-   更新对 BAM 主导入数据库中所有 BAM 实时数据 Microsoft Excel 文件的引用。 请参阅[更新 BAM 实时数据 Microsoft Excel 文件中的引用](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateExcel)。  
  
-   更新所有 BAM 分析 SSIS 包中的新服务器和数据库名称。 请参阅[来更新服务器和数据库名称在所有 BAM SSIS 程序包](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdatePckg)。  
  
-   更新新服务器和数据库名称在数据源中的所有 OLAP 多维数据集。 请参阅[来更新服务器和数据源中的所有 OLAP 多维数据集的数据库名称](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDSOLAP)。  
  
###  <a name="BKMK_UpdateDB"></a> 若要使用新的服务器名称更新 BizTalk 数据库  
  
1. 在运行 BizTalk Server 的计算机，浏览到以下文件夹：  
  
   - 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位版本的 Windows Server 上安装：  
  
      **%Programfiles (x86) %\Microsoft BizTalk Server 2010\bins32\Schema\Restore**  
  
   - 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：  
  
      **%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**  
  
2. 右键单击**SampleUpdateInfo.xml**，然后单击**编辑**。  
  
3. 注释掉所有除外 BizTalkMgmtDb、 OldPrimaryImportDatabase、 PrimaryImportDatabase、 ArchivingDatabase、 AnalysisDatabase、 StarSchemaDatabase 和警报的数据库部分。  
  
4. 中`OldPrimaryImportDatabase`部分中的文件，对于`ServerName`属性，替换**SourceServer**与数据库所在的现有服务器的名称。  
  
5. 中`PrimaryImportDatabase`部分中的文件，对于`ServerName`属性，替换**DestinationServer**与移动 BAM 主导入数据库的服务器的名称  
  
6. 对于的 BizTalkMgmtDb、 ArchivingDatabase、 AnalysisDatabase、 StarSchemaDatabase 和警报部分，设置"SourceServer"和"目标服务器"的现有服务器的名称到这些数据库所在。  
  
   > [!IMPORTANT]
   >  用引号将源系统和目标系统的名称括起来。  
   > 
   > [!NOTE]
   >  如果对任何 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库进行了重命名，则必须也相应地更新这些数据库的名称。  
  
7. 编辑完此文件后，请进行保存然后退出。  
  
8. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
9. 在命令提示符下，导航到以下目录：  
  
   - 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位版本的 Windows Server 上安装：  
  
      **%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Schema\Restore**  
  
   - 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：  
  
      **%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**  
  
10. 在命令提示符下，键入：  
  
     **cscript UpdateDatabase.vbs SampleUpdateInfo.xml**  
  
###  <a name="BKMK_Config"></a> 若要更新 BAM 门户的 Web.config 文件  
  
1.  在运行 BizTalk Server 的计算机，更新下的 Web.config 文件**\<驱动器\>: \Program Files\Microsoft BizTalk Server 2010\BAMPortal\BAMManagementService\Web.Config**。更新的 web.config 文件中的以下部分中的服务器和数据库名称：  
  
    ```  
    <appSettings>  
      <add key="BamServer" value="<ServerName>" />  
      <add key="BamDatabase" value="<DatabaseName>" />  
    </appSettings>  
    ```  
  
2.  在运行 BizTalk Server 的计算机，更新下的 Web.config 文件**\<驱动器\>: \Program Files\Microsoft BizTalk Server 2010\BAMPortal\BAMQueryService\Web.Config**。更新的 web.config 文件中的以下部分中的服务器和数据库名称：  
  
    ```  
    <appSettings>  
      <add key="BamServer" value="<ServerName>" />  
      <add key="BamDatabase" value="<DatabaseName>" />  
      <add key="MaxResultRows" value="2000" />  
    </appSettings>  
    ```  
  
3.  保存并关闭文件。  
  
###  <a name="BKMK_UpdateExcel"></a> 若要在 BAM 实时数据 Microsoft Excel 文件中更新引用  
  
1. 打开 Excel 实时数据文件。 以 _LiveData.xls 结尾的文件的名称。  
  
2. 上**BAM**菜单上，单击**BAM 数据库连接**。  
  
3. 在中**选择 BAM 数据库**对话框框中，输入[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机和 BAMPrimaryImport 数据库，然后依次**确定**。  
  
4. 上**文件**菜单上，单击**关闭并返回到 Microsoft Excel**。  
  
5. 在“文件”菜单上，单击“保存”。  
  
###  <a name="BKMK_UpdatePckg"></a> 若要更新服务器和数据库名称中的所有 BAM SSIS 包  
  
1.  更新所有 BAM 分析 SSIS 包中，带有"BAM_AN_"或"BAM_DM_"前缀的服务器和数据库名称。 若要执行此操作，请单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或者**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Business Intelligence Development Studio**。  
  
2.  在 SQL Server Business Intelligence Development Studio 中，创建一个新项目。 单击**文件**，单击**新建**，然后单击**项目**。  
  
3.  在中**新的项目**对话框中**项目类型**框中，单击**商业智能项目**。 在右窗格中，在**模板**框中，单击**Integration Services 项目**，然后单击**确定**。  
  
4.  在中**Integration Services 项目**对话框中，在解决方案资源管理器，右键单击**SSIS 包**，然后单击**添加现有包**。  
  
5.  在中**添加现有包副本**对话框中**Server**下拉列表框中，选择包含 BAM_AN_ * 和 BAM_DM_ * 包的服务器。  
  
6.  在中**包路径**，请单击省略号按钮。  
  
7.  在中**SSIS 包**对话框框中，选择你想要更新，请单击的包**确定**，然后单击**确定**。  
  
     现在，该包列在解决方案资源管理器中。  
  
8.  在解决方案资源管理器，双击上一步中添加的包。 在中**连接管理器**选项卡 （可用于在屏幕下半部分） 中，双击数据源数字 1 （BAMPrimaryImport 数据库）。  
  
9. 在中**连接管理器**对话框中**服务器名称**框中，输入服务器的名称，然后单击**确定**。  
  
10. 单击**包资源管理器**选项卡上，双击**变量**文件夹，然后将更新的值**PrimaryImportDatabase**和**PrimaryImportServer**变量。 必须更新为指向新的服务器和数据库的值。  
  
    > [!NOTE]  
    >  你想要更新的所有包重复步骤 4 到 10。  
  
11. 然后单击**文件**菜单，并单击**全部保存**。  
  
12. 启动 SQL Server Management Studio。 单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或者**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Management Studio**。  
  
13. 在中**连接到服务器**对话框中，从**服务器**类型下拉列表中，选择**Integration Services**。  
  
14. 指定服务器名称和凭据以连接到服务器，然后单击**确定**。  
  
15. 在中**对象资源管理器**，展开**Integration Services**，展开**存储的包**，然后单击**MSDB**。  
  
16. 在中**对象资源管理器详细信息**选项卡上，右键单击之前更新的程序包，然后单击**导入包**。  
  
17. 在中**导入包**对话框中，从**包位置**下拉列表中，选择**文件系统**。  
  
18. 在中**包路径**，导航到保存的项目，选择你想要导入，然后单击的包.dtsx 文件**打开**。  
  
19. 在包名称框以自动填充此框内单击。  
  
    > [!NOTE]  
    >  重复步骤 16 至 19 的你想要更新的所有包。  
  
20. 单击**确定**，然后单击**是**覆盖。  
  
21. 启用任何 BAM 多维数据集更新和数据维护 SSIS 包。  
  
###  <a name="BKMK_UpdateDSOLAP"></a> 若要更新服务器和数据源中的所有 OLAP 多维数据集的数据库名称  
  
1. 更新服务器和数据库名称在数据源中的所有 OLAP 多维数据集。 若要执行此操作，请单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或者**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Management Studio**。  
  
2. 在中**连接到服务器**对话框中，对于**服务器类型**下拉列表中，选择**Analysis Services**，提供服务器名称、 选择身份验证方法 （和提供凭据如果需要），然后单击**Connect**。  
  
3. 在对象资源管理器，展开**数据库**，展开**BAMAnalysis**，展开**数据源**，然后双击数据源。  
  
4. 在中**数据源属性**对话框框中，单击省略号按钮 **（...）** 针对**连接字符串**属性。  
  
5. 在中**连接管理器**对话框中**服务器名称**框中，输入承载 BAMPrimaryImport 数据库的服务器的名称，单击**确定**，然后单击**确定**。  
  
6. 启动所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务。 有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
7. 启动 IIS 服务。  
  
8. 启动 BAM 警报 Notification service:  
  
   1.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
   2.  在命令提示符下，键入：  
  
        **Net start NS$ BamAlerts**  
  
9. 解决任何未完成的跟踪实例。  有关解决不完整的 BAM 活动实例的信息，请参阅[如何解析不完整活动实例](http://go.microsoft.com/fwlink/?LinkId=151475)(http://go.microsoft.com/fwlink/?LinkId=151475)。  
  
## <a name="see-also"></a>请参阅  
 [移动数据库](../technical-guides/moving-databases.md)