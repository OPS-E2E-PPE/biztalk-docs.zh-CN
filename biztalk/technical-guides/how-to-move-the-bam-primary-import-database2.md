---
title: "如何移动 BAM 主导入 Database2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc4f2656-2faa-4503-9551-05e1b6eceb1a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd6abeeb04521e95b32b4d6007dcc7f1f532bdbb
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-move-the-bam-primary-import-database"></a>如何移动 BAM 主导入数据库
您可以使用此过程将 BAM 主导入数据库移至其他服务器。 从端到端方案的角度看，移动 BAM 主导入数据库涉及到两个主要步骤：  
  
-   [移动 BAM 主导入数据库](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_MovingBAMPI)  
  
-   [更新到新的 BAM 主导入数据库的引用](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_BAMPIRef)  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，登录使用的帐户必须是 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定服务器角色的成员。  
  
##  <a name="BKMK_MovingBAMPI"></a>移动 BAM 主导入数据库  
 执行以下过程将 BAM 主导入数据库中的步骤。  
  
#### <a name="to-move-the-bam-primary-import-database"></a>移动 BAM 主导入数据库  
  
1.  停止任何 BAM 多维数据集更新和数据维护 SSIS 包，或防止它们运行，直到你已还原 BAM 主导入数据库。  
  
2.  停止所有的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务。 有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
3.  停止 IIS 服务。  
  
4.  停止 BAM 警报通知服务：  
  
    1.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
    2.  在命令提示符下，键入：  
  
         **Net stop NS$ BamAlerts**  
  
5.  备份 BAM 主导入与旧服务器上的数据库。 有关备份数据库的说明，按照如何备份的数据库上的说明[How to： 备份数据库 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]联机丛书。  
  
