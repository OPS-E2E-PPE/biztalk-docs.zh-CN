---
title: 如何移动 BAM 存档 Database1 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e371321c-6b8d-4be6-a6d2-926f6218db01
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 383aef74519f7527383d9f681f83ace2e515eba7
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-move-the-bam-archive-database"></a>如何移动 BAM 存档数据库
您可以使用此过程将 BAM 存档数据库移到其他服务器。  从端到端方案的角度看，移动 BAM 存档数据库涉及到两个主要步骤：  
  
-   [移动 BAM 存档数据库](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_MovingArch)  
  
-   [更新到新的 BAM 存档数据库的引用](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArch)  
  
## <a name="prerequisites"></a>必要條件  
 若要执行此过程，登录使用的帐户必须是 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定服务器角色的成员。  
  
##  <a name="BKMK_MovingArch"></a> 移动 BAM 存档数据库  
 执行以下过程来移动 BAM 存档数据库中的步骤。  
  
#### <a name="to-move-the-bam-archive-database"></a>移动 BAM 存档数据库  
  
1.  停止任何 BAM 多维数据集更新和数据维护 SSIS 包，或防止它们运行，直到您已还原 BAM 存档数据库。  
  
2.  停止所有的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务。 有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394)中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
3.  停止 IIS 服务。  
  
4.  停止 BAM 警报通知服务：  
  
    1.  单击 **启动**, ，单击 **运行**, ，类型 **cmd**, ，然后单击 **确定**。  
  
    2.  在命令提示符下，键入：  
  
         **Net stop NS$ BamAlerts**  
  
5.  旧服务器上备份 BAM 存档数据库。 有关备份数据库的说明，请遵循的说明[How to： 备份数据库 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510)中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]如何备份数据库联机丛书。  
  
6.  BAM 存档数据库复制到新[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。  
  
7.  还原新的服务器上的 BAM 存档数据库。 对于说明还原数据库，请按照说明[如何： 还原数据库备份 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (http://go.microsoft.com/fwlink/?LinkId=156511)中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]如何还原数据库联机丛书。  
  
##  <a name="BKMK_UpdateArch"></a> 更新到新的 BAM 存档数据库的引用  
 将数据库移动后，你必须更新到新的 BAM 存档数据库的所有引用。 必须更新以下引用：  
  
-   使用新的数据库和服务器名称更新 BAM 配置。 请参阅[更新 BAM 配置](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchConfig)。  
  
-   更新所有 BAM 分析 SSIS 包中的新服务器和数据库名称。 请参阅[更新服务器和数据库名称中的所有 BAM SSIS 包](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchSSIS)。  
  
###  <a name="BKMK_UpdateArchConfig"></a> 若要更新 BAM 配置  
  
1.  获取用于还原 BAM 的 .xml 文件的副本：  
  
    1.  单击 **启动**, ，单击 **运行**, ，类型 **cmd**, ，然后单击 **确定**。  
  
    2.  在运行 BizTalk Server 的计算机，浏览到以下文件夹：  
  
        -   如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装在 64 位版本的 Windows Server 上：  
  
             **%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**  
  
        -   如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：  
  
             **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
    3.  在命令提示符下，键入：  
  
         **Bm.exe get-config –filename:BAMConfiguration.xml-server:\<servername\> -数据库：\<数据库\>**  
  
        > [!NOTE]  
        >  运行此命令时, 替换从其获取的配置信息的服务器的实际名称\<servername\>和替换从其获取的配置信息的数据库的实际名称\<数据库\>。 有关使用 BAM 管理 (BM) 实用工具的详细信息，请参阅[基础结构管理命令](http://go.microsoft.com/fwlink/?LinkId=156516)(http://go.microsoft.com/fwlink/?LinkId=156516)中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
2.  编辑 BAMConfiguration.xml 文件并将更改**ServerName**中`<DeploymentUnit Name="ArchivingDatabase">`到新的服务器名称的部分。  
  
3.  保存并关闭 BAMConfiguration.xml 文件。  
  
4.  单击 **启动**, ，单击 **运行**, ，类型 **cmd**, ，然后单击 **确定**。  
  
5.  在运行 BizTalk Server 的计算机，浏览到以下文件夹：  
  
    -   如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装在 64 位版本的 Windows Server 上：  
  
         **%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**  
  
    -   如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：  
  
         **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
6.  在命令提示符下，键入：  
  
     **bm.exe update-config -FileName:BAMConfiguration.xml**  
  
###  <a name="BKMK_UpdateArchSSIS"></a> 更新服务器和所有 BAM SSIS 包中的数据库名称  
  
1.  更新中的所有 BAM 分析 SSIS 包，以"BAM_DM_"作为前缀的服务器和数据库名称。 若要执行此操作，请单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**或**Microsoft SQL Server 2008 SP1**，然后单击**SQL Server Business Intelligence Development Studio**。  
  
2.  在 SQL Server Business Intelligence Development Studio 中，创建一个新项目。 单击 **文件**, ，单击 **新建**, ，然后单击 **项目**。  
  
3.  在**新项目**对话框中，在**项目类型**框中，单击**商业智能项目**。 在右窗格中，在**模板**框中，单击**Integration Services 项目**，然后单击**确定**。  
  
4.  在**Integration Services 项目**对话框中，在解决方案资源管理器，右键单击**SSIS 包**，然后单击**添加现有包**。  
  
5.  在**添加现有包副本**对话框中，在**服务器**下拉列表框中，选择包含 BAM_DM_ * 包的服务器。  
  
6.  在 **包路径**, ，单击省略号按钮。  
  
7.  在**SSIS 包**对话框框中，选择你想要更新，请单击的包**确定**，然后单击**确定**。  
  
     现在，该包列在解决方案资源管理器中。  
  
8.  在解决方案资源管理器中，双击上一步中添加的程序包。 在**连接管理器**选项卡 （可向屏幕的下半部分） 中，双击号为 2 （BAMArchive 数据库） 的数据源。  
  
9. 在**连接管理器**对话框中，在**服务器名称**框中，输入服务器的名称，然后单击**确定**。  
  
    > [!NOTE]  
    >  数据源数量 3 （MSDB 数据库） 重复此过程。  
  
10. 单击**包资源管理器**选项卡上，双击**变量**文件夹，然后更新的值**ArchivingDatabase**， **ArchivingServer**， **PrimaryImportDatabase**，和**PrimaryImportServer**变量。 你必须更新为指向新的服务器和数据库的值。  
  
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
  
20. 单击 **确定**, ，然后单击 **是** 覆盖。  
  
21. 启动所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务。 有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394)中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
22. 启动 IIS 服务。  
  
23. 启动 BAM 警报通知服务：  
  
    1.  单击 **启动**, ，单击 **运行**, ，类型 **cmd**, ，然后单击 **确定**。  
  
    2.  在命令提示符下，键入：  
  
         **Net 开始 NS$ BamAlerts**  
  
24. 启用任何 BAM 多维数据集更新和数据维护 SSIS 包。  
  
> [!TIP]  
>  作为一种良好做法，还应将 BAM_DM_ * SSIS 包移动到承载 BAMArchive 数据库的服务器。  
  
## <a name="see-also"></a>另请参阅  
 [移动数据库](../technical-guides/moving-databases.md)