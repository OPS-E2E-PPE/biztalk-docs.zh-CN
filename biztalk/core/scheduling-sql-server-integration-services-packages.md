---
title: "计划 SQL Server Integration Services 包 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 037ae2cf-c352-4823-95df-9a723f2b5a81
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17d8518a8c74f1fef77cf713852f1dfc87c8ef23
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="scheduling-sql-server-integration-services-packages"></a>计划 SQL Server Integration Services 包
用户可以创建基于存储在联机分析处理 (OLAP) 多维数据集中的数据的 BAM 视图。 多维数据集更新集成服务包将刷新多维数据集中的数据，以便 OLAP 视图可以反映正确的数据。  
  
 你必须至少运行一次此包才能使 OLAP 视图可以工作。 如果要进行实时维护，则应该安排该包定期运行。  
  
> [!IMPORTANT]
>  如果你在运行多维数据集更新集成服务包之前还原了 BAM 星型架构数据库或停止了 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，则必须先在 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 分析管理器中刷新数据源或者重新启动 OLAP 服务，然后才能成功运行该程序包。  
  
 你可以将保存的程序包安排在特定时间执行，既可以执行一次也可以按重复的时间间隔执行。 例如：  
  
-   每天的午夜。  
  
-   每个周日的 06:00。  
  
-   每月的第一天或者最后一天。  
  
 已安排的程序包将作为一项作业由 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 执行。  
  
 有关运行[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]包，请参阅[http://go.microsoft.com/fwlink/?LinkId=125738](http://go.microsoft.com/fwlink/?LinkId=125738)。  
  
> [!NOTE]
>  默认情况下，会打开归档 BAM SSIS 程序包以及计算其立方的日志记录，并将该日志记录存储在 msdb 数据库中。 一段时间后，大量 BAM 活动或频繁执行由 BAM 所有的 SSIS 程序包可能会造成数目庞大的 SSIS 事件日志数据。 可以删除旧的日志项以解决此问题，因为这些日志项主要用于调试目的。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 BizTalk Server Administrators 组成员的身份登录，才能执行这些过程。  
  
### <a name="to-run-the-cube-update-integration-services-package"></a>运行多维数据集更新集成服务包  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP1**或**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。  
  
2.  在**连接到服务器**对话框中，在**服务器类型**下拉列表中，选择**Integration Services**。  
  
3.  在**服务器名称**下拉列表中，选择在其运行包的服务器的名称。  
  
4.  在**身份验证**下拉列表中，选择要用于连接到服务器的身份验证类型。  
  
5.  如有必要，请键入你的用户名和密码。  
  
6.  单击 **“连接”**。  
  
7.  在控制台树中，展开**Integration Services**，展开**存储的包**，然后单击**MSDB**。  
  
8.  右键单击**BAM_AN_\<视图名称\>**包，并依次**运行包**。  
  
### <a name="to-run-the-maintaining-bam-data-integration-services-package"></a>运行维护 BAM 数据集成服务包  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP1**或**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。  
  
2.  在**连接到服务器**对话框中，在**服务器类型**下拉列表中，选择**Integration Services**。  
  
3.  在**服务器名称**下拉列表中，选择在其运行包的服务器的名称。  
  
4.  在**身份验证**下拉列表中，选择要用于连接到服务器的身份验证类型。  
  
5.  如有必要，请键入你的用户名和密码。  
  
6.  单击 **“连接”**。  
  
7.  在控制台树中，展开**Integration Services**，展开**存储的包**，然后单击**MSDB**。  
  
8.  右键单击**BAM_DM_\<活动名称\>**包，并依次**运行包**。  
  
### <a name="to-schedule-the-packages-to-run-regularly"></a>安排包进行定期运行  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP1**或**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。  
  
2.  在**连接到服务器**对话框中，在**服务器类型**下拉列表中，选择**数据库引擎**。  
  
3.  在**服务器名称**下拉列表中，选择在其运行包的服务器的名称。  
  
4.  在**身份验证**下拉列表中，选择要用于连接到服务器的身份验证类型。  
  
5.  如有必要，请键入你的用户名和密码。  
  
6.  单击 **“连接”**。  
  
7.  在控制台树中，展开你的服务器，然后选择**SQL Server 代理**。  
  
8.  如果**SQL Server 代理**是禁用，右键单击**SQL Server 代理**，然后选择**启动**。  
  
9. 右键单击**SQL Server 代理**，然后选择**新作业**。  
  
10. 在**新作业**对话框中，键入的名称中的作业**名称**文本框。  
  
11. 在**选择页**窗口中，单击**步骤**，然后单击**新建**。 这将打开**新建作业步骤**对话框。  
  
12. 在**步骤名称**文本框中，键入步骤的识别名称。  
  
13. 在**类型**下拉列表中，选择**SQL Server Integration Services 包**并在**包源**下拉列表中，选择**SSIS 包存储区**.  
  
14. 在**服务器**下拉列表中，选择在其运行作业的服务器。  
  
15. 单击的文件选择器按钮**包**文本框中，选择要计划的包 (任一**BAM_DM_\<活动名称\>**或**BAM_AN_\<视图名称\>**包)，然后单击**确定**。  
  
16. 在**选择页**窗口中，单击**计划**，然后单击**新建**。 这将打开**新建作业计划**对话框。  
  
17. 在**名称**文本框中，为计划键入一个名称。  
  
18. 使用频率字段创建你的计划。  
  
19. 单击 **“确定”** 保存作业。  
  
    > [!NOTE]
    >  如果使用 SQL Server 的非默认实例配置 BAM，则将不能正确计划/执行 BAM_AN_POCube DTSPackage。 需要修改配置文件以允许包继续运行。 有关详细信息，请参阅"修改配置文件内容"部分在[http://go.microsoft.com/fwlink/?LinkId=196768](http://go.microsoft.com/fwlink/?LinkId=196768)。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM 数据库](../core/managing-bam-databases.md)