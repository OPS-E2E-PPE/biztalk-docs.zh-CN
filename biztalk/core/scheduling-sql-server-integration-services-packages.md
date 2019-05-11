---
title: 计划 SQL Server Integration Services 包 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 037ae2cf-c352-4823-95df-9a723f2b5a81
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cbdb19b5b1f8ae7d800742c0dd211e772f98c7c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308006"
---
# <a name="scheduling-sql-server-integration-services-packages"></a>计划 SQL Server Integration Services 包
用户创建 BAM 视图基于联机分析处理 (OLAP) 多维数据集中存储数据。 多维数据集更新集成服务包刷新多维数据集中的数据，使 OLAP 视图可以反映正确的数据。  
  
 您必须运行此包至少一次的 OLAP 视图可以工作。 正在进行维护，应该安排该包定期运行。  
  
> [!IMPORTANT]
>  如果您还原 BAM 星型架构数据库或停止[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]之前运行多维数据集更新集成服务包，必须刷新的数据源中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]分析管理器或重新启动 OLAP 服务，然后才能运行包已成功。  
  
 您可以计划一次或按重复间隔在特定时间执行已保存的包。 例如：  
  
- 每天的午夜。  
  
- 每周的星期日午夜 06:00。  
  
- 月份的第一个或最后一天。  
  
  计划的包执行由[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]作为作业。  
  
  有关运行信息[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]包，请参阅[ http://go.microsoft.com/fwlink/?LinkId=125738 ](http://go.microsoft.com/fwlink/?LinkId=125738)。  
  
> [!NOTE]
>  默认情况下，存档和多维数据集 BAM SSIS 包的日志记录处于开启状态，并且存储在 msdb 数据库中。 随着时间的推移，这可能会导致大量引起大量的 BAM 活动的 SSIS 事件日志数据或频繁执行的 BAM 拥有 SSIS 包。 若要解决此问题，可以删除旧的日志条目，因为这些项主要用于调试。  
  
## <a name="prerequisites"></a>先决条件  
 您必须为要执行这些过程的 BizTalk Server Administrators 组的成员身份登录。  
  
### <a name="to-run-the-cube-update-integration-services-package"></a>若要运行多维数据集更新集成服务包  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP1**或者**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。  
  
2.  在中**连接到服务器**对话框中**服务器类型**下拉列表中，选择**Integration Services**。  
  
3.  在中**服务器名称**下拉列表中，选择运行包的服务器的名称。  
  
4.  在中**身份验证**下拉列表中，选择您用来连接到服务器的身份验证的类型。  
  
5.  如果有必要，请键入你的用户名和密码。  
  
6.  单击 **“连接”**。  
  
7.  在控制台树中，展开**Integration Services**，展开**存储的包**，然后单击**MSDB**。  
  
8.  右键单击**BAM_AN_\<视图名称\>** 打包，然后依次**运行包**。  
  
### <a name="to-run-the-maintaining-bam-data-integration-services-package"></a>若要运行维护 BAM 数据 Integration Services 包  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP1**或者**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。  
  
2.  在中**连接到服务器**对话框中**服务器类型**下拉列表中，选择**Integration Services**。  
  
3.  在中**服务器名称**下拉列表中，选择运行包的服务器的名称。  
  
4.  在中**身份验证**下拉列表中，选择您用来连接到服务器的身份验证的类型。  
  
5.  如果有必要，请键入你的用户名和密码。  
  
6.  单击 **“连接”**。  
  
7.  在控制台树中，展开**Integration Services**，展开**存储的包**，然后单击**MSDB**。  
  
8.  右键单击**BAM_DM_\<活动名称\>** 打包，然后依次**运行包**。  
  
### <a name="to-schedule-the-packages-to-run-regularly"></a>若要计划定期运行的包  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP1**或者**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。  
  
2.  在中**连接到服务器**对话框中**服务器类型**下拉列表中，选择**数据库引擎**。  
  
3.  在中**服务器名称**下拉列表中，选择运行包的服务器的名称。  
  
4.  在中**身份验证**下拉列表中，选择您用来连接到服务器的身份验证的类型。  
  
5.  如果有必要，请键入你的用户名和密码。  
  
6.  单击 **“连接”**。  
  
7.  在控制台树中，展开您的服务器，然后选择**SQL Server 代理**。  
  
8.  如果**SQL Server 代理**已禁用，右键单击**SQL Server 代理**，然后选择**启动**。  
  
9. 右键单击**SQL Server 代理**，然后选择**新作业**。  
  
10. 在中**新的作业**对话框中，键入的名称中的作业**名称**文本框。  
  
11. 在中**选择页**窗口中，单击**步骤**，然后单击**新建**。 这将打开**新建作业步骤**对话框。  
  
12. 在中**步骤名称**文字框中，键入在步骤的标识名称。  
  
13. 在中**类型**下拉列表中，选择**SQL Server Integration Services 包**并在**包源**下拉列表中，选择**SSIS 包存储区**.  
  
14. 在中**Server**下拉列表中，选择运行作业的服务器。  
  
15. 单击的文件选择器按钮**包**文字框中，选择要安排的包 (任一**BAM_DM_\<活动名称\>** 或**BAM_AN_\<视图名称\>** 包)，然后单击**确定**。  
  
16. 在中**选择页**窗口中，单击**计划**，然后单击**新建**。 这将打开**新建作业计划**对话框。  
  
17. 在中**名称**文本框中，为计划键入一个名称。  
  
18. 创建您的计划使用频率字段。  
  
19. 单击 **“确定”** 保存作业。  
  
    > [!NOTE]
    >  如果使用 SQL Server 的非默认实例配置 BAM，然后 BAM_AN_POCube DTSPackage 不会获取计划/执行准确。 您需要修改配置文件以允许程序包继续运行。 有关详细信息，请参阅"修改配置文件内容"部分[ http://go.microsoft.com/fwlink/?LinkId=196768 ](http://go.microsoft.com/fwlink/?LinkId=196768)。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 数据库](../core/managing-bam-databases.md)