6.  BAM 主导入数据库复制到新[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。  
  
7.  还原新服务器上的 BAM 主导入数据库。 为说明还原数据库，按照如何还原的数据库上的说明[如何： 还原数据库备份 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (http://go.microsoft.com/fwlink/?LinkId=156511) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]联机丛书。  
  
    > [!NOTE]  
    >  如果从备份还原 BAM 主导入数据库，则还应该使用该 BAM 主导入数据库备份之前的备份来还原 BAM 存档数据库、BAM 星型架构数据库和 BAM 分析数据库。  
  
##  <a name="BKMK_BAMPIRef"></a>更新到新的 BAM 主导入数据库的引用  
 将数据库移动后，你必须更新到新的 BAM 主导入数据库的所有引用。 必须更新以下引用：  
  
-   使用新的服务器名称更新所有 BizTalk 数据库。 可以使用 UpdateDatabase.vbs 脚本来执行此操作。 请参阅[以使用新的服务器名称更新 BizTalk 数据库](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDB)。  
  
-   更新 BAM 门户的 Web.config 文件。 请参阅[更新 BAM 门户的 Web.config 文件](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_Config)。  
  
-   更新对所有 BAM Livedata Microsoft Excel 文件中的 BAM 主导入数据库的引用。 请参阅[更新 BAM Livedata Microsoft Excel 文件中的引用](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateExcel)。  
  
-   更新所有 BAM 分析 SSIS 包中的新服务器和数据库名称。 请参阅[更新服务器和数据库名称中的所有 BAM SSIS 包](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdatePckg)。  
  
-   更新的新服务器和数据库名称数据源中所有 OLAP 多维数据集。 请参阅[更新服务器和数据源中的所有 OLAP 多维数据集的数据库名称](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDSOLAP)。  
  
###  <a name="BKMK_UpdateDB"></a>若要使用新的服务器名称更新 BizTalk 数据库  
  
1.  在运行 BizTalk Server 的计算机，浏览到以下文件夹：  
  
    -   如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装在 64 位版本的 Windows Server 上：  
  
         **%Programfiles (x86) %\Microsoft BizTalk Server 2010\bins32\Schema\Restore**  
  
    -   如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：  
  
         **%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**  
  
2.  右键单击**SampleUpdateInfo.xml**，然后单击**编辑**。  
  
3.  注释掉所有除外 BizTalkMgmtDb、 OldPrimaryImportDatabase、 PrimaryImportDatabase、 ArchivingDatabase、 AnalysisDatabase、 StarSchemaDatabase 和警报的数据库部分。  
  
4.  在`OldPrimaryImportDatabase`文件中，部分为`ServerName`属性，替换**SourceServer**替换现有的数据库所在的服务器的名称。  
  
5.  在`PrimaryImportDatabase`文件中，部分为`ServerName`属性，替换**DestinationServer**替换移动了 BAM 主导入数据库的服务器的名称  
  
6.  对于 BizTalkMgmtDb、 ArchivingDatabase、 AnalysisDatabase、 StarSchemaDatabase 和警报的部分中，设置"SourceServer"和"目标服务器"到现有的服务器的名称在这些数据库驻留的。  
  
    > [!IMPORTANT]  
    >  用引号将源系统和目标系统的名称括起来。  
  
    > [!NOTE]  
    >  如果对任何 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库进行了重命名，则必须也相应地更新这些数据库的名称。  
  
7.  编辑完此文件后，请进行保存然后退出。  
  
8.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
9. 在命令提示符下，导航到以下目录：  
  
    -   如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装在 64 位版本的 Windows Server 上：  
  
         **%Programfiles (x86) %\Microsoft BizTalk Server 2010\Schema\Restore**  
  
    -   如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：  
  
         **%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**  
  
10. 在命令提示符下，键入：  
  
     **cscript UpdateDatabase.vbs SampleUpdateInfo.xml**  
  
###  <a name="BKMK_Config"></a>若要更新 BAM 门户的 Web.config 文件  
  
1.  在运行 BizTalk Server 的计算机，更新下的 Web.config 文件**\<驱动器\>: files\microsoft BizTalk Server 2010\BAMPortal\BAMManagementService\Web.Config**。更新在 Web.config 中下一节中的服务器和数据库名称：  
  
    ```  
    <appSettings>  
      <add key="BamServer" value="<ServerName>" />  
      <add key="BamDatabase" value="<DatabaseName>" />  
    </appSettings>  
    ```  
  
2.  在运行 BizTalk Server 的计算机，更新下的 Web.config 文件**\<驱动器\>: files\microsoft BizTalk Server 2010\BAMPortal\BAMQueryService\Web.Config**。更新在 Web.config 中下一节中的服务器和数据库名称：  
  
    ```  
    <appSettings>  
      <add key="BamServer" value="<ServerName>" />  
      <add key="BamDatabase" value="<DatabaseName>" />  
      <add key="MaxResultRows" value="2000" />  
    </appSettings>  
    ```  
  
3.  保存并关闭文件。  
  
###  <a name="BKMK_UpdateExcel"></a>若要更新 BAM Livedata Microsoft Excel 文件中的引用  
  
1.  打开 Excel 实时数据文件。 以 _LiveData.xls 结尾的文件名称。  
  
2.  上**BAM**菜单上，单击**BAM 数据库连接**。  
  
3.  在**选择 BAM 数据库**对话框框中，输入[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机和数据库，并依次 BAMPrimaryImport**确定**。  
  
4.  上**文件**菜单上，单击**关闭并返回到 Microsoft Excel**。  
  
5.  在“文件”菜单上，单击“保存”。  
  
###  <a name="BKMK_UpdatePckg"></a>更新服务器和所有 BAM SSIS 包中的数据库名称  
  
1.  更新中的所有 BAM 分析 SSIS 包，以"BAM_AN_"或"BAM_DM_"作为前缀的服务器和数据库名称。 若要执行此操作，请单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Business Intelligence Development Studio**。  
  
2.  在 SQL Server Business Intelligence Development Studio 中，创建一个新项目。 单击**文件**，单击**新建**，然后单击**项目**。  
  
3.  在**新项目**对话框中，在**项目类型**框中，单击**商业智能项目**。 在右窗格中，在**模板**框中，单击**Integration Services 项目**，然后单击**确定**。  
  
4.  在**Integration Services 项目**对话框中，在解决方案资源管理器，右键单击**SSIS 包**，然后单击**添加现有包**。  
  
5.  在**添加现有包副本**对话框中，在**服务器**下拉列表框中，选择包含的 BAM_AN_ * 和 BAM_DM_ * 包的服务器。  
  
6.  在**包路径**，单击省略号按钮。  
  
7.  在**SSIS 包**对话框框中，选择你想要更新，请单击的包**确定**，然后单击**确定**。  
  
     现在，该包列在解决方案资源管理器中。  
  
8.  在解决方案资源管理器中，双击上一步中添加的程序包。 在**连接管理器**选项卡 （可向屏幕的下半部分） 中，双击号 1 （BAMPrimaryImport 数据库） 的数据源。  
  
9. 在**连接管理器**对话框中，在**服务器名称**框中，输入服务器的名称，然后单击**确定**。  
  
10. 单击**包资源管理器**选项卡上，双击**变量**文件夹，然后更新的值**PrimaryImportDatabase**和**PrimaryImportServer**变量。 你必须更新为指向新的服务器和数据库的值。  
  
    > [!NOTE]  
    >  你想要更新的所有包重复步骤 4 到 10。  
  
11. 然后单击**文件**菜单，，然后单击**保存所有**。  
  
12. 启动 SQL Server Management Studio。 单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Management Studio**。  
  
13. 在**连接到服务器**对话框中，从**服务器**类型下拉列表中，选择**Integration Services**。  
  
14. 指定服务器名称和凭据以连接到服务器，然后单击**确定**。  
  
15. 在**对象资源管理器**，展开**Integration Services**，展开**存储的包**，然后单击**MSDB**。  
  
16. 在**对象资源管理器详细信息**选项卡上，右键单击之前更新的包，然后单击**导入包**。  
  
17. 在**导入包**对话框中，从**包位置**下拉列表中，选择**文件系统**。  
  
18. 在**包路径**，导航到已保存项目，选择你想要导入，然后单击程序包的.dtsx 文件**打开**。  
  
19. 若要在框中自动填充的包名称框内单击。  
  
    > [!NOTE]  
    >  你想要更新的所有包重复步骤 16 至 19。  
  
20. 单击**确定**，然后单击**是**覆盖。  
  
21. 启用任何 BAM 多维数据集更新和数据维护 SSIS 包。  
  
###  <a name="BKMK_UpdateDSOLAP"></a>更新服务器和数据源中的所有 OLAP 多维数据集的数据库名称  
  
1.  更新的服务器和数据库名称数据源中所有 OLAP 多维数据集。 若要执行此操作，请单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Management Studio**。  
  
2.  在**连接到服务器**对话框中，为**服务器类型**下拉列表中，选择**Analysis Services**，提供服务器名称，选择身份验证方法 （和提供凭据如果需要），然后单击**连接**。  
  
3.  在对象资源管理器，展开**数据库**，展开**BAMAnalysis**，展开**数据源**，然后双击数据源。  
  
4.  在**数据源属性**对话框框中，单击省略号按钮**（...）**针对**连接字符串**属性。  
  
5.  在**连接管理器**对话框中，在**服务器名称**框中，输入承载 BAMPrimaryImport 数据库的服务器的名称，单击**确定**，然后单击**确定**。  
  
6.  启动所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务。 有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
7.  启动 IIS 服务。  
  
8.  启动 BAM 警报通知服务：  
  
    1.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
    2.  在命令提示符下，键入：  
  
         **Net 开始 NS$ BamAlerts**  
  
9. 解决任何不完整的跟踪实例。  有关解决不完整 BAM 活动实例的信息，请参阅[如何解决未完成的活动实例](http://go.microsoft.com/fwlink/?LinkId=151475)(http://go.microsoft.com/fwlink/?LinkId=151475)。  
  
## <a name="see-also"></a>另请参阅  
 [移动数据库](../technical-guides/moving-databases.md)