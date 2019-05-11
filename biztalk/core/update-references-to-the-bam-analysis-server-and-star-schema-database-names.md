---
title: 如何更新对 BAM 分析服务器和星型架构数据库名称的引用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- restoring [BAM], Analysis database
- Analysis database [BAM], restoring
- restoring, BAM
- restoring [BAM], updating references
- BAM, restoring
- Analysis database [BAM], updating references
ms.assetid: cbe5e500-0a25-427e-bc76-1eae24b3e5f3
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d66abdbc8a6361abe0acfba16f20f9a8bef5a85
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399450"
---
# <a name="how-to-update-references-to-the-bam-analysis-server-and-star-schema-database-names"></a>如何更新对 BAM 分析服务器和 BAM 星型架构数据库名称的引用
如果备份了 BAMAnalysis 和 BAMStarSchema 数据库，则在系统或数据发生故障，可以将该备份还原到另一台计算机，并可以重命名该备份。  
  
 若要还原 BAM 分析服务器或 BAMStarSchema 数据库，请执行中的步骤[如何还原您数据库](../core/how-to-restore-your-databases.md)。 此外，您必须使用新的服务器名称和数据库名称更新 BAM 数据转换服务 (DTS) 包。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组才能执行此过程。  
  
### <a name="to-update-references-to-the-bam-analysis-server-and-bam-star-schema-database-name-sql-server-2008-r2sp1"></a>若要更新对 BAM 分析服务器和 BAM 星型架构数据库名称 (SQL Server 2008 R2/SP1) 的引用  
  
1.  停止任何 BAM 多维数据集更新和数据维护 SSIS 包，或者阻止它们运行，直到 BAMAnalysis 或 BAMStarSchema 数据库还原时。  
  
2.  停止 BizTalk 应用程序服务 （其中包括 BAM 事件总线服务） 以便不会尝试将更多的数据导入数据库。  
  
    1.  单击**启动**，单击**运行**，然后键入**services.msc**。  
  
    2.  右键单击**BizTalk 服务 BizTalk 组：BizTalkServerApplication**服务，然后单击**停止**。  
  
    > [!TIP]
    >  若要停止服务的另一种方法是使用**Net Stop**命令。 若要停止 BizTalk 服务使用 Net Stop，打开**命令提示符**(如果使用 Windows Server 2008 或 Windows Vista，启动命令提示符处使用**以管理员身份运行**) 并键入以下命令： `Net Stop BTSSvc$BizTalkServerApplication`然后按**Enter**。  
  
3.  单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Business Intelligence Development Studio**.  
  
4.  在 SQL Server Business Intelligence Development Studio，创建新项目。 单击**文件**，单击**新建**，然后单击**项目**。  
  
5.  在中**新的项目**对话框中**模板**，单击**Integration Services 项目**，然后单击**确定**。  
  
6.  在中**Integration Services 项目**对话框中**解决方案资源管理器**，右键单击**SSIS 包**，然后单击**添加现有包**.  
  
7.  在中**添加现有包副本**对话框中**Server**下拉列表框中，选择包含 BAM_AN 包的服务器。  
  
8.  在中**包路径**，请单击省略号按钮。  
  
9. 在中**SSIS 包**对话框框中，选择 BAM_AN 包，单击**确定**，然后单击**确定**。  
  
     包现在列在解决方案资源管理器。  
  
10. 在中**解决方案资源管理器**，双击该 BAM_AN 包。 在中**连接管理器**，双击数据库编号 3(MSDB 数据库）。  
  
11. 在中**连接管理器**对话框中**服务器名称**框中，输入 MSDB 服务器的名称，然后单击**确定**。  
  
12. 单击**包资源管理器**选项卡上，双击**变量**文件夹，然后更新主导入服务器名称和主键的值导入数据库名称。  
  
13. 单击**文件**，然后单击**全部保存**。  
  
14. 在中**Microsoft SQL Server Management Studio**，单击**Connect**。  
  
15. 单击**Integration Services**，双击**存储的包**，单击**MSDB**，右键单击该 BAM_AN 包，并单击**导入包**.  
  
16. 在中**导入包**对话框中**包位置**，选择**文件系统**。  
  
17. 在中**包路径**，导航到保存的项目，选择 BAM_AN\*.dtsx 文件，然后单击**打开**。  
  
18. 在单击**包名称**框以自动填充此框。  
  
19. 单击**确定**，然后单击**是**覆盖。  
  
20. 重新启动 BizTalk 应用程序服务。  
  
    1.  单击**启动**，单击**运行**，然后键入**services.msc**。  
  
    2.  右键单击**BizTalk 服务 BizTalk 组：BizTalkServerApplication**服务，然后单击**启动**。  
  
21. 启用任何 BAM 多维数据集更新和数据维护 SSIS 包。  
  
## <a name="see-also"></a>请参阅  
 [备份和还原 BAM](../core/backing-up-and-restoring-bam.md)