---
title: 如何移动 BAM 分析数据库 1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8094153-072b-427a-b3a0-7310a37cf584
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29ab7e205777af9403157811388e9955b0f4d08f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401814"
---
# <a name="how-to-move-the-bam-analysis-database"></a>如何移动 BAM 分析数据库
可以使用此过程将 BAM 分析数据库移到另一台服务器。  从端到端方案的角度看，移动 BAM 分析数据库涉及两个主要步骤：  
  
-   [移动 BAM 分析数据库](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyMoveDB)  
  
-   [更新到新的 BAM 分析数据库的引用](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdate)  
  
## <a name="prerequisites"></a>先决条件  
 您必须是的成员的帐户登录[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]sysadmin 固定的服务器角色才能执行此过程。  
  
##  <a name="BKMK_AnalyMoveDB"></a> 移动 BAM 分析数据库  
 以下过程来移动 BAM 分析数据库中执行的步骤。  
  
#### <a name="to-move-the-bam-analysis-database"></a>移动 BAM 分析数据库  
  
1. 停止任何 BAM 多维数据集更新和数据维护 SSIS 包，或者阻止它们运行，直到 BAM 分析数据库的还原。  
  
2. 停止所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务。 有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
3. 停止 IIS 服务。  
  
4. 停止 BAM 警报 Notification service:  
  
   1.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
   2.  在命令提示符下，键入：  
  
        **net stop NS$ BamAlerts**  
  
5. 在旧服务器上备份 BAM 分析数据库。 备份数据库的说明，请遵循的说明[如何：备份数据库 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]上如何备份数据库的联机丛书。  
  
6. 将 BAM 分析数据库复制到新[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。  
  
7. 还原新服务器上的 BAM 分析数据库。 对于还原数据库的说明，请按照的说明[如何：还原数据库备份 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]上如何还原数据库的联机丛书。  
  
##  <a name="BKMK_AnalyUpdate"></a> 更新到新的 BAM 分析数据库的引用  
 在移动数据库之后，必须更新到新的 BAM 分析数据库的所有引用。 必须更新以下引用：  
  
-   使用新的数据库和服务器名称更新 BAM 配置。 请参阅[更新 BAM 配置](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdateBAMConfig)。  
  
-   更新所有 BAM 分析 SSIS 包中的新服务器和数据库名称。 请参阅[来更新服务器和数据库名称在所有 BAM SSIS 程序包](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdateSSIS)。  
  
###  <a name="BKMK_AnalyUpdateBAMConfig"></a> 若要更新 BAM 配置  
  
1. 获取用于还原 BAM 的.xml 文件的副本：  
  
   1. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
   2. 在运行 BizTalk Server 的计算机，浏览到以下文件夹：  
  
      - 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位版本的 Windows Server 上安装：  
  
         **%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**  
  
      - 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：  
  
         **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
   3. 在命令提示符下，键入：  
  
       **Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername\> -database:\<database\>**  
  
      > [!NOTE]
      >  当运行此命令，替换从其获取的配置信息的服务器的实际名称\<servername\>并将其替换实际获取的配置信息的数据库的名称\<数据库\>。 有关使用 BAM 管理 (BM) 实用程序的详细信息，请参阅[基础结构管理命令](http://go.microsoft.com/fwlink/?LinkId=156516)(<http://go.microsoft.com/fwlink/?LinkId=156516>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
2. 编辑 BAMConfiguration.xml 文件，将**ServerName**中`<DeploymentUnit Name="AnalysisDatabase">`到新的服务器名称的部分。  
  
3. 保存并关闭 BAMConfiguration.xml 文件。  
  
4. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
5. 在运行 BizTalk Server 的计算机，浏览到以下文件夹：  
  
   - 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位版本的 Windows Server 上安装：  
  
      **%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**  
  
   - 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：  
  
      **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
6. 在命令提示符下，键入：  
  
    **bm.exe update-config -FileName:BAMConfiguration.xml**  
  
###  <a name="BKMK_AnalyUpdateSSIS"></a> 若要更新服务器和数据库名称中的所有 BAM SSIS 包  
  
1. 更新所有 BAM 分析 SSIS 包中，带有"BAM_AN_"前缀的服务器和数据库名称。 若要执行此操作，请单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或者**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Business Intelligence Development Studio**。  
  
2. 在 SQL Server Business Intelligence Development Studio，创建新项目。 单击**文件**，单击**新建**，然后单击**项目**。  
  
3. 在中**新的项目**对话框中**项目类型**框中，单击**商业智能项目**。 在右窗格中，在**模板**框中，单击**Integration Services 项目**，然后单击**确定**。  
  
4. 在中**Integration Services 项目**对话框中，在解决方案资源管理器，右键单击**SSIS 包**，然后单击**添加现有包**。  
  
5. 在中**添加现有包副本**对话框中**Server**下拉列表框中，选择包含 BAM_AN_ * 包的服务器。  
  
6. 在中**包路径**，请单击省略号按钮。  
  
7. 在中**SSIS 包**对话框框中，选择你想要更新，请单击的包**确定**，然后单击**确定**。  
  
    包现在列在解决方案资源管理器。  
  
8. 在解决方案资源管理器，双击上一步中添加的包。 在中**连接管理器**选项卡 （可用于在屏幕下半部分） 中，双击数据源数 2 （BAMArchive 数据库）。  
  
9. 在中**连接管理器**对话框中**服务器名称**框中，输入服务器的名称，然后单击**确定**。  
  
    > [!NOTE]  
    >  数据源编号 3(MSDB 数据库） 重复上述操作。  
  
10. 在中**连接管理器**选项卡上，双击数据源编号 4 （BAMAnalysis 数据库）。 在中**添加 Analysis Services 连接管理器**对话框中，单击**编辑**。  
  
11. 在中**连接管理器**对话框中**服务器名称**框中，输入服务器的名称，单击**确定**，然后单击**确定**。  
  
12. 单击**包资源管理器**选项卡上，双击**变量**文件夹，然后将更新的值**AnalysisDatabase**， **AnalysisServer**， **PrimaryImportDatabase**， **PrimaryImportServer**， **StarSchemaDatabase**，和**StarSchemaServer**变量。 必须更新为指向新的服务器和数据库的值。  
  
    > [!NOTE]  
    >  重复步骤 4 到 12 的你想要更新的所有包。  
  
13. 然后单击**文件**菜单，并单击**全部保存**。  
  
14. 启动 SQL Server Management Studio。 单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或者**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Management Studio**。  
  
15. 在中**连接到服务器**对话框中，从**服务器**类型下拉列表中，选择**Integration Services**。  
  
16. 指定服务器名称和凭据以连接到服务器，然后单击**确定**。  
  
17. 在中**对象资源管理器**，展开**Integration Services**，展开**存储的包**，然后单击**MSDB**。  
  
18. 在中**对象资源管理器详细信息**选项卡上，右键单击之前更新的程序包，然后单击**导入包**。  
  
19. 在中**导入包**对话框中，从**包位置**下拉列表中，选择**文件系统**。  
  
20. 在中**包路径**，导航到保存的项目，选择你想要导入，然后单击的包.dtsx 文件**打开**。  
  
21. 在包名称框以自动填充此框内单击。  
  
    > [!NOTE]  
    >  你想要更新的所有包重复步骤 18 通过 21。  
  
22. 单击**确定**，然后单击**是**覆盖。  
  
23. 启动所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务。 有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
24. 启动 IIS 服务。  
  
25. 启动 BAM 警报 Notification service:  
  
    1.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
    2.  在命令提示符下，键入：  
  
         **Net start NS$ BamAlerts**  
  
26. 启用任何 BAM 多维数据集更新和数据维护 SSIS 包。  
  
## <a name="see-also"></a>请参阅  
 [移动数据库](../technical-guides/moving-databases.md)